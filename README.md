# go-mithril
GopherJS bindings to MithrilJS

### Why do this?
> *Because I can*

Mithril.js is a very small and expressive client-side MVC framework. These Go
bindings are intended for Developers like me who welcome the strong typing and
semantics of Go, and want to use it to easily build great front-end experiences.

Mithril's small API size makes it a great target for defining such a binding.
However, it's expressiveness lead to some very JS-centric idioms that are harder
to employ in Go.

### Who is the target audience?

> *Me, essentially.*

To determine if go-mithril is a good fit for your project, ask if you have:

* Tolerance for lower performance introduced by Gopherjs and having to go
  through a translation.
* Developers with at least a passing knowledge of how mithril itself works,
* Developers with at least a passing knowledge of front-end technologies, and finally,
* Developers with a strong preference for writing Go over Javascript.

Perhaps as this project ages, sufficient documentation and abstraction solidity
will mean that knowledge of mithril itself will not be necessary.

### How mature is this project?
> *Not very.*

This is a very new project. A lot of the methods exposed in `mithril.go` have
not yet been tested, and those that have had not been tested extensively. If you
elect to use this project, do so with the understanding that the API is still
unstable, and breaking changes have not yet been ruled out.

### How do I use it?
> *Glad you asked.*

The most basic bindings are available in the package
`github.com/danverbraganza/go-mithril`.

For example:

```
m.Render(
    dom.GetWindow().Document().GetElementByID("container"),
    m.M("a[href='/index.html']", nil, "Home"))
)
```

produces the following output

```
<div id="container">
     <a href="index.html">Home</a>
</div>
```

For a look at a slightly larger example,
[here](https://github.com/danverbraganza/go-mithril/blob/master/examples/linkrotor/linkrotor.go)
is some code that is equivalent to the first example involving rotating links at
[http://mithril.js.org/index.html](http://mithril.js.org/index.html)

This example showcases simple creation of components, views and controllers,
making an asynchronous request, and binding a view to a model.

### Moria

The bindings provided in package `mithril` do not provide for an idiomatic Go
approach to crafting front-end code. The next step of this project is to create
the subpackage moria, which allows user to work with types and functions that
more closely suit Go.

### Can I contribute?
> *Yes, but*

At the moment, I'm really enjoying lone-wolfing on the project in my spare time.
Due to the constraints of professional committments I fear I will not be able to
effectively manage contributions in a timely manner. However, contributions will
be gratefully accepted as I able.

### Changelog

2016-04-16: Scrapped RenderWithForce in favour of adding the field to render.
Loosened some types in Render. Started work on moria.

2016-04-12: The basic bindings to Mithril have been completed. However, with no
tests, it's very hard to determine if it is correct.

2016-04-09: With a lot of creakiness and careful conversion between *js.Object
and interface{}, the first working example of this library has been launched. It
is nowhere near being production ready, however.
