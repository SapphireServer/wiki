---
description: Welcome to the Sapphire wiki!
---

# Welcome

<figure><img src=".gitbook/assets/sapphire_logo.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
This wiki is intended for the currently active branches in Sapphire that target FFXIV 3.x (Heavensward).

For instructions and support for deprecated branches (4.0\~5.58), consult the old [Sapphire Wiki](https://github.com/SapphireServer/Sapphire/wiki).
{% endhint %}

* [What is Sapphire?](./#what-is-sapphire)
* [Is it stable?](./#is-it-stable)
* [Is it secure?](./#is-it-secure)
* [Can I run my own server?](./#can-i-run-my-own-server)
* [How do I install it?](./#how-do-i-install-it)
* [How can I contribute?](./#how-can-i-contribute)
* [How can I get help?](./#how-can-i-get-help)
* [What client version do I need/how to get a working client?](./#what-client-version-do-i-need-how-do-i-get-a-working-client)

### What is Sapphire?

Sapphire is a research implementation of the Final Fantasy XIV Online server. The purpose of Sapphire is to gain an understanding of how the retail game servers work internally.

Our current development focus is in FFXIV 3.x (Heavensward), an older version of the game. We seek to replicate the game as it used to be, as the aspects of the game were very different.

As such, you will need a 3.3 client to use Sapphire's `master`, `ThreePointOh` or `ThreePointThree` branches. The free trial client will **NOT** work. We do not provide client files or how to obtain them. See [Welcome/Client Version](./#what-client-version-do-i-need-how-do-i-get-a-working-client) for more info.

### Is it stable?

**No**, Sapphire is currently under heavy development. Unexpected crashes, unimplemented or inconsistent features, and data corruption are known issues, and are to be expected.

### Is it secure?

**No**, Sapphire has minimal encryption and security features for the database. Make sure all account credentials you use are throwaways.

### Can I run my own server?

Yes, you can run Sapphire locally or on a hosted server, however be aware of the security and stability issues before you expose the server to anyone else.

{% hint style="info" %}
Many features are not yet implemented, so please don't think of Sapphire as a replacement for FFXIV retail.

We suggest playing the FFXIV trial for a retail experience.
{% endhint %}

### How do I install it?

{% hint style="danger" %}
If you are not familiar with C++ project compilation, it is **highly** recommended you do not attempt this without studying up on software development.

Understand that this may be a lengthy process, depending on familiarity with programming.
{% endhint %}

Sapphire must be compiled from source code, as we do not provide binaries.

Further instructions are provided in this wiki, starting from the [Overview ](getting-started/overview.md)page.

### How can I contribute?

Pull requests to Sapphire are welcome. Please see documentation on the sidebar to the right, as well as the [code contributors guide](https://github.com/SapphireServer/Sapphire/blob/master/CONTRIBUTING.md). Testing and debugging can also be of great help, so you don't need to know C++ to contribute. To get in touch, reach out to us on [Discord](https://discord.gg/xxcdCER).

### How can I get help?

For bug reports, please see [GitHub Issues](https://github.com/SapphireServer/Sapphire/issues). You can also discuss problems in the #troubleshooting-the-heavens channel on [Discord](https://discord.gg/xxcdCER).

### What client version do I need/How do I get a working client?

{% hint style="danger" %}
We are not allowed to distribute the FFXIV client or any related content. Please do not ask for links or binaries related to FFXIV or Square Enix copyrighted content.
{% endhint %}

Sapphire currently targets `3.x` as the main development target, and the client version is documented in the `README.md` in the repo root. This version may change time to time as the client version moves forward, and you should check that you're on the correct version before reporting issues.

The free trial version of the client **will NOT work with Sapphire**, as it is not a 3.3 client. It is simply the retail client version, but with restricted access up to Heavensward.

The server will also need to point to the same game data version otherwise you may encounter issues.

A list of patches can be seen in the [Patch list](resources/patch-list.md) page.
