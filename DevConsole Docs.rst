DevConsole Commands
===================

spawn
-----
Can be used to spawn any ``Thing``. The ``Thing`` in question must have a parameterless constructor.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``spawn (thing) (x) (y)``

thing:
	The name of the ``Type`` of the ``Thing`` you wish to spawn.
x: 
	Target X-coordinate
y: 
	Target Y-coordinate

modhash
-------
Gets the SHA256CNG hash of the user's current mods. This hash is produced by taking all mods and concatenating them into a string and then hashing thew string. If the user has no mods the string "nomods" is returned instead of a hash.

Hashed string format:
    ``string.Join("|", Mods.Where(x => (!x is CoreMod) && !(a is DisabledMod)).Select(x => $"{x.Name}_{x.Version}")``
	

Example string pre-hash:
``ExampleMod_1.1|OtherExample_0.2``

Usage
~~~~~
``modhash``

netdebug
--------
Displays the console in the bottom left of the user's screen. Also output networking debug info.

Shows information such as latency, jitter, and loss in the top left corner of the user's screen.

Usage
~~~~~
``netdebug``

record
------
Begins recording gameplay. The recording is dumped as 2 files in your ``Duck Game`` root folder. (The folder where the game's EXE is)

Attempting to start a recording while another is in progress will crash your game.

Usage
~~~~~
``record (name)``

name:
	Name to save the recording under.

close
-----
Closes the console. The console will state that this is an invalid command. This is incorrect. The developers forgot a ``return`` statement after this command. It's sole intention seems to be to close the console.

Usage
~~~~~
``close``

stop
----
Stops any ongoing recordings.

Usage
~~~~~
``stop``

playback
--------
``Plays back a recording.``

Crashes the game due to an unimplemented method as of the time of writing.

Usage
~~~~~
``playback (name)``

name:
	Recording name to play back.

level
-----
Changes the current level.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``level (path)``

path:
	The relative path to the level file from the ``%duckgamebin%/Content/levels/deathmatch`` folder.

team
----
Sets a player's team.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``team (profile) (team)``

profile:
	The profile name of the player to have their team changed.

team:
	The team name to change the player to. This is a hat name.

give
----
Gives a player an item.

Cannot be used online or in any challenge arcade levels. Nor can it be used in the arcade.

Usage
~~~~~
``give (profile) (thing)``

profile:
	The profile name of the player to give the ``Thing`` to.

thing:
	The name of the ``Type`` of the ``Thing`` to give the player. The ``Thing`` must be a ``Holdable``.

call
----
Calls a parameterless method in the ``Duck`` class on behalf of a player.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``call (profile) (method)``

profile:
	The profile name of the ``Duck`` to run the method on behalf of.

method:
	The method name to run on.

set
---
Sets the value of a property in the ``Duck`` class on behalf of a player.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``set (profile) (property|field) (value)``

profile:
	The name of the profile of the ``Duck`` to change the property or field value.

property | field:
	The name of the property or field in the ``Duck`` class.

value:
	The value to set the property or field to.

Notes
~~~~~
The value is converted from the string given to the type of the member. The types supported are: float, int, bool, vec2.

vec2 requires two separate values for the x and y coordinates. All other types require a single value.

kill
----
Kills a duck.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``kill (profile)``

profile:
	The profile name of the duck to be killed.

globalscores
------------
Generates a score number for each profile in the game.

Usage
~~~~~
``globalscores``

scorelog
--------
Shows a realtime score rundown for the selected profile.

Usage
~~~~~
``scorelog (index)``

index:
	Zero-based index of the profiles in the game.

toggle
------
Toggles the rendering of a view layer.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``toggle (layer)``

layer:
	Layer to toggle.
	Possible layers:
		* background
		* parallax
		* foreground
		* game
		* HUD

splitscreen
-----------
Toggles splitscreen.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``splitscreen``

rhythmmode
----------
Toggles rhythm mode.

Seems to toggle more elements to be drawn on screen by calling ``RhythmMode.Draw()``. Crashes the game due to a music track not being found.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``rhythmmode``

qwopmode
--------
Toggles qwop mode.

Cannot be used online or in any challenge arcade levels. Can be used within the challenge arcade itself.

Usage
~~~~~
``qwopmode``

showislands
-----------
Shows collision islands.

Usage
~~~~~
``showislands``

showcollision
-------------
Does nothing.

Usage
~~~~~
``showcollision``
