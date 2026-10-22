# Lighting Watchdog — downloads

A free desktop app that checks a lighting network at load-in and watches Art-Net and sACN during the show — every dropout with its time, length, universes, the fixtures it hit and the likely cause. By [Squaresmile](https://squaresmile.de/lighting-watchdog).

**Free beta.** Download it from [squaresmile.de/lighting-watchdog](https://squaresmile.de/lighting-watchdog) with a free squaresmile.de account, or take the newest files from [Releases](https://github.com/Square-Smile/lighting-watchdog-releases/releases/latest).

*Deutsche Anleitung: [weiter unten](#installation-deutsch).*

---

## How to install

You need: macOS 12 or newer (Apple silicon or Intel), or Windows 10 / 11 (64-bit) — and a **wired** network adapter on the lighting network. Wi-Fi is fine for a quick look, not for a show.

### Windows — 3 steps, about 5 minutes

**Which file:** `Lighting.Watchdog_<version>_x64-setup.exe`

**1. Run the installer.**
Windows may show a blue box: **"Windows protected your PC"**.
This is not a virus warning — Windows just doesn't know the publisher yet, because the installer isn't code-signed yet.
Click **More info**, then **Run anyway**. Then click through the installer (no admin password needed).

> Whether this box appears depends on how the file got onto the PC: downloaded with a browser → it usually appears; copied from a USB stick → usually not. Both are the same file.

> **Tip — skip the box entirely:** before running the installer, right-click it → **Properties** → at the bottom of the **General** tab tick **Unblock** → **OK**. Windows then treats it like a file copied from a USB stick, and the box doesn't appear. (No Unblock checkbox there? Then the file isn't marked, and there won't be a box anyway.)

**2. Install Npcap when the installer asks.**
At the end the installer checks for **Npcap**, the free driver that lets the app see network traffic (it's from the makers of Nmap and Wireshark). If it's missing, a box asks to open the Npcap page — click **Yes**.

- On npcap.com, download the **Npcap installer** (the first link under "Downloading Npcap") and run it. This one needs your admin password.
- In its options:
  - ✅ **Support loopback traffic** — keep it **ticked**. Without it the app can't see a console and a media server talking on the same PC (e.g. grandMA2 onPC → MadMapper).
  - ✅ **Install Npcap in WinPcap API-compatible Mode** — leave as it is (ticked).
  - ⬜ **Restrict Npcap driver's access to Administrators only** — leave it **unticked**.
  - ⬜ Everything else — leave as it is.

> Why a separate download? Npcap's license doesn't allow us to put it inside our installer. If Wireshark is already installed, Npcap is already there — you can skip this step.

**3. Start Lighting Watchdog.**
If Npcap is still missing, the app shows the same three steps with a **Get Npcap** button. You can install Npcap while the app is open — it notices it by itself within a few seconds, no restart.

When you first press **Start check**, Windows Defender Firewall may ask whether to allow the app — click **Allow access**. (It's asked because Check sends test packets; watching works either way.)

### macOS — 2 steps

**Which file:** `Lighting.Watchdog_<version>_universal.dmg`

1. Open the DMG and drag **Lighting Watchdog** into **Applications**. Start it from there. It's signed and notarized by Apple, so it opens without warnings.
2. The first time you watch, the app asks to **Allow capture**: enter your Mac admin password once. It installs the same small helper Wireshark uses, so the app can read network traffic. Once per Mac.

### First watch (both)

1. Go to **Watch** and tick the adapter that's plugged into the lighting network. If console and media server run on the same computer, also tick the **loopback** adapter.
2. Press **Start watching**. You can close the window — it keeps running in the tray / menu bar.
3. After the show: **Stop & write report**, or open **Reports** later.

### Something doesn't work?

| What you see | What to do |
|---|---|
| "Windows protected your PC" | **More info → Run anyway** — or next time **Properties → Unblock** first (see step 1). |
| A banner "One more step on Windows: install Npcap" | Follow the three steps in the banner. |
| "Npcap is installed without loopback support" | Run the Npcap installer again and tick **Support loopback traffic**. |
| No adapters in the list (Windows) | Npcap is missing or was installed with "Administrators only" — reinstall it with that option unticked. |
| Adapter listed, but no data | Is the cable in the lighting network? Is the adapter's IP in the same range as the console (e.g. 2.x.x.x or 10.x.x.x)? |
| A red banner "Two or more programs hold the Art-Net port 6454" | Two programs on this PC share the Art-Net port — that alone loses data. Close one, or see the guide. |

The full guide: [squaresmile.de/help/lighting-watchdog](https://squaresmile.de/help/lighting-watchdog). Questions: **support@squaresmile.de**.

Check a download against `SHA256SUMS.txt` if you like.

---

## Installation (Deutsch)

Du brauchst: macOS 12 oder neuer (Apple Silicon oder Intel) oder Windows 10 / 11 (64 Bit) — und einen **kabelgebundenen** Netzwerkadapter im Lichtnetz. WLAN reicht zum Reinschauen, nicht für eine Show.

### Windows — 3 Schritte, ca. 5 Minuten

**Welche Datei:** `Lighting.Watchdog_<Version>_x64-setup.exe`

**1. Installer starten.**
Windows zeigt evtl. ein blaues Fenster: **„Der Computer wurde durch Windows geschützt“**.
Das ist keine Virenwarnung — Windows kennt den Herausgeber nur noch nicht, weil der Installer noch nicht signiert ist.
**Weitere Informationen** klicken, dann **Trotzdem ausführen**. Danach durch den Installer klicken (kein Admin-Passwort nötig).

> Ob das Fenster kommt, hängt davon ab, wie die Datei auf den PC kam: mit dem Browser heruntergeladen → meistens ja; vom USB-Stick kopiert → meistens nicht. Es ist dieselbe Datei.

> **Tipp — das Fenster ganz vermeiden:** vor dem Starten Rechtsklick auf den Installer → **Eigenschaften** → unten im Reiter **Allgemein** **Zulassen** anhaken → **OK**. Windows behandelt die Datei dann wie eine vom USB-Stick kopierte, und das Fenster kommt nicht. (Kein Kästchen „Zulassen“ da? Dann ist die Datei nicht markiert, und es kommt sowieso kein Fenster.)

**2. Npcap installieren, wenn der Installer fragt.**
Am Ende prüft der Installer, ob **Npcap** da ist — der kostenlose Treiber, mit dem die App Netzwerkverkehr sieht (von den Machern von Nmap und Wireshark). Fehlt er, fragt ein Fenster, ob die Npcap-Seite geöffnet werden soll — **Ja** klicken.

- Auf npcap.com den **Npcap installer** herunterladen (der erste Link unter „Downloading Npcap“) und ausführen. Der braucht das Admin-Passwort.
- In den Optionen:
  - ✅ **Support loopback traffic** — **angehakt** lassen. Ohne das sieht die App nicht, wenn Pult und Medienserver auf demselben PC laufen (z. B. grandMA2 onPC → MadMapper).
  - ✅ **Install Npcap in WinPcap API-compatible Mode** — so lassen (angehakt).
  - ⬜ **Restrict Npcap driver's access to Administrators only** — **nicht** anhaken.
  - ⬜ Alles andere — so lassen.

> Warum ein eigener Download? Die Npcap-Lizenz erlaubt nicht, dass wir es in unseren Installer packen. Ist Wireshark schon installiert, ist Npcap schon da — dann diesen Schritt überspringen.

**3. Lighting Watchdog starten.**
Fehlt Npcap noch, zeigt die App dieselben drei Schritte mit einem Knopf **Npcap holen**. Du kannst Npcap bei offener App installieren — sie bemerkt es nach ein paar Sekunden von selbst, ohne Neustart.

Beim ersten **Check starten** fragt evtl. die Windows-Defender-Firewall, ob die App zugelassen werden soll — **Zugriff zulassen** klicken. (Sie fragt, weil Check Testpakete sendet; das Beobachten geht so oder so.)

### macOS — 2 Schritte

**Welche Datei:** `Lighting.Watchdog_<Version>_universal.dmg`

1. DMG öffnen und **Lighting Watchdog** in **Programme** ziehen. Von dort starten. Die App ist von Apple signiert und notarisiert und öffnet sich ohne Warnung.
2. Beim ersten Beobachten fragt die App nach **Mitschnitt erlauben**: einmal das Admin-Passwort des Macs eingeben. Sie installiert denselben kleinen Helfer, den Wireshark nutzt, damit sie Netzwerkverkehr lesen kann. Einmal pro Mac.

### Erstes Beobachten (beide)

1. **Watch** öffnen und den Adapter anhaken, der im Lichtnetz steckt. Laufen Pult und Medienserver auf demselben Computer, zusätzlich den **Loopback**-Adapter anhaken.
2. **Beobachten starten** drücken. Das Fenster darfst du schließen — die App läuft im Tray / in der Menüleiste weiter.
3. Nach der Show: **Stoppen & Bericht schreiben**, oder später unter **Berichte** öffnen.

### Etwas geht nicht?

| Was du siehst | Was tun |
|---|---|
| „Der Computer wurde durch Windows geschützt“ | **Weitere Informationen → Trotzdem ausführen** — oder beim nächsten Mal vorher **Eigenschaften → Zulassen** (siehe Schritt 1). |
| Banner „Noch ein Schritt unter Windows: Npcap installieren“ | Den drei Schritten im Banner folgen. |
| „Npcap ist ohne Loopback-Unterstützung installiert“ | Npcap-Installer noch einmal ausführen und **Support loopback traffic** anhaken. |
| Keine Adapter in der Liste (Windows) | Npcap fehlt oder wurde mit „Administrators only“ installiert — ohne diese Option neu installieren. |
| Adapter da, aber keine Daten | Steckt das Kabel im Lichtnetz? Liegt die IP des Adapters im selben Bereich wie das Pult (z. B. 2.x.x.x oder 10.x.x.x)? |
| Rotes Banner „Zwei oder mehr Programme belegen den Art-Net-Port 6454“ | Zwei Programme auf diesem PC teilen sich den Art-Net-Port — das allein verliert Daten. Eins schließen oder Anleitung lesen. |

Die ganze Anleitung: [squaresmile.de/help/lighting-watchdog](https://squaresmile.de/help/lighting-watchdog). Fragen: **support@squaresmile.de**.

---

## What's in this repository

Only the installers and this guide. The source code is not public.

Art-Net™ Designed by and Copyright Artistic Licence.
