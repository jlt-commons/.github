# jlt-commons

A shared home for [Jolt](https://github.com/jolt-lang/jolt) libraries and tooling.

Jolt is a Clojure compiler built on Chez Scheme. This organization is where the people
building on it publish together: libraries that have outgrown a single maintainer, ports
of Clojure libraries, and new work that would rather start with company than alone. It is
modelled on [clj-commons](https://github.com/clj-commons), which has done the same job
for Clojure for years.

[jolt-lang](https://github.com/jolt-lang) keeps the language and its standard library,
and everything growing around them lives here. That is the arrangement Jolt's author,
Dmitri Sotnikov, proposed when this organization was raised on **#jolt**: the language
org stays focused on the essentials, and the wider ecosystem gets one obvious place to be
found rather than being scattered across personal accounts. The two overlap on purpose.
This organization's admins are members of jolt-lang too, and some jolt-lang projects are
expected to move here.

Core-team work lands here directly. [ebb](https://github.com/jlt-commons/ebb) and
[raylib-android](https://github.com/jlt-commons/raylib-android) were both started in this
organization by Jolt's author rather than moved in later, with more expected. Anyone else
can do the same, member or not.

Each project keeps its own maintainers, its own release cadence and its own review
protocol. What it gains by being here is shared ground: a documentation site built and
published for it, CI that checks it against a current Jolt, and conventions worked out
once instead of once per repository.

## Projects

| project | what it is |
|---|---|
| [raylib-jlt](https://github.com/jlt-commons/raylib-jlt) | 119 [raylib](https://www.raylib.com) examples, calling the system `libraylib` over its C ABI through `jolt.ffi`. [Docs](https://jlt-commons.github.io/raylib-jlt/) |
| [raygui-jlt](https://github.com/jlt-commons/raygui-jlt) | 24 examples of raygui, raylib's immediate-mode GUI library, bound the same way. [Docs](https://jlt-commons.github.io/raygui-jlt/) |
| [glitter](https://github.com/jlt-commons/glitter) | A [Replicant](https://github.com/cjohansen/replicant)-style GTK4 renderer: one state atom, a pure `state -> hiccup` view, and event handlers as data. [Docs](https://jlt-commons.github.io/glitter/) |
| [glitter-gl](https://github.com/jlt-commons/glitter-gl) | OpenGL geometry, matrices and shaders for glitter, plus a `:gl-area` widget to draw them in. [Docs](https://jlt-commons.github.io/glitter-gl/) |
| [glitter-uikit](https://github.com/jlt-commons/glitter-uikit) | The same renderer model driving native macOS `NSView` widgets through AppKit, rather than GTK4. [Docs](https://jlt-commons.github.io/glitter-uikit/) |
| [raylib-ios](https://github.com/jlt-commons/raylib-ios) | raylib and SDL2 on a physical iPhone, as portable bytecode with no JIT, since iOS forbids generating code at run time. Seventeen scenes at 60 fps. [Docs](https://jlt-commons.github.io/raylib-ios/) |
| [raylib-android](https://github.com/jlt-commons/raylib-android) | raylib on an Android phone as native arm64 code, with no JVM, Kotlin or Java anywhere in the app. Seventeen scenes under an owner loop of about thirty lines |
| [ebb](https://github.com/jlt-commons/ebb) | A port of [missionary](https://github.com/leonoel/missionary): composable tasks and flows with real cancellation and glitch-free dataflow, running on Chez fibers |

Six of the eight arrived by adoption, transferred rather than forked, so their history
and issues came with them and each kept its original maintainer. raylib-android and ebb
were started here by Jolt's author.

Those six publish through [docs-engine](https://github.com/jlt-commons/docs-engine),
so none of them maintains a site generator of its own, and each site lives at
`jlt-commons.github.io/<repo>/`.

## Two ways a project gets here

**Adoption.** A Jolt project whose maintainer can no longer look after it, taken over so
the community keeps a working version. We ask the current owner first, every time.

**Incubation.** New work started here. Ports of widely used Clojure libraries, and new
libraries that belong beside the language rather than inside it. ebb and raylib-android
came in this way. The bar is deliberately low: a real gap, and someone willing to
maintain it.

## Getting involved

Everyone is welcome to help, member or not. Open an issue or a pull request on any repo here.

- **Propose a project**, or volunteer to maintain one: [open an issue in `meta`](https://github.com/jlt-commons/meta/issues)
- **Read the rules**, both short: [governance](https://github.com/jlt-commons/meta/blob/main/GOVERNANCE.md) and [proposing a project](https://github.com/jlt-commons/meta/blob/main/PROPOSING.md)
- **Talk to us** on **#jolt** on the [Clojurians Slack](https://clojurians.net)
- **Use the docs engine.** Any project here can publish through
  [docs-engine](https://github.com/jlt-commons/docs-engine): write markdown and a short
  config file, and CI builds and deploys the site on merge.

New projects here are EPL-2.0, matching Jolt and Clojure. Adopted projects keep the
license they arrived with.
