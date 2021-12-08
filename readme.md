# Nuzlocke Tracker Data

This project is a dump of all the `.txt` files used to generate the
data for my [Nuzlocke Tracker](https://nuzlocke.vercel.app).

The repository includes game data for all supported games, and I
welcome contributions for new Rom Hacks or missing games.

## Contributing

Currently, I'm working through entering the data for all existing
games myself but this can easily be made to support mods or custom game
formats.

If you would like to contribute you will need to provide the following files, the
`routes.txt` and `league.txt` which should be in the following format
below

You can use the [**Boss Editor** app](https://nuzlocke-builder.vercel.app/) to help validate the data you're creating.

### **League data**
```
--1|Gym Leader Name|Gym Leader Speciality|/image/path
pokemon|level|move1,move2,move3,move4|ability|held-item
pokemon|level|move1,move2,move3,move4|ability|held-item
pokemon|level|move1,move2,move3,move4|ability|held-item
```

### **Route data**
A list of routes with accompanying Boss battles.

```
Route 1
Route 2
--battle name|battle id|battle type
Route 3
```

- `battle type` should be one of `evil-team`, `gym-leader`, `rival` or `elite-four` - This is used for filtering
- `battle id` should match with boss battles provided in your `league` data

### **Patches**

Patches are needed by RomHacks as they often make changes to abilities, moves, items, and stats.

To support a RomHack you will need to provide a patches file containing the following

```
--item
item name|item sprite|item description
```

```
--move
name|type*|power*|description
```


```
--ability
name|description
```

```
--pokemon
hp,atk,def,spa,spd,spe*|name|type1,type2*
```

`*` denotes an optional field, you can leave these blank but you must include the necessary number of `|`s, e.g. `cut||90` will only modify the power, and `slash|dark` will only modify the type

Pokemon stats are a comma `,` separated list, but for brevity you only need to include the modifications, e.g. `,,100` will modify the Defense to `100`

---

Examples can be found for all three inside [`leagues`](/leagues), [`routes`](/routes) & [`patches`](/patches).
PR's welcome where I will do the testing necessary before approval.
