This tutorial shows you how you can set up EasyEnemies and teaches you a basic implementation of the module.

## Installation

Get the module from the [Roblox library](https://www.roblox.com/library/9041187417/EasyEnemies)

<!-- or get the [latest release](https://github.com/00xima/RBLX-SimplePath/releases) from GitHub. -->

!!! Note
For the purposes of the tutorial, the script assumes the modulescript is in `game.ServerScriptService`; For security purposes it would be best if placed `game.ServerScriptService` .

After you insert the module to your place, add a new script to `game.ServerScriptService` and paste the folowing code to start using the module:

```lua
--Import the module so you can start using it
local ServerScriptService = game:GetService("ServerScriptService")
local EasyEnemies = require(ServerScriptService.EasyEnemies)
```

The next part of the code defines all of the different methods of usage:

```lua

-- Defining Enemy Settings
local enemy_settings = {
    health = 100, -- Enemy Health
    damage = 1, -- Enemy Base Damage
    wander = false, -- Enemy Wandering

    attack_range = 20, -- Enemy Search Radius
    attack_radius = 5, -- Enemy Attack Radius

    attack_ally = false, -- Enemy Attacking Team Members
    attack_npcs = true, -- Enemy Attacking Random NPC's
    attack_players = true, -- Enemy Attacking Players

    default_animations = {8972576500}, -- Enemy Animations should be used for 'Light' Attacks // Example default_animations = {8972576500}
    default_functions = { -- Functions for said 'Light' Attacks ^
        function(target) -- functions pass the target as the first argument automatically
            print(target)
        end,
    },

    special_animations = {8972576500}, -- Enemy Animations should be used for 'Heavy' Attacks // Example special_animations = {8972576500}
    special_functions = { -- Functions for said 'Heavy' Attacks ^
        function(target) -- functions pass the target as the first argument automatically
            print('specialMove')
        end,
    },
}
```

!!! Note
`EasyEnemies.new()` is a constructor that initializes a new Enemy and it should only be initialized once per enemy.

<hr>

# There are 2 ways to initialize enemies

## Method 1: Using CollectionService Tags

The following is a video showcasing the usage of tags:

<div style="width:100%;height:0px;position:relative;padding-bottom:56.825%;"><iframe src="https://streamable.com/e/w30mnq" frameborder="0" width="100%" height="100%" allowfullscreen style="width:100%;height:100%;position:absolute;left:0px;top:0px;overflow:hidden;"></iframe></div>

The following code initializes every model with 'EnemyTag' CollectionService Tag:

```lua
  local Enemy = EasyEnemies.new('EnemyTag', enemy_settings)
```

## Method 2: Using Models

The following is a video showcasing the usage of models:

<div style="width:100%;height:0px;position:relative;padding-bottom:56.825%;"><iframe src="https://streamable.com/e/0js368" frameborder="0" width="100%" height="100%" allowfullscreen style="width:100%;height:100%;position:absolute;left:0px;top:0px;overflow:hidden;"></iframe></div>

The following code initializes the model passed in the first parameter on the `EasyEnemies.new()` function:

```lua
  local Enemy = EasyEnemies.new(Dummy, enemy_settings) -- Initializes specific Model
```

<hr>

## Choosing the right method

SimplePath gives you the freedom to code in any method you prefer. You are not limited to the two methods mentioned in this tutorial as they are simply meant to be examples. You can even combine both methods and implement them together at once. It all depends on how you decide to structure your code based on the performance, compatibility, etc. and personal preference.
