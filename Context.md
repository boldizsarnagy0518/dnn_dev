# NaturaCo – teljes projektkontextus

Ez a dokumentum a NaturaCo egyetemi beadandó teljes kontextusát foglalja össze úgy, hogy egy új ember vagy AI is megértse a projektet minden előzetes háttértudás nélkül.

---

# 1. Projekt célja

A projekt célja egy meglévő, prémium egészséges élelmiszereket árusító webshophoz kapcsolódó egyetemi rendszerterv és UI/UX koncepció kidolgozása.

A rendszer több részből áll:

1. **Meglévő webshop / weboldal**
2. **Egy webshophoz kapcsolódó egyedi modul**
3. **Egy külön kliensalkalmazás**
4. **A kliensalkalmazás és a webshopmodul logikai kapcsolata**

A cél nem egy teljes enterprise rendszer elkészítése, hanem egy **jól átgondolt, hasznos, közepes bonyolultságú, beadandó-kompatibilis megoldás** tervezése és demonstrálása.

A projekt fő szempontjai:

* legyen **frappáns**
* legyen **hasznos**
* kapcsolódjon szervesen a webshophoz
* ne legyen túl bonyolult
* üzletileg is legyen értelme
* UI/UX szempontból illeszkedjen a meglévő weboldalhoz

---

# 2. A márka és a webshop kontextusa

## 2.1 Márkanév

**NaturaCo**

## 2.2 Márkapozíció

A NaturaCo egy prémium, egészségtudatos, magas minőségű élelmiszereket árusító webshop.

A brand fő jellemzői:

* prémium minőség
* egészségtudatosság
* magas ár + magas minőség
* letisztult, elegáns megjelenés
* etikus és fenntartható szemlélet
* lifestyle / élmény jelleg
* nem tömegpiaci, inkább válogatott és nívós

## 2.3 Történet / narratíva

A NaturaCo története szerint négy vállalkozó szellemű fiatal alapította a céget azzal a céllal, hogy egy helyen lehessen prémium, az élethez szükséges, különleges és magas minőségű termékeket vásárolni.

A fő üzenetek:

* szakértői válogatás
* felejthetetlen vásárlói élmény
* prémium termékpaletta
* testet és lelket is tápláló kínálat
* fenntartható és etikus partnerekkel való együttműködés
* felelősségteljesebb jövő támogatása

## 2.4 Vizualitás / design irány

A meglévő webshop stílusa:

* világos háttér
* sok whitespace
* fekete szöveg és fekete gombok
* vékony ikonok
* minimál design
* prémium, letisztult webshop-hangulat
* visszafogott elegancia
* enyhe arany/sárga brand accent a logó környékén

### Stílusjegyek

* nem harsány
* nem játékos
* nem tech-startup stílus
* inkább wellness / premium grocery / healthy luxury hangulat

---

# 3. A meglévő webshopról ismert információk

## 3.1 Fő menüpontok

A meglévő weboldal navigációjában például ezek szerepelnek:

* Főoldal
* Étlap
* Rólunk
* Információ
* Kosár

## 3.2 Étlap / termékoldal struktúra

A webshop jelenlegi termékoldala az alábbi mintát követi:

* kategóriák ikonos megjelenítéssel
* kereső / szűrő jellegű felület
* termékkártyák
* ár
* terméknév
* „Megveszem” jellegű CTA

## 3.3 Példa kategóriák

A webshopban látható kategóriák közül például:

* Étrendkiegészítők
* Italok
* Fehérjeforrás
* Szénhidrátforrás
* Rost és vitamin
* Egészséges zsírok
* Ízesítők
* Készételek

Ez azért fontos, mert a későbbi moduloknak és kliensalkalmazásoknak **ezekhez a termékekhez kell kapcsolódniuk**.

---

# 4. A projekt fejlődése – fontos döntések és irányváltások

A projekt során több ötlet is felmerült, de végül kialakult egy kiforrottabb koncepció.

## 4.1 Korábbi ötlet: napi kalóriaszükséglet + ajánlott termékek modul

Korábban felmerült egy olyan webshop modul ötlete, ahol a felhasználó megadja saját adatait:

* nem
* életkor
* testsúly
* magasság
* aktivitási szint
* cél

