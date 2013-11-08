General
-------
For obvious bugs, just send a pull request.

Building
--------

Compiling and building idas-blue requires Go version 1.1+. Download it from [http://golang.org/](http://golang.org/).

To grab the latest development version of Vole and run it:

    git clone https://github.com/idas-blue/idas-blue.git
    cd idas-blue 
    export GOPATH=`pwd`
    export PATH=$PATH:$GOPATH/bin
    go run src/idas-blue/idas-blue.go

In your browser, navigate to http://localhost:6789.

Windows
-------

To set the Go path on Windows, use:

    set GOPATH="c:\Users..."
    set PATH=%GOPATH%\bin;%PATH%

Testing
-------

To run tests, execute `go test -v lib/store` from the root of the Vole project. This will create a ~/VoleTest folder with test data. This can be safely deleted once the tests have run.
