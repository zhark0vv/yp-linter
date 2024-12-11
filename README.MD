
# Instructions for Setting Up and Running Linters with Task

This guide will help you install Task, set up a package manager, and run linters for your Go project.

---

## 0. Clone the Repository

Clone the repository to your local machine and copy the configuration files to your project directory:
```bash
git clone https://github.com/zhark0vv/yp-linter.git
OR 
git@github.com:zhark0vv/yp-linter.git

cd yp-linter
cp .golangci.yml ~/YourProj.golangci.yml
cp Taskfile.yml ~/YourProj.Taskfile.yml
```
## 1. Install a Package Manager

### macOS:
Ensure [Homebrew](https://brew.sh/) is installed:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Verify the installation:
```bash
brew --version
```

### Windows:
Ensure [Chocolatey](https://chocolatey.org/install) is installed:

Run this command in an elevated PowerShell terminal:
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

Verify the installation:
```powershell
choco --version
```

---

## 2. Install Task

Task is a simple task runner for managing project commands. Follow the steps below to install Task on your system:

### macOS/Linux:
Install Task using Homebrew:
```bash
brew install go-task/tap/go-task
```

### Windows:
Install Task using Chocolatey:
```powershell
choco install task
```

For more installation methods, refer to the [Task installation documentation](https://taskfile.dev/#/installation).

---

## 3. Install `golangci-lint`

With Task installed, run the following command to install `golangci-lint`:
```bash
task install-linter
```

This command uses the `Taskfile.yml` to install `golangci-lint` based on your operating system.

### Troubleshooting
- **macOS**: Ensure Homebrew is installed if the task fails.
- **Windows**: Ensure Chocolatey is installed if the task fails.
- **Linux**: Refer to the [official golangci-lint installation guide](https://golangci-lint.run/usage/install/#install-from-linux-packages) for manual installation options.

---

## 4. Run Linters

Once `golangci-lint` is installed, you can run the linter using:
```bash
task lint
```

This command will check your Go project for issues using the configuration specified in `.golangci.yml`.

---

### References
- [Task Documentation](https://taskfile.dev/)
- [GolangCI-Lint Installation](https://golangci-lint.run/welcome/install/)
- [Homebrew](https://brew.sh/)
- [Chocolatey](https://chocolatey.org/)