és a rendszer kiszámolja:

* napi kalóriaszükségletét
* makrotápanyagigényét
* majd ehhez termékeket ajánl a webshopból

Ez jó ötlet volt, és készült hozzá UI koncepció is, de **a későbbi receptes irány végül erősebbnek bizonyult**, mert jobban kapcsolódik közvetlenül a webshop-termékekhez és a vásárláshoz.

## 4.2 Korábbi kliensalkalmazás ötlet: termékkezelő admin

Korábban felmerült egy klasszikus termékkezelő kliensalkalmazás is, amelyben lehetett volna:

* termékeket keresni
* szerkeszteni
* újat hozzáadni
* törölni
* készletet kezelni

Ez jó admin ötlet volt, de később a beadandóhoz **egy specifikusabb, üzletileg izgalmasabb kliensalkalmazás** került előtérbe: a receptkezelő.

---

# 5. A jelenlegi véglegesebb koncepció

A jelenlegi fő irány:

## 5.1 Új kliensalkalmazás

**Receptkezelő kliensalkalmazás**

## 5.2 Új webshop modul

**Receptoldal / receptek modul**, amely a webshop termékeire épít

A két rész együtt alkot logikus rendszert:

* a kliensalkalmazásban kezelik és szerkesztik a recepteket
* a webshop modul ezeket a recepteket publikálja és vásárlásra fordítja

Ez a kapcsolat a projekt egyik legerősebb része.

---

# 6. A végleges kliensalkalmazás – receptkezelő admin

## 6.1 Rövid leírás

A kliensalkalmazás célja, hogy admin / szerkesztő oldalon lehessen recepteket létrehozni és karbantartani úgy, hogy azok a webshopban elérhető termékekből épüljenek fel.

Ez tehát **nem általános receptíró app**, hanem egy **shop-integrált receptkezelő rendszer**.

## 6.2 A kliensalkalmazás fő funkciója

A szerkesztő egy recepthez össze tudja állítani:

* milyen webshopos termékekből áll a recept
* melyikből mennyi kell
* hány főre szól a recept
* mennyi a kalória és makró
* mennyi a becsült költség
* milyen elkészítési időkkel dolgozik
* milyen lépésekből áll
* milyen diétás vagy egyéb címkéket kapjon

## 6.3 Kliensalkalmazás fő funkciók

### Alapfunkciók

* recept létrehozása
* recept szerkesztése
* recept mentése
* recept tervezetként kezelése
* recept címének megadása
* recept leírás megadása
* recept elkészítési lépések megadása

### Strukturált receptadatok

* hány főre szól
* előkészítési idő
* főzési idő
* teljes idő
* recepthez tartozó címkék

### Összetevő-kezelés

* webshopban elérhető termékek keresése
* kategória szerinti szűrés
* alapanyag hozzáadása a recepthez
* mennyiség megadása
* mértékegység figyelembevétele
* összetevő törlése
* inline mennyiségszerkesztés

### Automatikus számítások

* összes kalória
* fehérje
* szénhidrát
* zsír
* költségbecslés
* adagonkénti mutatók

### Shophoz kapcsolódó logika

* készlet látszódjon az adminnak
* a recept kizárólag a webshopban elérhető termékekből épüljön fel
* a recept publikálható legyen a webshop modulra

## 6.4 UX szempontok a kliensoldalon

A kliensalkalmazás legyen:

* gyorsan kezelhető
* jól szűrhető
* admin szemszögből praktikus
* vizuálisan letisztult
* prémium, de funkcionális

A jelenlegi UX-irány:

* külön metaadat panel
* külön összetevő-választó panel
* külön kiválasztott összetevők panel
* külön statisztika / összegzés panel

## 6.5 Javasolt extra funkciók a klienshez

Internetes inspiráció és tervezési logika alapján ezek lehetnek még hasznosak:

* allergén jelölés
* költség / adag számítás
* alacsony készlet figyelmeztetés
* diétás címkék
* recept publikálása webshopra
* draft / publish állapot
* recept kategóriák
* helyettesítő termék javaslat, ha valami nincs készleten

---

# 7. A második modul – webshop recept modul

## 7.1 Rövid leírás

