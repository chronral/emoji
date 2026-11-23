# chronral / emoji

Custom sticker & emoji packs curated by **chronral** (PNG / GIF), with C2PA Content Credentials and SHA-256 checksum manifests.

## Packs

### 1. Meoshi (`packs/meoshi`)

* **Format:** `240×240` transparent PNG (32-bit RGBA)
* **Count:** 8 stickers
* **Curated by:** `@chronral`
* **Note:** AI-assisted fan-style chibi sticker pack
* **Telegram Emoji:** [t.me/addemoji/meishio](https://t.me/addemoji/meishio)
* **Provenance:** C2PA Content Credentials ([`certs/chronral-c2pa-root.pem`](./certs/chronral-c2pa-root.pem)) + DigiCert RFC 3161 TSA
* **Manifest:** [`packs/meoshi/manifest.json`](./packs/meoshi/manifest.json)
* **Checksums:** [`packs/meoshi/SHA256SUMS.txt`](./packs/meoshi/SHA256SUMS.txt)

| `01-wave-hi` | `02-sipping-coffee` | `03-thumbs-up` | `04-confused` |
| :---: | :---: | :---: | :---: |
| <img src="./packs/meoshi/png/01-wave-hi.png" width="96" alt="wave hi" /> | <img src="./packs/meoshi/png/02-sipping-coffee.png" width="96" alt="sipping coffee" /> | <img src="./packs/meoshi/png/03-thumbs-up.png" width="96" alt="thumbs up" /> | <img src="./packs/meoshi/png/04-confused.png" width="96" alt="confused" /> |

| `05-shocked` | `06-laughing` | `07-pouting` | `08-crying` |
| :---: | :---: | :---: | :---: |
| <img src="./packs/meoshi/png/05-shocked.png" width="96" alt="shocked" /> | <img src="./packs/meoshi/png/06-laughing.png" width="96" alt="laughing" /> | <img src="./packs/meoshi/png/07-pouting.png" width="96" alt="pouting" /> | <img src="./packs/meoshi/png/08-crying.png" width="96" alt="crying" /> |

## Releases

* **`meoshi-v1.1.0`** — Embedded C2PA Content Credentials (`~700 KB` per PNG), recommended for provenance and archival.
* **`meoshi-v1.0.0`** — Lightweight raw PNGs (`~67 KB` per PNG), recommended for chat platforms with strict upload size limits (e.g., Discord / Telegram).

## Verification

```bash
# Verify file integrity
cd packs/meoshi && sha256sum -c SHA256SUMS.txt

# Verify embedded C2PA Content Credentials against the published root CA
c2patool packs/meoshi/png/01-wave-hi.png trust --trust_anchors certs/chronral-c2pa-root.pem
```

> Using `--trust_anchors certs/chronral-c2pa-root.pem` returns `"validation_state": "Trusted"` with `"failure": []` (the DigiCert RFC 3161 timestamp digest validates cleanly; `timeStamp.untrusted` under `informational` only appears when no external TSA trust list is supplied). Public web verifiers without this root CA loaded will display `signingCredential.untrusted` while still validating author metadata, timestamps, and tamper-evident hashes.

## Usage & Attribution

Assets in this repository are AI-assisted fan-style sticker packs curated for personal and non-commercial use. See [USAGE.md](./USAGE.md) for full guidelines.
