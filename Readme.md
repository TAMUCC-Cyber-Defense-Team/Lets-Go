# Let's Go!

This is a cumulation of notes from learning GoLang. These notes are meant for experienced developers wishing to learn more about Go.

## Table of Contents
1. [Install Go](#Lets-Go-Install-Go)
   1. [Windows](#Lets-Go-Install-Go-on-Windows)
   1. [Linux](#Lets-Go-Install-Go-on-Linux)
1. [Setup Go](Setup-Go.md)
   1. [Windows](#Lets-Go-Setup-Go-on-Windows)
   1. [Linux](#Lets-Go-Setup-Go-on-Linux)
1. [Make Our First Project](#Lets-Go-Make-Our-First-Project)
1. [Test Our Project](#Lets-Go-Test-Our-Project)
1. [References](#References)

## Let's Go Install Go!
1. Prior to installing Go, if you are upgrading from an older version of Go, you must first remove the existing version.
   1. To remove an existing Go installation from your system, delete the `go` directory. This is usually `/usr/local/go` under Linux, macOS, and FreeBSD or `c:\Go` under Windows.
   1. You should also remove the Go `bin` directory from your `PATH` environment variable. Under Linux and FreeBSD you should edit `/etc/profile` or `$HOME/.profile`. If you installed Go with the macOS package, then you should remove the `/etc/paths.d/go` file. Under Windows, you may remove environment variables through the `Environment Variables` button on the `Advanced` tab of the `System` control panel. Some versions of Windows provide this control panel through the `Advanced System Settings` option inside the `System` control panel.

### Let's Go Install Go on Windows!
### Let's Go Install Go on Linux!
1. Install from binary.
   1. Download the latest Linux release from the following URL:
      1. [GoLang Downloads](https://golang.org/dl/)
   1. Extract the archive:
      1. `sudo tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz`
         1. Choose the archive file appropriate for your installation. For instance, if you are installing Go version 1.2.1 for 64-bit x86 on Linux, the archive you want is called go1.2.1.linux-amd64.tar.gz.
   1. Add the Go binaries to the PATH environment variable.
      1. Edit the global bash profile:
         1. `sudo vim /etc/profile`
      1. Add the following line to the bottom of the file:
         1. `export PATH=$PATH:/usr/local/go/bin`
      1. Log out and log back in to apply changes.

## Let's Go Setup Go!
1. All Go projects are meant to live in the same place, called your workspace.
   1. By default, this is a folder called go in your home directory.
   1. Find it using the following command:
      1. `go env GOPATH`
   1. This folder does not exist by default, so we will create it in the sections below.
   1. Inside this folder will be 3 additional folders: `bin`, `pkg`, and `src`. The `bin` folder stores Go binaries compiled using `built` or `install` commands. The `pkg` folder stores  objects used to build Go projects, including third-party Go dependencies that your code might rely on. Finally, the `src` folder will store your source code.

### Let's Go Setup Go on Windows!
### Let's Go Setup Go on Linux!
1. Create workspace:
   1. `go env GOPATH | xargs -I {} mkdir "{}"`
1. In the workspace, create a location to store all source code related to your Go projects:
   1. `go env GOPATH | xargs -I {} mkdir "{}/src"`

## Let's Go Make Our First Project!
1. Navigate to the `src` folder and make a new folder for the project:
   1. ``cd `go env GOPATH`/src ``
   1. `mkdir Test`
   1. `cd Test`
1. Start editing your first Go file:
   1. `vim hello.go`
      1. In other projects, the project will be written in `main.go`, but this is not necessary.
   1. The first line in the Go file should include a reference to the `main` package, as shown below:
      1. `package main`
   1. The next line begins to import packages.
      1. Add the following lines to import the `fmt` library for terminal input/output:
         1. ```
            import (
                "fmt"
            )
            ```
      1. Library names should be quoted and separated by newlines.
      1. Packages in the standard library and their documentation can be found here:
         1. [GoLang Packages](http://golang.org/pkg)
   1. After this, we will create the `main` function, which will display "Hello, World!" to the user:
      1. ```
         func main() {
            fmt.Println("Hello, World!")
         }
         ```
         1. If you are like me and prefer to have the curly bracket for the `main` function to start on the following line, sorry! Go requires the opening curly bracket to be at the end of the line where the function starts.
    1. Save and close the file.

## Let's Go Test Our Project
1. Method 1 - `go run`
   1. `go run` does not compile the code into a binary. Instead, it interprets the code and runs it live.
   1. Test the code in the Go file made above by typing the following in the project's directory:
      1. `go run hello.go`
   1. This should print `Hello, World!`
1. Method 2 - `go build`
   1. `go build` will create a compiled binary based on the project.
   1. Compile the project by typing the following in the project's directory:
      1. `go build`
      1. In the project's directory is now a binary based on the project folder's name.
   1. Test the binary:
      1. `./Test`
1. Method 3 - `go install`
   1. `go install` is very similar to `go build`, however, the binary is placed in the `bin` folder located in the `GOPATH`.
   1. Compile the project by typing the following in the project's directory:
      1. `go install`
      1. In the `bin` directory is now a binary based on the project folder's name. If there were any dependencies, Go would have collected and cached these in the `pkg` folder in the `GOPATH`.
   1. Navigate to the `bin` directory:
      1. ``cd `go env GOPATH`/bin ``
   1. Test the binary:
      1. `./Test`

## References
- Books
  - Black Hat Go
- Videos
  - Learn Go in 12 Minutes:
    - https://www.youtube.com/watch?v=C8LgvuEBraI
- Websites
  - Getting Started with Go
    - https://github.com/abourget/getting-started-with-golang
  - GoStart
    - https://github.com/alco/gostart
  - GoLang
    - https://golang.org/doc/