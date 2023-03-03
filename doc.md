# Building data

## Master JSON files

Building all data is based on the following files

```
./routes/*.txt    # <game-id>.txt
./leagues/*.txt   # <game-id>.txt
./patches/*.txt   # <game-id>.txt
```

Run

```
make data
```

This will produce `leagues.json`, `patches.json` & `routes.json` in the main application 

## Game JSON files

To help reduce payload sizes, we then render master records for each
league and starter type. To generate this data, make sure the main application 
is running on port `:5173`

Run

```
make static/<game-id>   # e.g. make static/red
```

This will produce three files, `<game-id>.fire.json`, `<game-id>.water.json` & `<game-id>.grass.json`

---

# Fetching data 

## Route information

<!-- TODO: Write this up -->

```
```

## Pokemon information

<!-- TODO: Write this up -->
