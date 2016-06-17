# QtNode

QtNode is a QT application written entirely in C++ using the QT libraries that provides a ECMAScript environment with a API that strives to be compatible with Node.js and Javascript libraries written for it.

This is an ambitious undertaking that will take some time.

It was dreamed up as our commercial product Indis.Connect has been maturing and we wished to tap into the vast libraries available through the Node.js ecosystem. We had 'adapted' some and it wasn't as hard as we thought, so we are giving it a spin.

Some ideals that guide the project over just reimplementing Node.js directly
- The Qt project already has the majority of the work covered, reducing external dependencies (libuv, v8, zlib, etc)
  - Already Cross-Platform, includes Async, networking, etc without much effort to make API compatible 
- The Qt V4 ECMAScript (Javascript) Engine provided by QT,and used in the Indis.Connect implementation, has proven to be fast, reliable, and entirely less complicated than Google's v8 (based entirely our experience, our initial version used v8 and we found it ...dificult)
  - We should test this performance and ensure we can maintain similar performance througout development
- Find a better balance in the core between what is c++ and what is Javascript
  - The Node.js project has attempted to keep as much code as possible in Javascript, we have found through trial and error that there is a balance to be had here, becuase of the simplicity of Qt's V4 Binding system, finding that balance is more trivial than with v8
- Provide a better way to extend the core
  - This is made much easier through the use of Qts plugin system, also with support for versioning
  - Building with QT is Cross Platform and relatively easy, especially compared to building libraries like v8
- Encourage the use of Typescript by writing any core component in Typescript and including a wrapper for the Typescript Compiler
  - Maybe its just us, but Javascript is elegant when its short but a nightmare as it grows, Typescript (IMHO), makes this less so while maintaining compatibility, most of the (development) issues we've had with Node.js could have been partially resolved with Type checking. This is a primary driver for the 'balance' mentioned above, in our experience we can write more maintainable code in c++, but love 'business logic' in Javascript.

This project is just getting started so bear with us. Thoughts on implemntation are always appreciated.
