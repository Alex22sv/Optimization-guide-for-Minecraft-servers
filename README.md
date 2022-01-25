# Optimization guide for Minecraft servers
This guide will help you optimize your Minecraft server to reduce lag and improve the performance.

# Java Edition
## Vanilla

## Forge

## FabricMC
One of the best ways to reduce lag is using performance mods. You can find a list of performance mods that are server-side only to improve your performance [here](https://github.com/comp500/fabric-serverside-mods/blob/main/README.md#performance).
Some reasons that might increase lags are described in the following list with a possible solution:
* Too many mods: Usually mods don't give enough lag except heavy mods. Make sure you only use the important mods.
* Too many entities: This might cause lag to your world, to fix this you can execute the command `/kill @e[type=NAME]` where NAME would be the name of the entitie, e.g. `/kill @e[type=item]` will delete all dropped items. For more information about the command, read [this guide](https://minecraft.fandom.com/wiki/Commands/kill).
* RAM too low: Increasing your server RAM will not always fix lag but might improve a little your server performance.
* randomTickSpeed value too high: Increasing the gamerule randomTickSpeed value to a really high value can have a bad performance on your server. It is recommended to always set it to the default value, which is `3`.

## Spigot

## PaperMC
Paper itself is a very good optimized server software but if you continue to have lags or low TPS you can follow the instructions listed below:
### Edit your server bukkit.yml file.
1. Update spawn-limits
```
spawn-limits:
  monsters: 50
  animals: 8
  water-animals: 7
  water-ambient: 10
  water-underground-creature: 3
  ambient: 1
```
2. Update chunk-gc
```
chunk-gc:
  period-in-ticks: 400
```
3. Update ticks-per
```
ticks-per:
  animal-spawns: 400
  monster-spawns: 5
  water-spawns: 11
  water-ambient-spawns: 21
  water-underground-creature-spawns: 1
  ambient-spawns: 31
  autosave: 6000
```
### Edit your spigot.yml file.
1. Update save-user-cache-on-stop-only
```
settings:
  save-user-cache-on-stop-only: true
```
2. Update merge-radius
```
world-settings:
  default:
    merge-radius:
      item: 4.0
      exp: 6.0
```
3. Update item-despawn-rate
```
world-settings: 
  default:
    item-despawn-rate: The-Value-You-Think-Would-Be-Better
```
* Note: this will update the time in ticks it takes for ground items to get removed.
4. Update mob-spawn-range
```
world-settings:
  default:
    mob-spawn-range: 6
```
5. Update max-tick-time
```
world-settings:
  default:
    max-tick-time:
      tile: 1000
      entity: 1000
```
6. Update nerf-spawner-mobs
```
world-settings:
  default:
    nerf-spawner-mobs: true
```
7. Update entity-activation-range
```
world-settings:
  default:
    entity-activation-range:
      animals: 16
      monsters: 24
      raiders: 48
      misc: 8
```
8. Update tick-inactive-villagers
```
world-settings:
  default:
    entity-activation-range:
      tick-inactive-villagers: false
```

## MohistMC

## Modpacks
It's hard to have a good performance using modpacks, mostly because modpacks usually have too many heavy mods. Some solutions are mentioned in the list below:
* Check your list of mods: make sure that you don't have client-side mods on your server, since it's a client-side mod, you only need it on your Minecraft client, not on your server. You can also remove mods that you will not use, it's not really a good idea to have mods on your server that you will not even use.
* Increase RAM: The modpack page usually provides what's the required amount of RAM for your server to run smoothly, increasing at least 1GB of RAM might help but it's not guaranteed.

# Bedrock Edition
## Bedrock

## PocketMine-MP

# Credits
* Thanks to @Alex22-SV and @adriellwc for writing this guide. 
* [[GUIDE] Server Optimization⚡](https://www.spigotmc.org/threads/guide-server-optimization%E2%9A%A1.283181/)
* [Lags - Aternos](https://support.aternos.org/hc/en-us/articles/360027350792-Lags)
