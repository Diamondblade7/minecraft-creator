---
author: mammerla
ms.author: v-jillheaden
title: Entity Documentation - minecraft:shareables
ms.prod: gaming
---

# Entity Documentation - minecraft:shareables

`minecraft:shareables` defines a list of items the mob wants to share or pick up.

## Parameters

|Name |Default Value  |Type  |Description  |
|:----------|:----------|:----------|:----------|
| all_items| False| Boolean| A bucket for all other items in the game. Note this category is always least priority items. |
| all_items_max_amount| -1| Integer| Maximum number of this item the entity will hold. |
| all_items_surplus_amount| -1| Integer| Number of this item considered extra that the entity wants to share. |
| all_items_want_amount| -1| Integer| Number of this item the entity wants to share. |
| items| *not set*| List| List of items that the entity wants to share.|

### items

`items` is a list defined by eleven parameters. Each item has the following properties:

| Name| Default Value| Type| Description|
|:----------|:----------|:----------|:----------|
| admire| False| Boolean| Entity will admire the item after picking up by looking at it. For this to happen the entity needs to have an [Admire](minecraftComponent_admire_item.md) component and an [Admire](../EntityGoals/minecraftBehavior_admire_item.md) goal.|
| barter| False| Boolean| Entity will barter for the item after picking it up. For this to work the entity needs to have a [Barter](minecraftComponent_barter.md) component and a [Barter](../EntityGoals/minecraftBehavior_barter.md) goal.|
| consume_item|False|Boolean|Determines whether the entity will consume the item or not.|
| craft_into|*not set*|String| Defines the item the entity wants to craft with the item defined by "item". Should be an item name.|
|item |*not set* | String| The name of the item. Aux value can be specified, for instance `minecraft:skull:1`.|
| max_amount| *not set*| Integer| Maximum number of this item the entity will hold.|
| pickup_limit| *not set*| Integer| Maximum number of this item the entity will pick up during a single goal tick.|
| pickup_only | false | Boolean | Determines whether the entity can only pickup the item and not drop it. |
| priority| *not set*| Integer| Prioritizes which items the entity prefers. 0 is the highest priority.|
| stored_in_inventory| *not set*| Boolean| Determines whether the entity will try to put the item in its inventory if it has the inventory component and if it can't be equipped.|
| surplus_amount| *not set*| Integer| Number of this item considered extra that the entity wants to share.|
| want_amount| *not set*| Integer| Number of this item the entity wants to have.|

## Example

In this example, an entity wants to be able to make `bread` from `wheat`. Since bread requires 3 total wheat, the entity will want a total of 3 and will consider 4 or more as surplus.

```json
"minecraft:shareables":{
    "all_items": true,
    "all_items_max_amount": 1,
    "all_items_surplus_amount": 4,
    "all_items_want_amount": 3,
    "items": [
        {
            "item": "minecraft:wheat",
            "admire": false,
            "barter": false,
            "consume_item": false,
            "craft_into": "minecraft:bread",
            "priority": 0,
            "max_amount": 3,
            "pickup_limit": -1, //no limit
            "pickup_only": true,
            "store_in_inventory": true,
            "surplus_amount": 4,
            "want_amount": 3
        }
    ]
}
```

## Vanilla entities examples

### villager

```json
"minecraft:shareables": {
          "items": [
            {
              "item": "minecraft:bread",
              "want_amount": 3,
              "surplus_amount": 6,
              "stored_in_inventory": true
            },
            {
              "item": "minecraft:carrot",
              "want_amount": 60,
              "surplus_amount": 4,
              "stored_in_inventory": true
            },
            {
              "item": "minecraft:potato",
              "want_amount": 60,
              "surplus_amount": 24,
              "stored_in_inventory": true
            },
            {
              "item": "minecraft:beetroot",
              "want_amount": 60,
              "surplus_amount": 24,
              "stored_in_inventory": true
            },
            {
              "item": "minecraft:wheat_seeds",
              "want_amount": 64,
              "surplus_amount": 64,
              "stored_in_inventory": true,
              "pickup_only": true
            },
            {
              "item": "minecraft:beetroot_seeds",
              "want_amount": 64,
              "surplus_amount": 64,
              "stored_in_inventory": true,
              "pickup_only": true
            },
            {
              "item": "minecraft:wheat",
              "want_amount": 45,
              "surplus_amount": 18,
              "craft_into": "minecraft:bread",
              "stored_in_inventory": true
            }
          ]
        },
        "minecraft:behavior.harvest_farm_block": {
          "priority": 9,
          "speed_multiplier": 0.5
        }
```

## Vanilla entities using `minecraft:shareables`

- [drowned](../../../../Source/VanillaBehaviorPack_Snippets/entities/drowned.md)
- [fox](../../../../Source/VanillaBehaviorPack_Snippets/entities/fox.md)
- [husk](../../../../Source/VanillaBehaviorPack_Snippets/entities/husk.md)
- [piglin](../../../../Source/VanillaBehaviorPack_Snippets/entities/piglin.md)
- [pillager](../../../../Source/VanillaBehaviorPack_Snippets/entities/pillager.md)
- [skeleton](../../../../Source/VanillaBehaviorPack_Snippets/entities/skeleton.md)
- [stray](../../../../Source/VanillaBehaviorPack_Snippets/entities/stray.md)
- [villager_v2](../../../../Source/VanillaBehaviorPack_Snippets/entities/villager_v2.md)
- [villager](../../../../Source/VanillaBehaviorPack_Snippets/entities/villager.md)
- [wither_skeleton](../../../../Source/VanillaBehaviorPack_Snippets/entities/wither_skeleton.md)
- [zombie_pigman](../../../../Source/VanillaBehaviorPack_Snippets/entities/zombie_pigman.md)
- [zombie_villager_v2](../../../../Source/VanillaBehaviorPack_Snippets/entities/zombie_villager_v2.md)
- [zombie_villager](../../../../Source/VanillaBehaviorPack_Snippets/entities/zombie_villager.md)
- [zombie](../../../../Source/VanillaBehaviorPack_Snippets/entities/zombie.md)
