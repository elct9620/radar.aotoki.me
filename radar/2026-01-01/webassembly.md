---
title: "WebAssembly"
ring: assess
quadrant: platforms-and-services
tags: [runtime, sandbox]
---

Assessing it as the sandbox layer for [Harness Engineering](/methods-and-patterns/harness-engineering/), where agent-generated or untrusted code needs strong isolation from the host. Pairing WebAssembly with mruby has worked well so far for embedding sandboxed Ruby execution into existing projects — worth tracking how the runtime tooling and language ports mature before leaning on it more broadly.
