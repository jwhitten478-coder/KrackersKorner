# A26-X Pre-Rooted ROM Builder

This repository contains an improved build script and CI for creating a pre-rooted SM-A266V (A26 5G) ROM — "A26-X".

Important
- Backup your device and data before flashing.
- Rooting / modifying firmware can void warranty or violate carrier terms.
- Test in a VM or isolated environment before using on a real device.

Quickstart
1. Clone this repo:
   ```
   git clone https://github.com/<your-org-or-username>/KrackersKorner.git
   cd KrackersKorner
   ```
2. Create and switch to a branch (if not already):
   ```
   git checkout -b a26x-builder-add
   ```
3. Make sure the main toolset sits in `tools/` (the script will clone it automatically if missing).
4. Make the script executable:
   ```
   chmod +x build_a26x.sh
   ```
5. Run a dry run:
   ```
   ./build_a26x.sh --firmware path/to/firmware_a26.tar.md5 --dry-run
   ```
6. When ready, run the real build:
   ```
   ./build_a26x.sh --firmware path/to/firmware_a26.tar.md5
   ```

CI
- A simple GitHub Actions workflow runs shellcheck and a script dry-run on every PR.

Files added
- `build_a26x.sh` — robust build script with logging, dry-run, and safety checks
- `.github/workflows/ci.yml` — CI for static checks/dry-run
- `README.md` — usage and warnings

Contributing
- Add `--keep-work`/`--clean` flags if you want finer workspace control.
- Add checksum verification and signing for output zips.
- Add more device variant support as needed.

License & Disclaimer
- This repo does not provide legal disclaimers for your country/carrier. Use at your own risk. KrackersKorner
