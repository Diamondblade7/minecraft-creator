---
author: mammerla
ms.author: v-jimseaman
title: Entity Documentation - minecraft:attack_damage
ms.prod: gaming
---

# Entity Documentation - minecraft:attack_damage

`minecraft:attack_damage` specifies how much damage is dealt by the entity when it attacks.

## Parameters

|Name |Default Value  |Type  |Description  |
|:----------|:----------|:----------|:----------|
|value|*not set* | Integer | How much an attack should damage a target. |


## Example

```json
"minecraft:attack_damage": {
        "value": 4
      }
```

## Vanilla entities examples

### cat

```json
"minecraft:attack_damage": {
        "value": 4
      }
```

### ocelot

```json
"minecraft:attack_damage": {
        "value": 3
      }
```

## Vanilla entities using `minecraft:attack_damage`

- [cat](../../../../Source/VanillaBehaviorPack_Snippets/entities/cat.md)
- [ocelot](../../../../Source/VanillaBehaviorPack_Snippets/entities/ocelot.md)
