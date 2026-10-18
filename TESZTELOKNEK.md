# DriveBridge – útmutató tesztelőknek

Köszönjük, hogy kipróbálod a DriveBridge-et! Ez az útmutató lépésről lépésre végigvezet a telepítésen, a beállításon és a használaton. Technikai tudás nem kell hozzá.

*English version: [TESTERS.md](TESTERS.md)*

## Mi a DriveBridge?

A DriveBridge egy Android-alkalmazás, amellyel vezetés közben, a telefon érintése nélkül beszélgethetsz a saját AI-asszisztenseddel. A kérdést diktálod, a választ az autó hangszórója olvassa fel, a vezérlés pedig az autó médiagombjaival megy. A beszélgetés a saját AI-fiókodban marad, így később az íróasztalnál is folytathatod.

## Amire szükséged van

- **Android-telefon**, Android 13 vagy újabb rendszerrel. A diktáláshoz kell, hogy a telefon beszédfelismerője tudja a választott nyelvet.
- **Autó vagy fejhallgató**, amely Bluetoothon lejátssza a telefon hangját, és vannak médiagombjai.
- **AI-fiók**: Claude vagy Grok. Ehhez adod hozzá a DriveBridge-et connectorként.
- Egyszer egy **böngésző** (vagy a Claude Desktop) a connector hozzáadásához.
- **Internetkapcsolat** a telefonon vezetés közben.

## 1. Az alkalmazás telepítése

