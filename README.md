<h1 align="center">SPAM SHARER</h1>

<p align="center">
  A powerful, secure tool for advanced spam sharing on Facebook platform using Termux.
  <br />
  <br />
  <a href="https://t.me/sehraks">
    <img src="https://img.shields.io/badge/Contact-Cerax-24A1DE?style=flat-square&cacheSeconds=3600&logo=telegram&logoColor=white" alt="Telegram Contact Badge" />
  </a>
  <img src="https://img.shields.io/badge/Python-3.10+-FFD43B?style=flat-square&cacheSeconds=3600&logo=python&logoColor=white" alt="Python" />
  <a href="https://cerax.pages.dev">
    <img src="https://img.shields.io/badge/About%20the%20Developer-Site-4CAF50?style=flat-square&cacheSeconds=3600&logo=globe&logoColor=white" alt="About the Developer" />
  </a>
  <a href="https://github.com/sehraks/spam-sharer/blob/main/changelogs.md">
    <img src="https://img.shields.io/badge/Version-1.9-808080?style=flat-square&cacheSeconds=3600&logo=info&logoColor=white" alt="Version" />
  </a>
  <a href="https://github.com/sehraks/spam-sharer/blob/main/changelogs.md">
    <img src="https://img.shields.io/badge/Changelog-View%20Changes-00A1D6?style=flat-square&cacheSeconds=3600&logo=book&logoColor=white" alt="Changelog" />
  </a>
</p>

<p align="center">
  <img src="https://github.com/sehraks/spam-sharer/raw/main/screenshots/screenshot1.jpg" alt="Accounts Management" width="45%" />
  <img src="https://github.com/sehraks/spam-sharer/raw/main/screenshots/screenshot2.jpg" alt="Spam Sharing Process" width="45%" />
</p>

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
  - **Appstate JSON Import**: Paste your JSON in `/storage/emulated/0/Spam-Sharer/private/appstate.json`.

- **Multiple Supported URLs**  
  Seamlessly supports a variety of URLs, including video links, group posts, and other shareable content for versatile sharing.

- **Network Error Handling**  
  Automatically pauses and resumes sharing during connectivity issues, ensuring robust operation.

- **Spam Restriction Detection**  
  Detects account restrictions, stops sharing, saves progress, and suggests switching accounts with recovery advice.

- **Batch Processing**  
  Shares posts in configurable batches with random delay ranges for efficient and stealthy operation.

- **Resume Functionality**  
  Saves progress to `storage/data/spam_sharing/resume/{content_type}_{content_id}.json` when interrupted by Ctrl+C or spam restrictions, allowing resumption of posts or videos. Resume files are automatically deleted upon successful completion.

- **Enhanced UI**  
  Features masked post links, cyan-colored delay messages, streamlined resume prompt matching input style, and detailed results panel with network issue tracking and resume status.

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

> [!NOTE]
> If `~/.bashrc` doesn’t exist, `micro` will create it. The `fbs` alias automatically navigates to the correct directory.

## Usage

- **First Run**: Select **Option 3 (Update)** to check for updates. This is required before performing other actions to ensure the tool is up-to-date.
- **Account Management**: Use **Option 1** to:
  - Add accounts via cookie strings or appstate JSON imports (located at `/storage/emulated/0/Spam-Sharer/private/appstate.json`).
  - Copy cookie strings to your clipboard (requires Termux:API).
  - Switch between multiple accounts for seamless operation.
- **Spam Sharing**: Use **Option 2** to start sharing tasks:
 1. **Enter Post URL**: Input a valid Facebook post URL (e.g., regular posts, video links, or group posts).
 2. **Specify Total Shares**: Enter the total number of shares to perform.
 3. **Set Shares per Batch**: Define how many shares to process simultaneously in each batch (recommended: 3-5 for stealth).
 4. **Set Delay Range**: Input minimum and maximum delay (in seconds) for random pauses between batches to enhance stealth.
5. **Confirm Configuration**: Review the summary (including masked post link for readability) and confirm to start sharing.
 6. **Monitor Progress**: View real-time batch progress, network issue notifications, and spam restriction alerts. The tool pauses and resumes automatically during connectivity issues.
 7. **View Results**: Check the results panel for total successful shares, batches completed, total time, network issues detected, and success rate.
- **Exit**: Select **Option 4** to close the tool safely.
- **Data Storage**: Account data and share tracking are securely stored in the `storage/` directory and protected from updates.

## Force reclone the `Spam-Sharer`

Reclone the project if ever the `Spam-Sharer` local files gets corrupted.

Copy this bash and paste it into your Termux:

```bash
# Make sure first you are in the home directory
cd $home

# Remove the entire local project
rm -rf ~/spam-sharer

# Clone a fresh copy
git clone https://github.com/sehraks/spam-sharer.git ~/spam-sharer

# Go to the project
cd ~/spam-sharer
```
> [!CAUTION]  
> Recloning the repository will delete all of your local `spam-sharer` files, including important files like `storage/accounts.json` and `storage/current_account.json`.  
>  
> If you have multiple cookies stored in `accounts.json`, all of them will be lost. Consider using this option carefully.  
>  
> If you are not experiencing major issues, use the **inbuilt updater** within the app instead — it will fetch new features, bug fixes, and minor changes from the remote version without deleting your `spam-sharer` local files.

> [!IMPORTANT]
> **Use this when**:
> - The local project is corrupted or misconfigured.
> - You want a fully clean start.
> - The .git folder or remote config is broken.

> [!NOTE]  
> Sometimes, even if you reclone it, it may not work if the repository does not have any new commits. Please wait for the developer to push an update, or check this GitHub repository for newly added commits.

## Guidelines

> [!TIP]
> **Acquire Wake Lock**: Run `termux-wake-lock` before starting long-running tasks like spam sharing. This keeps the CPU awake, preventing Android from killing the Termux process, which ensures progress is saved reliably even if the app is swiped out or runs in the background.

> [!TIP]
> **Run Multiple Sessions**: Speed up tasks by swiping left in Termux to open new sessions and run multiple sharing tasks simultaneously!

> [!IMPORTANT]
> **Clipboard Feature**: Requires Termux:API
> 
> If not installed yet: `pkg install termux-api`
 
> [!NOTE]
> **Troubleshooting**
> 
> **Pip issues**: Update pip with `pip install --upgrade pip`.
> 
> **Storage errors**: Re-run `termux-setup-storage` or check Termux permissions in Android settings.
> 
> **Missing `.gitignore`**: Create it manually:
```bash echo "storage/" > .gitignore ```
> 
> **Alias issues**: Verify `~/.bashrc` path and reload with `source ~/.bashrc`.

## For other issues

Open a [GitHub issue](https://github.com/sehraks/spam-sharer/issues) or [Message me on Telegram](https://t.me/sehraks).

## Requirements

See `requirements.txt` for Python dependencies:  
- `rich>=13.7.1`  
- `aiohttp>=3.9.5`  
- `fake-useragent>=1.5.1`
