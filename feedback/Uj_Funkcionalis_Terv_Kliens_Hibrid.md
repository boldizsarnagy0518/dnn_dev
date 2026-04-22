# NaturaCo Receptkezelő Kliensalkalmazás - Hibrid Funkcionális Terv

## 1. Bevezetés és Koncepcióváltás
A korábbi tervekkel ellentétben – amelyek egy teljesen egyedi adatbázis-struktúrát (saját Recept és Összetevő táblákat) javasoltak – a NaturaCo projekt új irányvonala a **Hibrid Megoldás**. Ennek lényege, hogy maximálisan kihasználjuk a Hotcakes Commerce beépített funkcióit, ezáltal csökkentve a fejlesztési időt és a karbantartási terheket.

Az új modellben a Hotcakes felel az adatok tárolásáért:
- **A Recept egy Hotcakes Kategória (Category).** A kategória neve a recept neve, a leírása (Description) pedig a recept elkészítési lépéseit tartalmazza.
- **Az Összetevők Bundle (csomag) termékként jelennek meg.** A kategóriához egy speciális Bundle terméket rendelünk, ami tartalmazza az összes szükséges alapanyagot a megfelelő mennyiségben.
- **Az alapanyagok (sima termékek)** is hozzáadásra kerülnek a kategóriához, hogy egyenként is megvásárolhatóak legyenek.

A Kliensalkalmazás továbbra is egy asztali (WinForms) felület marad, de az adatmentés mechanizmusa átalakul.

## 2. A Kliensalkalmazás Feladatai
A WinForms kliensalkalmazás az adminisztrátor (PO) munkaeszköze, amivel összeállíthatja a recepteket. Mivel a háttérben a Hotcakes adatszerkezete egy picit komplex (Category létrehozása, Bundle létrehozása, termékek összerendelése), a kliens feladata, hogy ezt a komplexitást teljesen elrejtse.

Az admin ugyanazt a letisztult, "Kliens_and_modul.ts"-ben megálmodott UI-t látja:
1. Recept metaadatok megadása (Név, Lépések, Főszám).
2. Termékek kikeresése a meglévő Hotcakes katalógusból (Hotcakes REST API segítségével).
3. Mennyiségek megadása.
4. "Mentés és Publikálás" gomb megnyomása.

## 3. Technikai Megvalósítás: A Hibrid Mentési Folyamat
A WinForms alkalmazás képes lekérni a termékeket a standard Hotcakes REST API-val, de **Bundle terméket nem tud közvetlenül létrehozni** az API korlátai miatt. Ezért bevezetünk egy saját fejlesztésű **DNN Web API végpontot**, ami hídként szolgál.

A mentés folyamata:
1. Az admin rákattint a mentés gombra.
2. A WinForms kliens összeállít egy JSON csomagot, ami tartalmazza a recept adatait és a kiválasztott termékek azonosítóit/mennyiségeit.
3. Ezt elküldi egy egyedi DNN Web API-nak (pl. `/api/NaturaCoRecipes/SaveRecipe`).
4. **Szerver oldali műveletek (Hotcakes SDK-val):**
   - A DNN végpont a belső `Hotcakes.Commerce.dll` felhasználásával létrehoz egy új **Kategóriát** a megadott névvel és leírássel.
   - Létrehoz egy új **Bundle Terméket**, és hozzárendeli a recepthez kiválasztott alapanyagokat a megfelelő mennyiségekkel.
   - Hozzáadja az egyedi termékeket és a Bundle terméket is az új Kategóriához.
   
## 4. UI/UX Követelmények (Kliens oldalon)
A WinForms felületnek modernnek és átláthatónak kell lennie:
- **Bal oldali panel:** Keresőmező, kategóriaszűrő, terméklista a meglévő Hotcakes termékekkel. Egy "Hozzáadás" gomb minden sornál.
- **Középső panel (Összetevők):** A már hozzáadott termékek listája, ahol módosítható a mennyiség (inline editorral), és valós időben frissül a becsült költség.
- **Jobb oldali panel (Recept adatok):** Név, Leírás (lépések), Címkék, Adagok száma.
- **Lábjegyzet/Statisztika:** Automatikusan számolt összes kalória, makrók és becsült ár a kiválasztott termékek adatai alapján.

## 5. Előnyök az eredeti tervhez képest
- Nincs szükség külön SQL táblák menedzselésére, a Hotcakes mindent megold natívan.
- A DNN cache-elés, a SEO és a képek kezelése automatikusan működik (mivel sima Hotcakes kategóriáról és termékekről van szó).
- Ha a PO módosít egy termék árán a shopban, az a recept (Bundle) árában is azonnal, automatikusan érvényesül.
