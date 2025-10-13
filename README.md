# 🧰 ps-dev-tools

**Shell scripts to automate PrestaShop module and theme development & release workflows.**  
This repository provides a collection of lightweight tools to speed up common tasks — cleaning before release, generating ZIP archives, removing unnecessary dependencies, etc.

---

## 🚀 Installation

### Option 1 — Clone directly

```bash
git clone git@github.com:axel-paillaud/ps-dev-tools.git
cd ps-dev-tools
chmod +x bin/*
````

Run a script directly:

```bash
./bin/ps-module-build-zip my-module/
```

Or install the scripts globally:

```bash
sudo cp bin/* /usr/local/bin/
```

---

### Option 2 — Via Composer (recommended)

If your PrestaShop project uses Composer, simply add the package as a development dependency:

```bash
composer require --dev axel-paillaud/ps-dev-tools
```

You can then run the tools directly from your project:

```bash
vendor/bin/ps-module-build-zip
vendor/bin/clean-release-deps
```

Example:

```bash
vendor/bin/ps-module-build-zip path/to/module
```

---

## 🧩 Available scripts

| Script                | Description                                                                                    |
| --------------------- | ---------------------------------------------------------------------------------------------- |
| `module-build-zip` | Cleans a module (removes `.git`, `node_modules`, etc.) and creates a `.zip` ready for release.    |
| `theme-build-zip`  | Cleans a theme (removes `.git`, `node_modules`, etc.) and creates a `.zip` ready for release.     |
| *(coming soon)*       | Other handy tools for PrestaShop modules and themes.                                           |

---

## ⚙️ Example usage

```bash
module-build-zip modules/my-module
# or, if installed via composer
vendor/bin/module-build-zip modules/my-module
```

The script will create a `my-module.zip` file in the home directory, ready to insatll to your PrestaShop store.

---

## 🧼 Best practices

* Always run the scripts from your project root.
* Add `set -euo pipefail` at the top of new scripts for better error handling.
* Validate your scripts with [`shellcheck`](https://www.shellcheck.net/).

---

## 📦 Repository structure

```
ps-dev-tools/
├─ bin/                    # Executable Bash scripts
│  └─ module-build-zip
├─ composer.json           # Composer package definition
├─ README.md
└─ .github/workflows/ci.yml (optional)
```

---

## 🪪 License

MIT © Axel Paillaud
You are free to use, modify, and redistribute these scripts under the terms of the MIT License.

