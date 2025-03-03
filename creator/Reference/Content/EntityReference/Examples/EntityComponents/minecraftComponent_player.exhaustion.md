---
author: mammerla
ms.author: v-jillheaden
title: Entity Documentation - minecraft:player.exhaustion
ms.prod: gaming
---

# Entity Documentation - minecraft:player.exhaustion

`minecraft:player.exhaustion` defines the player's exhaustion level.

## Parameters

|Name |Default Value  |Type  |Description  |
|:----------|:----------|:----------|:----------|
|max| *not set* | Integer| The maximum player.exhaustion of this entity |
|value|  *not set* | Integer|  The initial value of the player.exhaustion |

## Example

```json
"minecraft:player.exhaustion": {
        "value": 0,
        "max": 20
      }
```

## Vanilla entities examples

### player

```json
"minecraft:player.exhaustion": {
        "value": 0,
        "max": 20
      }
```

## Vanilla entities using `minecraft:exhaustion_values`

- [player](../../../../Source/VanillaBehaviorPack_Snippets/entities/player.md)
