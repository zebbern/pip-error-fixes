### `Error Fixes` & `Cheet Sheet` for `Pip`

> [!Note]
> - **Try multiple of the fixes under!**
> 
> - **Sometimes its only 1 way to install the `pip-lib` Your trying to get**
---
## Fix 1 ➠ ![Linux|MacOS|Windows](https://img.shields.io/badge/Linux|MacOS|Windows-Fix-black)
  - **[Activate Virtual Environment Before Installing Pip Libs](#virtual-environment-activate)**
  - **Activating a `virtual env` usually fixes Most `pip install errors`**
  - **If that does not work look for your issue under!**
    
---

##   [Windows Fixes](#windows11) ➠ ![Windows](https://img.shields.io/badge/Windows-Fixes-blue)
- **If [Activate Virtual Environment](#virtual-environment-activate) did not work you can try these:**
  
   - [ModuleNotFoundError](#modulenotfounderror)
   - [ERROR: Could not install packages due to an EnvironmentError](#error-could-not-install-packages-due-to-an-environmenterror)
   - [ERROR: Command errored out with exit status 1](#error-command-errored-out-with-exit-status-1)
   - [ERROR: pip is configured with locations that require TLS/SSL](#error-pip-is-configured-with-locations-that-require-tlsssl)
   - [SSL Certificate Verification Error](#ssl-certificate-verification-error)
   - [UnicodeDecodeError](#unicodedecodeerror)
   - [error: Microsoft Visual C++ 14.0 or greater is required](#error-microsoft-visual-c-140-or-greater-is-required)
   - [pip freeze` not displaying packages](#pip-freeze-not-displaying-packages)
   - [break system packages error windows](#break-system-packages-error-windows)

---

##   [Linux/macOS Fixes](#linux12) ➠ ![Linux|MacOS](https://img.shields.io/badge/Linux|MacOS-Fixes-black)
- **If [Activate Virtual Environment](#virtual-environment-activate) did not work you can try these:**
  
   - [ModuleNotFoundError](#modulenotfounderror-1)
   - [ERROR: Could not install packages due to an EnvironmentError](#error-could-not-install-packages-due-to-an-environmenterror-1)
   - [ERROR: Command errored out with exit status 1](#error-command-errored-out-with-exit-status-1-1)
   - [ERROR: pip is configured with locations that require TLS/SSL](#error-pip-is-configured-with-locations-that-require-tlsssl-1)
   - [SSL Certificate Verification Error](#ssl-certificate-verification-error-1)
   - [UnicodeDecodeError](#unicodedecodeerror-1)
   - [`fatal error: Python.h: No such file or directory](#fatal-error-pythonh-no-such-file-or-directory)
   - [pip freeze not displaying packages](#pip-freeze-not-displaying-packages-1)
   - [break system packages error linux](#break-system-packages-error-linux)

---

## [Pip Tips](#piptips) ➠ ![Linux|MacOS|Windows](https://img.shields.io/badge/Linux|MacOS|Windows-Fix-black)
- **Recommended to always [Activate Virtual Environment](#virtual-environment-activate) before installing any pip libs!**

   - [Upgrade pip](#upgrade-pip)
   - [Check pip version](#check-pip-version)
   - [Install a package](#install-a-package)
   - [Install from requirements.txt](#install-from-requirementstxt)
   - [Clear pip cache](#clear-pip-cache)
   - [Resolve dependency conflicts](#resolve-dependency-conflicts)
   - [List installed packages](#list-installed-packages)
   - [Freeze installed packages into a file](#freeze-installed-packages-into-a-file)
   - [Uninstall a package](#uninstall-a-package)
   - [Allow breaking system packages](#allow-breaking-system-packages)
   - [Downgrade pip or packages](#downgrade-pip-or-packages)
   - [Install from GitHub](#install-from-github)
   - [Check dependencies with pipdeptree](#check-dependencies-with-pipdeptree)
   - [Autoremove unused packages](#autoremove-unused-packages)

---

## Virtual Environment Activate

#### Linux/macOS
```bash
python3 -m venv venv && source venv/bin/activate
```

#### Windows
```bash
python -m venv venv && .\venv\Scripts\activate
```

#### Common Error: "Virtual environment not activating"
Ensure you have the necessary permissions and correct Python version installed. On Linux/macOS, check the shell configuration:
```bash
chmod +x venv/bin/activate
source venv/bin/activate
```
On Windows:
```bash
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

---

<div align="center" 

<a name="windows11"></a>

![Windows](https://github.com/user-attachments/assets/9b7231bf-ab64-41de-819c-ead7f17f58b6)

</div>

---

#### `ModuleNotFoundError`
```bash
python -m pip install --upgrade --force-reinstall <package_name>
```

#### `ERROR: Could not install packages due to an EnvironmentError`
```bash
pip install --user <package_name>
```

#### `ERROR: Command errored out with exit status 1`
```bash
pip install --no-cache-dir <package_name>
```

#### `ERROR: pip is configured with locations that require TLS/SSL`
```bash
pip install <package_name> --trusted-host pypi.org --trusted-host files.pythonhosted.org
```

#### SSL Certificate Verification Error
```bash
pip install <package_name> --trusted-host pypi.org --trusted-host files.pythonhosted.org
```

#### UnicodeDecodeError
```bash
set PYTHONUTF8=1
```

#### `error: Microsoft Visual C++ 14.0 or greater is required`
- Install [Build Tools for Visual Studio](https://visualstudio.microsoft.com/visual-cpp-build-tools/).

#### `pip freeze` not displaying packages
Ensure you are in the correct virtual environment:
```bash
pip list
pip freeze > requirements.txt
```

#### `break system packages error windows`
When encountering this error, explicitly allow breaking system packages:
```bash
pip install <package_name> --break-system-packages
```

#### Downgrade pip or packages
If upgrading causes compatibility issues:
```bash
pip install pip==<specific_version>
```
```bash
pip install <package_name>==<specific_version>
```

---

<div align="center" 

<a name="linux12"></a>


![linux-macos](https://github.com/user-attachments/assets/6707e68e-0b44-4ecc-8ae8-7b34c159eae0)

</div>

#### `ModuleNotFoundError`
```bash
python3 -m pip install --upgrade --force-reinstall <package_name>
```

#### `ERROR: Could not install packages due to an EnvironmentError`
```bash
pip install --user <package_name>
```

#### `ERROR: Command errored out with exit status 1`
```bash
pip install --no-cache-dir <package_name>
```

#### `ERROR: pip is configured with locations that require TLS/SSL`
```bash
pip install <package_name> --trusted-host pypi.org --trusted-host files.pythonhosted.org
```

#### SSL Certificate Verification Error
```bash
pip install <package_name> --trusted-host pypi.org --trusted-host files.pythonhosted.org
```

#### UnicodeDecodeError
```bash
export PYTHONUTF8=1
```

#### `fatal error: Python.h: No such file or directory`
```bash
sudo apt-get install python3-dev    # Ubuntu/Debian
sudo yum install python3-devel      # CentOS/Red Hat
```

#### `pip freeze` not displaying packages
Ensure you are in the correct virtual environment:
```bash
pip list
pip freeze > requirements.txt
```

#### `break system packages error linux`
When encountering this error, explicitly allow breaking system packages:
```bash
pip install <package_name> --break-system-packages
```

---

<div align="center" 

<a name="piptips"></a>

![pip-tips](https://github.com/user-attachments/assets/dda60b27-239a-4fee-b440-9b349b77cadd)

</div>

#### Upgrade pip
```bash
python3 -m pip install --upgrade pip
```

#### Check pip version
```bash
pip --version
```

#### Install a package
```bash
pip install <package_name>
```

#### Install from `requirements.txt`
```bash
pip install -r requirements.txt
```

#### Clear pip cache
```bash
pip cache purge
```

#### Resolve dependency conflicts
```bash
pip install <package_name> --use-deprecated=legacy-resolver
```

#### List installed packages
```bash
pip list
```

#### Freeze installed packages into a file
```bash
pip freeze > requirements.txt
```

#### Uninstall a package
```bash
pip uninstall <package_name>
```

#### Allow breaking system packages
```bash
pip install <package_name> --break-system-packages
```

#### Downgrade pip or packages
```bash
pip install pip==<specific_version>
```
```bash
pip install <package_name>==<specific_version>
```

#### Install from GitHub
Install a package directly from a GitHub repository:
```bash
pip install git+https://github.com/<user>/<repo>.git
```

#### Check dependencies with pipdeptree
Generate a dependency tree to debug conflicts:
```bash
pip install pipdeptree
pipdeptree
```

#### Autoremove unused packages
Clean up unused dependencies:
```bash
pip install pip-autoremove
pip-autoremove <package_name>
```

---

Feel free to contribute or open an issue if new errors arise!
