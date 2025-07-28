---
description: Setting up the Sapphire server and database
---

# Configuring

### Editing the configuration files&#x20;

1. Open the `Sapphire build\bin\config` folder;
2. Copy `global.ini.default` to `global.ini` and open your copy to personalize it;
3. Adjust the MySQL settings to match your MySQL server;
   * **Host** - the IP of the machine your MySQL server is running on. Default: `127.0.0.1`. If you have added a new user, make sure that the host entry on the new MySQL user replicates the host you're connecting to otherwise MySQL will not let you connect;
   * **Port** - the port that the MySQL server can be accessed on. Default: `3306`
   * **Database** - the database name for your Sapphire server. Default: `sapphire`
   * **Username** - the username for your MySQL server. Default: `root`
   * **Pass** - the password for your MySQL server. Use the password you set during MySQL Server installation. If you used a pre-packaged MySQL server, the default root password may be blank or vary.
4. Adjust the **DataPath** of the server's settings.xml to your FFXIV client's **game\sqpack** folder. Double backslashes are required.

{% hint style="danger" %}
Make sure that your path is set correctly to the **game\\\sqpack** folder inside the FFXIV client folder.

Example: `C:\\Program Files (x86)\\SquareEnix\\FINAL FANTASY XIV - A Realm Reborn\\game\\sqpack`)

Failing this step will cause the server to crash, alerting you of a DataPath error.
{% endhint %}

5. Adjust the **ZoneHost**, **LobbyHost**, and **RestHost** IP addresses if needed. For a local server for testing, keep these as `127.0.0.1`;
6. Adjust any other server-specific configuration in their appropriate sections as needed.

### Import the database

The DBM tool can be used to import and update your database for Sapphire. This tool can be located in your `Sapphire build\bin\tools` folder.

Use the DBM application with your terminal or command line to set up your database with the following command. Replace the command arguments with your MySQL configuration.

{% code overflow="wrap" %}
```bash
dbm --mode initialize --user <sql-username> --database <sql-database> --pass <sql-password>
```
{% endcode %}

{% hint style="success" %}
If you have completed all the steps above, then you have the minimum required to run the server. You may proceed to [Generate navmeshes](configuring.md#generating-navmeshes), or the [Running](running.md) page if you wish to ignore enemies in-game.
{% endhint %}

### Generating navmeshes

{% hint style="warning" %}
Make sure that you build nav\_export in release.&#x20;

You can do this by changing the `Debug` dropdown in Visual Studio or adding the following argument to your CMake command line: `-DCMAKE_BUILD_TYPE=RelWithDebInfo`.&#x20;

Not building nav\_export in release could take several hours to generate all the navmeshes instead of 5-10 minutes.
{% endhint %}

1. Go to the `Sapphire build\bin\tools` folder;
2. Use the nav\_export application to generate obj files with the following commands.
   * You will need to run this from a terminal or command line (cmd.exe, powershell, git bash, etc);
3. Provide the program with the path to your `FFXIV Client\game\sqpack\` folder.
4. Wait for meshes to be generated. You can transfer them to later builds as long as no new maps have been added to the game.

{% code overflow="wrap" %}
```bash
nav_export <path-to-ffxiv-client>\game\sqpack\
```
{% endcode %}

After you finish generating navmeshes, you may proceed to [Running](running.md) the server.

{% content-ref url="running.md" %}
[running.md](running.md)
{% endcontent-ref %}

### Updating the database

If you're updating sapphire to a new(er) version and not doing a clean setup, you may need to update the database to a newer version. This is unlikely to be a destructive action, but due to the nature of the project things may be lost. If you're concerned, feel free to ask.

You do not need to do this if you're doing a clean setup of Sapphire. If you are, this will be done for you during the previous step automatically.

{% code overflow="wrap" %}
```bash
dbm --mode migrate --user <sql-username> --database <sql-database> --pass <sql-password>
```
{% endcode %}

### Deleting the database

If, for some reason, you need to delete/wipe Sapphire data from your MySQL, the following command can be used. **Server data will be lost**.

{% code overflow="wrap" %}
```bash
dbm --mode liquidate --user <sql-username> --database <sql-database> --pass <sql-password> --force
```
{% endcode %}
