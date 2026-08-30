---
title: "Route Note 003 — OpenCode 1.18.16 against a custom Responses provider"
url: "https://infer.flow7.org/notes/opencode-1-18-16-custom-responses-provider"
date: "2026-08-11"
feed_url: "https://infer.flow7.org/feed.xml"
---
OpenCode 1.18.16 sent title and main requests directly to /v1/responses in a local capture. Infer's isolated SSE and mocked tool-loop checks passed. At publication, structured output was not tested and live routed-model and public-availability checks were pending.
