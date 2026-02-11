# Releasing the dataset

## Recreate the raw data from glottography-data

In case of upstream changes in glottography-data:
```shell
cldfbench download cldfbench_edwards2020metathesis.py
```

## Recreate the CLDF data

```shell
cldfbench makecldf cldfbench_edwards2020metathesis.py --glottolog-version v5.2
cldfbench cldfreadme cldfbench_edwards2020metathesis.py
cldfbench zenodo --communities glottography cldfbench_edwards2020metathesis.py
cldfbench readme cldfbench_edwards2020metathesis.py
```

## Validation

```shell
cldf validate cldf
```

```shell
cldfbench geojson.validate cldf
75      valid features
67      valid speaker areas
```

```shell
cldfbench geojson.glottolog_distance cldf --format pipe
```

| ID | Distance | Contained | NPolys |
|:---------|-----------:|:------------|---------:|
| amar1273 | 0.00 | True | 1 |
| aput1237 | 0.06 | False | 2 |
| bilb1242 | 0.00 | True | 1 |
| buna1278 | 0.00 | True | 1 |
| dela1251 | 0.00 | True | 3 |
| deng1253 | 0.00 | True | 2 |
| dhao1237 | 0.00 | True | 1 |
| fata1247 | 0.00 | True | 2 |
| galo1243 | 0.00 | True | 2 |
| habu1241 | 0.05 | False | 1 |
| helo1243 | 0.00 | True | 7 |
| idat1237 | 0.00 | True | 1 |
| iliu1237 | 0.00 | True | 6 |
| kair1265 | 0.00 | False | 3 |
| kema1243 | 0.00 | True | 2 |
| kisa1266 | 0.00 | True | 3 |
| kupa1239 | 0.06 | False | 1 |
| laka1255 | 0.01 | False | 1 |
| leti1246 | 0.00 | True | 1 |
| lole1239 | 0.00 | True | 1 |
| luan1263 | 0.00 | True | 4 |
| maka1316 | 0.00 | True | 1 |
| maku1277 | 0.03 | False | 1 |
| mamb1306 | 0.05 | False | 2 |
| naue1237 | 0.01 | False | 1 |
| oira1263 | 0.01 | False | 1 |
| pera1257 | 0.00 | True | 1 |
| ring1244 | 0.00 | True | 2 |
| roma1332 | 0.00 | True | 11 |
| sabu1255 | 0.00 | True | 2 |
| term1237 | 0.00 | True | 1 |
| tetu1245 | 0.00 | False | 2 |
| tetu1246 | 0.00 | True | 1 |
| tiii1241 | 0.00 | True | 34 |
| tugu1245 | 0.00 | True | 1 |
| tuku1254 | 0.00 | True | 1 |
| uabm1237 | 0.00 | True | 2 |
| waim1252 | 0.00 | True | 1 |
| wela1235 | 0.15 | False | 1 |


## Release

Commit and push all changes.

Run
```
cldfbench glottography.release cldfbench_edwards2020metathesis.py vX.Y
```
and follow the instructions given in the output of the command.