# GO

## Install Go

If you are upgrading from an older version of Go you must first remove the existing version.
To remove an existing Go installation from your system delete the go directory.

```console
# Linux & Mac
$ sudo rm -rf /usr/local/go

# Windows
Delete c:\Go
```

To install Go, run the following command:

```console
$ go_version=1.18.1
$ cd ~/Downloads
$ sudo apt-get update
$ sudo apt-get install -y build-essential git curl wget
$ wget https://go.dev/dl/go${go_version}.linux-amd64.tar.gz
$ sudo tar -C /usr/local -xzf go${go_version}.linux-amd64.tar.gz
$ sudo chown -R $(id -u):$(id -g) /usr/local/go
$ rm go${go_version}.linux-amd64.tar.gz
```

Add go to your $PATH variable

```console
$ mkdir $HOME/go
$ nano ~/.bashrc
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:/usr/local/go/bin:$PATH
$ source ~/.bashrc
$ go version
```

### Troubleshoot Go
- `cannot allocate memory`: [http://stackoverflow.com/a/35027241](http://stackoverflow.com/a/35027241)

## Install Intellij GoLand IDE
- https://www.jetbrains.com/go/

## Learn Go

- [An Introduction to Programming in GO](https://www.golang-book.com/books/intro)

## Learn Go Nuances

Read these books / articles / web pages in order:

- [https://github.com/golang/go/wiki/Switch](https://github.com/golang/go/wiki/Switch)
- Slices
  - [Iterating Over Slices In Go](https://www.ardanlabs.com/blog/2013/09/iterating-over-slices-in-go.html)
     - [Using goroutines on loop iterator variables](https://github.com/golang/go/wiki/CommonMistakes)
  - [SliceTricks](https://github.com/golang/go/wiki/SliceTricks)
  - [Go Slices: usage and internals](http://blog.golang.org/go-slices-usage-and-internals)
  - [Arrays, slices (and strings): The mechanics of 'append'](https://blog.golang.org/slices)
- [10 things you did not know](https://talks.golang.org/2012/10things.slide#1)
- [50 Shades of Go: Traps, Gotchas, and Common Mistakes for New Golang Devs](http://devs.cloudimmunity.com/gotchas-and-common-mistakes-in-go-golang/)
- [Effective GO](https://golang.org/doc/effective_go.html)

If you just want a quick refresh of the syntax, the following link is very handy: [A Tour of Go](https://tour.golang.org/)


### Flag Library

- https://github.com/spf13/pflag

### Cli Library

- https://github.com/spf13/cobra


### Dependency management

```
$ export GO111MODULE=on
```

- [Go 1.11 Modules](https://github.com/golang/go/wiki/Modules)
- [https://roberto.selbach.ca/intro-to-go-modules/](https://roberto.selbach.ca/intro-to-go-modules/)



### Error handling & Reporting

- [https://github.com/pkg/errors](https://github.com/pkg/errors)
- [https://www.youtube.com/watch?v=29LLRKIL_TI](https://www.youtube.com/watch?v=29LLRKIL_TI) (spf13 errors)

### OOP Concepts in Go

- [https://github.com/luciotato/golang-notes/blob/master/OOP.md](https://github.com/luciotato/golang-notes/blob/master/OOP.md)
- [http://www.hydrogen18.com/blog/golang-embedding.html](http://www.hydrogen18.com/blog/golang-embedding.html)
- [http://www.goinggo.net/2014/05/methods-interfaces-and-embedded-types.html](http://www.goinggo.net/2014/05/methods-interfaces-and-embedded-types.html)

### Interfaces in GO

- [http://jordanorelli.com/post/32665860244/how-to-use-interfaces-in-go](http://jordanorelli.com/post/32665860244/how-to-use-interfaces-in-go)

### Reflection

- https://golangbot.com/reflection/

### Mixin

- [https://gist.github.com/haazime/270657beb140a307a559](https://gist.github.com/haazime/270657beb140a307a559)
- [https://en.wikipedia.org/wiki/Mixin](https://en.wikipedia.org/wiki/Mixin)

### Mutexes

- [https://gobyexample.com/mutexes](https://gobyexample.com/mutexes)
- [http://www.alexedwards.net/blog/understanding-mutexes](http://www.alexedwards.net/blog/understanding-mutexes)

### Concurrency
- Basic Concepts
  - [Concurrency](https://golangbot.com/concurrency/)
  - [Go routines](https://golangbot.com/goroutines/)
  - [Channels](https://golangbot.com/channels/)
- Video: [Concurrency Made Easy (Practical Tips For Effective Concurrency In Go)](https://www.youtube.com/watch?v=DqHb5KBe7qI)
- Video: [Kavya Joshi - Understanding Channels](https://www.youtube.com/watch?v=KBZlN0izeiY)
- [Channel Axioms](https://dave.cheney.net/2014/03/19/channel-axioms)
- [Curious Channels](http://dave.cheney.net/2013/04/30/curious-channels)
- [Why are there nil channels in Go?](https://medium.com/justforfunc/why-are-there-nil-channels-in-go-9877cc0b2308)
- [The Behavior Of Channels](https://www.ardanlabs.com/blog/2017/10/the-behavior-of-channels.html)
- [https://blog.golang.org/pipelines](https://blog.golang.org/pipelines)

### Go Style guide

- Use `go fmt <file>.go`
- [https://github.com/golang/go/wiki/CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)

- Install [golint](https://github.com/golang/lint)

```console
$ go get -u github.com/golang/lint/golint
$ golint <file>.go

```

- go vet examines Go source code and reports suspicious constructs. See how to use it [here](https://godoc.org/golang.org/x/tools/cmd/vet).
- Command goimports updates your Go import lines, adding missing ones and removing unreferenced ones.

[https://godoc.org/golang.org/x/tools/cmd/goimports](https://godoc.org/golang.org/x/tools/cmd/goimports)

### Documenting Go Code

- [http://blog.golang.org/godoc-documenting-go-code](http://blog.golang.org/godoc-documenting-go-code)

### HTTP Basic
- [HTTP: The Protocol Every Web Developer Must Know - Part 1](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)
- [HTTP: The Protocol Every Web Developer Must Know - Part 2](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-2--net-31155)
- [HTTP Status Codes in 60 Seconds](https://webdesign.tutsplus.com/tutorials/http-status-codes-in-60-seconds--cms-24317)
- [A Beginner’s Guide to HTTP and REST](https://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340)
- [HTTP Headers for Dummies](https://code.tutsplus.com/tutorials/http-headers-for-dummies--net-8039)

### GO net/http

- [Creating A Simple Web Server With Golang](https://tutorialedge.net/golang/creating-simple-web-server-with-golang/)
- [Encoding and Decoding JSON, with Go’s net/http package](https://kev.inburke.com/kevin/golang-json-http/)
- https://github.com/go-chi/chi
- https://golang.org/pkg/net/http/
- [https://cryptic.io/go-http/](https://cryptic.io/go-http/)
- [https://github.com/google/go-querystring](https://github.com/google/go-querystring)
- [https://github.com/tent/http-link-go](https://github.com/tent/http-link-go)

### Tracing HTTP Connections

- [Golang httptrace Example](https://golang.cafe/blog/golang-httptrace-example.html)
- [How to re-use HTTP Connections in Go](https://golang.cafe/blog/how-to-reuse-http-connections-in-go.html)
- https://github.com/hashicorp/go-cleanhttp

```
// By default, Transport caches connections for future re-use.
// This may leave many open connections when accessing many hosts.
// This behavior can be managed using Transport's CloseIdleConnections method
// and the MaxIdleConnsPerHost and DisableKeepAlives fields.
//
// Transports should be reused instead of created as needed.
// Transports are safe for concurrent use by multiple goroutines.
```


### JSON

- [http://json.org/](http://json.org/)
- http://blog.golang.org/json-and-go
- https://gobyexample.com/json
- http://mholt.github.io/json-to-go/
- [How to Parse a JSON Request Body in Go](https://www.alexedwards.net/blog/how-to-properly-parse-a-json-request-body)
- [JSON and struct composition in Go](http://attilaolah.eu/2014/09/10/json-and-struct-composition-in-go/)
- [Custom Marshaller/Unmarshaller](https://gist.github.com/mdwhatcott/8dd2eef0042f7f1c0cd8)

### YAML

- [YAML Techniques](https://github.com/helm/helm/blob/v2.16.5/docs/chart_template_guide/yaml_techniques.md)
- [sigs.k8s.io/yaml](https://github.com/kubernetes-sigs/yaml)

### GO Template Engine

- [https://medium.com/@IndianGuru/understanding-go-s-template-package-c5307758fab0](https://medium.com/@IndianGuru/understanding-go-s-template-package-c5307758fab0)
- [https://hackernoon.com/golang-template-2-template-composition-and-how-to-organize-template-files-4cb40bcdf8f6](https://hackernoon.com/golang-template-2-template-composition-and-how-to-organize-template-files-4cb40bcdf8f6)
- [https://golang.org/pkg/text/template/](https://golang.org/pkg/text/template/)
- [https://gist.github.com/tamalsaha/cc86951e3ef7ae23de34f2b116814541](https://gist.github.com/tamalsaha/cc86951e3ef7ae23de34f2b116814541)
- [http://gohugo.io/templates/go-templates/](http://gohugo.io/templates/go-templates/)
- [http://golang.org/pkg/html/template/](http://golang.org/pkg/html/template/)
- [http://macaron.gogs.io/docs/middlewares/templating.html](http://macaron.gogs.io/docs/middlewares/templating.html)
- [https://player.oreilly.com/videos/9781491938294](https://player.oreilly.com/videos/9781491938294)


### GO INI Lib

[https://github.com/go-ini/ini](https://github.com/go-ini/ini)

### JSON Query Lib

[https://github.com/jmespath/go-jmespath](https://github.com/jmespath/go-jmespath)

### GO Debugger

[https://github.com/davecgh/go-spew](https://github.com/davecgh/go-spew)

### Testing time-sensitive code

[https://github.com/jmhodges/clock](https://github.com/jmhodges/clock)

Where you'd use time.Now, instead use clk.Now where clk is an instance of Clock. When running your code in production, pass it a Clock given by Default() and when you're running it in your tests, pass it an instance of Clock from NewFake().

Clock Utility Methods: [https://github.com/jinzhu/now](https://github.com/jinzhu/now)

### Unit Testing Library

- [https://github.com/stretchr/testify](https://github.com/stretchr/testify)
- https://golang.org/pkg/testing/
- https://blog.alexellis.io/golang-writing-unit-tests/
- https://blog.codeship.com/testing-in-go/
- [https://speakerdeck.com/mitchellh/advanced-testing-with-go](https://speakerdeck.com/mitchellh/advanced-testing-with-go)

**Mocks**

- [https://github.com/stretchr/testify#mock-package](https://github.com/stretchr/testify#mock-package)

**HTTP Testing**

- [http://www.markjberger.com/testing-web-apps-in-golang/](http://www.markjberger.com/testing-web-apps-in-golang/)
- [http://keighl.com/post/mocking-http-responses-in-golang/](http://keighl.com/post/mocking-http-responses-in-golang/)
- [https://blog.pivotal.io/labs/labs/a-rubyist-leaning-go-testing-http-handlers](https://blog.pivotal.io/labs/labs/a-rubyist-leaning-go-testing-http-handlers)

**BDD Testing**

- [https://github.com/onsi/ginkgo](https://github.com/onsi/ginkgo)
- [https://github.com/onsi/gomega](https://github.com/onsi/gomega)

**HTTP Load testing tool**

- [https://github.com/tsenart/vegeta](https://github.com/tsenart/vegeta)

### GO Profiling and Application Performance

- [An Introduction to "go tool trace"](https://www.youtube.com/watch?v=V74JnrGTwKA)
- [https://golang.org/pkg/net/http/pprof/](https://golang.org/pkg/net/http/pprof/)
- [Creating call graph in golang](https://stackoverflow.com/a/31363995)
- [https://github.com/uber/go-torch](https://github.com/uber/go-torch)

It will show how pprof can be used to analyze both CPU and heap profile as well as demonstrate how to use go-torch to build Flamegraphs. This process makes it easier to identify hotspots in your service and gives you a better understanding of where time is spent.


### Get Password from Terminal Without showing Password

- [https://github.com/howeyc/gopass](https://github.com/howeyc/gopass)

### Plugins in Go

- [https://github.com/progrium/go-extpoints](https://github.com/progrium/go-extpoints)
- [https://github.com/kubernetes/heapster/blob/master/extpoints/extpoints.go](https://github.com/kubernetes/heapster/blob/master/extpoints/extpoints.go)


## Best Practices
- [Ashley McNamara + Brian Ketelsen. Go best practices.](https://www.youtube.com/watch?v=MzTcsI6tn-0)
