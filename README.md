# Rikai Examples
## Scripts
+ `bin/rikai`: runner, eg. `bin/rikai coco.py`
+ `bin/rikai-shell`: REPL, eg. `bin/rikai-shell`

## Convention
Use `/tmp/rikai_example` as rikai warehouse, for `xyz.py`, save rikai formatted data into `/tmp/rikai_example/{xyz}[optional]`.

## Getting Started
```
$ conda create --no-default-packages -n rikai-example python=3.8 --yes
$ conda activate rikai-example
$ pip install -r requirements.txt
$ bin/rikai coco.py
$ bin/rikai-shell
>>> df = spark.read.format("rikai").load("/tmp/rikai_example/coco")
>>> df.show(1, truncate=False, vertical=True)
-RECORD 0---------------------------------------------------------------------------------------------------------------------------------------------------------------------
 image       | Image(uri='Some(coco_sample/train_sample/000000070211.jpg)')
 image_id    | 70211
 annotations | [{Box2d(xmin=135.0, ymin=13.05, xmax=230.55, ymax=36.379999999999995), book, 84}, {Box2d(xmin=325.53, ymin=0.0, xmax=362.53999999999996, ymax=40.62), tv, 72}]
only showing top 1 row
```