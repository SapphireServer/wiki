---
description: Overview of Sapphire installation
---

# Overview

### Requirements

Sapphire has been tested to run on Linux (GCC, Clang), Mac and Windows.

{% hint style="info" %}
The only architecture we provide support for is x86-64. 32-bit builds and other architectures are not guaranteed to work.
{% endhint %}

### Downloading Sapphire

We do not provide downloadable binaries for Sapphire. In order to use Sapphire, you must compile the code in your machine.

The best way to get the code for Sapphire is to use `git`.

After a git clone, cd into the repository, checkout the branch you wish to target (default **master**) and initialise the library submodules.

{% hint style="info" %}
There are several branches available for multiple client versions.

`master`is the branch that targets Sapphire for FFXIV 3.3, and the version under active development.
{% endhint %}

{% code overflow="wrap" %}
```bash
$ git clone https://github.com/SapphireServer/Sapphire.git sapphire
$ cd sapphire
$ git submodule update --init
```
{% endcode %}

We advise against downloading the zip source code ("tarball") through the github page, as it will be missing dependencies **required** for building.

### Downloading Sapphire Launcher

Sapphire provides a standard launcher to launch the FFXIV client while configuring it to connect to Sapphire.

{% hint style="warning" %}
The launcher has only been tested to work on Windows.&#x20;
{% endhint %}

{% hint style="info" %}
There are alternative launchers (not developed by the Sapphire team) that can be setup to work with Sapphire, if desired.&#x20;

We do not provide support for them.
{% endhint %}

You may clone the Sapphire Launcher by running the following command. Make sure you are not running the command inside the Sapphire folder.

<pre class="language-bash" data-overflow="wrap"><code class="lang-bash"><strong>$ git clone https://github.com/SapphireServer/SapphireLauncher.git
</strong></code></pre>

### Install Dependencies

Sapphire requires CMake and a C++ compiler to build.&#x20;

Additionally, Sapphire makes use of several dependencies. The submodule initialization through git will provide most of them, however SQL development headers need to be provided separately.

### How to build

Instructions on how to build for each of the supported platforms can be found in the [Installation](installation/) page.
