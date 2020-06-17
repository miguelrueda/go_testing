To create program
> go mod init example.com/user/hello

Go Helo
> go help test

To run the program
> go run main.go

TO build the program
> go build hello.go

Then run 
> ./hello

To create the binary
> go install example.com/user/hello

To run the module 
> go run github.com/pluralsight/webservice 

To see concurrent problems
> go run --race .


## TESTING

Add _test to filenames
Prefix tests with "Test"
Accept one parameter - *testing.T
Same package for whitebox tests
Add _test suffix to package for blackbox tests

For Immediate Failure
t.FailNow()
t.Fatal(args)
t.Fatalf(format, args)

Non-immediate failure
t.Fail()
t.Error(args)
t.Errorf(format, args)

To run tests
> go test
> go test {pkg1} ... Test specified packages
> go test ./...     Run tests in current package and descendants
> go test -v 
> go test -run {regexp}

## COVERAGE
To run with coverage
> go test -cover
To output the result
> go test -coverprofile cover.out
To see coverage report on html
> go tool cover -html cover.out
To see the low/high coverage scale
> go test -coverprofile count.out -covermode count

Some packages
- testify
- ginkgo
- goConvey
- httpexpect
- gomock
- go-sqlmock

## BENCHMARK TESTS

- b.N - Number of times to run

For the setup: 
- b.StartTimer
- b.StopTimer
- b.ResetTimer

To parallelize
- b.RunParallel

To run
> go test
To run all tests
> go test -bench .
Run benchmark targetimg the specified time
> go test -bench -benchtime 10s
Report memory allocation statistics for benchmarks
> go test -benchmem
Record execution trace to {trace.out} for analysis
> go test -trace {†race.out}
Generate profile of requested type:
> go test -{type}profile {file}
 - block
 - cover
 - cpu
 - mem
 - mutex

 > go test -bench Alloc -memprofile profile.out
 > go tool pprof profile.out
 (pprof) svg