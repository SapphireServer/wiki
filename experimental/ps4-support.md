---
description: Experimental and temperal support for PS4 connections
---

# PS4 Support

{% hint style="danger" %}
Sapphire works on a PS4 out of the box. However, connecting to it is unsafe and bad and shouldn't be used for more than testing.
{% endhint %}

To use Sapphire with a PS4, you will need the following things:

* A fully set-up Sapphire Server (see [Getting Started](broken-reference));
* A PS4 with the matching FFXIV client version;
* A usable Square Enix service account;
* Python 2.6.

1.  Set the AllowNoSessionConnect parameter in the lobby configuration file to `true`;

    <figure><img src="https://camo.githubusercontent.com/9d487412ec848baec3debdbb60401c30b75317a4caf8788e7deb5dc4b59d493d/68747470733a2f2f692e696d6775722e636f6d2f574a6f7162745a2e706e67" alt=""><figcaption><p>Disaster</p></figcaption></figure>
2. Start your servers and run the `ps4dns.py` Python-Script in the `src/tools` folder;
3. Set the DNS Server on your PS4 to the local IP Address of your PC;
4. Log into the game on your PS4 - exit the lobby but do not quit the game;
5.  Copy the selected text that should be printed in the lobby console;

    <figure><img src="https://camo.githubusercontent.com/83e03a0b917252329f62b9cf65cfbe067eb5180fc58c678e792224563bc45a83/68747470733a2f2f692e696d6775722e636f6d2f736b77743352452e706e67" alt=""><figcaption></figcaption></figure>
6. Navigate to PS4transitionally.html in a browser which should be running on your REST server;
7. Enter the following information to the page:

![](https://camo.githubusercontent.com/5822ad4e2652f1bb911e327803da79338d6e9df66b1f625abd3c3a446f759a8e/68747470733a2f2f692e696d6775722e636f6d2f474d4c304a79362e706e67)

_Secret_ should be the secret set for REST in the server config - `default` as default.

_sId_ should be the text you just copied from your lobby server console.

_accountId_ should be the id of the already created sapphire account you want to use on your PS4;

8. Click `insert`, and change the Data Center on your PS4.

Done! You should now see your characters on the PS4 and be able to log in just fine.
