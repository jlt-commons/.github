# jlt-commons

A community-led home for [Jolt](https://github.com/jolt-lang/jolt) libraries and tooling.

Jolt is a Clojure compiler built on Chez Scheme. This organization exists so that
useful Jolt libraries have somewhere to go when they outgrow one maintainer, and so
that new community work has a home without having to be an official project first.
It is modelled on [clj-commons](https://github.com/clj-commons), which has done the
same job for Clojure for years.

**This is not the official Jolt organization**, and it is complementary to it rather
than a competitor. [jolt-lang](https://github.com/jolt-lang) owns the language and its
standard library.

The split is the one Jolt's author, Dmitri Sotnikov, proposed when this organization was
raised on **#jolt**: the official org was starting to get crowded, so it keeps the bare
essentials and the rest moves to the commons. Some jolt-lang projects are expected to
move here on that basis.

Membership here is not a core-team recommendation of any particular library. The projects
are maintained by the people who brought them.

## Projects

| project | what it is |
|---|---|
| [raylib-jlt](https://github.com/jlt-commons/raylib-jlt) | 119 [raylib](https://www.raylib.com) examples, calling the system `libraylib` over its C ABI through `jolt.ffi`. [Docs](https://jlt-commons.github.io/raylib-jlt/) |
| [raygui-jlt](https://github.com/jlt-commons/raygui-jlt) | 24 examples of raygui, raylib's immediate-mode GUI library, bound the same way. [Docs](https://jlt-commons.github.io/raygui-jlt/) |
| [glitter](https://github.com/jlt-commons/glitter) | A [Replicant](https://github.com/cjohansen/replicant)-style GTK4 renderer: one state atom, a pure `state -> hiccup` view, and event handlers as data. [Docs](https://glitter.b12n.app/) |
| [glitter-gl](https://github.com/jlt-commons/glitter-gl) | OpenGL geometry, matrices and shaders for glitter, plus a `:gl-area` widget to draw them in. [Docs](https://glitter-gl.b12n.app/) |

All four arrived by adoption, transferred rather than forked, so their history and
issues came with them. Each keeps its original maintainer.

The two GTK projects still publish their documentation from where it was built before
they moved. Both are being brought onto
[docs-engine](https://github.com/jlt-commons/docs-engine), and their links change to
`jlt-commons.github.io` when that lands.

## Two ways a project gets here

**Adoption.** A Jolt project whose maintainer can no longer look after it, taken over so
the community keeps a working version. We ask the current owner first, every time.

**Incubation.** New community work. Ports of widely used Clojure libraries, and new
libraries the core team does not want to own. The bar is deliberately low: a real gap,
and someone willing to maintain it.

## Getting involved

You do not need to be a member to help. Open an issue or a pull request on any repo here.

- **Propose a project**, or volunteer to maintain one: [open an issue in `meta`](https://github.com/jlt-commons/meta/issues)
- **Read the rules**, both short: [governance](https://github.com/jlt-commons/meta/blob/main/GOVERNANCE.md) and [proposing a project](https://github.com/jlt-commons/meta/blob/main/PROPOSING.md)
- **Talk to us** on **#jolt** on the [Clojurians Slack](https://clojurians.net)
- **Use the docs engine.** Every project here publishes through
  [docs-engine](https://github.com/jlt-commons/docs-engine): write markdown and a short
  config file, and CI builds and deploys the site on merge.

New projects here are EPL-2.0, matching Jolt and Clojure. Adopted projects keep the
license they arrived with.
