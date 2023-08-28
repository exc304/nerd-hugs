### Embrace modular harmony, unit test your code's dependencies
---

Welcome to `nerd-hugs`!  
  The mission? To simplify the definition and enforcement of dependencies, all while spreading the joy of clean, organized code. Whether you're a seasoned code whisperer 🧙‍♀️ or a budding enthusiast, this repo invites you to explore the joy of intentional design and tidy structure.

What does it do?
---
1. Document Design  
  Clearly document design goals of a project through unit tests.

2. Promotes Ascension to Code Excellence  
  Mitigate cyclic dependencies, ensure contract integrity, and distinctly isolate contract implementations. Identify instances of code that operate outside the confines of module definitions, preventing the gradual encroachment of features that deviate from the meticulously established project module guidelines.

3. Simulate standalone compilation units in Maven, minus the added burdens  
  No need to create numerous Maven submodules and dependencies solely for maintaining a tidy classpath. Skip the hassle and focus on writing unit tests instead!

Overview
---

🚯 Say No to Build-time Drama  
  No need for build-time plugins or elaborate frameworks! Defining and enforcing module dependencies is a breeze, all within the realm of unit tests. If your build system can handle unit tests, you're already equipped to experience the embrace of nerd hugs.

🚮 Intentional Modularity, Effortlessly Achieved  
  While there are no mandatory changes, you'll find that using this library encourages a newfound sense of purpose in your package structure. We believe that intentionality is key to maintaining a healthy codebase, and nerd hugs nudges you in the right direction.

🍝 Banishing the Spaghetti Nightmare  
  Let's face it — many a coding journey starts without a thought for modularity. We're here to make module definitions a painless endeavor even in your smallest of projects. No more excuses for tangled spaghetti code or bewildering meatballs. Start with clarity, right from the beginning.

Let's create code that's not just functional, give your modules the hugs they deserve. 🤗

Getting Started  
---
Imagine an application called `sparkle` with a package structure like so:  

    blizen.ports.gateway
    sparkle.ports.db
    sparkle.ports.api

    sparkle.core

    sparkle.app  

In this app, `sparkle.ports` contains all the contracts for its module boundaries. This package depends on nothing else in the project. The package `sparkle.core` contains general application functionality. It uses the interfaces defined in `ports` to do its job. You can think of all of its inputs and outputs as having been mocked out by ports. The `app` package contains the basic configuration and wiring code to connect the ports implementations to the core of the application. This is where the `main` for the application would live. This is a reasonable modular structure for an app to maintain.

The last part of this structure is the specific implementations of the various ports. Let's assume that we'll nest specific implementations of ports underneath their contract definitions for now:
