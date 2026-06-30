# FindACase

**Verschlüssele deine Dateien in einen einzigen, sicheren Tresor — offline, auf
Windows und Android, direkt vom USB-Stick. Keine Installation, kein Konto, keine
Cloud, kein Internet.**

*Encrypt your files into one secure vault — offline, on Windows and Android,
straight from a USB stick. No installation, no account, no cloud, no internet.*

Created and published by **Marco Aurelio Fattizzo**.
Official repository: **https://github.com/eVersor-HN/FindACase**

---

## Deutsch

FindACase ist eine einzige, in sich geschlossene HTML-App. Sie verschlüsselt
beliebige Dateien in **einen** standardkonformen [`age`](https://age-encryption.org)-Tresor
(`.age`) und entschlüsselt sie wieder — komplett **offline** in deinem Browser.
Die Oberfläche ist zweisprachig (Deutsch / English).

### Herunterladen & Echtheit prüfen

1. Lade `FindACase.html` aus dem neuesten **[Release](../../releases/latest)** dieses Repos.
2. Prüfe den **SHA-256-Wert** deiner Datei und vergleiche ihn mit dem hier
   veröffentlichten Wert:
   - **Windows (PowerShell):** `Get-FileHash FindACase.html`
   - **Linux / macOS:** `sha256sum FindACase.html`

```
SHA-256 (FindACase.html) =
3d31550d05e88a9f4db5abe48292eddcd253774565c7ff52edc99b519297cf3d
```

Stimmt der Wert überein, hast du das **unveränderte Original**. Lade FindACase
**nur** aus diesem Repo; für Kopien aus anderen Quellen wird keine Gewähr übernommen.
(Der SHA-256 jeder Version steht auch in [`SHA256SUMS.txt`](SHA256SUMS.txt) und in
den jeweiligen Release-Notes.)

### Benutzen

- **Windows (empfohlen, auch für große Tresore):** Den gesamten Ordner aus dem
  Release auf den Stick kopieren und `Windows-Start.cmd` doppelklicken. Es startet
  nur lokal einen Mini-Server (kein Internet) und öffnet die App.
- **Schnell / Android:** `FindACase.html` direkt im Browser öffnen.
- Die ausführliche Anleitung steckt **in der App** (Knopf „Anleitung") und in der
  `LIESMICH.txt` im Release.

### Lizenz (Kurzfassung)

FindACase ist **proprietäre Closed-Source-Software**, © 2026 Marco Aurelio
Fattizzo — **alle Rechte vorbehalten**.

- **Erlaubt:** kostenlose Nutzung, **privat und kommerziell** (auch in Firmen),
  inklusive der dafür nötigen internen Kopien.
- **Nicht erlaubt:** Verändern, Reverse-Engineering, Verkauf, Vermietung,
  Unterlizenzierung oder Weiterverbreitung.

Vollständige Bedingungen: **[LICENSE](LICENSE)**. Haftungs- und
Gewährleistungsausschluss: **[DISCLAIMER.md](DISCLAIMER.md)**. Die enthaltenen
Krypto-Bibliotheken stehen unter ihren eigenen Open-Source-Lizenzen:
**[THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt)**.

### Wichtig

Die Verschlüsselung ist echt: **Ohne Passwort (bzw. Schlüsseldatei) gibt es keine
Wiederherstellung.** Bewahre Passwörter und Sicherungen sicher und getrennt vom
Tresor auf. Öffne Tresore nur auf Geräten, denen du vertraust.

---

## English

FindACase is a single, self-contained HTML app. It encrypts any files into **one**
standard [`age`](https://age-encryption.org) vault (`.age`) and decrypts them
again — entirely **offline** in your browser. The interface is bilingual
(German / English).

### Download & verify authenticity

1. Download `FindACase.html` from this repo's latest **[Release](../../releases/latest)**.
2. Compute the **SHA-256** of your file and compare it with the value published here:
   - **Windows (PowerShell):** `Get-FileHash FindACase.html`
   - **Linux / macOS:** `sha256sum FindACase.html`

```
SHA-256 (FindACase.html) =
3d31550d05e88a9f4db5abe48292eddcd253774565c7ff52edc99b519297cf3d
```

If it matches, you have the **unmodified original**. Download FindACase **only**
from this repo; copies from other sources come with no guarantee. (Each version's
SHA-256 is also listed in [`SHA256SUMS.txt`](SHA256SUMS.txt) and in the
corresponding release notes.)

### Use

- **Windows (recommended, also for large vaults):** copy the whole folder from the
  release onto your stick and double-click `Windows-Start.cmd`. It only starts a
  local mini-server (no internet) and opens the app.
- **Quick / Android:** open `FindACase.html` directly in your browser.
- The full guide is **inside the app** (the "Anleitung / Help" button) and in the
  `LIESMICH.txt` shipped with the release.

### License (summary)

FindACase is **proprietary, closed-source software**, © 2026 Marco Aurelio
Fattizzo — **all rights reserved**.

- **Permitted:** free use, **private and commercial** (companies included),
  including the internal copies needed to run it.
- **Not permitted:** modification, reverse engineering, resale, rental,
  sublicensing, or redistribution.

Full terms: **[LICENSE](LICENSE)**. Warranty and liability disclaimer:
**[DISCLAIMER.md](DISCLAIMER.md)**. Bundled crypto libraries remain under their own
open-source licenses: **[THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt)**.

### Important

The encryption is real: **if you lose your password (or key file) there is no
recovery.** Keep passwords and backups safe and separate from the vault. Only open
vaults on devices you trust.

---

© 2026 Marco Aurelio Fattizzo · FindACase · proprietary, all rights reserved
