---
title: "Hono"
ring: adopt
quadrant: languages-and-frameworks
tags: [backend, coding]
---

Now the default for small backends on [Cloudflare Workers](/platforms-and-services/cloudflare-workers/) — the per-request context and lazy environment binding keep a throwaway tool down to a single file, so the cost of shipping one is low enough that it stops being a decision. It also pairs well with the stateless mode of [Model Context Protocol](/platforms-and-services/model-context-protocol/) v2, where a server holds no session state and a new capability can be handed to an agent as just another Worker.
