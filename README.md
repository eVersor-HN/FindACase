# FindACase

**Encrypt your files into one secure vault — offline, on Windows and Android,
straight from a USB stick. No installation, no account, no cloud, no internet.**

Created and published by **Marco Aurelio Fattizzo**.
Official repository: **https://github.com/eVersor-HN/FindACase**

---

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
0db99cad31b73016997fc0152b3dcf110878ba1de93bd973f77b141303faba5b
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
- The full guide is **inside the app** (the Help button) and in the `README.txt`
  shipped with the release.

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
