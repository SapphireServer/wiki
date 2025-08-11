---
description: Launching the server and client
---

# Running

### Running the server

{% hint style="warning" %}
Ensure that your Firewall is not blocking the necessary ports.

For Windows, ensure that you allow access to each of the servers when prompted by Windows Firewall.
{% endhint %}

1. Start your MySQL server if it is not running already;
2. Start `lobby`;
3. Start `api`;

{% hint style="info" %}
The API server requires Port 80 to function. Ensure no other programs are using this port such as Skype, Apache/httpd, etc.
{% endhint %}

4. Start `world`;

{% hint style="info" %}
On Windows with Hyper-V (WSL 2) you might run into an issue where high ports are reserved. If you see an error about binding to the port, run the following command to check if this is the case:

```bash
netsh int ip show excludedportrange protocol=tcp
```
{% endhint %}

5. Create a folder called "log" if it does not already exist. The servers **will** crash if your file permissions prevent creating this folder.

In case of crashes upon initializing the servers, please check if your FFXIV client version matches the version required by your chosen Sapphire server branch.

### Launching the client

Sapphire provides a standard launcher to launch the FFXIV client while configuring it to connect to Sapphire.

{% hint style="info" %}
The launcher has only been tested to work on Windows.&#x20;
{% endhint %}

{% hint style="info" %}
There are alternative launchers (not developed by the Sapphire team) that can be setup to work with Sapphire, if desired.&#x20;

We do not provide support for them.
{% endhint %}

1.  Open the Sapphire Launcher;&#x20;

    <figure><img src="https://camo.githubusercontent.com/f9a4cb29b48b20fe4a7297367e1228047b94bca5803dd05ef4a52f362c63f2b4/68747470733a2f2f692e696d6775722e636f6d2f757374444c39572e706e67" alt=""><figcaption></figcaption></figure>
2.  Click on the gear in the top right to configure the launcher;

    <figure><img src="https://camo.githubusercontent.com/40a5f090bbce5c3eeca53f9b9e3e8e125d8498e0f03385bf97cecd12d06c3db6/68747470733a2f2f692e696d6775722e636f6d2f384b4e417068692e706e67" alt=""><figcaption></figcaption></figure>
3. Enter the URL to connect to your REST server. Default: `http://localhost/login.html`. Press `Check availability` to confirm your URL works;
4. Navigate to your FFXIV client folder\game and select the ffxiv.exe for DirectX9 mode or ffxiv\_dx11.exe for DirectX11 mode;
5. Select your Expansion level and Language;
6.  You should be greeted by the Sapphire Login screen;

    ![](https://camo.githubusercontent.com/74d2985caaa4718da10251bd17a89e20732d0384c56e8e015f2521a36c68e191/68747470733a2f2f692e696d6775722e636f6d2f746a705a595a532e706e67)
7. Create an account if needed and login.

{% hint style="danger" %}
Your client **will crash if existing retail FFXIV data exists**.

Backup, rename or delete the following folder:

`Documents\My Games\FINAL FANTASY XIV - A Realm Reborn`
{% endhint %}
