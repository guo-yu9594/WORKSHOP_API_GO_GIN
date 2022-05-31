# workshop-api-go-gin

<p align="center"><a href="https://go.dev" target="_blank"><img src="https://go.dev/blog/go-brand/Go-Logo/PNG/Go-Logo_Blue.png" width="400"></a></p>

# Introduction

Go, or also called Golang, is absolutely trendy, and rightly so.
It is not as difficult to learn as C or C++, but still quite fast, and has a great community & many interesting and helpful packages and libraries. The language was also developed by some of the brightest minds in the computer science world at Google.

**A speedy language**\
Go is a speedy language. Because Go is compiled into machine code, languages that are interpreted or have virtual runtime will naturally outperform. Go programs compile quite fast, and the resulting binary is very small.

**Easy to Learn**\
Compared to other languages, Go’s syntax is small, and learning is easy. You can fit in your head, which means you don’t need to look and waste so much time. It’s very smooth and easy to read as well. Non-going programmers can read a Go program and generally comprehend about what’s going on, particularly those used to C-style syntax.

**Garbage Collection**\
Memory management in Go was intentionally made easier than in C and C++. Dynamically allocated objects are garbage collected. Go makes using pointers much safer because it doesn’t allow pointer arithmetic. It also gives you the option of using value types.

**Growing Pool Of Talent**\
According to <a href="https://hired.com/2022-state-of-software-engineers/">Hired<a/>, Go is the #1 most in-demand programming language across the planet. Companies are gaining more awareness of how beneficial using  Golang can be for their businesses, and programmers are brushing their skills of the language in droves.

These are probably enough reasons to look at the language in which Docker and Kubernetes were written.

# Step 0 - Installation

## Part 1

To install Go :
```bash
sudo pacman -S go # if you are on Archlinux
-----
sudo dnf install snapd  # install snap on Fedora
sudo apt install snapd  # install snap on Ubuntu
sudo snap install go --classic # install go
```

You can use the following command to check if Go has been correctly installed :
```bash
go version # check if your version is >= 1.18.2
```
Now we need to install Postman which will help you to test your api.
```bash
sudo snap install postman
```

## Part 2

Create a project:
```bash
go mod init (project name)
touch main.go
```
Create a new directory, this directory will have a go file, it will be used to contain our functions for the api
```bash
mkdir exemple
cd exemple
touch api.go
```

Install gin:
```bash
go get github.com/gin-gonic/gin
```


Run this code (main.go) to see if it's working properly
```go
package main

import "fmt"

func main() {
    fmt.Println("hello world")
}
```

To test your program without building the binary, you can use
```bash
go run main.go
```
Or building the binary
```bash
go build
./(project name)
```

# Step 1 - Setup the REST API

## Part 1

Create a server with Gin and try to print "Hello World" in the "/hello" route

Here is some documentation that can help you:

https://gin-gonic.com/docs/quickstart/ \
https://github.com/gin-gonic/gin

To test your newly born route, use your preinstalled Postman to send request to your server. Here a documentation to learn how to make request with Postman : https://learning.postman.com/docs/sending-requests/requests/

## Part 2

Create a structure that will contain the data of a person (ID, last name, first name, age)\
Then create a list of the structure you just created and add a person to it \
This variable will be used as a database

# Step 2 - Build a simple REST API

## GET Route

Create a GET Route that will display everything you have stored in the database \
Example
```json
[
    {
        "id": 1,
        "last_name": "Arnaud",
        "first_name": "Ho",
        "age": 20
    },
    {
        "id": 2,
        "last_name": "Guo",
        "first_name": "Yu",
        "age": 20
    }
]
```

## POST Route

Create a POST Route that will add a new person in the database \
Example
```json
[
    {
        "id": 1,
        "last_name": "Arnaud",
        "first_name": "Ho",
        "age": 20
    },
    {
        "id": 2,
        "last_name": "Guo",
        "first_name": "Yu",
        "age": 20
    },
    {
        "id": 3,
        "last_name": "Toni",
        "first_name": "Da",
        "age": 20
    }
]
```
## DELETE Route

Create a DELETE Route that will delete a person by ID in the database \
Before
```json
[
    {
        "id": 1,
        "last_name": "Arnaud",
        "first_name": "Ho",
        "age": 20
    },
    {
        "id": 2,
        "last_name": "Guo",
        "first_name": "Yu",
        "age": 20
    },
    {
        "id": 3,
        "last_name": "Toni",
        "first_name": "Da",
        "age": 20
    }
]
```
After
```json
[
    {
        "id": 1,
        "last_name": "Arnaud",
        "first_name": "Ho",
        "age": 20
    },
    {
        "id": 2,
        "last_name": "Guo",
        "first_name": "Yu",
        "age": 20
    }
]
```

## PUT Route

Create a PUT Route that modifies a person's data by ID in the database \
Before
```json

[
    {
        "id": 1,
        "last_name": "Arnaud",
        "first_name": "Ho",
        "age": 20
    },
    {
        "id": 2,
        "last_name": "Guo",
        "first_name": "Yu",
        "age": 20
    }
]
```
After
```json
[
    {
        "id": 1,
        "last_name": "Alain",
        "first_name": "Provist",
        "age": 18
    },
    {
        "id": 2,
        "last_name": "Guo",
        "first_name": "Yu",
        "age": 20
    }
]
```
# Bonus
## Wow too easy and have nothing to do ?
Create a new structure that will contain a username and a password \
Then try to do an authentification system (register, login) \
The password needs to be encrypted (use Bcrypt)

**Don't forget to do error management**
