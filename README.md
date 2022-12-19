# meltano-tutorial
Codespaces based

## Part 0: ##
Running with batect & codespaces.

1. open up a new codespaces
2. inside codespaces run 
``./batect melt``

to do a quick start, run Part 1: Step 1 (init), and then do a 
- rm my-meltano-project/meltano.yml
- cp new_project/meltano.yml my-meltano-project/meltano.yml
- cp new_project/.env my-meltano-project/.env

and edit the .env file.

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

