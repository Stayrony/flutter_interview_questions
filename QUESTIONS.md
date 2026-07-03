<a id="top"></a>

# Flutter Interview Questions

A curated question bank. Each table lists questions by topic — **click a question to jump to its answer** further down in this file. Use the "↑ Back to top" link under any answer to return.

**Levels:** 🟢 Junior · 🟡 Mid · 🔴 Senior

## What each level is expected to know

A rough guide to calibrate questions and self-assessment. Each level builds on the ones before it.

### 🟢 Junior

Can build screens and wire up basic behavior with guidance.

- **Dart basics:** variables (`var`/`final`/`const`), null safety (`?`, `!`, `??`, `late`), functions, named/positional params, classes, collections, `for`/`if` collection syntax.
- **Widgets:** stateless vs. stateful, common widgets (`Container`, `Row`/`Column`, `Stack`, `ListView`, `Text`, `Image`), `build` method, `BuildContext` basics.
- **State:** `setState` for local state; lifting state up.
- **Layout:** basic flex layout, padding/margin, alignment, `MediaQuery` basics.
- **Navigation:** `Navigator.push`/`pop`, named routes, passing arguments.
- **Async:** `Future`, `async`/`await`, `FutureBuilder`, basic HTTP calls and JSON parsing.
- **Tooling:** hot reload vs. restart, `pubspec.yaml` and adding packages, reading errors.

### 🟡 Mid

Works independently, makes sound design choices within a feature, writes tests.

- **Dart:** mixins, extensions, generics, enums with methods, streams, error handling.
- **State management:** confident with at least one solution (Provider/Riverpod/BLoC); knows `InheritedWidget`, `ChangeNotifier`, when to choose which.
- **Widgets/lifecycle:** `State` lifecycle (`initState`/`didChangeDependencies`/`dispose`), keys, `const` for performance, custom reusable widgets.
- **Async/concurrency:** `Stream` vs. `Future`, `StreamBuilder`, cancelling subscriptions, basic isolates/`compute`.
- **Performance:** avoiding unnecessary rebuilds, `const` constructors, `ListView.builder`.
- **Testing:** unit + widget tests, `WidgetTester`, mocking dependencies.
- **Architecture:** separating UI from logic, repositories, dependency injection, folder structure for a feature.
- **Platform:** basic platform channels, using plugins, handling permissions.

### 🔴 Senior

Owns architecture, mentors others, reasons about trade-offs and internals.

- **Framework internals:** the three trees (Widget/Element/RenderObject), element lifecycle, the frame pipeline (build→layout→paint→composite→raster), constraint model, rebuild/relayout/repaint boundaries.
- **Performance engineering:** profiling with DevTools, diagnosing UI- vs. raster-thread jank, `RepaintBoundary`, shader/Impeller considerations, image memory and list optimization.
- **Concurrency:** event loop, microtask vs. event queue, isolates and message passing, `TransferableTypedData`.
- **State management at scale:** trade-offs between approaches, provider lifecycle/`autoDispose`, minimizing rebuild scope, testability.
- **Architecture:** clean/layered architecture, feature-first structure, modularization into packages (monorepo/`melos`), error-handling strategy (exceptions vs. `Result`/`Either`), DI at scale.
- **Navigation:** declarative routing (Navigator 2.0 / `go_router`), deep linking, nested navigators.
- **Testing & quality:** golden tests, integration tests, CI, and setting testing standards for a team.
- **Leadership:** code review, technical decision-making, mentoring, balancing delivery with maintainability.

## Topics

