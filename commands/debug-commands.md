# Debug Commands

Debug commands are custom commands that exist in Sapphire to easily manipulate the server and player.

### !\<command>

| Name            | Usage                       | Details                                                      |
| --------------- | --------------------------- | ------------------------------------------------------------ |
| `help`          | `!help`                     | Shows registered commands for your GM Level and what they do |
| `info`          | `!info`                     | Shows server info                                            |
| `inject`        | `!inject <file name>`       | Injects a premade packet to the calling character            |
| `injectc`       | `!injectc <file name>`      | Injects a premade chat packet to the calling character       |
| `nudge`         | `!nudge <Amount> {Up/Down}` | Moves you forward or Up/Down by a specified amount           |
| `unlock`        | `!unlock`                   | Empties out State Flags                                      |
| `script_reload` | `!script_reload`            | Force reload all server scripts                              |

### !set \<command>

| Name              | Usage                                       | Details                                                                                      |
| ----------------- | ------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `cfpenalty`       | `!set cfpenalty <time>`                     | Sets a Duty Finder penalty (in minutes)                                                      |
| `classjob`        | `!set classjob <Class/JobID>`               | Changes your Class/Job to specified ID. See [Class/Job List](../resources/class-job-list.md) |
| `discovery`       | `!set discovery <ZoneID> <DiscoverID>`      | Unlocks the discovery point entered                                                          |
| `discovery_reset` | `!set discovery_reset`                      | Resets all Discover Points                                                                   |
| `festival`        | `!set festival <festivalID> <additionalID>` | Sets the current festival to the ID entered                                                  |
| `festivaldisable` | `!set festivaldisable`                      | Disables the current festival                                                                |
| `mount`           | `!set mount <MountID>`                      | Rides the Mount entered                                                                      |
| `pos`             | `!set pos <x> <y> <z>`                      | Sets your position within the current zone                                                   |
| `tele`            | `!set tele <AetheryteID>`                   | Instantly teleports to the Aetheryte ID entered                                              |

### !get \<command>

| Name  | Usage      | Details                                       |
| ----- | ---------- | --------------------------------------------- |
| `pos` | `!get pos` | Shows your current position, MapID and ZoneID |

### !add \<command>

| Name     | Usage                                                                                                     | Details                                                                                                                                          |
| -------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `actrl`  | Refer to the [Actor Control](https://github.com/SapphireServer/Sapphire/wiki/ActorControl) page for usage | Sends the Actor Control entered                                                                                                                  |
| `bnpc`   | `!add bnpc <bNPCTemplateName>`                                                                            | Spawns the entered bNPC on the calling character (make sure you enter the bNPC's name and not its ID, for example, `!add bnpc littleladybug_49`) |
| `op`     | `!add op <OpCode>`                                                                                        | Sends the OpCode entered                                                                                                                         |
| `status` | `!add status <StatusID> <Duration> <Param>`                                                               | Inflicts the entered Status Effect to the calling character                                                                                      |
| `title`  | `!add title <TitleID>`                                                                                    | Adds the entered Title to the list of available Titles                                                                                           |

### !instance \<command>

| Name                  | Usage                                           | Details                                                                                                                                             |
| --------------------- | ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `create` or `cr`      | `!instance cr <InstanceContentID>`              | <p>Creates an instance for the InstanceContent and gives you its ID.<br>See <a href="../resources/instance-cfc-list.md">Instance List</a></p>       |
| `bind`                | `!instance bind <InstanceID>`                   | Binds player to the instance entered                                                                                                                |
| `unbind`              | `!instance unbind <InstanceID>`                 | Unbinds player from the instance entered                                                                                                            |
| `createzone` or `crz` | `!instance crz <ZoneID>`                        | <p>Creates an instance for Territory entered and gives you its ID.<br>See <a href="../resources/territory-type-list.md">Territory Type List</a></p> |
| `set`                 | `!instance set <index> <value>`                 | Alters the director vars of the instance                                                                                                            |
| `objstate`            | `!instance objflag <Eobj Name> <state>`         | <p>Alters the state of the eobj entered<br>(In most cases, <code>1</code> disables them, and <code>0</code> enables them)</p>                       |
| `objflag`             | `!instance objflag <Eobj Name> <flag1> <flag2>` | Alters the flags of the eobj entered                                                                                                                |
| `bgm`                 | `!instance bgm <BGMID>`                         | <p>Changes the current background music to the one entered<br>Only works in InstanceContent</p>                                                     |
| `return` or `ret`     | `!instance ret`                                 | Exits the current instance                                                                                                                          |
| `remove` or `rm`      | `!instance rm <InstanceID>`                     | Deletes the instance entered                                                                                                                        |

### !replay \<command>

| Name    | Usage                         | Details                                           |
| ------- | ----------------------------- | ------------------------------------------------- |
| `start` | `!replay start <folder name>` | Replays packets contained in the specified folder |
| `stop`  | `!replay stop`                | Stops a replay                                    |
| `info`  | `!replay info`                | Shows info about an ongoing replay                |

### !script \<command>

| Name                   | Usage                        | Details                                                            |
| ---------------------- | ---------------------------- | ------------------------------------------------------------------ |
| `unload`               | `!script unload <name>`      | Unloads a currently loaded script via its set name                 |
| `find` or `f`          | `!script find <name>`        | Searches loaded scripts names for the search term - case sensitive |
| `load` or `l`          | `!script load <path>`        | Loads the specified script from the supplied path                  |
| `queuereload` or `qrl` | `!script queuereload <name>` | Queues a script to be reloaded on the next server tick             |
