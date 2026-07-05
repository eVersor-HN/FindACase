# FindACase (FAC)

**FAC** is a single-file encryption app that locks your files into **one standard
[`age`](https://age-encryption.org) vault** and opens it again — on **Windows and Android**
(Linux/macOS too), fully **offline**, straight from a USB stick. No installation, no account,
no cloud, **no internet access at all**. The app is one self-contained `FindACase.html`; the
vault it produces is a plain `age` + `tar` file (an open standard), so your data stays
recoverable even without this tool.

> **Closed-source, proprietary application.** Free to use (including commercially) —
> **not for sale, not modifiable, no reverse-engineering, no redistribution.**
> See [LICENSE](LICENSE) and [DISCLAIMER](DISCLAIMER.md).

> 💛 **FAC is free.** If it keeps your files safe, you can support development with a
> donation: **PayPal [paypal.me/FAMarco](https://paypal.me/FAMarco)** (`@FAMarco`). Thank you!

## Offline first, private by design

FindACase is built as an **offline tool for your own files** — it works with the network
cable pulled, and that is not a promise but a technical property of the app itself.

- **No ads. No account. No subscription.** Copy one file to a stick, open it, done.
- **No telemetry, no phone-home — no network, by construction:** the page ships a strict
  `Content-Security-Policy` (`default-src 'none'`, no `connect-src`, no `eval`). Everything
  is inlined into the single HTML file, so the app **cannot open any connection**, not even
  to its own local origin.
- **Open vault format:** an `age` v1 file (scrypt passphrase or X25519 public-key,
  ChaCha20-Poly1305 in STREAM mode) wrapping a standard `tar` archive — see
  [Recovering a vault without FindACase](#recovering-a-vault-without-findacase).

Author / copyright: **© 2026 Marco Aurelio Fattizzo** ([@eVersor-HN](https://github.com/eVersor-HN)).
This is the **official** distribution repository — get FindACase only from here:
**https://github.com/eVersor-HN/FindACase**

---

## Download & install

1. Open the [**Releases**](https://github.com/eVersor-HN/FindACase/releases) page and
   download from the latest release:
   - **`FindACase.html`** — the app itself (this is the file the checksum verifies), or
   - **`FindACase-<version>.zip`** — the full USB-stick package (app + `Windows-Start.cmd`
     and `start.sh` launchers + `README.txt` manual + LICENSE / DISCLAIMER / notices).
2. **Verify it is the genuine original** (see below) before using it.
3. There is nothing to install — copy the file (or the unzipped folder) onto a USB stick or
   anywhere else and open it. No administrator rights are ever needed.

---

## Verify authenticity (SHA-256)

Every official release publishes the **SHA-256 checksum** of `FindACase.html`. Comparing the
checksum of your download against the published value proves the file is the **unmodified
original** and was not tampered with. (The same repository address and this verification hint
are shown inside the app under **Help → About**.)

**v1.0.1 — `FindACase.html`:**

```
fad0b489b7cae4aed24667d8cda1970f75c3ebfe2a140242026cb5bf6102e4c7
```

The authoritative value for each release is in that release's notes and in its
[`SHA256SUMS.txt`](SHA256SUMS.txt) asset.

**Check it on Windows:**

```powershell
Get-FileHash .\FindACase.html -Algorithm SHA256
```

**Check it on Linux / macOS / Android (Termux):**

```bash
sha256sum FindACase.html
```

The printed hash must match the value above (case-insensitive). If it does **not** match, do
**not** use the file — it is not the genuine FindACase build.

---

## Features

- **One vault, open format** — all selected files and folders go into **one** encrypted
  `.age` file: `age` v1 with ChaCha20-Poly1305 in STREAM mode, wrapping a standard `tar`
  archive. Truncated or tampered vaults are **rejected** on extraction, and a **Verify**
  button checks a whole vault without writing any files.
- **Two ways to lock a vault** — a **passphrase** (scrypt) or a **public key** (X25519
  `age1…` recipients; the vault opens only with the matching private identity, no password).
- **Optional 2-factor** — combine the passphrase with a **key file**; both are then required
  to open the vault.
- **Selectable protection level** — scrypt work factor 18 / 19 / 20 (≈ 256 MB / 512 MB / 1 GB
  RAM to open), so you choose the brute-force cost.
- **Built-in generators** — strong random passwords (selectable length, entropy shown), key
  files, and X25519 key pairs, all generated locally.
- **Streams everything, constant memory** — tar and age both stream, so **multi-GB vaults**
  work without filling RAM (verified: a 1 GB vault round-trips at ~115 MB peak RSS).
- **Bilingual UI** — German / English, switchable top-right; full guide, FAQ and About are
  built into the app (Help button).
- **USB-stick launchers** — `Windows-Start.cmd` (Windows) and `start.sh` (Linux/macOS) start
  a tiny local `127.0.0.1` server (no admin, no internet, DNS-rebinding-proof Host-header
  check, serves only `FindACase.html`) and open the app over localhost, which unlocks the
  File System Access API for **direct disk streaming**.
- **Runs anywhere** — any modern browser; no dependencies bundled or required for quick use.

## How to run it

- **Windows, full streaming (recommended for large vaults):** double-click
  `Windows-Start.cmd` from the release zip. It uses the PowerShell that ships with Windows —
  nothing to install.
- **Linux / macOS:** run `start.sh` (prefers PowerShell 7 `pwsh`, falls back to Python 3).
  Direct disk streaming then works in Chromium browsers (Chrome, Edge, Brave);
  Firefox/Safari automatically fall back to the in-memory path.
- **Quick use / Android:** open `FindACase.html` directly in your browser (`file://`).
  Reading and decrypting still stream; created/extracted files go through memory, so prefer
  the launcher for very large vaults on desktop.

## Recovering a vault without FindACase

The vault format is deliberately **not** proprietary. If this tool ever disappears, any
vault still opens with the official open-source `age` CLI (or `rage`) plus `tar` — `tar`
ships with Windows 10/11:

```bash
age -d -o vault.tar vault.age    # prompts for the passphrase
tar xf vault.tar                 # (public-key vaults: age -d -i identity.txt ...)
```

The `__tresor_manifest__.json` entry inside is just the vault's table of contents.

> **Important — the encryption is real:** if you lose your password (or key file / private
> identity) there is **no recovery**, by anyone. Keep passwords and backups safe and
> separate from the vault, and only open vaults on devices you trust.

## System requirements

- Any modern browser. On desktop, a **Chromium-based** browser (Chrome, Edge, Brave) enables
  direct disk streaming via the launcher; Firefox/Safari use the in-memory path.
- **Windows 10 / 11** for `Windows-Start.cmd` (built-in PowerShell, no admin rights);
  **Linux / macOS** need `pwsh` or Python 3 for `start.sh`. Android needs no launcher.

## License (summary)

FindACase is **proprietary, closed-source** software under the **FindACase EULA**
(full text in [`LICENSE`](LICENSE)):

- **Permitted:** free **use** for any purpose, **private and commercial** (companies
  included), plus the exact copies needed to install, run, back up and deploy it internally
  (USB sticks, company devices, intranet).
- **Not permitted:** modifying or adapting it, reverse engineering / decompiling /
  disassembling, selling, renting, sublicensing, or redistributing it to third parties —
  except where applicable mandatory law provides otherwise (see LICENSE, Section 3).

It bundles open-source crypto libraries under their own licenses — **typage**
(`age-encryption`, BSD-3-Clause) and the **noble** cryptography libraries (MIT) — in
minified/obfuscated form with their copyright notices preserved. Full details and texts:
[`THIRD-PARTY-NOTICES.txt`](THIRD-PARTY-NOTICES.txt).

No warranty — see [`DISCLAIMER.md`](DISCLAIMER.md).

---

© 2026 Marco Aurelio Fattizzo · FindACase · proprietary, all rights reserved