- [Dart Language](#dart-language)
- [Core Concepts & Widgets](#core-concepts--widgets)
- [State Management](#state-management)
- [Navigation & Routing](#navigation--routing)
- [Async & Concurrency](#async--concurrency)
- [Animations](#animations)
- [Rendering Pipeline](#rendering-pipeline)
- [Performance](#performance)
- [Testing](#testing)
- [Networking & Data](#networking--data)
- [Platform & Native](#platform--native)
- [Architecture](#architecture)
- [Tooling & Build](#tooling--build)

---

## Dart Language

| # | Question | Level |
|---|----------|-------|
| 1 | [What is the difference between `final` and `const`?](#a1) | 🟢 |
| 2 | [What are null safety and the `?`, `!`, `late`, `??` operators?](#a2) | 🟢 |
| 3 | [What is the difference between named and positional parameters?](#a3) | 🟢 |
| 4 | [How does Dart handle single-threaded concurrency?](#a4) | 🟡 |
| 5 | [What are mixins and when would you use them?](#a5) | 🟡 |
| 36 | [How does Dart's garbage collection work?](#a36) | 🔴 |
| 37 | [What are `sync*` and `async*` generators?](#a37) | 🔴 |
| 63 | [`var` vs. `dynamic` vs. `Object`?](#a63) | 🟡 |
| 64 | [What are extension methods?](#a64) | 🟡 |
| 65 | [Factory constructor vs. named constructor?](#a65) | 🟡 |
| 66 | [What are the cascade (`..`) and spread (`...`) operators?](#a66) | 🟢 |
| 67 | [Records, sealed classes, and pattern matching (Dart 3)?](#a67) | 🔴 |
| 68 | [What are generics and why use them?](#a68) | 🟡 |
| 69 | [`extends` vs. `implements` vs. `with`; abstract class vs. interface?](#a69) | 🟡 |
| 70 | [What is a `typedef`?](#a70) | 🟢 |

## Core Concepts & Widgets

| # | Question | Level |
|---|----------|-------|
| 6 | [What is a Widget in Flutter?](#a6) | 🟢 |
| 7 | [Difference between `StatelessWidget` and `StatefulWidget`?](#a7) | 🟢 |
| 8 | [What is `BuildContext`?](#a8) | 🟡 |
| 9 | [What are Keys and when do you need them?](#a9) | 🔴 |
| 10 | [What is the difference between `const` and non-`const` widget constructors?](#a10) | 🟡 |
| 38 | [Explain the Element lifecycle (mounted, active, inactive, defunct).](#a38) | 🔴 |
| 39 | [When are `GlobalKey`s expensive, and what are the alternatives?](#a39) | 🔴 |
| 71 | [What are the `StatefulWidget` lifecycle methods?](#a71) | 🟡 |
| 72 | [What is the `mounted` property and why check it?](#a72) | 🟡 |
| 73 | [`MaterialApp` vs. `WidgetsApp`, and the role of `Scaffold`?](#a73) | 🟢 |
| 74 | [`Expanded` vs. `Flexible`?](#a74) | 🟡 |
| 75 | [`Container` vs. `SizedBox`?](#a75) | 🟢 |
| 76 | [What are `MediaQuery` and `SafeArea`?](#a76) | 🟢 |
| 77 | [How do you observe app lifecycle (`AppLifecycleState`)?](#a77) | 🟡 |
| 78 | [What is tree shaking?](#a78) | 🟡 |
| 79 | [How does Flutter's reconciliation (diffing) algorithm work?](#a79) | 🔴 |

## State Management

| # | Question | Level |
|---|----------|-------|
| 11 | [What is `setState` and what are its limitations?](#a11) | 🟢 |
| 12 | [What is an `InheritedWidget`?](#a12) | 🟡 |
| 13 | [Compare Provider, Riverpod, and BLoC.](#a13) | 🔴 |
| 14 | [What problem does BLoC solve and how does it work?](#a14) | 🟡 |
| 40 | [How does provider lifecycle and `autoDispose` work in Riverpod?](#a40) | 🔴 |
| 41 | [How do you avoid rebuilds with `Selector` / `context.select`?](#a41) | 🔴 |
| 53 | [Difference between ephemeral (local) state and app state?](#a53) | 🟢 |
| 54 | [Cubit vs. Bloc — when to use each?](#a54) | 🟡 |
| 55 | [`BlocProvider`, `BlocBuilder`, `BlocListener`, `BlocConsumer` — what's the difference?](#a55) | 🟡 |
| 56 | [`ChangeNotifier` vs. `ValueNotifier` vs. `ValueListenableBuilder`?](#a56) | 🟡 |
| 57 | [In Provider, difference between `context.read`, `context.watch`, `context.select`?](#a57) | 🟡 |
| 58 | [What Provider variants exist (`ChangeNotifierProvider`, `FutureProvider`, `ProxyProvider`…)?](#a58) | 🟡 |
| 59 | [What are the main Riverpod provider types?](#a59) | 🔴 |
| 60 | [How do you test a BLoC / Cubit?](#a60) | 🟡 |
| 61 | [What is unidirectional data flow and why does it matter?](#a61) | 🟡 |
| 62 | [How do you handle side effects (navigation, snackbars) in BLoC?](#a62) | 🔴 |

## Navigation & Routing

| # | Question | Level |
|---|----------|-------|
| 15 | [Difference between imperative Navigator 1.0 and declarative Navigator 2.0?](#a15) | 🔴 |
| 16 | [How do you pass data between routes?](#a16) | 🟢 |
| 17 | [What is a named route and how is it configured?](#a17) | 🟢 |
| 42 | [How do you implement deep linking?](#a42) | 🔴 |
| 43 | [How do nested navigators work (e.g. per-tab stacks)?](#a43) | 🔴 |
| 88 | [`push` vs. `pushReplacement` vs. `pushAndRemoveUntil`?](#a88) | 🟢 |
| 89 | [`Navigator` vs. `Router`?](#a89) | 🟡 |

## Async & Concurrency

| # | Question | Level |
|---|----------|-------|
| 18 | [What is the difference between `Future` and `Stream`?](#a18) | 🟢 |
| 19 | [What is an Isolate and when do you use one?](#a19) | 🔴 |
| 20 | [What does `async`/`await` actually do?](#a20) | 🟡 |
| 21 | [Difference between `FutureBuilder` and `StreamBuilder`?](#a21) | 🟡 |
| 44 | [Difference between the microtask queue and the event queue?](#a44) | 🔴 |
| 45 | [How do isolates communicate, and what can be sent between them?](#a45) | 🔴 |
| 85 | [What is a `StreamController`; single vs. broadcast streams?](#a85) | 🟡 |
| 86 | [`Future.wait`, `Future.any`, `Future.forEach`?](#a86) | 🟡 |
| 87 | [How do you handle errors in async code?](#a87) | 🟡 |

## Animations

| # | Question | Level |
|---|----------|-------|
| 80 | [What are `AnimationController`, `Ticker`, and `vsync`?](#a80) | 🟡 |
| 81 | [Implicit vs. explicit animations?](#a81) | 🟡 |
| 82 | [What is a `Tween`?](#a82) | 🟢 |
| 83 | [What is the `Hero` widget?](#a83) | 🟢 |
| 84 | [What is a `CustomPainter`?](#a84) | 🔴 |

## Rendering Pipeline

| # | Question | Level |
|---|----------|-------|
| 22 | [Explain the three trees: Widget, Element, RenderObject.](#a22) | 🔴 |
| 23 | [What happens during a frame in Flutter?](#a23) | 🔴 |
| 24 | [How does Flutter decide whether to rebuild, relayout, or repaint?](#a24) | 🔴 |
| 46 | [Explain Flutter's constraint model ("constraints go down, sizes go up").](#a46) | 🔴 |
| 47 | [What are slivers and how does `CustomScrollView` work?](#a47) | 🔴 |

## Performance

| # | Question | Level |
|---|----------|-------|
| 25 | [How do you reduce unnecessary widget rebuilds?](#a25) | 🟡 |
| 26 | [Why is `const` important for performance?](#a26) | 🟡 |
| 27 | [What is `RepaintBoundary` and when do you use it?](#a27) | 🔴 |
| 28 | [How do you diagnose jank?](#a28) | 🔴 |
| 48 | [What causes shader compilation jank and how do you fix it?](#a48) | 🔴 |
| 49 | [How do you optimize long lists and image memory?](#a49) | 🔴 |

## Testing

| # | Question | Level |
|---|----------|-------|
| 29 | [What are the three types of Flutter tests?](#a29) | 🟢 |
| 30 | [What is a `WidgetTester` and `pumpWidget`?](#a30) | 🟡 |
| 31 | [Difference between `pump` and `pumpAndSettle`?](#a31) | 🟡 |
| 50 | [What are golden tests and when do you use them?](#a50) | 🔴 |

## Networking & Data

| # | Question | Level |
|---|----------|-------|
| 90 | [How do you make HTTP requests in Flutter?](#a90) | 🟢 |
| 91 | [How do you persist data locally? What are the options?](#a91) | 🟡 |
| 92 | [How do you handle offline mode and caching?](#a92) | 🔴 |
| 93 | [How do you store sensitive data securely?](#a93) | 🔴 |

## Platform & Native

| # | Question | Level |
|---|----------|-------|
| 32 | [What is a platform channel?](#a32) | 🟡 |
| 33 | [Difference between `MethodChannel`, `EventChannel`, and `BasicMessageChannel`?](#a33) | 🔴 |

## Architecture

| # | Question | Level |
|---|----------|-------|
| 34 | [How would you structure a large Flutter app?](#a34) | 🔴 |
| 35 | [What is dependency injection and how is it done in Flutter?](#a35) | 🟡 |
| 51 | [How do you handle errors across layers (Result / `Either`)?](#a51) | 🔴 |
| 52 | [How and why would you modularize an app into packages?](#a52) | 🔴 |

## Tooling & Build

| # | Question | Level |
|---|----------|-------|
| 94 | [Hot reload vs. hot restart?](#a94) | 🟢 |
| 95 | [What are the build modes: debug, profile, release?](#a95) | 🟢 |
| 96 | [JIT vs. AOT compilation?](#a96) | 🔴 |
| 97 | [What are DevTools and the Flutter Inspector?](#a97) | 🟡 |
| 98 | [What is `pubspec.yaml`; packages vs. plugins?](#a98) | 🟢 |
| 99 | [`main()` vs. `runApp()`?](#a99) | 🟢 |

---

# Answers

<a id="a1"></a>
### 1. Difference between `final` and `const`?

`final` means the variable can be assigned **once** but its value is determined at **runtime**. `const` means the value is a **compile-time constant** — fully known before the program runs, and deeply immutable. Every `const` is implicitly `final`, but not vice versa. `const` objects are canonicalized (identical instances are shared).

```dart
final now = DateTime.now();   // OK: runtime value
const pi = 3.14;              // OK: compile-time constant
// const bad = DateTime.now(); // Error: not known at compile time
```

[↑ Back to top](#top)

<a id="a2"></a>
### 2. Null safety and the `?`, `!`, `late`, `??` operators

With sound null safety, types are non-nullable by default. `String` cannot be null; `String?` can.
- `?` — marks a type as nullable (`int? x`).
- `!` — null assertion; throws if the value is actually null (`x!`).
- `??` — if-null operator, provides a fallback (`x ?? 0`).
- `??=` — assign only if currently null.
- `late` — a non-nullable variable initialized after declaration; throws if read before assignment.

[↑ Back to top](#top)

<a id="a3"></a>
### 3. Named vs. positional parameters

Positional parameters are matched by order; named parameters are matched by name and improve readability. Named parameters are wrapped in `{}` and can be marked `required`; optional positional parameters use `[]`.

```dart
void a(int x, int y) {}                 // positional
void b({required int x, int y = 0}) {}  // named, one required
void c(int x, [int y = 0]) {}           // optional positional
```

[↑ Back to top](#top)

<a id="a4"></a>
### 4. How does Dart handle single-threaded concurrency?

Dart runs your code on a single thread with an **event loop**. Async work (I/O, timers, futures) is scheduled onto a queue and processed when the current synchronous work finishes — so nothing blocks the thread while waiting. For true parallelism (CPU-heavy work) you use **Isolates**, which have their own memory and event loop and communicate via message passing.

[↑ Back to top](#top)

<a id="a5"></a>
### 5. Mixins and when to use them

A mixin lets you reuse a class's methods/fields across multiple class hierarchies without inheritance. You add behavior with `with`. Use them for cross-cutting, stateless-ish behavior shared by unrelated classes (e.g. `SingleTickerProviderStateMixin`). Constrain a mixin with `on` to require a superclass.

```dart
mixin Logger { void log(String m) => print(m); }
class Service with Logger {}
```

[↑ Back to top](#top)

<a id="a6"></a>
### 6. What is a Widget?

A widget is an **immutable description of part of the UI** at a point in time. Widgets are cheap configuration objects, not the actual rendered pixels. Flutter builds a tree of widgets; the framework inflates them into Elements and RenderObjects that do the real work. Everything is a widget — layout, styling, gestures, even the app itself.

[↑ Back to top](#top)

<a id="a7"></a>
### 7. `StatelessWidget` vs. `StatefulWidget`

`StatelessWidget` has no mutable state — its appearance depends only on its constructor inputs; it rebuilds only when a parent passes new configuration. `StatefulWidget` holds mutable state in a companion `State` object that persists across rebuilds; calling `setState` marks it dirty and triggers a rebuild. Use stateful only when the widget must change over its lifetime independent of its parent.

[↑ Back to top](#top)

<a id="a8"></a>
### 8. What is `BuildContext`?

`BuildContext` is a handle to the location of a widget in the **Element tree**. It is actually the widget's `Element`. You use it to look up inherited widgets (`Theme.of(context)`), find ancestors/descendants, and navigate. Because it's tied to a position in the tree, using a stale or wrong-level context is a common source of bugs (e.g. showing a dialog with a context above the `Navigator`).

[↑ Back to top](#top)

<a id="a9"></a>
### 9. Keys and when you need them

Keys preserve widget/element **identity** when the framework diffs the tree. You usually don't need them, but you do when reordering, adding, or removing items in a list of **stateful** widgets of the **same type** — without a key, Flutter may match the wrong element and state "jumps" to the wrong item. `ValueKey`, `ObjectKey`, and `UniqueKey` are local keys; `GlobalKey` gives access to state/element across the tree (use sparingly — it's expensive).

[↑ Back to top](#top)

<a id="a10"></a>
### 10. `const` vs. non-`const` widget constructors

A `const` widget constructor produces a canonicalized, compile-time instance. When Flutter rebuilds a parent, a `const` child is the **same object**, so the framework can short-circuit and skip rebuilding that subtree. Non-`const` widgets are re-created on every build. Prefer `const` constructors wherever inputs are compile-time constant — it's one of the cheapest performance wins.

[↑ Back to top](#top)

<a id="a11"></a>
### 11. `setState` and its limitations

`setState` marks the `State` object dirty so the framework rebuilds it on the next frame. It's simple and built-in, ideal for local, ephemeral UI state. Limitations: it only rebuilds that widget's subtree (not shared state across the tree), it doesn't separate business logic from UI, and it doesn't scale for app-wide state — that's where Provider/Riverpod/BLoC come in. Calling it after `dispose` or with heavy synchronous work inside is a common mistake.

[↑ Back to top](#top)

<a id="a12"></a>
### 12. What is an `InheritedWidget`?

`InheritedWidget` propagates data **down** the tree efficiently and lets descendants rebuild when that data changes. Widgets register a dependency via `dependOnInheritedWidgetOfExactType` (usually through a static `.of(context)`). It's the primitive under `Theme`, `MediaQuery`, and most state-management libraries (Provider is a thin wrapper over it).

[↑ Back to top](#top)

<a id="a13"></a>
### 13. Provider vs. Riverpod vs. BLoC

- **Provider** — a lightweight wrapper over `InheritedWidget`; exposes objects/`ChangeNotifier`s to the tree. Simple, but depends on `BuildContext` and can be verbose for complex graphs.
- **Riverpod** — a rewrite of Provider that is compile-safe, context-independent, and testable; providers are global and composable. Good default for new apps.
- **BLoC** — enforces a unidirectional events→states stream pattern. More boilerplate, but excellent for large teams needing strict structure and testability.

Choice depends on team size, complexity, and preference for explicit structure vs. minimal boilerplate.

<details><summary>🔍 Senior deep-dive</summary>

A trade-off matrix seniors are expected to reason through:

| Dimension | Provider | Riverpod | BLoC / Cubit |
|-----------|----------|----------|--------------|
| Foundation | `InheritedWidget` wrapper | Independent (no `BuildContext` needed) | Streams + `InheritedWidget` (`flutter_bloc`) |
| Boilerplate | Low | Low–medium | Medium–high (events/states) |
| Compile-safety | Runtime `ProviderNotFoundException` | Compile-time; no runtime lookup errors | Typed events/states |
| Testability | Good (needs a widget/pumped context sometimes) | Excellent (`ProviderContainer`, no widget tree) | Excellent (`bloc_test`, pure Dart) |
| Structure enforced | Little | Some | Strong, unidirectional |
| Where it strains | `ProxyProvider` graphs, context dependence, `read`/`watch` misuse | Learning curve; more concepts (`family`, `autoDispose`, notifiers) | Ceremony for trivial state; overkill for local UI |

Decision guidance: **Cubit/Bloc** when you want enforced unidirectional flow, a traceable event log, and strict testability across a large team. **Riverpod** as a modern default for new apps — compile-safe, context-free, composable, easy to test. **Provider** for smaller apps or when you want the lightest thing over `InheritedWidget`. They're not mutually exclusive — Cubit for feature state + Provider/Riverpod for DI is common.

The senior point: the *pattern* (unidirectional flow, separating ephemeral vs. app state, keeping rebuild scope small) matters more than the library. Interviewers probe whether you can justify a choice against constraints, not recite one library.

</details>

[↑ Back to top](#top)

<a id="a14"></a>
### 14. What problem does BLoC solve and how does it work?

BLoC (Business Logic Component) separates business logic from the UI using streams. The UI dispatches **events**; the BLoC processes them and emits **states**; the UI rebuilds from states via `BlocBuilder`/`StreamBuilder`. This gives a predictable, unidirectional data flow that is easy to test (feed events, assert emitted states) and reuse across platforms.

[↑ Back to top](#top)

<a id="a15"></a>
### 15. Navigator 1.0 (imperative) vs. 2.0 (declarative)

1.0 is **imperative**: you `push`/`pop` routes on a stack. Simple, but hard to synchronize with app state or deep links/web URLs. 2.0 is **declarative**: you supply a list of pages (`Navigator(pages: [...])`) derived from app state, so navigation is a function of state. 2.0 (often via `go_router`) handles deep linking, web URLs, and complex flows better, at the cost of more setup.

<details><summary>🔍 Senior deep-dive</summary>

The Router API (2.0) has four collaborators feeding the `Router` widget:

- **`RouteInformationProvider`** — surfaces the current route info from the platform (initial deep link, browser URL changes, new intents).
- **`RouteInformationParser`** — `parseRouteInformation` turns a URL string into a typed app-state object (`configuration`); `restoreRouteInformation` does the reverse so the browser URL stays in sync.
- **`RouterDelegate`** — the heart: `build` constructs a `Navigator(pages: [...])` from your app state, `setNewRoutePath` applies a parsed configuration, and `popRoute` handles back. It's a `Listenable` — you `notifyListeners()` and the Navigator's page list is rebuilt.
- **`BackButtonDispatcher`** — routes the Android system back button to the delegate.

The mental model: **navigation stack = pure function of app state.** You mutate state and the page list re-derives, rather than imperatively pushing. This is what makes web URLs, browser back/forward, and deep links "just work" — they're all the same code path (state → pages).

Why people reach for **`go_router`**: raw Navigator 2.0 is verbose and error-prone (implementing a correct delegate/parser by hand is a lot). `go_router` implements those four pieces for you, giving declarative path-based routes, typed params, redirects (auth guards), nested/`ShellRoute` navigation, and deep-link handling — while still being Router-API under the hood. Senior interviewers want you to explain *why* 2.0 exists (state-driven, URL-syncable) and that `go_router` is the pragmatic way to consume it.

</details>

[↑ Back to top](#top)

<a id="a16"></a>
### 16. Passing data between routes

Pass data forward via the route's widget constructor (or `settings.arguments`), and return data back through the `Future` from `push`:

```dart
final result = await Navigator.push(
  context,
  MaterialPageRoute(builder: (_) => DetailPage(item: item)),
);
// on the detail page: Navigator.pop(context, selectedValue);
```

[↑ Back to top](#top)

<a id="a17"></a>
### 17. Named routes

Named routes map string names to builders, centralizing navigation config.

```dart
MaterialApp(
  routes: {
    '/': (_) => HomePage(),
    '/details': (_) => DetailsPage(),
  },
);
Navigator.pushNamed(context, '/details', arguments: id);
```

Good for small apps; for deep linking and web, prefer `onGenerateRoute` or `go_router`.

[↑ Back to top](#top)

<a id="a18"></a>
### 18. `Future` vs. `Stream`

A `Future` represents a **single** asynchronous value that completes once (success or error). A `Stream` is a **sequence** of asynchronous events over time (zero or many), which you listen to. Use a `Future` for one-shot operations (an HTTP GET); use a `Stream` for ongoing data (websocket messages, sensor updates, user input events).

[↑ Back to top](#top)

<a id="a19"></a>
### 19. Isolates

An Isolate is an independent worker with its **own memory heap and event loop** — Dart's mechanism for true parallelism. Isolates don't share memory; they communicate by passing messages over ports. Use one for CPU-heavy work (parsing large JSON, image processing) to avoid blocking the UI isolate. `compute()` is a convenience wrapper for a one-off isolate task.

<details><summary>🔍 Senior deep-dive</summary>

**Isolate vs. thread:** a thread shares memory with its peers (needing locks); an isolate has a **private heap** and communicates only by message passing, so there are **no shared-memory races and no locks** by design. That's the whole safety model.

**When NOT to use one:** isolates don't help with I/O-bound work — network/file waits already don't block the event loop (async does that). Reach for an isolate only for **CPU-bound** work that would otherwise stall frame production: large JSON decode + model mapping, image/crypto/compression, parsing big files.

**Cost & granularity:** spawning has real overhead (new heap, startup) and every message is **copied** (except `TransferableTypedData` and immutables). So many tiny messages are worse than a few big ones. `compute()` spawns, runs one top-level function, returns once, and tears down — perfect for one-shot work but wasteful if called repeatedly in a loop; for sustained work keep a long-lived isolate with a port, or use a pool.

**Modern APIs:**
- `Isolate.run(fn)` (Dart 2.19+) — cleaner one-shot than `compute`, no `SendPort` boilerplate.
- **Isolate groups** — isolates spawned from the same code share runtime/JITed code and start faster.
- Long-lived worker: spawn once, exchange requests/responses over a `SendPort`, `kill` when done.

Follow-ups seniors get: "why doesn't awaiting an HTTP call need an isolate?" (event loop, not blocking) and "why can't I send a closure that captures state?" (it may reference non-sendable objects; only sendable messages cross).

</details>

[↑ Back to top](#top)

<a id="a20"></a>
### 20. What does `async`/`await` do?

`async` marks a function that returns a `Future`. `await` suspends the function until the awaited `Future` completes, then resumes with its value — without blocking the thread, other events keep processing meanwhile. It's syntactic sugar over `Future.then` chains that makes async code read like synchronous code. Errors from awaited futures surface as normal exceptions you can `try/catch`.

[↑ Back to top](#top)

<a id="a21"></a>
### 21. `FutureBuilder` vs. `StreamBuilder`

Both rebuild UI from async data via an `AsyncSnapshot`. `FutureBuilder` subscribes to a single `Future` (one result). `StreamBuilder` subscribes to a `Stream` and rebuilds on each emitted event. Common pitfall: creating the future/stream **inside** `build` re-triggers it on every rebuild — create it in `initState` or a state holder instead.

[↑ Back to top](#top)

<a id="a22"></a>
### 22. The three trees

- **Widget tree** — immutable configuration; rebuilt frequently and cheaply.
- **Element tree** — the mutable, long-lived instantiation of widgets; tracks state, position, and the link between widgets and render objects. Elements are reused across rebuilds when the widget type and key match.
- **RenderObject tree** — handles layout, painting, and hit-testing (the actual pixels).

Flutter keeps these in sync: when a widget changes, the framework diffs it against the element; if compatible, it updates in place; otherwise it rebuilds that subtree.

[↑ Back to top](#top)

<a id="a23"></a>
### 23. What happens during a frame?

On each frame (driven by the vsync signal), Flutter runs the pipeline: **build** (run dirty widgets' `build` methods) → **layout** (compute sizes/positions, parent passes constraints down, children pass sizes up) → **paint** (record paint commands into layers) → **composite** (assemble layers) → **rasterize** (the GPU/raster thread turns layers into pixels). Keeping each phase under the frame budget (~16ms at 60fps) avoids jank.

<details><summary>🔍 Senior deep-dive</summary>

The full sequence, driven by `SchedulerBinding` on the vsync tick, has more phases than the summary:

1. **Animation / transient callbacks** — tickers fire; `AnimationController`s advance and mark dependents dirty.
2. **Microtasks** drain.
3. **Build (`buildScope`)** — `WidgetsBinding.drawFrame` rebuilds dirty elements. Dirty elements are held in a list sorted by **depth** so parents build before children (a parent may re-configure a child, avoiding double work). `BuildOwner` tracks the dirty list.
4. **Layout (`flushLayout`)** — `RenderObject`s marked `needsLayout` re-run `performLayout`. **Relayout boundaries** stop `markNeedsLayout` from bubbling to the root: a node is a boundary when its size can't affect its parent (`parentUsesSize == false`, tight constraints, or `sizedByParent`), so only the subtree below re-lays out.
5. **Compositing bits** update (which layers need updating).
6. **Paint (`flushPaint`)** — nodes marked `needsPaint` re-record into a `PictureLayer`. **Repaint boundaries** (`RepaintBoundary`) give a subtree its own layer so its repaints don't dirty siblings.
7. **Compositing** — the `Layer` tree is flattened into a `Scene`.
8. **Semantics** flush (for accessibility).
9. **Rasterization** — handed to the **raster thread**; Impeller/Skia turns the scene into GPU commands. This is a *separate thread*, which is why "UI jank" and "raster jank" are diagnosed differently.

Two threads matter: the **UI (Dart) thread** runs steps 1–8; the **raster thread** runs step 9. A frame is late if *either* misses the budget (~16.6ms @ 60Hz, ~8.3ms @ 120Hz). Follow-up interviewers love: "which thread does `RepaintBoundary` help?" (raster — fewer/smaller layers to re-rasterize) and "does `const` help layout or build?" (build — skips re-instantiation and short-circuits the diff).

</details>

[↑ Back to top](#top)

<a id="a24"></a>
### 24. Rebuild vs. relayout vs. repaint

These are decoupled for efficiency. `setState`/new config marks an element **dirty** → rebuild. A rebuild triggers **layout** only if constraints/size-affecting properties changed (a render object marks itself `needsLayout`). It triggers **paint** only if visual properties changed (`needsPaint`). Flutter also uses **relayout boundaries** and **repaint boundaries** so changes don't propagate further up the tree than necessary.

<details><summary>🔍 Senior deep-dive</summary>

The three are genuinely independent dirty flags on the `RenderObject`: `_needsLayout`, `_needsPaint`, `_needsCompositingBitsUpdate`. Key consequences:

- **A rebuild need not relayout.** Changing a `Text`'s color rebuilds the widget and marks `needsPaint`, but the render object's size is unchanged → **no** layout. Changing font size marks `needsLayout` → layout **and** paint.
- **`markNeedsLayout` bubbles up to the nearest relayout boundary, not the root.** A boundary exists when the child's size can't change the parent's layout (tight constraints, `parentUsesSize: false`, or `sizedByParent`). Inside a `SizedBox(width/height)` the child is a boundary, so its internal changes never relayout the ancestors.
- **`markNeedsPaint` bubbles to the nearest repaint boundary.** Without one, a repaint can force a large composited layer to re-rasterize.
- **Layout runs before paint**, always, in a single pass — there is no measure/arrange two-pass like some frameworks; constraints down + sizes up happens once.

Practical senior insight: over-`setState`ing a huge subtree is often *not* the layout/paint cost you fear — if children are `const` and sizes don't change, the framework short-circuits most of it. The real cost is usually rebuilding expensive `build` methods; fix that with smaller widgets and boundaries, not by fighting layout.

</details>

[↑ Back to top](#top)

<a id="a25"></a>
### 25. Reducing unnecessary rebuilds

- Use `const` constructors so subtrees are skipped.
- Push state as low in the tree as possible; keep rebuild scopes small.
- Split large `build` methods into smaller widgets rather than helper methods.
- Use selective listening (`context.select`, `Consumer`, `BlocBuilder`'s `buildWhen`) so only affected widgets rebuild.
- Cache expensive objects outside `build`.

[↑ Back to top](#top)

<a id="a26"></a>
### 26. Why `const` matters for performance

`const` widgets are instantiated once and canonicalized, so on rebuild the framework sees the **same object reference** and can skip rebuilding, laying out, and painting that subtree entirely. It also reduces GC pressure by avoiding repeated allocations. It's a near-free optimization the analyzer even suggests.

[↑ Back to top](#top)

<a id="a27"></a>
### 27. `RepaintBoundary`

`RepaintBoundary` isolates a subtree into its own compositing layer so that repaints inside it don't force the rest of the screen to repaint (and vice versa). Use it around frequently-animating content (e.g. an animation over a static background) to limit repaint cost. Overusing it wastes memory on extra layers, so apply it where profiling shows repaint churn.

[↑ Back to top](#top)

<a id="a28"></a>
### 28. Diagnosing jank

Use Flutter DevTools: the **Performance** view shows frame timeline and which frames blew the budget, distinguishing UI-thread vs. raster-thread jank. Enable "Track widget rebuilds" to find over-rebuilding widgets, and the "Repaint Rainbow" / "Performance Overlay" to spot excessive repaints. Profile in **profile mode** (not debug), then fix the specific phase (build/layout/raster) that's slow.

<details><summary>🔍 Senior deep-dive</summary>

A repeatable methodology, not just "open DevTools":

1. **Always measure in profile mode on a real, low-end device.** Debug is JIT + asserts and is not representative; emulators hide GPU cost.
2. **Identify the thread.** In the Performance Overlay, two bars: top = **raster (GPU)** thread, bottom = **UI (Dart)** thread. Red bars tell you *where* the budget was blown.
   - **UI-thread jank** → too much work in `build`/layout: heavy synchronous work, giant rebuilds, expensive layout (unbounded/`IntrinsicHeight`), JSON parsing on the UI isolate. Fixes: `const`, smaller rebuild scope, move CPU work to an isolate/`compute`, avoid `Opacity`/`saveLayer` where a cheaper widget works.
   - **Raster-thread jank** → too much for the GPU: large/overlapping layers, `saveLayer` (from `Opacity`, `ShaderMask`, clips with anti-alias), many `RepaintBoundary`s, huge images. Fixes: `cacheWidth`/`cacheHeight`, `RepaintBoundary` around animating content, replace `Opacity` with `AnimatedOpacity`/`FadeTransition` or opacity in the paint.
3. **Zoom into the flame chart** for the janky frame to see the exact expensive call (`buildScope`, a specific `performLayout`, `saveLayer`).
4. **First-run stutter that only happens once** → shader compilation jank (see #48), not steady-state cost.
5. **Confirm the fix by re-profiling** — count frames over budget before/after, don't eyeball it.

Common root causes seniors should name instantly: rebuilding above the widget that actually changed, missing `const`, `ListView` (not `.builder`) with many children, unbounded images, and `saveLayer`-triggering widgets in a scroll/animation.

</details>

[↑ Back to top](#top)

<a id="a29"></a>
### 29. Three types of Flutter tests

- **Unit tests** — verify a single function/class/method in isolation; no UI. Fastest.
- **Widget tests** — render a single widget in a test environment and interact with it (`WidgetTester`); verify UI and behavior without a device.
- **Integration tests** — run the full app on a device/emulator and test end-to-end flows, including performance. Slowest but highest fidelity.

[↑ Back to top](#top)

<a id="a30"></a>
### 30. `WidgetTester` and `pumpWidget`

`WidgetTester` is the harness for widget tests; it lets you build widgets, tap/drag, and inspect the tree via `Finder`s. `tester.pumpWidget(widget)` inflates and renders a widget as the root of the test app, triggering a single frame. Subsequent `tester.pump()` calls trigger additional frames to advance animations/rebuilds.

[↑ Back to top](#top)

<a id="a31"></a>
### 31. `pump` vs. `pumpAndSettle`

`pump()` schedules and renders a **single** frame (optionally after a duration). `pumpAndSettle()` repeatedly pumps frames until there are **no more scheduled frames** (animations finished) or a timeout. Use `pump` for controlled, step-by-step frame advancement; use `pumpAndSettle` to wait for animations/transitions to complete — but avoid it with infinite animations (it will time out).

[↑ Back to top](#top)

<a id="a32"></a>
### 32. What is a platform channel?

A platform channel is the bridge for calling **native platform code** (Kotlin/Java on Android, Swift/Obj-C on iOS) from Dart and vice versa. Messages are serialized (via a codec) and passed asynchronously across the boundary. It's how plugins access device features Flutter doesn't expose directly (Bluetooth, sensors, native SDKs).

[↑ Back to top](#top)

<a id="a33"></a>
### 33. `MethodChannel` vs. `EventChannel` vs. `BasicMessageChannel`

- **MethodChannel** — request/response method invocations (returns a `Future`). Most common.
- **EventChannel** — a continuous **stream** of events from native to Dart (e.g. sensor updates, connectivity changes).
- **BasicMessageChannel** — bidirectional passing of arbitrary messages with a custom codec; for continuous two-way messaging.

[↑ Back to top](#top)

<a id="a34"></a>
### 34. Structuring a large Flutter app

Common approaches: **feature-first** (group by feature module, each with its own presentation/domain/data layers) is usually preferred over **layer-first** at scale. Apply a layered/clean architecture: separate presentation (widgets + state), domain (entities, use cases), and data (repositories, data sources). Keep dependencies pointing inward, inject them, and put shared code in a `core`/`common` module. Choose one state-management approach consistently.

[↑ Back to top](#top)

<a id="a35"></a>
### 35. Dependency injection in Flutter

DI supplies a class's dependencies from outside rather than constructing them internally, improving testability and decoupling. In Flutter it's done via: constructor injection (simplest), `InheritedWidget`/Provider/Riverpod to expose objects down the tree, or a service locator like `get_it`. Combine with mockable interfaces so tests can substitute fakes.

[↑ Back to top](#top)

<a id="a36"></a>
### 36. How does Dart's garbage collection work?

Dart uses a **generational, tracing garbage collector** tuned for the "most objects die young" pattern common in UI code (widgets rebuilt every frame). It has two generations: a fast **young space** collected by a scavenger (cheap, copying collector) and an **old space** collected by a mark-sweep/mark-compact collector. Short-lived allocations are reclaimed quickly and cheaply; survivors are promoted to old space. This is why avoiding needless allocations in `build` (e.g. via `const`) reduces GC pressure and jank. Each isolate has its own heap and GC.

[↑ Back to top](#top)

<a id="a37"></a>
### 37. `sync*` and `async*` generators

Generator functions produce sequences lazily using `yield`.
- `sync*` returns an `Iterable`; values are produced on demand as the consumer iterates.
- `async*` returns a `Stream`; values are produced asynchronously over time.
- `yield` emits one value; `yield*` delegates to another iterable/stream.

```dart
Iterable<int> countTo(int n) sync* { for (var i = 1; i <= n; i++) yield i; }
Stream<int> ticks(int n) async* { for (var i = 0; i < n; i++) yield i; }
```

[↑ Back to top](#top)

<a id="a38"></a>
### 38. Element lifecycle (mounted, active, inactive, defunct)

An `Element` moves through defined states:
- **initial** → created but not yet mounted.
- **active** — mounted in the tree; `mounted == true`; can rebuild and its `RenderObject` is attached.
- **inactive** — removed from the tree but retained temporarily (e.g. during a `GlobalKey` reparent within the same frame). If it isn't reactivated before the frame ends, it's disposed.
- **defunct** — permanently unmounted; its `State.dispose()` has run and it will never rebuild.

This is why you must not call `setState` on a disposed widget, and why you check `mounted` after an `await` before using `context`.

[↑ Back to top](#top)

<a id="a39"></a>
### 39. When are `GlobalKey`s expensive, and alternatives?

`GlobalKey`s let you access an element/state from anywhere and preserve state when moving a subtree across the tree (reparenting). They're costly because the framework maintains a global registry, reparenting forces layout work, and holding a `GlobalKey`'s state can cause memory/logic leaks if misused. Overuse (e.g. one per list item) is an anti-pattern. Alternatives: pass data via constructors, lift state up, use `ValueKey`/`ObjectKey` for identity in lists, use callbacks or a state-management solution instead of reaching into another widget's state. Reserve `GlobalKey` for genuine cases like `Form` access or preserving state across a reparent.

[↑ Back to top](#top)

<a id="a40"></a>
### 40. Provider lifecycle and `autoDispose` in Riverpod

A Riverpod provider is initialized lazily the first time it's read and its value is cached. By default it stays alive for the app's lifetime. `.autoDispose` changes that: when the last listener stops listening, the provider's state is disposed and re-created on next use — good for per-screen state to avoid leaks. `ref.onDispose` registers cleanup (cancel subscriptions/timers), and `ref.keepAlive()` can pin an autoDispose provider after an expensive load. `ref.watch` rebuilds on change; `ref.read` reads once; `ref.listen` runs side effects.

[↑ Back to top](#top)

<a id="a41"></a>
### 41. Avoiding rebuilds with `Selector` / `context.select`

By default a `Consumer`/`context.watch` rebuilds whenever the whole model notifies. `Selector` (Provider) and `context.select` let a widget subscribe to a **derived slice** of state and rebuild only when that slice changes (by `==`):

```dart
final userName = context.select<UserModel, String>((m) => m.name);
```

This minimizes rebuild scope. The selected value should be equatable so unchanged slices don't trigger rebuilds. BLoC's equivalent is `buildWhen` / `BlocSelector`.

[↑ Back to top](#top)

<a id="a42"></a>
### 42. Implementing deep linking

Deep linking maps an external URL (custom scheme or Universal/App Links) to in-app navigation. You register the scheme/domain natively (Android intent filters + `assetlinks.json`, iOS associated domains + `apple-app-site-association`), then map incoming URIs to routes in Dart. With `go_router` (or Navigator 2.0's `RouteInformationParser`/`RouterDelegate`), the path is parsed into typed routes and the navigation stack is rebuilt from app state. Handle both cold-start links (initial route) and links received while running.

[↑ Back to top](#top)

<a id="a43"></a>
### 43. Nested navigators (per-tab stacks)

A nested `Navigator` maintains an independent route stack inside a subtree — commonly one `Navigator` per bottom-nav tab, so each tab preserves its own history and back behavior. Wrap each tab in its own `Navigator` (or use `go_router`'s `StatefulShellRoute` / `IndexedStack` to keep tab state alive). Care points: handling the system back button (pop the inner navigator before the outer one via `WillPopScope`/`PopScope`), and deciding whether tab state persists when switching tabs.

[↑ Back to top](#top)

<a id="a44"></a>
### 44. Microtask queue vs. event queue

Dart's event loop drains **two** queues. The **microtask queue** has higher priority and is fully emptied before the next event is processed; it's used for short internal continuations (e.g. `Future.then` callbacks, `scheduleMicrotask`). The **event queue** handles external events: I/O, timers, gestures, `Timer`, and `Future`s completed from outside. After each event, all pending microtasks run before the next event. Scheduling heavy work as microtasks can starve the event queue and block I/O/UI.

[↑ Back to top](#top)

<a id="a45"></a>
### 45. Isolate communication and what can be sent

Isolates don't share memory; they communicate by **message passing** over `SendPort`/`ReceivePort`. You spawn one with `Isolate.spawn`, passing a `SendPort` so the two sides can exchange messages. Messages must be sendable: primitives, strings, lists/maps of sendable values, and `TransferableTypedData` (for moving large byte buffers efficiently). Closures capturing state, sockets, and most native handles can't be sent. `compute()` wraps the spawn/communicate/dispose cycle for a single function call.

<details><summary>🔍 Senior deep-dive</summary>

**The handshake for two-way communication.** `Isolate.spawn` only hands the child *one* `SendPort`, so the child must send *its* port back to establish a reply channel:

```dart
Future<SendPort> start() async {
  final receive = ReceivePort();
  await Isolate.spawn(_entry, receive.sendPort); // give child our port
  return await receive.first as SendPort;        // child replies with its port
}

void _entry(SendPort toMain) {
  final myReceive = ReceivePort();
  toMain.send(myReceive.sendPort);               // hand main a way to reach us
  myReceive.listen((msg) { /* handle requests */ });
}
```

**What can cross the boundary:** immutables and primitives, `String`, `List`/`Map`/`Set` of sendable values, `SendPort` itself, and `TransferableTypedData` — which **moves** (zero-copy transfers ownership of) a large byte buffer instead of copying it, important for images/files. Everything else is deep-**copied** on send, which is why large or frequent messages are costly.

**Cannot be sent:** open sockets/files, most `dart:ffi` pointers/native resources, and closures that capture non-sendable state. (The entry-point function must be a top-level or static function.)

**Costs to call out:** copy cost scales with message size; use `TransferableTypedData` for big binary payloads; batch small messages; and for request/response workloads keep the isolate alive rather than paying spawn cost per call.

</details>

[↑ Back to top](#top)

<a id="a46"></a>
### 46. Flutter's constraint model

Layout is a single pass governed by: **constraints go down, sizes go up, parent sets position.** A parent passes a `BoxConstraints` (min/max width and height) to each child; the child chooses its own size **within** those constraints and returns it; the parent then positions the child. A widget cannot know its size without its parent's constraints, and a parent can't size itself until children report back. Understanding this explains "unbounded height" errors (e.g. a `Column` inside a scroll view) and why widgets like `Expanded`, `Flexible`, and `ConstrainedBox` manipulate the constraints rather than sizes directly.

[↑ Back to top](#top)

<a id="a47"></a>
### 47. Slivers and `CustomScrollView`

A **sliver** is a scrollable region with a lazy, viewport-aware layout protocol (it lays out only what's visible plus a cache extent). `CustomScrollView` hosts multiple slivers in one scroll view, enabling effects impossible with a single `ListView` — e.g. collapsing headers (`SliverAppBar`), mixed lists/grids (`SliverList`, `SliverGrid`), and pinned/floating sections. Standard scrollables like `ListView`/`GridView` are convenience wrappers around slivers. Use `CustomScrollView` when you need several scrolling sections to share one scroll offset.

[↑ Back to top](#top)

<a id="a48"></a>
### 48. Shader compilation jank

The first time a shader is used, the engine compiles it at runtime, which can stall the raster thread and cause a visible hitch on first run of an animation/transition (historically worse on iOS/Skia). Fixes: use **Impeller** (the current Flutter renderer, which precompiles shaders and largely eliminates this), or on the legacy Skia backend, use **SkSL shader warm-up** — capture shaders during a profile run and bundle them so they're precompiled at startup. Keeping animations simple and reusing common effects also reduces the set of shaders needed.

<details><summary>🔍 Senior deep-dive</summary>

**Why it happens (Skia):** Skia generates GPU shaders lazily and compiles them on the raster thread the first time a given draw is needed. Compilation can take tens of ms — a guaranteed dropped frame — and it's most visible on the *first* play of an animation or route transition, so it looks like "jank only the first time." iOS was worse historically because of the Metal backend's compile cost.

**Impeller (the modern fix):** Impeller precompiles a fixed, known set of shaders at **engine build time**, so there's no runtime shader compilation for its built-in drawing. It's the default on iOS and Android in current Flutter. Adopting Impeller is the recommended answer today; SkSL warm-up is legacy.

**SkSL warm-up (legacy Skia workflow):**
1. `flutter run --profile --cache-sksl --purge-persistent-cache` on a real device.
2. Exercise every animation/transition/screen so all shaders compile.
3. `flutter screenshot --type=sksl --observatory-uri=…` to dump the collected SkSL.
4. Ship it: `flutter build … --bundle-sksl-path flutter_01.sksl.json`.

Caveats seniors should mention: warm-up SkSL is device/GPU/driver-specific and brittle across engine upgrades; it only covers the paths you actually exercised; and custom `FragmentProgram` shaders are a separate concern. The strategic answer: **migrate to Impeller** rather than maintain SkSL bundles.

</details>

[↑ Back to top](#top)

<a id="a49"></a>
### 49. Optimizing long lists and image memory

Lists: always use the lazy `.builder` constructors (`ListView.builder`/`SliverList`) so only visible items are built; provide `itemExtent`/`prototypeItem` when heights are uniform (skips per-item layout measurement), tune `cacheExtent`, add `RepaintBoundary` around expensive items, and keep item widgets `const` where possible. Images: use `cacheWidth`/`cacheHeight` (or `ResizeImage`) to decode at display resolution rather than full size, leverage the built-in `ImageCache` (size it appropriately), use `cached_network_image` for disk caching, and dispose controllers/streams. The goal is to bound both build work and decoded-image memory.

[↑ Back to top](#top)

<a id="a50"></a>
### 50. Golden tests

Golden (snapshot) tests render a widget and compare the output against a stored reference image ("golden file"), catching **visual regressions** that behavior-only assertions miss. Use `matchesGoldenFile` (or `golden_toolkit`) and regenerate baselines with `flutter test --update-goldens`. They're best for stable, design-critical UI (components, themes). Caveats: renders can differ across platforms/font versions, so run them in a consistent environment (often CI with a fixed setup) to avoid flaky diffs.

[↑ Back to top](#top)

<a id="a51"></a>
### 51. Handling errors across layers

Two common strategies. **Exceptions**: throw typed errors in lower layers, translate infrastructure errors (e.g. `DioException`) into domain failures at the repository boundary, and handle/display them in the presentation layer. **Result types**: return a `Result`/`Either<Failure, Success>` (e.g. via `dartz`/`fpdart` or a sealed class) so errors are part of the type signature and the compiler forces callers to handle both branches — no invisible throws. Either way: map to domain-specific failure types, keep UI-facing messages separate from technical details, and centralize logging/reporting.

<details><summary>🔍 Senior deep-dive</summary>

**Translate at boundaries.** The data layer speaks in infrastructure errors (`DioException`, `SocketException`, `PlatformException`); the domain layer must not. Each repository is the seam that maps them into a small set of domain `Failure`s (`NetworkFailure`, `AuthFailure`, `NotFound`, `ValidationFailure`). Upper layers depend only on those, so swapping Dio for another client changes one place.

**Result vs. exceptions — the trade-off:**
- Exceptions are ergonomic (no wrapping) but *invisible* in signatures — callers can silently forget to handle them, and control flow jumps.
- `Result`/`Either` (or a Dart 3 **sealed class** `sealed class Result<T> { Success | Failure }`) makes failure part of the type, and an **exhaustive `switch`** forces every caller to handle both branches at compile time. Cost: wrapping/unwrapping boilerplate. Dart 3 sealed classes make this idiomatic without a functional-programming package.

```dart
sealed class Result<T> {}
class Ok<T> extends Result<T> { final T value; Ok(this.value); }
class Err<T> extends Result<T> { final Failure failure; Err(this.failure); }

// caller — compiler enforces both cases:
switch (result) {
  Ok(:final value) => show(value),
  Err(:final failure) => showError(failure),
}
```

**Presentation.** UI shows a *user* message, never a stack trace or technical string; map `Failure → localized message` in one place. Model errors in state (a `status`/`error` field or an error state), not as thrown exceptions inside `build`.

**Global net.** Catch what slips through with `FlutterError.onError` (framework errors) and `PlatformDispatcher.instance.onError` / `runZonedGuarded` (uncaught async), forwarding to Crashlytics/Sentry. This is the safety net, not the primary strategy.

</details>

[↑ Back to top](#top)

<a id="a52"></a>
### 52. Modularizing an app into packages

Split the app into multiple local packages (a monorepo via `melos`, or path/git dependencies): e.g. `feature_*` packages, a shared `core`/`design_system`, and `data`/`domain` packages. Benefits: enforced boundaries (a package can only use what it explicitly depends on), faster incremental builds and tests, independent ownership, and reuse across apps. Costs: dependency-graph management and versioning overhead. Keep dependencies acyclic and pointing toward stable shared packages; expose narrow public APIs via `library` exports.

<details><summary>🔍 Senior deep-dive</summary>

**Why packages beat folders:** a folder convention is unenforced — nothing stops a `feature_a` file from importing `feature_b`'s internals. A **package** boundary is compiler-enforced: `feature_a` can only import what's in its `pubspec.yaml` dependencies, and only the `lib/` files another package chooses to export. Boundaries become real, not aspirational.

**A typical graph (dependencies point *inward*, toward stable code):**
```
app                      (wires everything, DI, routing)
 ├─ feature_auth ─┐
 ├─ feature_cart ─┤→ domain (entities, use-cases, repo interfaces)
 └─ feature_feed ─┘→ core / design_system (shared UI, utils)
      each feature → data (repo impls, DTOs) → domain
```
Features never depend on each other; they meet only at `app` (or via `domain` interfaces). Keep the graph **acyclic** — cycles break incremental builds and mean the split is wrong.

**Encapsulation:** put implementation under `lib/src/` and expose a curated surface via a barrel (`library`/`export`). Consumers can't reach `src/` of another package, so you can refactor internals freely.

**Tooling:** **`melos`** manages the monorepo — bootstraps path dependencies, runs `test`/`analyze`/`build` across all packages, and versions/changelogs them together. Use `dependency_overrides` or path deps during dev.

**Costs to acknowledge:** more `pubspec`s and version coordination, heavier initial setup, and refactors that cross boundaries touch multiple packages. Payoff scales with team size and codebase — worth it for large/multi-team apps or shared code across several apps; overkill for a small single-team app, where feature-first *folders* may suffice until boundaries start leaking.

</details>

[↑ Back to top](#top)

<a id="a53"></a>
### 53. Ephemeral (local) state vs. app state

**Ephemeral state** belongs to a single widget and doesn't need to be shared — e.g. the current tab index, a checkbox toggle, or animation progress. `setState` (a `StatefulWidget`) is the right tool. **App state** is shared across widgets or persists across screens — e.g. logged-in user, cart contents, cached data — and belongs in a state-management solution (Provider/Riverpod/BLoC). The first design question is always: does anything *outside* this widget need this state? If no, keep it local.

[↑ Back to top](#top)

<a id="a54"></a>
### 54. Cubit vs. Bloc

Both come from the `bloc` package and emit **states** the UI rebuilds from. A **Cubit** exposes plain methods that call `emit(newState)` — less boilerplate, ideal for simpler logic. A **Bloc** is event-driven: the UI `add`s **events**, and `on<Event>` handlers map them to states. Bloc adds structure and a full, traceable event log (great for complex flows, analytics, `transformEvents` like debounce), at the cost of more code. Rule of thumb: start with Cubit; move to Bloc when you need explicit events, event transformations, or richer traceability.

```dart
class CounterCubit extends Cubit<int> {
  CounterCubit() : super(0);
  void increment() => emit(state + 1);
}
```

[↑ Back to top](#top)

<a id="a55"></a>
### 55. `BlocProvider`, `BlocBuilder`, `BlocListener`, `BlocConsumer`

- **`BlocProvider`** — creates/provides a bloc to the subtree via the widget tree (and disposes it). `MultiBlocProvider` provides several. `RepositoryProvider` does the same for repositories.
- **`BlocBuilder`** — rebuilds UI in response to state changes; supports `buildWhen` to filter rebuilds.
- **`BlocListener`** — runs **side effects** (navigation, snackbars, dialogs) on state changes without rebuilding; supports `listenWhen`.
- **`BlocConsumer`** — combines builder + listener when you need both for the same bloc.

Access the bloc with `context.read<MyBloc>()` (for calling methods/adding events) and `context.watch` / `BlocBuilder` (for rebuilding).

[↑ Back to top](#top)

<a id="a56"></a>
### 56. `ChangeNotifier` vs. `ValueNotifier` vs. `ValueListenableBuilder`

- **`ChangeNotifier`** — a class holding arbitrary mutable state; you call `notifyListeners()` after mutations. Listeners (e.g. via `Provider`) rebuild. Good for models with multiple fields.
- **`ValueNotifier<T>`** — a `ChangeNotifier` specialized to a single value; setting `.value` auto-notifies if the value changed by `==`.
- **`ValueListenableBuilder<T>`** — a widget that rebuilds when a `ValueListenable` (like a `ValueNotifier`) changes, scoping the rebuild to just that subtree — no state-management package required.

```dart
final counter = ValueNotifier<int>(0);
ValueListenableBuilder<int>(
  valueListenable: counter,
  builder: (_, value, __) => Text('$value'),
);
```

[↑ Back to top](#top)

<a id="a57"></a>
### 57. `context.read` vs. `context.watch` vs. `context.select`

- **`context.watch<T>()`** — subscribes; the widget rebuilds whenever `T` notifies. Use in `build`.
- **`context.read<T>()`** — reads once without subscribing; the widget does **not** rebuild. Use inside callbacks (`onPressed`) to call methods. Never use in `build` to react to changes.
- **`context.select<T, R>((t) => t.slice)`** — subscribes to a **derived slice**; rebuilds only when that slice changes by `==`, minimizing rebuild scope.

Using `watch` where `read` is needed (or vice versa) is a very common bug — `read` in build won't update the UI; `watch` in a callback throws or over-rebuilds.

[↑ Back to top](#top)

<a id="a58"></a>
### 58. Provider variants

The `provider` package offers several providers:
- **`Provider<T>`** — exposes a plain (immutable/read-only) value or service.
- **`ChangeNotifierProvider<T>`** — provides a `ChangeNotifier` and rebuilds listeners on `notifyListeners()`; disposes it automatically.
- **`FutureProvider<T>`** / **`StreamProvider<T>`** — expose the latest value of a `Future`/`Stream` (with an initial value).
- **`ValueListenableProvider`** — exposes a `ValueListenable`'s value.
- **`ProxyProvider`** — builds a value that depends on other providers, rebuilding when they change (dependency composition).
- **`MultiProvider`** — nests several providers without deep indentation.

[↑ Back to top](#top)

<a id="a59"></a>
### 59. Main Riverpod provider types

- **`Provider`** — a read-only/computed value or service (dependency injection, derived values).
- **`StateProvider`** — simple mutable state for trivial cases (a filter, a toggle).
- **`NotifierProvider`** / **`AsyncNotifierProvider`** — the modern way to hold complex state with methods (sync/async); replaces the older `StateNotifierProvider`.
- **`FutureProvider`** — exposes an async computation as `AsyncValue` (`loading`/`data`/`error`).
- **`StreamProvider`** — exposes a stream as `AsyncValue`, rebuilding on each event.

Any of these can be `.autoDispose` (dispose when unused) and `.family` (parameterized by an argument). `AsyncValue` gives clean `.when(loading:, error:, data:)` handling in the UI.

[↑ Back to top](#top)

<a id="a60"></a>
### 60. Testing a BLoC / Cubit

Blocs/cubits are pure Dart, so they test without a widget tree. The `bloc_test` package gives a `blocTest` helper: you `build` the bloc, `act` on it (add events / call methods), and assert the ordered sequence of emitted states. Mock dependencies (repositories) with `mocktail`/`mockito`.

```dart
blocTest<CounterCubit, int>(
  'emits [1] when increment is called',
  build: () => CounterCubit(),
  act: (cubit) => cubit.increment(),
  expect: () => [1],
);
```

Also test error paths (repository throws → error state) and use `seed`/`skip`/`wait` for more complex flows.

[↑ Back to top](#top)

<a id="a61"></a>
### 61. Unidirectional data flow

Data flows in **one direction**: the UI dispatches intents (events/actions) → business logic processes them and produces a new immutable state → the UI rebuilds from that state. The UI never mutates state directly. This makes behavior predictable and debuggable (state changes are traceable and reproducible), simplifies testing (given events, assert states), and avoids the tangled two-way bindings that cause hard-to-trace bugs. It underpins BLoC and Redux-style architectures.

[↑ Back to top](#top)

<a id="a62"></a>
### 62. Handling side effects in BLoC

State should be **declarative data**, so one-off side effects — navigation, snackbars, dialogs, toasts — don't belong in `BlocBuilder` (which can rebuild multiple times). Handle them in **`BlocListener`** (or the listener half of `BlocConsumer`), which fires once per state change for side effects and doesn't rebuild. Options for modeling the trigger: a dedicated status field in the state, a one-shot value the listener consumes, or an emitted "action"/side-effect stream separate from render state. The key principle: keep render state idempotent, and route effects through listeners so they don't re-fire on rebuild.

[↑ Back to top](#top)

<a id="a63"></a>
### 63. `var` vs. `dynamic` vs. `Object`

- **`var`** — type inference; the type is fixed at compile time from the initializer (`var x = 1` is `int`), just without writing it out. Type-safe.
- **`Object`** — the base type of (almost) everything; you can assign anything, but you can only call `Object` members without a cast. Type-safe (checked).
- **`dynamic`** — opts **out** of static type checking; any member call compiles and is only checked at runtime, so it can throw. Use sparingly (e.g. decoding untyped JSON).

[↑ Back to top](#top)

<a id="a64"></a>
### 64. Extension methods

Extensions add methods, getters, or operators to an **existing type** you don't own, without subclassing or modifying it. They're resolved statically (based on the declared type). Useful for readable helpers.

```dart
extension StringCasing on String {
  String get capitalized => isEmpty ? this : this[0].toUpperCase() + substring(1);
}
'hello'.capitalized; // 'Hello'
```

[↑ Back to top](#top)

<a id="a65"></a>
### 65. Factory constructor vs. named constructor

A **named constructor** (`ClassName.named()`) is just an alternative constructor that always creates a new instance. A **factory constructor** doesn't have to create a new instance — it can return a cached instance, a subtype, or one built from complex logic (e.g. `factory User.fromJson(...)`, or a singleton). Factories can't access `this` and must return an object of the type.

```dart
factory Logger(String name) => _cache[name] ??= Logger._internal(name);
```

[↑ Back to top](#top)

<a id="a66"></a>
### 66. Cascade (`..`) and spread (`...`) operators

- **Cascade `..`** — perform a sequence of operations on the **same object** without repeating it; returns the object, not the call results.
- **Spread `...`** — inline the elements of one collection into another; `...?` spreads null-safely.

```dart
final p = Paint()..color = Colors.red..strokeWidth = 2;
final all = [0, ...first, ...?maybeMore];
```

[↑ Back to top](#top)

<a id="a67"></a>
### 67. Records, sealed classes, and pattern matching (Dart 3)

- **Records** — lightweight, immutable, anonymous groupings of values; great for returning multiple values without a class: `(int, String) f() => (1, 'a');` accessed via `.$1` or named fields.
- **Sealed classes** — a class whose subtypes are all known in the same library; the compiler enforces **exhaustive** `switch` handling, ideal for modeling states (`Loading | Data | Error`).
- **Pattern matching** — `switch`/`if-case` can destructure records, objects, and collections and match by shape, enabling type-safe, exhaustive state handling.

```dart
sealed class Result {}
class Ok extends Result { final int v; Ok(this.v); }
class Err extends Result { final String m; Err(this.m); }

String describe(Result r) => switch (r) {
  Ok(:final v) => 'ok $v',
  Err(:final m) => 'err $m',
};
```

[↑ Back to top](#top)

<a id="a68"></a>
### 68. Generics

Generics parameterize a type or function over another type (`List<T>`, `Future<T>`), giving compile-time type safety and reuse without `dynamic`. You can constrain a type parameter with `extends` (`class Box<T extends num>`). They let one implementation work for many types while the compiler still catches misuse.

[↑ Back to top](#top)

<a id="a69"></a>
### 69. `extends` vs. `implements` vs. `with`; abstract class vs. interface

- **`extends`** — single inheritance; reuse a superclass's implementation.
- **`implements`** — implement a type's **interface**; you must provide every member (Dart has no separate `interface` keyword — any class defines an implicit interface).
- **`with`** — mix in a mixin's implementation.

An **abstract class** can't be instantiated and may contain both concrete and abstract members (shared base). An **interface** in Dart is just a class used with `implements`, forcing the implementer to define all members with no inherited implementation. Dart 3 also adds `interface`, `base`, `final`, and `sealed` class modifiers to control how classes can be used.

[↑ Back to top](#top)

<a id="a70"></a>
### 70. What is a `typedef`?

A `typedef` defines a named alias for a type — most often a function signature — improving readability and reuse.

```dart
typedef IntTransform = int Function(int);
typedef Json = Map<String, dynamic>;
int apply(IntTransform f, int x) => f(x);
```

[↑ Back to top](#top)

<a id="a71"></a>
### 71. `StatefulWidget` lifecycle methods

In order: **`createState()`** → **`initState()`** (one-time setup; no `context`-dependent inherited widgets yet) → **`didChangeDependencies()`** (after init and whenever an inherited dependency changes) → **`build()`** → **`didUpdateWidget(old)`** (parent rebuilt with new config; compare old vs. new) → **`setState()`** triggers rebuild → **`deactivate()`** (removed from tree, maybe temporarily) → **`dispose()`** (permanent teardown — cancel timers/controllers/subscriptions). `reassemble()` runs on hot reload.

[↑ Back to top](#top)

<a id="a72"></a>
### 72. The `mounted` property

`mounted` is `true` while the `State`'s element is in the tree, and `false` after `dispose()`. Because `setState` and `context` are invalid after disposal, you should guard async continuations: after an `await`, the widget may have been removed, so check `if (!mounted) return;` before calling `setState` or using `context`. Ignoring it causes "setState called after dispose" errors.

[↑ Back to top](#top)

<a id="a73"></a>
### 73. `MaterialApp` vs. `WidgetsApp`, and `Scaffold`

`WidgetsApp` is the low-level app wrapper providing the essentials: navigation, localization, and basic setup. `MaterialApp` builds on it, adding Material Design: theming (`ThemeData`), Material routing/transitions, `Scaffold` support, and widgets like `AppBar`. (`CupertinoApp` is the iOS-style equivalent.) **`Scaffold`** implements the basic Material visual layout structure for a screen — slots for `appBar`, `body`, `floatingActionButton`, `drawer`, `bottomNavigationBar`, and snackbars.

[↑ Back to top](#top)

<a id="a74"></a>
### 74. `Expanded` vs. `Flexible`

Both work inside a `Row`/`Column`/`Flex` to distribute free space by `flex` factor. **`Expanded`** forces the child to **fill** all the allocated space (it's `Flexible` with `fit: FlexFit.tight`). **`Flexible`** (default `FlexFit.loose`) lets the child be **at most** its allocated space but no larger than it needs — it can be smaller. Use `Expanded` to stretch, `Flexible` to cap-but-not-force.

[↑ Back to top](#top)

<a id="a75"></a>
### 75. `Container` vs. `SizedBox`

`SizedBox` is a lightweight box that only constrains size (or adds fixed spacing); it can be `const`. `Container` is a convenience composite of multiple widgets (padding, margin, color, decoration, constraints, transform) — more flexible but heavier. Use `SizedBox` for pure sizing/spacing (and `const` for free performance); reach for `Container` only when you need its decoration/padding features.

[↑ Back to top](#top)

<a id="a76"></a>
### 76. `MediaQuery` and `SafeArea`

**`MediaQuery`** exposes information about the current media/screen — size, orientation, device pixel ratio, text scale factor, padding/insets (keyboard, notches) — via `MediaQuery.of(context)`, the basis for responsive layouts. **`SafeArea`** insets its child to avoid OS intrusions (notches, status bar, home indicator, rounded corners) by applying the appropriate padding automatically.

[↑ Back to top](#top)

<a id="a77"></a>
### 77. Observing app lifecycle (`AppLifecycleState`)

To react to the app going to background/foreground, register a `WidgetsBindingObserver` and override `didChangeAppLifecycleState`, which reports `resumed`, `inactive`, `paused`, `detached`, and `hidden`. Use it to pause/resume work (e.g. stop a camera or timer when backgrounded, refresh on resume). Remember to add the observer in `initState` and remove it in `dispose`.

[↑ Back to top](#top)

<a id="a78"></a>
### 78. Tree shaking

Tree shaking is a compile-time optimization that removes code (functions, classes, even icon glyphs) that is never referenced, shrinking the release binary. Flutter's AOT compiler does this in release/profile builds — e.g. `--tree-shake-icons` drops unused `IconData` from font files. It's why avoiding dynamic/reflective access to code helps: the compiler must be able to prove code is unused to strip it.

[↑ Back to top](#top)

<a id="a79"></a>
### 79. Reconciliation (diffing) algorithm

When a widget rebuilds, Flutter walks the new widget subtree against the existing element tree and, for each position, calls `Widget.canUpdate(old, new)` — true when the **runtime type and key match**. If they match, the element is **updated in place** (cheap, state preserved) with the new widget's config. If not, the old element (and its subtree) is discarded and a new one is created. This per-position, single-pass matching (not a full tree diff) is why keys matter for reordering and why type/key stability preserves state.

<details><summary>🔍 Senior deep-dive</summary>

The core is `Element.updateChild(child, newWidget, slot)`:

- `newWidget == null` → deactivate & unmount the child.
- `child == null` → inflate the new widget (`newWidget.createElement()` → `mount`).
- `Widget.canUpdate(child.widget, newWidget)` (same `runtimeType` **and** `key`) → `child.update(newWidget)` — reuse element & `State`, keep the render object, just re-configure.
- otherwise → deactivate old child, inflate new one (`State` is lost).

For multi-child lists (`updateChildren`), Flutter runs a **two-ended sync** (match from the top, then the bottom), then uses **keys** to match the remaining middle by identity rather than position. This is exactly why a keyless list of stateful items breaks on reorder: positions match, so `State` "sticks" to the slot instead of the item.

Deactivated elements go to the `BuildOwner._inactiveElements` list. If a **`GlobalKey`** element is re-inserted elsewhere in the *same frame*, it's pulled back out (reactivated) with its `State` intact — that's the mechanism behind GlobalKey reparenting. Anything not reactivated by end-of-frame is unmounted (`dispose`).

Senior gotcha: `canUpdate` compares `runtimeType`, so two *different generic instantiations* or wrapping a widget in a new type will throw away state even if "it looks the same." Also, adding/removing a widget above a subtree changes depth and can force re-creation unless keys pin identity.

</details>

[↑ Back to top](#top)

<a id="a80"></a>
### 80. `AnimationController`, `Ticker`, and `vsync`

An **`AnimationController`** drives an animation's value (typically 0→1) over a `Duration`; you `forward()`, `reverse()`, `repeat()`, etc. It needs a **`Ticker`** — an object that fires a callback every frame (on the vsync signal). **`vsync`** is the `TickerProvider` you pass to the controller so the ticker is tied to the screen's refresh and is paused when the widget is off-screen (avoiding wasted work). You provide it via `SingleTickerProviderStateMixin` (one controller) or `TickerProviderStateMixin` (several). Always `dispose()` the controller.

[↑ Back to top](#top)

<a id="a81"></a>
### 81. Implicit vs. explicit animations

**Implicit** animations (`AnimatedContainer`, `AnimatedOpacity`, `AnimatedPositioned`, `TweenAnimationBuilder`) animate automatically to a new target value over a duration — no controller needed; great for simple state-to-state transitions. **Explicit** animations use an `AnimationController` (often with `AnimatedBuilder`/transitions like `FadeTransition`) for full control: repeating, reversing, chaining, and coordinating multiple animations. Choose implicit for simple one-shot changes, explicit when you need control over timing/looping.

[↑ Back to top](#top)

<a id="a82"></a>
### 82. What is a `Tween`?

A `Tween<T>` maps the controller's 0→1 value onto a range of typed values — `begin`→`end` (colors, offsets, sizes). It defines *what* interpolates; the controller defines *when*. You typically `tween.animate(controller)` (optionally with a `CurvedAnimation` for easing) and read `.value` in the build.

```dart
final anim = ColorTween(begin: Colors.red, end: Colors.blue).animate(controller);
```

[↑ Back to top](#top)

<a id="a83"></a>
### 83. The `Hero` widget

`Hero` creates a shared-element transition: when navigating between two routes that each contain a `Hero` with the **same `tag`**, Flutter animates the widget flying from its position on the first screen to its position on the second. Common for image-thumbnail → detail transitions. Tags must be unique per screen and match across routes.

[↑ Back to top](#top)

<a id="a84"></a>
### 84. What is a `CustomPainter`?

`CustomPainter` lets you draw arbitrary graphics directly onto a `Canvas` (paths, shapes, text, gradients) inside a `CustomPaint` widget — for charts, custom shapes, signatures, and effects beyond standard widgets. You override `paint(canvas, size)` and `shouldRepaint(old)` (return `false` when nothing changed to avoid needless repaints). It operates at the render layer, below the widget system.

[↑ Back to top](#top)

<a id="a85"></a>
### 85. `StreamController`; single vs. broadcast streams

A `StreamController` creates a stream you feed manually via `.add()`, `.addError()`, `.close()`, exposing `.stream` to listeners — the bridge between imperative code and the stream API. A **single-subscription** stream (default) allows exactly one listener and buffers until then — for one consumer of a sequence. A **broadcast** stream (`StreamController.broadcast()`) allows many simultaneous listeners and doesn't buffer — for events fanned out to multiple consumers. Always `close()` the controller to avoid leaks.

[↑ Back to top](#top)

<a id="a86"></a>
### 86. `Future.wait`, `Future.any`, `Future.forEach`

- **`Future.wait([...])`** — runs futures **concurrently** and completes when **all** finish, returning a list of results (rejects if any fails, unless `eagerError`/handled). Use to parallelize independent async calls.
- **`Future.any([...])`** — completes with the result of the **first** future to finish.
- **`Future.forEach(items, fn)`** — runs an async action **sequentially** over items, awaiting each before the next.

[↑ Back to top](#top)

<a id="a87"></a>
### 87. Error handling in async code

With `async`/`await`, wrap awaited calls in `try/catch/finally` — errors from the future surface as thrown exceptions. With `Future` chains, use `.catchError()` and `.whenComplete()`. For streams, provide `onError` in `listen` (or `try/catch` in `await for`). Catch specific types (`on FormatException catch (e)`), translate low-level errors to domain errors at boundaries, and never swallow errors silently — log or surface them. Uncaught async errors can be captured globally via `runZonedGuarded`/`FlutterError.onError`.

[↑ Back to top](#top)

<a id="a88"></a>
### 88. `push` vs. `pushReplacement` vs. `pushAndRemoveUntil`

- **`push`** — adds a new route on top; the previous route stays in the stack (back returns to it).
- **`pushReplacement`** — replaces the current route with a new one (no back to the old one) — e.g. splash → home.
- **`pushAndRemoveUntil`** — pushes a new route and pops existing routes until a predicate is met — e.g. after login, go to home and clear the whole auth flow.

[↑ Back to top](#top)

<a id="a89"></a>
### 89. `Navigator` vs. `Router`

`Navigator` manages a **stack of routes** with imperative `push`/`pop` (Navigator 1.0). The `Router` widget (Navigator 2.0) sits above it and makes navigation **declarative and URL-driven**: a `RouteInformationParser` turns the platform route (URL/deep link) into app state, and a `RouterDelegate` builds the `Navigator`'s pages from that state. `Router` is what enables proper web URLs, browser back/forward, and deep linking; `go_router` wraps it in a friendlier API.

[↑ Back to top](#top)

<a id="a90"></a>
### 90. Making HTTP requests

Use the `http` package for simple calls or `dio` for advanced needs (interceptors, timeouts, cancellation, retries). You `await` the request, check the status code, and decode the JSON body (`jsonDecode`) into models. Do parsing off the UI thread with `compute` for large payloads.

```dart
final res = await http.get(Uri.parse('https://api.example.com/items'));
if (res.statusCode == 200) {
  final data = jsonDecode(res.body) as List;
}
```

Wrap calls in a repository, handle errors/timeouts, and inject the client for testability.

[↑ Back to top](#top)

<a id="a91"></a>
### 91. Persisting data locally

Options by use case:
- **`shared_preferences`** — small key–value primitives (settings, flags).
- **SQLite** via `sqflite` / `drift` — structured, relational, queryable data.
- **`hive` / `isar` / `objectbox`** — fast NoSQL object stores, good for larger local datasets.
- **File storage** (`path_provider` + `dart:io`) — blobs, documents, caches.
- **`flutter_secure_storage`** — encrypted key–value for secrets/tokens.

Choose by data shape, query needs, size, and whether it's sensitive.

[↑ Back to top](#top)

<a id="a92"></a>
### 92. Offline mode and caching

Adopt an **offline-first / repository** pattern: the repository is the single source of truth, reading from a local cache (DB) and syncing with the network when available. Strategies: cache API responses (with TTL) in `hive`/`sqflite`, serve cached data immediately then refresh, queue mutations made offline and replay them when connectivity returns, and detect connectivity with `connectivity_plus`. Handle conflict resolution and show clear stale/offline indicators.

[↑ Back to top](#top)

<a id="a93"></a>
### 93. Storing sensitive data securely

Never keep secrets in plain `shared_preferences` or source code. Use **`flutter_secure_storage`**, which stores values in the platform-encrypted stores — iOS **Keychain** and Android **Keystore/EncryptedSharedPreferences**. Keep tokens short-lived, avoid logging them, use HTTPS/certificate pinning for transport, and don't embed API keys in the client (proxy sensitive calls through a backend). For highly sensitive apps, add biometric gating and obfuscation (`--obfuscate`).

[↑ Back to top](#top)

<a id="a94"></a>
### 94. Hot reload vs. hot restart

**Hot reload** injects changed source into the running Dart VM and rebuilds the widget tree, **preserving app state** — near-instant, ideal for UI tweaks. It won't apply changes to `main()`/global state, `initState`, or type/enum declarations. **Hot restart** rebuilds the app from scratch, **losing state**, but applies those structural changes. Both are debug-mode features (JIT); neither exists in release builds.

[↑ Back to top](#top)

<a id="a95"></a>
### 95. Build modes: debug, profile, release

- **Debug** — JIT-compiled, assertions on, hot reload, DevTools/service extensions; not performance-representative.
- **Profile** — AOT-compiled like release but keeps enough tracing hooks to profile performance on a real device; used for measuring.
- **Release** — fully AOT-compiled, assertions/debug info stripped, optimized and minified; what you ship.

Always benchmark in profile/release, never debug.

[↑ Back to top](#top)

<a id="a96"></a>
### 96. JIT vs. AOT compilation

**JIT** (Just-In-Time) compiles Dart at runtime — enables fast incremental compilation and **hot reload**, used in debug/development. **AOT** (Ahead-Of-Time) compiles Dart to native machine code at build time — faster startup, consistent runtime performance, no compilation overhead — used for profile/release. Flutter uses both: JIT for development velocity, AOT for shipping.

[↑ Back to top](#top)

<a id="a97"></a>
### 97. DevTools and the Flutter Inspector

**DevTools** is Flutter/Dart's suite of debugging and performance tools: the **Widget Inspector** (visualize the widget tree, select widgets on-device, inspect layout/constraints), the **Performance** view (frame timeline, jank analysis), the **CPU profiler**, the **Memory** view (allocations, leaks), **Network** view, and logging. The Inspector specifically helps understand layout issues and rebuild behavior. Run analysis in profile mode for representative numbers.

[↑ Back to top](#top)

<a id="a98"></a>
### 98. `pubspec.yaml`; packages vs. plugins

**`pubspec.yaml`** is the project manifest: metadata, the Dart SDK/Flutter constraints, dependencies (and dev dependencies), and asset/font declarations. `pub get` resolves them into `pubspec.lock`. A **package** is pure Dart code shared via pub.dev; a **plugin** is a package that also includes **platform-specific native code** (via platform channels) to access device capabilities (camera, geolocation). Every plugin is a package; not every package is a plugin.

[↑ Back to top](#top)

<a id="a99"></a>
### 99. `main()` vs. `runApp()`

`main()` is the Dart program's **entry point** — execution starts here; you do pre-launch setup (e.g. `WidgetsFlutterBinding.ensureInitialized()`, DI, `await` initialization). **`runApp(Widget)`** takes the root widget, attaches it to the render tree via the binding, and starts the Flutter app/rendering. `main()` typically ends by calling `runApp()`.

[↑ Back to top](#top)
