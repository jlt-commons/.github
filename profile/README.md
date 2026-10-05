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
This organization's admins are members of jolt-lang too, and four jolt-lang projects
(instaparse, tapestry, duratom and mulog) have since moved here.

Core-team work lands here directly. Jolt's author has started eight projects in this
organization rather than moving them in later, among them
[ebb](https://github.com/jlt-commons/ebb), [ensemble](https://github.com/jlt-commons/ensemble)
and [writ](https://github.com/jlt-commons/writ). Anyone else can do the same, member or not.

Each project keeps its own maintainers, its own release cadence and its own review
protocol. What it gains by being here is shared ground: a documentation site built and
published for it, CI that checks it against a current Jolt, and conventions worked out
once instead of once per repository.

## Projects

Twenty-four so far. Six arrived by adoption, transferred rather than forked, so their
history and issues came with them and each kept its original maintainer. Four moved over
from jolt-lang. Fourteen were started here, eight of them by Jolt's author.

### Graphics and games

| project | what it is |
|---|---|
| [raylib-jlt](https://github.com/jlt-commons/raylib-jlt) | [raylib](https://www.raylib.com) bindings that call the system `libraylib` over its C ABI through `jolt.ffi`, with a keyword-argument drawing API on top. Its examples now live in raylib-jolt-demo. [Docs](https://jlt-commons.github.io/raylib-jlt/) |
| [raylib-jolt-demo](https://github.com/jlt-commons/raylib-jolt-demo) | 187 raylib examples built on raylib-jlt, each one its own small runnable project. [Docs](https://jlt-commons.github.io/raylib-jolt-demo/) |
| [raygui-jlt](https://github.com/jlt-commons/raygui-jlt) | 24 examples of raygui, raylib's immediate-mode GUI library, bound the same way. [Docs](https://jlt-commons.github.io/raygui-jlt/) |
| [raylib-ios](https://github.com/jlt-commons/raylib-ios) | raylib and SDL2 on a physical iPhone, as portable bytecode with no JIT, since iOS forbids generating code at run time. The platform: host loop, bindings, build and deploy tools. [Docs](https://jlt-commons.github.io/raylib-ios/) |
| [raylib-ios-demo](https://github.com/jlt-commons/raylib-ios-demo) | What runs on raylib-ios: 137 scenes, each a sub-project that builds an iPhone app of its own, plus a gallery app holding them all. [Docs](https://jlt-commons.github.io/raylib-ios-demo/) |
| [raylib-android](https://github.com/jlt-commons/raylib-android) | raylib on an Android phone as native arm64 code, with no JVM, Kotlin or Java anywhere in the app. Seventeen scenes under an owner loop of about thirty lines. [Docs](https://jlt-commons.github.io/raylib-android/) |
| [graviton](https://github.com/jlt-commons/graviton) | A physics game where you place gravitational attractors to steer a ship toward prizes and away from death zones. A Jolt and raylib port of a 2018 ClojureScript game, its field math checked by writ. |

### User interfaces

| project | what it is |
|---|---|
| [glitter-core](https://github.com/jlt-commons/glitter-core) | The natives-free two-thirds of glitter: the Replicant-style reconciler and `IRender`/`IMemory` protocols, with no toolkit dependency at all. What glitter, glitter-uikit, and uikit-demo all build on. [Docs](https://jlt-commons.github.io/glitter-core/) |
| [glitter](https://github.com/jlt-commons/glitter) | A [Replicant](https://github.com/cjohansen/replicant)-style GTK4 renderer built on glitter-core: one state atom, a pure `state -> hiccup` view, event handlers as data. [Docs](https://jlt-commons.github.io/glitter/) |
| [glitter-gl](https://github.com/jlt-commons/glitter-gl) | OpenGL geometry, matrices and shaders for glitter, plus a `:gl-area` widget to draw them in. [Docs](https://jlt-commons.github.io/glitter-gl/) |
| [glitter-uikit](https://github.com/jlt-commons/glitter-uikit) | the same renderer model driving native macOS `NSView` widgets through AppKit, rather than GTK4. [Docs](https://jlt-commons.github.io/glitter-uikit/) |
| [uikit-demo](https://github.com/jlt-commons/uikit-demo) | A demo of glitter-uikit: a hub of live example windows (counter, currency converter, live FX, particle toy) built as a real macOS app bundle. [Docs](https://jlt-commons.github.io/uikit-demo/) |
| [nexus-jolt](https://github.com/jlt-commons/nexus-jolt) | A Jolt port of [nexus](https://github.com/cjohansen/nexus): data-driven action/effect/placeholder dispatch, used today by the glitter family. [Docs](https://jlt-commons.github.io/nexus-jolt/) |
| [ftxui-jolt](https://github.com/jlt-commons/ftxui-jolt) | A reagent-style API over [FTXUI](https://github.com/ArthurSonzogni/FTXUI), the C++ terminal UI library: components as functions returning hiccup, rendered through FTXUI's own event loop, focus handling and mouse support. |

### Concurrency and state

| project | what it is |
|---|---|
| [ebb](https://github.com/jlt-commons/ebb) | A port of [missionary](https://github.com/leonoel/missionary): composable tasks and flows with real cancellation and glitch-free dataflow, running on Chez fibers. [Docs](https://jlt-commons.github.io/ebb/) |
| [ensemble](https://github.com/jlt-commons/ensemble) | Erlang processes and the OTP behaviours on Jolt's native fibers: links, monitors, selective receive, `gen_server`, `gen_statem` and supervisors. |
| [tapestry](https://github.com/jlt-commons/tapestry) | Structured concurrency, where a unit of work is a derefable fiber carrying its result, errors, timeouts and cancellation. A port of [teknql/tapestry](https://github.com/teknql/tapestry) onto `core.async`. |
| [duratom](https://github.com/jlt-commons/duratom) | A durable atom that writes every change through to a pluggable backend. A port of [jimpil/duratom](https://github.com/jimpil/duratom). |

### Libraries and ports

| project | what it is |
|---|---|
| [instaparse](https://github.com/jlt-commons/instaparse) | [instaparse](https://github.com/Engelberg/instaparse) on Jolt: parsers from EBNF or ABNF grammars, including left-recursive and ambiguous ones. |
| [mulog](https://github.com/jlt-commons/mulog) | The published [mulog](https://github.com/BrunoBonacci/mulog) 0.9.0, with the Java classes it bundles supplied by portable Jolt registrations. |
| [aws-api-jolt](https://github.com/jlt-commons/aws-api-jolt) | The unmodified [cognitect aws-api](https://github.com/cognitect-labs/aws-api) Maven release running on Jolt. It supplies an HTTP client and a host-class declaration, and nothing is forked. |
| [clj-to-ys](https://github.com/jlt-commons/clj-to-ys) | Translates Clojure source into idiomatic [YS (YAMLScript)](https://yamlscript.org), built on the instaparse port. |

### Checking and deciding

| project | what it is |
|---|---|
| [writ](https://github.com/jlt-commons/writ) | Checks plain Clojure against a spec of what the code is for: signatures, plus laws run through test.check. Built as a gate for code an LLM writes. |
| [lev](https://github.com/jlt-commons/lev) | A decision engine that answers typed questions about a state with calibrated probabilities, using small encoder models or a GGUF chat model through llama.cpp. |

Thirteen of these publish through [docs-engine](https://github.com/jlt-commons/docs-engine),
so none of them maintains a site generator of its own, and each site lives at
`jlt-commons.github.io/<repo>/` with search built in. The rest are recent enough that their
documentation is still the repo README. The org also keeps some shared tooling:
[setup-jolt](https://github.com/jlt-commons/setup-jolt) installs Jolt on a GitHub Actions
runner, and [ci-builds](https://github.com/jlt-commons/ci-builds) builds every project
against one Jolt version so a breaking release shows up the day it ships.

These tables are only what's hosted here. For everything in the wider Jolt ecosystem
(jolt-lang's own libraries, JVM and Clojure compatibility, docs and tooling), see
[awesome-jolt](https://github.com/jlt-commons/awesome-jolt), a community-maintained
curated list. [Its own site](https://jlt-commons.github.io/awesome-jolt/) publishes
through docs-engine too.

## Two ways a project gets here

**Adoption.** A Jolt project whose maintainer can no longer look after it, taken over so
the community keeps a working version. We ask the current owner first, every time.

**Incubation.** New work started here. Ports of widely used Clojure libraries, and new
libraries that belong beside the language rather than inside it. Fourteen projects came in
this way, eight of them started by Jolt's author. The bar is deliberately low: a real gap, and someone willing
to maintain it.

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
