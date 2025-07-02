<div align="center">

  <h1 align="center">SPAM SHARER</h1>
  <img src="https://img.shields.io/badge/Version-1.0-blue?style=flat" alt="Version" />

  <p align="center">
    A powerful, secure tool for advanced spam sharing on Meta platforms.
    <br />
    <br />
    <a href="https://www.facebook.com/100033379733340">
      <img src="https://img.shields.io/badge/Contact-Cerax-blue?style=flat&logo=facebook" alt="Facebook" />
    </a>
    <a href="#">
      <img src="https://img.shields.io/badge/Python-3.10+-yellow?style=flat&logo=python" alt="Python" />
    </a>

  <p align="center">
    <img src="https://github.com/sehraks/spam-sharer/raw/main/screenshots/screenshot1.jpg" alt="Accounts Management" width="45%" />
    <img src="https://github.com/sehraks/spam-sharer/raw/main/screenshots/screenshot2.jpg" alt="Spam Sharing Process" width="45%" />
  </p>

</div>

## Developer’s Note

The `Spam-Sharer` code is obfuscated to protect its internal logic and prevent unauthorized misuse or modification. I, Cerax, assure you that this tool is designed with user safety in mind.

- **No data is sent externally**: Cookies, appstate data, and personal information stay **local** in the `storage/` directory (e.g., `storage/accounts.json`, `storage/current_account.json`, `storage/data/spam_sharing/data.json`). These files are protected by `.gitignore` to ensure they remain on your device.
- **Offline operations**: Sensitive tasks like cookie handling are performed locally.
- **Clipboard functionality**: Features like copying cookies (via Termux:API) are entirely local.

## Features

- **Advanced User-Agent Rotation**  
  Uses `fake-useragent` to generate random user agents, evading detection on Meta platforms for smooth operation.

- **Seamless Account Management**  
  Add, switch, or manage multiple accounts to maintain functionality even if a cookie is restricted. Easily copy cookie strings to your clipboard (requires Termux:API).

- **Flexible Account Input**  
  Supports both **cookie strings** and **appstate JSON** imports:  
  - **Cookie String Example** (structure only):  
    ```
    datr=xxxx; sb=xxxx; m_pixel_ratio=3; vpd=xxxx; x-referer=xxxx; ps_l=1; ps_n=1; wd=360x820; c_user=xxxx; xs=xxxx; fr=xxxx; locale=en_US; fbl_st=xxxx; wl_cbv=xxxx
    ```  
  - **Appstate JSON Import**: Place your file in `/storage/emulated/0/Spam-Sharer/private/appstate.json`.

- **More to Come**  
  Exciting updates and features are in the pipeline—stay tuned!

## Installation in Termux

Get `Spam-Sharer` up and running in just a few steps:

1. **Install Termux and Termux:API**  
   Download **Termux** and **Termux:API** from the [Google Play Store](https://play.google.com/store/apps/details?id=com.termux) or [F-Droid](https://f-droid.org/packages/com.termux/).

2. **Update Termux and Install Dependencies**  
   ```bash
   pkg update && pkg upgrade
   pkg install git python termux-api
   ```

3. **Grant Storage Permissions**  
   Allow Termux to access storage for saving account data:  
   ```bash
   termux-setup-storage
   ```

4. **Clone the Repository**  
   ```bash
   git clone https://github.com/sehraks/spam-sharer.git
   ```

5. **Install Python Dependencies**  
   Navigate to the project directory and install required packages:  
   ```bash
   cd spam-sharer
   pip install -r requirements.txt
   ```

6. **Run the Script**  
   Launch `Spam-Sharer`:  
   ```bash
   python3 main.py
   ```

## Optional: Set Up a Shortcut

Run `Spam-Sharer` with a single `fbs` command from anywhere in Termux:

1. **Install `micro` Editor**  
   ```bash
   pkg install micro
   ```

2. **Edit `.bashrc`**  
   Open the `.bashrc` file:  
   ```bash
   micro ~/.bashrc
   ```  
   Add this line at the end:  
   ```bash
   alias fbs='cd ~/spam-sharer && python3 main.py'
   ```  
   Save (`Ctrl+S`) and exit (`Ctrl+Q`).

3. **Apply the Alias**  
   ```bash
   source ~/.bashrc
   ```

4. **Test the Shortcut**  
   Run `fbs` from any directory to start `Spam-Sharer`.

> **Note**: If `~/.bashrc` doesn’t exist, `micro` will create it. The `fbs` alias automatically navigates to the correct directory.

## Usage

- **First Run**: Select **Option 3 (Update)** to check for updates (required before other actions).
- **Account Management**: Use **Option 1** to add accounts via cookie strings or appstate JSON, or to copy/switch accounts.
- **Spam Sharing**: Use **Option 2** to start sharing tasks.
- **Exit**: Select **Option 4** to close the tool.
- **Data Storage**: Account data is securely stored in the `storage/` directory and protected from updates.

## Tips

- **Run Multiple Sessions**: Speed up tasks by swiping left in Termux to open new sessions and run multiple sharing tasks simultaneously!

## Notes

- **Correct Directory**: Run `python3 main.py` from the `spam-sharer` directory (`cd spam-sharer`), unless using the `fbs` alias.
- **Account Data**: Stored securely in `storage/` and protected by `.gitignore`.
- **Clipboard Feature**: Requires Termux:API (`pkg install termux-api`).
- **Troubleshooting**:  
  - **Pip issues**: Update pip with `pip install --upgrade pip`.  
  - **Storage errors**: Re-run `termux-setup-storage` or check Termux permissions in Android settings.  
  - **Missing `.gitignore`**: Create it manually:  
    ```bash
    echo "storage/" > .gitignore
    ```  
  - **Alias issues**: Verify `~/.bashrc` path and reload with `source ~/.bashrc`.  
  - For other issues, open a [GitHub issue](https://github.com/sehraks/spam-sharer/issues) or [DM on Facebook](https://www.facebook.com/100033379733340).

## Requirements

See `requirements.txt` for Python dependencies:  
- `rich>=13.7.1`  
- `aiohttp>=3.9.5`  
- `fake-useragent>=1.5.1`
