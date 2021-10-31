## SQLBoiler Benchmarks

### Requirements

This repo requires Go 1.14+ to run.

To regenerate models, a running docker daemon is required.

### Instructions

To run the benchmarks, run: `go test -bench . -benchmem`

To generate the models, run: `./scripts/gen-models`

To benchmark using a different version of SQLBoiler, you can use a module
replacement that points at a local checkout. For example:

```sh
go mod edit -replace github.com/volatiletech/sqlboiler/v4=/home/user/sqlboiler
```

Regenerate the models as needed. The model generation script and the code in
this repo will use the replaced SQLBoiler. The same can be done for any other
dependency as needed.

**Note**: Graphs can be generated using benchx-cli. First you need to install.
```
go get github.com/eduardhasanaj/benchx-cli
```
After that you run the following command
```
benchx-cli run groups Delete Insert RawBind SelectAll SelectComplex SelectSubset Update
```
Graphs are generated in a folder called graphs.

The homepage for the [SQLBoiler](https://github.com/volatiletech/sqlboiler) is located at: https://github.com/volatiletech/sqlboiler
