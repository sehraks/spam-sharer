<br />
<div align="center">

  <h3 align="center">SPAM SHARER</h3>

  <p align="center">
    An advanced tool for efficient spam sharing.
    <br/>
    <a href="https://www.facebook.com/sehraks"><strong>DM me on Facebook for questions »</strong></a>
    <br/>
    <a href="https://github.com/sehraks/spam-sharer/issues"><strong>Or open an issue on GitHub »</strong></a>
    <br/>
    <br/>
  </p>
</div>

## Features

- **Advance Useragent**:
  - Utilizes `fake-useragent` to generate random user agents, helping to avoid detection by Meta platforms and ensuring seamless operation.

- **Accounts Management**:
  - Add and manage multiple accounts to maintain functionality even if a cookie gets restricted, providing flexibility and reliability.

- **Cookie String and Appstate (JSON) Supported**:
  - Add accounts using a cookie string or by importing an appstate JSON file.
  - **Cookie String Example**
    ```
    datr=xxxx; sb=xxxx; m_pixel_ratio=3; vpd=xxxx; x-referer=xxxx; ps_l=1; ps_n=1; wd=360x820; c_user=xxxx; xs=xxxx; fr=xxxx; locale=en_US; fbl_st=xxxx; wl_cbv=xxxx
    ```
  - **Appstate JSON Import**:
    - Place your appstate JSON file in `/storage/emulated/0/Spam-Sharer/private/appstate.json` to import it.

- **More Features Coming Soon**:
  - Stay tuned for additional enhancements and updates!

## Installation in Termux

Follow these steps to set up and run Spam-Sharer in Termux:

1. **Install Termux**:
   - Download Termux from the Google Play Store or F-Droid.

2. **Update Termux and Install Dependencies**:
   - Update the package manager and install Git and Python:
     ```bash
     pkg update && pkg upgrade
     pkg install git python
     ```

3. **Grant Storage Permissions**:
   - Allow Termux to access storage (required for saving account data):
     ```bash
     termux-setup-storage
     ```

4. **Clone the Repository**:
   - Clone the Spam-Sharer project to your current directory:
     ```bash
     git clone https://github.com/sehraks/spam-sharer.git
     ```

5. **Navigate to Project Directory and Install Python Dependencies**:
   - Change to the project directory and install required packages:
     ```bash
     cd spam-sharer
     pip install -r requirements.txt
     ```

6. **Run the Script**:
   - Start the Spam-Sharer tool:
     ```bash
     python3 main.py
     ```

## Usage

- On first run, select **Option 3 (Update)** to check for updates (required before other options).
- Use **Option 1 (Accounts Management)** to add accounts via cookie strings or appstate JSON.
- Use **Option 2 (Spam Share)** to perform sharing tasks.
- Select **Option 4 (Exit)** to close the tool.
- Account data is saved in the `storage/` directory and protected from updates.

## Notes

- **Run from Correct Directory**: Always run `python3 main.py` from the `spam-sharer` directory (`cd spam-sharer`).
- **Account Data**: Stored in `storage/accounts.json`, `storage/current_account.json`, and `storage/data/spam_sharing/data.json`, which are ignored by Git to prevent overwriting during updates.
- **Troubleshooting**:
  - If `pip install -r requirements.txt` fails, update pip:
    ```bash
    pip install --upgrade pip
    ```
  - If storage errors occur, re-run `termux-setup-storage` or check Android permissions for Termux.
  - If `.gitignore` is missing, manually create it:
    ```bash
    echo "storage/" > .gitignore
    ```
  - For other issues, open a GitHub issue or DM on Facebook.

## Requirements

See `requirements.txt` for dependencies:
- `rich>=13.7.1`
- `aiohttp>=3.9.5`
- `fake-useragent>=1.5.1`
