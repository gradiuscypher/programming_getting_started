# Setting up your Go Development Environment - Ubuntu Linux

## Introduction
Go is a compiled programming language, with an easy to read syntax similar to that of Python. Go is designed to be easily compiled to portible binaries for many OSes. Compile times are quick, and concurrency is simple to implement. Importing remote libraries can be done via `go get` or with more complex Go package managers like Go's `dep` toolchain. If portability/multiple-OS compatibility, concurrency, and more strict typing are important, Go can be quite a helpful language. The community for Go is growing quickly as well, so there's quite a large group of people to support you.

## Setting up Go and Go dep

### Setting up Go
Using Ubuntu's `snap` package manager, the most recent version of Go is simple to setup.

```sh
sudo snap install --classic go
```

### Setting up Go Dependency Management Tool - dep
[Go dep](https://github.com/golang/dep) is used to manage dependencies for your projects.

First, we'll download dep with `go get`:
```sh
go get -u github.com/golang/dep/cmd/dep
```

Next, we'll want to make sure we include our Go workspace directories in our path so that we can execute binaries we install to our Go `bin` path. Add this snippet to the top of your ~/.bashrc file. Afterwards, restart your terminal:
```sh
# Add Go workspace to path
export PATH="~/go/bin:$PATH"
```

Once your terminal is restarted, you should be able to execute `dep` and get the help message.

### Testing your Go install
Once we have Go and `dep` installed, it's time to test it. After this, feel free to move on to follow up documents related to Go. The remaining material is for future reference.

* Navigate to `~/go/src`
* Make the directory `hello` in `~/go/src`
* Add these contents to `hello.go` in that directory:

```
package main

import "fmt"

func main() {
    fmt.Printf("hello, world\n")
}
```

* Execute `go build` while in that directory
* Run the new executable with the command `./hello`, you should be greeted with "hello, world"
* If that all worked correctly, your Go setup is working!

### How to use the Go workspace
Your Go source will be stored in `~/go/src`, and if you're using Github to manage your code (which I highly recommend), each project will be stored in `~go/src/github.com/<YOUR_GITHUB_USERNAME>/<PROJECT_NAME>`.

#### Starting up a workspace with dep
First, don't worry about using `dep` just yet. As long as you were able to compile and run the example below, you're good to Go (get it?). We'll talk more about importing and dependencies later. This section is for future reference.

Create a new directory in either `~/go/src/<PROJECT_NAME>` or `~/go/src/github.com/<YOUR_GITHUB_USERNAME>/<PROJECT_NAME>`. Once that directory is created, run the command `dep init` which will create all the required files and folders for using `dep` as a dependency manager. Add some Go code, import some other requirements in your code and use `dep ensure` to download those requirements to the `vendor` directory. Go will know to use this directory when compiling your binary. If you change your dependencies, `dep ensure` will also sync up your project's dependencies to the `vendor` folder.

More information about `dep` can be [found here](https://golang.github.io/dep/docs/daily-dep.html).
