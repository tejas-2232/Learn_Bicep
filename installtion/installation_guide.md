
## Azure CLI

* When you use Azure CLI with Bicep, you have everything you need to deploy and decompile Bicep files. 
* Azure CLI automatically installs the Bicep CLI when a command is executed that needs it.

* You must have Azure CLI version 2.20.0 or later installed.

__To verify your current version, run:__
```
az --version
```

__To validate your Bicep CLI installation, use:__
```
az bicep version
```

__To upgrade to the latest version, use:__

```bash
az bicep upgrade
```


## Installation for apt(debian,ubuntu)

|Distribution|Version|
|---|---|
|Ubuntu|	18.04 LTS (Bionic Beaver), 20.04 LTS (Focal Fossa), 22.04 (Jammy Jellyfish)|
|Debian|10 (Buster), 11 (Bullseye)|


__Option 1: Install with one command__

```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

__Option 2: Step-by-step installation instructions__

* If you prefer a step-by-step installation process, complete the following steps to install the Azure CLI.

1. Get packages needed for the install process:

```Bash
sudo apt-get update
sudo apt-get install ca-certificates curl apt-transport-https lsb-release gnupg
```

2. Download and install the Microsoft signing key:

```bash
curl -sL https://packages.microsoft.com/keys/microsoft.asc |
    gpg --dearmor |
    sudo tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null
```

3. Add the Azure CLI software repository:

```bash
AZ_REPO=$(lsb_release -cs)
echo "deb [arch=`dpkg --print-architecture`] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" |
    sudo tee /etc/apt/sources.list.d/azure-cli.list
```

4. Update repository information and install the azure-cli package:

```bash
sudo apt-get update
sudo apt-get install azure-cli
```

__Install specific version__

* You must first configure azure-cli repository information as shown above.

1. To view available versions with command:

```bash
apt-cache policy azure-cli
```

2. To install specific version:

```bash
sudo apt-get install azure-cli=<version>-1~bullseye
```


## Installation for dnf(RHEL,centOS)

__Install__

1. Import the Microsoft repository key.

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```

2. For RHEL 9 or CentOS Stream 9, add `packages-microsoft-com-prod` repository:

```bash
sudo dnf install -y https://packages.microsoft.com/config/rhel/9.0/packages-microsoft-prod.rpm
```

For RHEL 8 or CentOS Stream 8, add `packages-microsoft-com-prod` repository:
```bash
sudo dnf install -y https://packages.microsoft.com/config/rhel/8/packages-microsoft-prod.rpm
```

For RHEL 7 or CentOS 7, add `azure-cli` repository:
```bash
echo -e "[azure-cli]
name=Azure CLI
baseurl=https://packages.microsoft.com/yumrepos/azure-cli
enabled=1
gpgcheck=1
gpgkey=https://packages.microsoft.com/keys/microsoft.asc" | sudo tee /etc/yum.repos.d/azure-cli.repo
```

3. Install with the dnf install command.

```bash
sudo dnf install azure-cli
```


# For windows Installation of azure CLI please refer this [LINK](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli)
