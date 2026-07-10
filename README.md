# Tumbler

A client-side Solana wallet generator that runs entirely in your browser — no backend, no build step, no dependencies loaded at runtime. One self-contained HTML file.

Named after the pins inside a lock: the mechanism that has to line up exactly right to work.

## What it does

- **Generate New** — a fresh BIP39 seed phrase (12 or 24 words), standard Solana derivation path
- **Vanity Address** — search for an address that starts with letters you choose (e.g. `TUMB`)
- **From Private Key** — import an existing wallet from a base58 secret key
- **From Seed Phrase** — import an existing wallet from a seed phrase (validated against the full BIP39 checksum)
- **Bulk derivation** — generate 1 to 100,000 wallets from a single seed phrase (same BIP44 accounts Phantom creates when you tap "Add Wallet")
- **Optional password** — adds extra entropy to generation and unlocks an AES-256-GCM encrypted backup export (not a BIP39 passphrase — losing it never locks you out of the seed phrase itself)
- **Paper wallet** — printable backup view
- **CSV / JSON export** of derived wallets

## Security

This tool is for learning, testing, and prototyping — **not** for wallets that will hold real funds. It's unaudited code running in a browser tab, which has no secure element, no independent review, and no protection against a compromised device. For anything real, use official wallet software (Phantom, Solflare) or a hardware wallet.

Read the in-app warning before generating anything. The code is intentionally kept in one plain, readable file so you (or anyone) can verify exactly what it does — recommended before trusting it with anything, even for testing.

## Running it

No install, no server required:

- Open `solana-wallet-generator-offline.html` directly in a browser, **or**
- Serve it via GitHub Pages / any static host and install it to your phone's home screen as an app (Chrome → ⋮ menu → "Install app")

Works fully offline once loaded — this page makes zero network requests.

## Tech

- Solana derivation: BIP44 + SLIP-0010 (ed25519), path `m/44'/501'/i'/0'`
- Pure vanilla JS, no build tooling, no external libraries
- Content-Security-Policy locked down (`connect-src: none`) so the page can never phone home, even accidentally

## License

MIT — do whatever you want with it, no warranty.

https://lion89-a1.github.io/tumbler-wallet-generator/solana-wallet-generator-offline.html
