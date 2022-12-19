# meltano-tutorial
Codespaces based

## Part 0: ##
Running with batect & codespaces.

1. open up a new codespaces
2. inside codespaces run 
``./batect melt``

to do a quick start, run:
- ./batect test (first to fill the cache)
- ./batect melt (second to open up your terminal)

and edit the .env file. Then you can do the invoke & run steps right away!

## Part 1: ##
https://docs.meltano.com/getting-started/part1 

Step 1: 

``meltano init my-meltano-project``


Step 2:

``meltano add extractor tap-github``


Step 3:

``meltano config tap-github set --interactive``


Step 4:

``meltano config tap-github``

Step 5: 

``meltano select tap-github --list --all``

Step 6:

```bash
    meltano select tap-github commits url
    meltano select tap-github commits sha
    meltano select tap-github commits commit_timestamp
```

Step 7: 

``meltano select tap-github --list``

Step 8: 

``meltano invoke tap-github``

Step 9: 

``meltano add loader target-jsonl``

Step 10:

``meltano run tap-github target-jsonl``

## Part 2: ##
https://docs.meltano.com/getting-started/part2

For a quickstart, run `./batect clean; ./batect test_2`.  

meltano add loader target-postgres --variant=meltanolabs
meltano invoke target-postgres --help
meltano config target-postgres set user meltano
meltano config target-postgres set password password
meltano config target-postgres set database postgres
meltano config target-postgres set host host.docker.internal
meltano config target-postgres set host postgres
meltano config target-postgres set add_metadata_columns True

meltano config target-postgres

meltano run tap-github target-postgres
