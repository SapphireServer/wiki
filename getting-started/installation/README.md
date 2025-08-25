---
description: Building and installing Sapphire
---

# Installation

We provide installation guides for multiple platforms.

Follow the guide to your platform as desired. Make sure you follow all the instructions as close as possible.

* [Windows](./#windows)
* [Linux](./#linux)
* [MacOS](./#macos)

## Windows

{% hint style="info" %}
#### Windows Linux Subsystem (WSL)

If you are using WSL:

Sapphire will also operate correctly (save for unforeseen issues) within the WSL and is actively tested in this environment.

While setup will not be covered in this guide, please note that it does work and you may prefer to use this environment for development over the standard Windows development environment. You can refer to the [Linux Installation Guide](./#linux) as the steps are the same regardless of where your Linux installation is hosted.

**CLion** may be used as a substitute over Visual Studio, as it has a very stable integration for WSL which may be preferable.
{% endhint %}

### Prerequisites

* [Visual Studio 2022](https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community\&rel=17) (Older versions may not work);
* [MariaDB 10.x](https://downloads.mariadb.org/) **(64-Bit required)**;
  * Alternatively, Oracle MySQL 5.7 (not newer) will also work, however MariaDB is hugely preferred over it.
* [Git](https://git-scm.com/download/win) or a graphical Git client like [GitKraken](https://www.gitkraken.com);
* Sapphire source code, as obtained via git clone (see [Overview](../overview.md#building-sapphire));
* Sapphire Launcher source code (optional);
* MySQL client (optional) ie. [HeidiSQL](https://www.heidisql.com/download.php) (included with MariaDB);

### Setup Development Environment

**Install MariaDB or MySQL 5.7**

{% hint style="warning" %}
We really recommend to install MariaDB (64-Bit) and avoid the hassle that is Oracle MySQL's awful installer and hidden packages.
{% endhint %}

1. Download MariaDB 10.x installer (x64 MSI);
2. Proceed through installation. Make sure you note down any settings you change;
   *   If you only need development headers and libraries, you can deselect everything else;

       ![](https://camo.githubusercontent.com/b606c91945957e04e69eaed2469e3fc55dd694bfcba74cd7aaf68e1633a95730/68747470733a2f2f692e696d6775722e636f6d2f387564575773422e706e67)

       **NOTE**: The architecture matters! Please install 64-bit Database Server, and compile Sapphire for x64. 32-bit support has been dropped.

       <figure><img src="https://camo.githubusercontent.com/30f6033d7e668372d5de80c880c5cb160aeabe830d5ef76dd122217ba083a209/68747470733a2f2f692e696d6775722e636f6d2f45575553464c772e706e67" alt=""><figcaption></figcaption></figure>
3. Wait for the installation to complete.
   * If you installed a server, you will be guided through setup.
   * If you only installed development headers and libraries, you can cancel out of product configuration.

**Installing Visual Studio 2022 with C++ and C# support**

1.  Download the Visual Studio 2022 installer and open it.

    ![](https://camo.githubusercontent.com/18ca5d9aaf0a1269cec9f5da0e32295ca7fee81e8db50a8befb441fede3316d5/68747470733a2f2f692e696d6775722e636f6d2f7671774c36416a2e706e67)
2. Run the installer selecting the .Net Desktop development and Desktop development with C++ options.
3.  Make sure you have the latest version of VS2022 and the MSVC v143 - VS 2022 C++ x64/x86 build tools package on the right. It should be selected by default;

    ![](https://camo.githubusercontent.com/248309f30c041aa2ad0a84125976c1b535883e23720ddb7397a8eaee8c1d5ca6/68747470733a2f2f692e696d6775722e636f6d2f4c4c59565967562e706e67)
4.  Switch to Individual components. You'll need to also select NuGet for installation. Select any additional features as needed. You can always add them later;

    ![](https://camo.githubusercontent.com/967dc2378ba4c505f727efd27b7fa124f67d799afc591f97fef11f9491de2594/68747470733a2f2f692e696d6775722e636f6d2f5a6635457a734f2e706e67)
5. Wait for the installation to complete. You will be prompted to restart your computer. ​

#### Build the Server project

1. Open Visual Studio 2022;
2. Using the "Open Folder" file option, browse to the Sapphire source code folder. The project should open and CMake will begin generating a cache automatically;

{% hint style="info" %}
If you're using CMake externally, open the generated SLN file instead.
{% endhint %}

3. If a CMake cache was not generated, select a Build Configuration.
   * Your MySQL installation will need to match your Build Configuruation. (Make sure you install **64 bit** versions.)

{% hint style="info" %}
You may change the desired build output folder by editing the CMakeSettings.json file in the project folder.
{% endhint %}

3. Build the solution. Depending on how your Visual Studio is configured, you can build by: `Build` menu > `Build All` Right-click the CMakeLists.txt file and select `Build`;
4. Files will be generated according to the buildRoot path specified in your CMakeSettings.json file. By default this is **%userprofile%\CMakeBuild**{hash}\build{build configuration}. The full path assuming a default installation of Windows 7 or later is `C:\Users\[your username here]\CMakeBuild`.

#### Build the Launcher project

1. Open the `Sapphire Launcher` source folder;
2. Open the `SapphireBootWPF.sln` solution file;
3.  Right-click the Solution and select `Restore NuGet Packages`;

    ![Launcher Restore NuGet](https://camo.githubusercontent.com/49c420ce73ce9ee4cbc1a6c61fb92d0d24913e34fed06daec3864ea591d78e3d/68747470733a2f2f692e696d6775722e636f6d2f7269796e38464a2e706e67)
4. Set your build target. The defaults are `Debug` and `Win32`;
5. Build the launcher;
6. You can find the launcher executable files in `Sapphire launcher`\bin\[`x86`/`x64`]\\\[`Debug`/`Release`] accordingly.

If you have successfully built all the projects required, you may proceed to configuring the server.

{% content-ref url="../configuring.md" %}
[configuring.md](../configuring.md)
{% endcontent-ref %}

## Linux

{% hint style="danger" %}
We currently do not provide a Linux version of our Sapphire launcher.
{% endhint %}

### Setup

You will need to install build and runtime dependencies before compiling, please see below for your specific distribution.

{% hint style="warning" %}
Care must be taken when considering versioning for libraries, especially in rolling release distros such as Arch Linux.

Make sure you're targeting the correct version.
{% endhint %}

{% tabs %}
{% tab title="Debian/Ubuntu" %}
If you don't already have a development environment setup, run the following:

```bash
$ sudo apt install -y build-essential
```

Install development headers and tools:

```bash
$ sudo apt install cmake git libmariadb-dev zlib1g-dev mariadb-client xorg-dev
```

After installing all dependencies, you can proceed building.
{% endtab %}

{% tab title="Arch Linux" %}
If you don't already have a development environment setup, run the following:

```bash
$ pacman -Sy --needed base-devel
```

Install development headers and tools:

```bash
$ pacman -Sy cmake git libmariadbclient
```

After installing all dependencies, you can proceed building.
{% endtab %}

{% tab title="CentOS/Fedora" %}
If you don't already have a development environment setup, run the following:

```bash
$ yum groupinstall -y development
```

Install development headers and tools:

```bash
$ yum install -y cmake git libmariadb-devel zlib-devel MariaDB-client
```

After installing all dependencies, you can proceed building.
{% endtab %}
{% endtabs %}

### Build

Locate and open the folder in which you cloned the Sapphire server through the terminal.

```bash
$ cmake -B build -DCMAKE_BUILD_TYPE=RelWithDebInfo
$ cmake --build build -j
```

{% hint style="info" %}
In a headless environment (server/WSL) you can disable the toolkit GUI with `cmake -B build -DSAPPHIRE_BUILDTOOLKIT=OFF`. The toolkit depends on GLFW and you need the development packages for Wayland/X11 installed on your system. To use Wayland instead of X11 specify `-DGLFW_USE_WAYLAND=ON`.
{% endhint %}

If you have successfully built all the projects required, you may proceed to configuring the server.

{% content-ref url="../configuring.md" %}
[configuring.md](../configuring.md)
{% endcontent-ref %}

## MacOS

### Setup

You will need to install build and runtime dependencies before compiling.

{% code overflow="wrap" %}
```bash
$ brew install cmake git mariadb zlib
```
{% endcode %}

### Build

Locate and open the folder in which you cloned the Sapphire server through the terminal.

```bash
$ cmake -B build -DCMAKE_BUILD_TYPE=RelWithDebInfo
$ cmake --build build -j
```

### Starting the MariaDB server

It is recommended that you start up the MySQL server manually to configure the database.

```bash
# Start the service
$ brew services start mariadb
# Secure the database
$ sudo mariadb-secure-installation
```

{% hint style="warning" %}
MySQL is **not supported** with Sapphire on MacOS (the development headers changed too much). If you installed MySQL in the past, you might need to remove it and run the following commands to delete all the data:

```sh
# Delete configuration
$ rm -rf /opt/homebrew/etc/my.cnf*
# Delete databases
$ rm -rf /opt/homebrew/var/mysql
```
{% endhint %}

If you have successfully built all the projects required, you may proceed to configuring the server.

{% content-ref url="../configuring.md" %}
[configuring.md](../configuring.md)
{% endcontent-ref %}