1. **Töltsd le** a telefonodra a telepítőfájlt: [DriveBridge-0.11.10.apk](https://github.com/Endre999/DriveBridge-Release/releases/download/drivebridge-reader-v0.11.10/DriveBridge-0.11.10.apk). Mindig a [README](README.md) legfrissebb linkjét használd.
2. **Engedélyezd az ismeretlen alkalmazások telepítését** annak az alkalmazásnak, amellyel a fájlt megnyitod (például a böngésződnek vagy a fájlkezelőnek). A pontos menü telefononként más. Általában a Beállítások → Alkalmazások (vagy Biztonság) → *Ismeretlen alkalmazások telepítése* helyen találod. Sok telefon a fájl megnyitásakor magától rákérdez, és egy gombbal oda is visz.
3. **Nyisd meg a letöltött APK-fájlt** (az értesítésekből vagy a Letöltések mappából), és koppints a *Telepítés* gombra.
4. **Ha a Google Play Protect figyelmeztet**: ez természetes, mert az alkalmazás még nincs fent a Google Playen. Ilyenkor általában a *További részletek* (*More details*), majd a *Telepítés mindenképp* (*Install anyway*) lehetőséget kell választani. A pontos felirat változhat.
5. **Ellenőrzés (nem kötelező):** ha szeretnéd, összevetheted a fájl SHA-256 kivonatát a README-ben megadott értékkel. Az APK a DriveBridge saját kiadási kulcsával van aláírva. A tanúsítvány SHA-256 ujjlenyomata a README alján található.

## 2. Első indítás

1. Indítsd el a DriveBridge-et. Két engedélyt kér: a **mikrofont** (a diktáláshoz) és az **értesítéseket** (a médiavezérlőhöz). Mindkettőt add meg.
2. Ezután **kiválaszthatod az alkalmazás nyelvét**. Később a főképernyő fejlécéből is módosíthatod.
3. **DriveBridge-fiók:** jelszó nincs. Az e-mail-címedet adod meg, és egy kódot kapsz rá e-mailben. Regisztrálj az alkalmazásban azzal az e-mail-címmel, amelyet a connector hozzáadásakor is használni fogsz. A fiókodat a böngészőben, a [https://mcp.pandaonthemoon.io/login](https://mcp.pandaonthemoon.io/login) oldalon is eléred, szintén e-mail-címmel és kóddal.
4. A főképernyő alján ezt látod: `Build 0.11.10 (72)`.

## 3. Az AI-kliens csatlakoztatása (egyszer kell)

A connector címe mindenhol ugyanaz:

```
https://mcp.pandaonthemoon.io/mcp
```

A neve legyen: `DriveBridge`.

**Claude** (a claude.ai oldalon vagy a Claude Desktopban):
1. Nyisd meg a Settings menüt, majd a Customize → Connectors részt. Válaszd a *+ Add*, majd az *Add custom connector* lehetőséget.
2. Név: `DriveBridge`, a *Remote MCP server URL* mező: `https://mcp.pandaonthemoon.io/mcp`.

**Grok:**
1. Nyisd meg a Connectors listát, és görgess le a felajánlott (Featured) connectorok legaljára. Saját connectort csak ott tudsz hozzáadni.
2. Név: `DriveBridge`, cím: `https://mcp.pandaonthemoon.io/mcp`.

**Ezután mindkettőnél:**
1. Megnyílik a „DriveBridge engedélyezés” oldal. Írd be a DriveBridge-fiókod e-mail-címét.
2. 6 számjegyű kód érkezik e-mailben („DriveBridge connector kód” tárgyú levélben). Ha nem jön meg, nézd meg a Spam és a Promóciók mappát is. Írd be a kódot ugyanazon az oldalon.
3. A böngésző visszavisz a Claude-ba vagy a Grokba, és a connector csatlakozik. Ettől kezdve a telefonos AI-alkalmazásban is elérhető.

**Fontos a Claude-ban:** a Connectors menüben válaszd ki a DriveBridge-et, és a *Tool permissions* részben állítsd az összes eszközét *Always allow* értékre. Ha vezetés közben engedélyt kér, senki nem tudja megnyomni a gombot, és a beszélgetés megáll. **A Claude frissítés után, vagy amikor új eszköz jelenik meg, néha visszaállítja ezt.** Ilyenkor kapcsold be újra az *Always allow*-t.

A menük nevei a Claude-tól és a Groktól függenek, és idővel változhatnak.

## 4. Használat az autóban

1. Csatlakoztasd a telefont Bluetoothon az autóhoz (vagy a fejhallgatóhoz), ahogy zenehallgatáshoz is tennéd.
2. A DriveBridge-ben nyomd meg a **Kapcsolódás** gombot. A telefon egy 6 jegyű kódot mutat, és a vágólapra másol egy kész mondatot, benne ezzel a kóddal.
3. Nyisd meg az AI-alkalmazásodat azon a beszélgetésen, amelyben dolgozni szeretnél, és ellenőrizd, hogy a DriveBridge connector be van kapcsolva. Illeszd be és küldd el a mondatot. Az AI csatlakozik, és várja az első kérdésedet.
4. A DriveBridge Készenlétbe vált. Lezárhatod a képernyőt, és elteheted a telefont. Az autó médiagombjaival vezérelsz: a **Lejátszás** elindítja a diktálást, az **Előre** elküldi a kérdést, a választ pedig az autó hangszórója olvassa fel. A gombok részletes leírása: [DriveBridge vezérlés](https://www.pandaonthemoon.io/hu/drivebridge/controls/).
5. **A kód 5 percig érvényes.** Új kódot 60 másodperc után kérhetsz (óránként legfeljebb ötöt), és az új kód érvényteleníti a régit. Ha egy menet lezárult, a telefon magától újat indít, friss kóddal.
6. A menet végén nyomd meg kétszer a **Beszélgetés vége** gombot.

Közben ne szóljon más alkalmazás, mert különben a DriveBridge elveszíti a hangot. A menet leirata 7 napig megmarad a telefonon, a Leiratok alatt.

A részletes útmutató a honlapon van: [DriveBridge beüzemelése](https://www.pandaonthemoon.io/hu/drivebridge/setup/).

## 5. Frissítés új verzióra

Töltsd le az új APK-t, és telepítsd rá a régire. **Eltávolítani nem kell**, mert minden verzió ugyanazzal a kiadási kulccsal van aláírva (0.10.0-tól). Csak akkor kell eltávolítani, ha a telefonodon egy más aláírású tesztverzió van. Ez törli a telefonon tárolt leiratokat, ezért a megtartandókat előtte mentsd ki.

## 6. Visszajelzés – ez segít nekünk a legtöbbet 💬

A legegyszerűbb, ha **a saját AI-asszisztensednek mondod el** (Claude-nak vagy Groknak), bármelyik beszélgetésben, ahol a DriveBridge connector be van kapcsolva. Például:

> „Küldd el visszajelzésnek a DriveBridge fejlesztőjének, hogy a második gombnyomás után nem indult el a diktálás.”

Az AI a te szavaiddal, közvetlenül a fejlesztőnek továbbítja az üzenetet. Bármit szívesen fogadunk: **hibát, ötletet, kérdést vagy bármi mást**.

Ami sokat segít:
- a **telefon típusa** és az **Android-verzió**;
- az alkalmazás verziója (a főképernyő alján, például `Build 0.11.10 (72)`);
- az autó vagy a fejhallgató típusa;
- **mi történt**, és mit csináltál közvetlenül előtte.

Ha ez valamiért nem megy, szólj annak, akitől a tesztmeghívót kaptad.

## 7. Adatvédelem röviden

- Amit diktálsz, és a válaszok, a DriveBridge szerverén haladnak át a telefon és az AI között, és ott nem tárolódnak tartósan.
- A beszédet a telefonod beszédfelismerője alakítja szöveggé, nem a DriveBridge.
- A beszélgetés a saját AI-fiókodban marad. A DriveBridge nem fér hozzá az AI-belépésedhez, a beszélgetéseid listájához és a projektjeid tartalmához.
- A menet leirata 7 napig marad meg a telefonon, utána törlődik.
- A visszajelzésként elküldött üzeneted a fiókod e-mail-címével együtt jut el a fejlesztőhöz, hogy válaszolni tudjon.

Részletek: [Adatvédelem](https://www.pandaonthemoon.io/hu/privacy/), [Feltételek](https://www.pandaonthemoon.io/hu/terms/).

Jó utat és jó tesztelést! 🚗