Ez a modul a webshop új oldalán / új page-én jelenik meg, és a kliensalkalmazásban kezelt recepteket jeleníti meg a vásárlók számára.

Ez a modul azt a célt szolgálja, hogy a webshop ne csak különálló termékeket áruljon, hanem **konkrét recept-alapú vásárlási élményt** nyújtson.

## 7.2 Fő funkció

A felhasználó egy receptet meg tud nézni, és látja:

* a recept nevét
* rövid leírását
* hány főre szól
* mennyi az elkészítési idő
* mennyi a kalória / adag
* milyen alapanyagok kellenek hozzá
* ezek közül melyik webshopos termék
* mennyit kell belőle vásárolni

Majd a felhasználó:

* egyenként kosárba tudja rakni az összetevőket
* vagy egy gombbal az egész recept összes összetevőjét hozzá tudja adni a kosárhoz

## 7.3 Fő funkciók

### Receptlista oldalon

* receptkártyák
* recept neve
* kép / vizuális elem
* hány főre szól
* elkészítési idő
* kcal / adag
* címkék (pl. high protein, gluténmentes)

### Recept részletező oldalon

* receptleírás
* összetevők listája
* mennyiség minden összetevőhöz
* készletjellegű információk vagy elérhetőség
* elkészítési lépések
* diétás címkék

### Shop-integrált CTA-k

* „Hozzáadás a kosárhoz” minden egyes összetevőnél
* „Összes étel hozzáadása a kosárhoz” / „Összes étel hozzáadása” a teljes receptre

### Skálázás

* a felhasználó tudja állítani, hogy hány főre akarja elkészíteni a receptet
* a mennyiségek ehhez igazodnak
* a kosárba rakott mennyiségek is skálázódnak

## 7.4 Javasolt extra funkciók

A projekt során felmerült, hogy ezek is hasznosak lehetnek:

* kedvencekhez mentés
* heti menühöz adás
* bevásárlólista export
* allergén ikonok
* bio / protein / vegán / rost szűrők
* helyettesítő termék ajánlása
* hiányzó készlet jelölése

## 7.5 UX szempontok a webshop modulnál

A modulnak illeszkednie kell a NaturaCo webshophoz, ezért:

* erősen kártya-alapú
* letisztult
* prémium grocery webshop hangulatú
* fekete CTA-k
* világos háttér
* sok whitespace
* nem túl zsúfolt

A jelenlegi UX-koncepció elemei:

* hero jellegű recept fejléc
* fő adatok (idő, fő, kalória)
* összetevők listája
* jobb oldali gyors kosár-összegzés
* sticky jellegű summary panel

---

# 8. A kliensalkalmazás és a webshop modul kapcsolata

A rendszer lényege nem két különálló ötlet, hanem egy összefüggő folyamat:

1. Az admin a kliensalkalmazásban létrehoz egy receptet.
2. A recept webshopban elérhető termékekből áll.
3. A rendszer kiszámolja a recept tápértékét és költségét.
4. A recept publikálható a webshop modulra.
5. A vásárló a webshopban megtekinti a receptet.
6. Egyenként vagy egyszerre kosárba rakja az alapanyagokat.

Ez a logikai kapcsolat a beadandó egyik legfontosabb eleme.

---

# 9. Minta domain modell / adatszerkezet

A projekt alapján a következő fő entitások logikusak:

## 9.1 Product

A webshop meglévő termékei.

Tipikus mezők:

* id
* name
* category
* unit
* price
* kcal per base unit
* protein per base unit
* carbs per base unit
* fat per base unit
* stock
* isBio
* tags

## 9.2 Recipe

A recept fő adatai.

Tipikus mezők:

* id
* title
* description
* servings
* prepMinutes
* cookMinutes
* tags
* steps
* status (draft/published)

## 9.3 RecipeIngredient

Kapcsolótábla / kapcsolat a recept és a termékek között.

Tipikus mezők:

* recipeId
* productId
* quantity
* optional unit override
* optional order index

## 9.4 Cart / webshop oldal logika

A receptből kosárba kerülő tételek.

---

# 10. A projekt UI/UX iránya

## 10.1 Általános irány

Minden új UI-elemnek illeszkednie kell a NaturaCo brandhez.

### Kulcsjellemzők

