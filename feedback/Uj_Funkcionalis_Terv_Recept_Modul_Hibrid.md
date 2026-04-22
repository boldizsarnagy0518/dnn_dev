# NaturaCo Webshop Recept Modul - Hibrid Funkcionális Terv

## 1. Bevezetés és Koncepcióváltás
A NaturaCo webshop új recept modulja egy innovatív, Hibrid Megközelítést alkalmaz. Ahelyett, hogy egy teljesen független, nulláról felépített MVC modult készítenénk egyedi adatbázissal és saját kosár-integrációval, az új terv értelmében **a Hotcakes Commerce beépített rendszerét használjuk adatforrásként és kosár-motorként**.

A koncepció:
- A vásárlók számára a receptek tulajdonképpen vizuálisan átdolgozott **Hotcakes Kategóriák**.
- A "Mindent a kosárba" (vagyis az egész recept megvásárlása) funkció nem más, mint egy **Hotcakes Bundle termék** kosárba helyezése.
- Az egyes összetevők (ha valaki csak rizst kér a receptből) a kategóriában szereplő **normál termékek**.

Ez a megoldás robusztus, hibatűrő, és a Hotcakes beépített frissítéseivel is kompatibilis marad.

## 2. A Modul Feladata és Architektúrája
A modul feladata, hogy egy "normál" Hotcakes kategóriát (amit a WinForms kliens alkalmazás receptként generált) a weboldalon úgy jelenítsen meg, ahogyan az a vizuális terveken (Figma / `Kliens_and_modul.ts`) szerepel.

Technikailag ezt kétféleképpen valósíthatjuk meg, mindkettő MVC alapú:
1. **Custom Hotcakes Category View (Javasolt):** Egyedi Razor template-t készítünk a Hotcakes kategóriákhoz, amit hozzárendelünk a "Receptek" szülőkategória alatti elemekhez. Ez egy MVC nézet, ami hozzáfér a kategória adataihoz, termékeihez és a Bundle-höz.
2. **Különálló DNN MVC Modul:** A modul lekéri a Hotcakes SDK-val egy adott kategória adatait, és az alapján építi fel a felületet. 

A javaslat a custom view vagy egy könnyű MVC modul, amiben a kliens oldali logika (TypeScript/React vagy Vanilla JS) teszi interaktívvá a felületet.

## 3. UI/UX Folyamat és Fő Funkciók
A vásárló az alábbi flow-val találkozik az oldalon:

### A) Receptlista (Kategória Lista)
- A "Receptek" főoldalon a vásárló a kategóriákat (recepteket) látja kártyás nézetben. 
- Egy kártyán látszik a Recept neve (Kategória neve) és a kategória indexképe.

### B) Recept Részletező (A konkrét Recept Oldal)
Amikor a vásárló belemegy egy receptbe, a modul egyedi layoutja tölt be:
- **Fejléc:** Hatalmas, hero jellegű kép, alatta a recept neve és rövid leírása (a kategória Description mezőjéből).
- **Elkészítés:** Számozott listaként renderelt lépések (szintén a Description-ből szétszedve).
- **Hozzávalók Listája:** A kategóriában lévő hagyományos termékek listázása elegáns kártyákon. Itt egyenként is be lehet rakni a kosárba az elemeket (Hotcakes Cart API-val).
- **Adagméret Skálázás (Frontend Logika):** Ha a vásárló 2 fős adagról 4 fősre vált, a felület (JavaScript) dinamikusan felszorozza a megjelenített mennyiségeket és árakat. 
- **"Összes hozzávaló kosárba" gomb:** Ez a legfontosabb gomb. Rákattintva a háttérben **nem** 8 különálló API hívás megy le az egyes alapanyagokra, hanem szimplán a recepthez tartozó **Hotcakes Bundle terméket** tesszük a kosárba. 
  - *Ha a vásárló módosította a főszámot (adagot)*, a rendszer ennek megfelelő darabszámú Bundle terméket tesz a kosárba (pl. 2x csomag a 4 főhöz).

## 4. Kihívások Elegáns Kezelése a Hibrid Modellben
- **Készletkezelés:** Mivel minden termék és Bundle natív Hotcakes elem, a Hotcakes alapból kezeli, hogy van-e elég készlet. Ha az egyik összetevőből hiány van, a Bundle termék sem lesz megvásárolható, így elkerüljük az inkonzisztenciát.
- **Kosár funkcionalitás:** Egyáltalán nem kell saját kosarat fejleszteni. A DNN+Hotcakes gyári kosara tökéletesen integrálja ezeket a termékeket.
- **Tápérték, Kcal és egyéb adatok:** Ezeket a kategória "Custom Fields" (egyedi mezők) részeiben lehet tárolni, vagy a Bundle termék terméktulajdonságai (Product Properties) között, amiket a nézet egyszerűen kiolvas és megjelenít a frontend StatCard-jain.

## 5. Összegzés
Az új hibrid MVC modul minimális egyedi adatszerkezettel oldja meg a komplex vásárlási feladatot. A weboldal (és a kosár) szemszögéből minden szabványos Hotcakes termék marad, a vásárló szemszögéből viszont egy interaktív, lenyűgöző élményt adó Recept alkalmazást kapunk. Ez messze a legjobb kompromisszum stabilitás, fejleszthetőség és minőség tekintetében.
