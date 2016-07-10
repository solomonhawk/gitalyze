## [JQ](https://stedolan.github.io/jq/)
command line json tool

parse json into grep friendly output
http://stackoverflow.com/a/6320876/4611471

    $ some.json | python -mjson.tool


# Thoughts

Harder things:

* handling output requires more thought (I'm relatively newb with unix)
* handling errors is different
* looping is kind of annoying
* complex conditionals suck
* no named arguments to functions
* dereferencing variables can get tricky esp. with nested expressions
* uhh, string concatenation? :(
* testing???

# TODO

* Help users avoid creating many temporary files
* Avoid needing || Automate adding - `gitalyze/bin` to $PATH