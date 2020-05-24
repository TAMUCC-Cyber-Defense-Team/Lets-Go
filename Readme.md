# Let's Go!

This is a cumulation of notes from learning GoLang. These notes are meant for experienced developers wishing to learn more about Go.

## Table of Contents
1. [Install Go](#Lets-Go-Install-Go)
   1. [Windows](#Lets-Go-Install-Go-on-Windows)
   1. [Linux](#Lets-Go-Install-Go-on-Linux)
1. [Setup Go](Setup-Go.md)
   1. [Windows](#Lets-Go-Setup-Go-on-Windows)
   1. [Linux](#Lets-Go-Setup-Go-on-Linux)
1. [References](References.md)

## Let's Go Install Go!
1. Prior to installing Go, if you are upgrading from an older version of Go, you must first remove the existing version
   1. To remove an existing Go installation from your system, delete the `go` directory. This is usually `/usr/local/go` under Linux, macOS, and FreeBSD or `c:\Go` under Windows.
   1. You should also remove the Go `bin` directory from your `PATH` environment variable. Under Linux and FreeBSD you should edit `/etc/profile` or `$HOME/.profile`. If you installed Go with the macOS package, then you should remove the `/etc/paths.d/go` file. Under Windows, you may remove environment variables through the `Environment Variables` button on the `Advanced` tab of the `System` control panel. Some versions of Windows provide this control panel through the `Advanced System Settings` option inside the `System` control panel.

### Let's Go Install Go on Windows
### Let's Go Install Go on Linux
1. Install from binary
   1. Download the latest Linux release from the following URL
      1. `https://golang.org/dl/`
   1. Extract the archive
      1. `sudo tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz`
         1. Choose the archive file appropriate for your installation. For instance, if you are installing Go version 1.2.1 for 64-bit x86 on Linux, the archive you want is called go1.2.1.linux-amd64.tar.gz.
   1. Add the Go binaries to the PATH environment variable
      1. Edit the global bash profile
         1. `sudo vim /etc/profile`
      1. Add the following line to the bottom of the file
         1. `export PATH=$PATH:/usr/local/go/bin`
      1. Log out and log back in to apply changes

## Let's Go Setup Go!
1. All Go projects are meant to live in the same place, called your workspace.
   1. By default, this is a folder called go in your home directory.
   1. Find it using the following command:
      1. go env GOPATH
   1. This folder does not exist by default, so we will create it in the sections below.

### Let's Go Setup Go on Windows
### Let's Go Setup Go on Linux
1. Create workspace
   1. `go env GOPATH | xargs -I {} mkdir "{}"`
1. In the workspace, create a location to store all source code related to your Go projects
   1. `go env GOPATH | xargs -I {} mkdir "{}/src"`

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