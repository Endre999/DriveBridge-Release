# DriveBridge – letöltés és telepítés tesztelőknek

A DriveBridge Android-alkalmazás: vezetés közben, a telefon érintése nélkül beszélhetsz a saját Claude-fiókoddal. A kérdést diktálod, a választ az autó hangszórója olvassa fel, a vezérlés az autó médiagombjaival megy.

Az alkalmazás zárt tesztben van, és nincs a Google Playen. A tesztelők innen töltik le a telepítőfájlt (APK).

## Aktuális verzió

A [Releases](https://github.com/Endre999/DriveBridge-Release/releases) oldalon mindig csak a legújabb verzió van.

| | |
|---|---|
| Verzió | 0.11.8 (build 70) |
| Fájl | `DriveBridge-0.11.8.apk`, 1 702 624 bájt |
| Letöltés | [DriveBridge-0.11.8.apk](https://github.com/Endre999/DriveBridge-Release/releases/download/drivebridge-reader-v0.11.8/DriveBridge-0.11.8.apk) |
| SHA-256 | `b464eee4b7fe9b73d24472258381544eeaa9aac5e83ce93b23461f2afb8a8beb` |

A kiadás közvetlenül letölthető APK-ként, ZIP-csomagolás nélkül.

## Újdonságok a 0.11.8-ban

- Az alkalmazás eddig beégetett feliratai (például a „Vissza a DriveBridge-hez” gomb és a verziófelirat) mind a 32 nyelven lefordítva jelennek meg.
- Kikerült a Diagnosztika rész (naplómentés és -törlés).
- A beszélgetés végét visszaigazoló hangüzenet már nem vágódik félbe, végig elhangzik.

## Amire szükséged van

- Android-telefon, Android 13 vagy újabb. A diktáláshoz a választott nyelv beszédfelismerése kell a telefonon.
- Autó, amely Bluetoothon hangot játszik le, és vannak médiagombjai.
- Claude-fiók, amelyhez egyéni connector adható.
- Böngésző vagy Claude Desktop a connector egyszeri hozzáadásához.
- Internetkapcsolat a telefonon vezetés közben.

## Telepítés

1. Töltsd le a telefonra a fenti `DriveBridge-0.11.8.apk` fájlt.
2. Nyisd meg a letöltött fájlt, és engedélyezd a telepítést ebből a forrásból, amikor az Android rákérdez.
3. Indítsd el a DriveBridge-et. Két engedélyt kér: a mikrofont a diktáláshoz és az értesítéseket a médiavezérlőhöz. Utána kiválaszthatod az alkalmazás nyelvét.
4. Ellenőrizd a főképernyő alján a feliratot: `Build 0.11.8 (70)`.

A fiókba a honlap Belépés gombjáról lehet belépni, e-mail-címmel és kóddal, jelszó nélkül.

### Frissítés korábbi verzióról

A 0.11.8 ugyanazzal a kiadási tanúsítvánnyal van aláírva, mint a korábbi verziók (0.10.0-tól), ezért eltávolítás nélkül frissíthető.

Ha a telefonon lévő tesztverzió más aláírással készült, előbb el kell távolítani, mert az Android nem engedi rá telepíteni az újat. Az eltávolítás törli a telefonon tárolt leiratokat, ezért a megtartandókat előbb mentsd ki az alkalmazás Leiratok listájából.

## Beüzemelés

A teljes, lépésenkénti útmutató a honlapon van: **[DriveBridge beüzemelése](https://www.pandaonthemoon.io/hu/drivebridge/setup/)**. Ugyanezt nyitja meg az alkalmazás Kapcsolódás kártyáján a „Beállítási útmutató” gomb.

A lényeg röviden:

1. **Connector hozzáadása a Claude-hoz**, egyszer. Név: `DriveBridge`, cím: `https://mcp.pandaonthemoon.io/mcp`.
2. **Jóváhagyás.** A hozzáadáskor megnyíló „DriveBridge engedélyezés” oldal a DriveBridge-fiók e-mail-címét kéri, majd az e-mailben érkező kódot. Jelszó nincs.
3. **Eszközengedélyek.** A Claude-ban a DriveBridge minden eszközét állítsd „Always allow” értékre. Ha a Claude vezetés közben engedélyt kér, senki nem tudja megnyomni a választ, és a beszélgetés megáll.
4. **Minden út elején:** csatlakoztasd a telefont az autóhoz Bluetoothon, nyomd meg a DriveBridge-ben a Kapcsolódás gombot, majd a vágólapra másolt mondatot illeszd be és küldd el abban a Claude-beszélgetésben, amelyben dolgozni szeretnél.

A gombok részletes leírása: [DriveBridge vezérlés](https://www.pandaonthemoon.io/hu/drivebridge/controls/).

## Hová kerül, amit mondasz

- A diktált szöveg és a válaszok a DriveBridge szerverén haladnak át a telefon és a Claude között, és ott nem tárolódnak tartósan.
- A beszédet a telefon beszédfelismerő szolgáltatása alakítja szöveggé, nem a DriveBridge.
- A beszélgetés a saját Claude-fiókodban marad. A DriveBridge nem fér hozzá a Claude-belépésedhez, a beszélgetéseid listájához és a projektjeid tartalmához.
- A menet leirata 7 napig megmarad a telefonon, utána törlődik.

Részletek: [Adatvédelem](https://www.pandaonthemoon.io/hu/privacy/), [Feltételek](https://www.pandaonthemoon.io/hu/terms/).

## Visszajelzés

A hibákat és az észrevételeket annak jelezd, akitől a tesztmeghívót kaptad. Segít, ha megírod a verziót (`Build 0.11.8 (70)`), a telefon és az autó típusát, és azt, hogy mit csináltál közvetlenül a hiba előtt.

## A letöltött fájl ellenőrzése

Nem kötelező. A fájl SHA-256 kivonata egyezzen a fenti értékkel; ugyanez a Releases oldalon a `DriveBridge-0.11.8.apk.sha256` fájlban is megvan.

Az APK a DriveBridge saját kiadási kulcsával van aláírva. Az aláíró tanúsítvány SHA-256 ujjlenyomata:

`eeb48e8fc76744ca4c07f0fa13dfa0d1684894250a7f870a214e2492b203e5fa`