* minimalista
* prémium
* világos háttér
* fekete gombok
* finom arany/sárga accent
* lekerekített kártyák
* puha, elegáns admin és webshop UI
* sok levegő / whitespace

## 10.2 Mit kell elkerülni

* neon színek
* túlzsúfolt admin dashboard vibe
* túl sok erős szín
* gamifikált vagy túl játékos megjelenés
* túl technikai, enterprise-szürke corporate UX

## 10.3 Kliensoldali UX elvárás

* gyors receptfelvitel
* könnyű alapanyagkeresés
* inline szerkesztés
* azonnali összesítés
* egyértelmű mentési flow

## 10.4 Webshop oldali UX elvárás

* recept gyors értelmezhetősége
* adagméret állíthatóság
* egyértelmű kosár-flow
* összetevők egyszerű áttekinthetősége
* szép, prémium recept-megjelenítés

---

# 11. A jelenleg elkészült TypeScript / React preview célja

Készült egy interaktív preview, amely a projekt két fő részét egy React alapú demonstrációban mutatja meg:

1. **Kliensalkalmazás nézet**

   * recept metaadatok
   * összetevő-választó
   * kiválasztott összetevők
   * makró- és költségösszesítés

2. **Webshop modul nézet**

   * recept fejléc
   * adagméret skálázás
   * hozzávalók listája
   * egyedi kosárba rakás
   * összes hozzávaló kosárba rakása
   * gyors kosár összegzés

Ez a preview jelenleg UI demonstráció és koncepcióellenőrzés céljára szolgál.

---

# 12. Technológiai kontextus

## 12.1 Figma

A projekt vizuális megtervezésére Figma használata merült fel.

A cél:

* NaturaCo-stílusú, magas minőségű mockupok készítése
* web modul és kliensalkalmazás képernyők megtervezése

## 12.2 Frontend preview

A jelenlegi preview React + TypeScript irányban készült, erős UI fókuszú mintaként.

## 12.3 Egyetemi környezet

A projekt egy egyetemi beadandó része, ezért fontos, hogy:

* érthető legyen
* bemutatható legyen
* ne legyen túl komplex
* üzletileg és logikailag jól védhető legyen

---

# 13. Mi számít jelenleg véglegesnek

## Véglegesnek tekinthető fő irányok

* a webshop márkája: NaturaCo
* a brand: prémium, egészséges, letisztult
* a végleges kliensalkalmazás: **receptkezelő admin**
* a második webshop modul: **receptoldal / receptek modul**
* a kettő kapcsolódik egymáshoz
* a rendszer webshopban elérhető termékekre épül

## Korábbi, de már nem elsődleges ötletek

* kalóriaszükséglet modul
* általános termékkezelő admin

Ezek koncepcionálisan hasznos előzmények, de jelenleg nem ezek a fő deliverable-ek.

---

# 14. Rövid executive summary

A NaturaCo projekt egy prémium, egészséges élelmiszereket árusító webshophoz készülő egyetemi koncepció, amely két új rendszerelemet tartalmaz:

1. **Receptkezelő kliensalkalmazás adminok számára**, ahol a webshop termékeiből recepteket lehet összeállítani, mennyiségekkel, adagokkal, idővel, tápértékekkel és költséggel.
2. **Webshop recept modul a vásárlók számára**, ahol a receptek megjelennek, az összetevők listázhatók, skálázhatók főszám szerint, és a felhasználó egyenként vagy egyszerre kosárba tudja rakni az alapanyagokat.

A projekt lényege az, hogy a webshop ne csak termékeket áruljon, hanem receptalapú, kényelmes és prémium vásárlási élményt is nyújtson.

---

# 15. Ha ezt a dokumentumot egy új ember vagy AI olvassa

Akkor az alábbiakat kell elsőként megértenie:

* NaturaCo = prémium healthy food webshop
* a design legyen letisztult, elegáns és webshophoz illő
* a projekt jelenlegi fókusza a **receptkezelő kliens + recept webshop modul**
* a kliens oldalon admin receptszerkesztés történik
* a webshop oldalon a recept vásárlásba fordul át
* a két rendszer közös termékadatokra épül
* a beadandó célja a jó ötlet, a hasznosság, a közepes komplexitás és a világos bemutathatóság
