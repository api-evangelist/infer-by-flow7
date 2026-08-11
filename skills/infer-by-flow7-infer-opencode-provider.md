---
name: infer-opencode-provider
description: Configure or review Infer by Flow7 as an OpenCode custom provider over the Responses API. Use when a user asks to add Infer to opencode.json, select an Infer model or policy in OpenCode, diagnose an Infer/OpenCode configuration, or check the versioned OpenCode compatibility boundary.
---

# Infer OpenCode Provider

Use current product evidence. Never infer availability from a published catalog entry, and never reuse a cached model count, selector, price, or status.

## Establish the task

Classify the request as configuration, review, or diagnosis. Ask for a model preference only when it changes the requested result. Never ask the user to paste an API key into chat, a URL, a shell argument, or a configuration file. OpenCode must read the key from `INFER_API_KEY`.

Before changing `opencode.json`, `opencode.jsonc`, or a global OpenCode configuration, read it and preserve unrelated providers, agents, tools, permissions, plugins, and instructions. Make a recoverable backup before writing a user-level file.

## Check live state

Read both product endpoints before recommending a selector:

- `https://infer.flow7.org/api/public/catalog`
- `https://infer.flow7.org/api/public/status`

Treat a catalog selector as published metadata, not proof that it is callable. If the matching status is not operational, stop before any paid request and state the current boundary. If the user has no live key, direct them to `https://infer.flow7.org/signup`. Public registration creates a workspace; the user must verify the account email, fund the live wallet, and create a scoped live API key before paid live inference.

## Configure OpenCode

Prefer the current generator at `https://infer.flow7.org/integrations/opencode`. Its dated protocol record applies to OpenCode `1.18.16`; do not silently extend that record to another version.

When writing the JSON directly, use a selector returned by the current catalog and this shape:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "model": "infer/<current-infer-model-id>",
  "provider": {
    "infer": {
      "npm": "@ai-sdk/openai",
      "name": "Infer by Flow7",
      "options": {
        "baseURL": "https://infer.flow7.org/v1",
        "apiKey": "{env:INFER_API_KEY}"
      },
      "models": {
        "<current-infer-model-id>": {
          "id": "<current-full-infer-selector>",
          "name": "<current-model-and-policy-label>"
        }
      }
    }
  }
}
```

The provider uses `@ai-sdk/openai`, not `@ai-sdk/openai-compatible`, because Infer exposes `/v1/responses`, not Chat Completions. The base URL ends at `/v1`; the SDK appends `/responses`. The outer OpenCode model is `infer/<model-id>`, while the nested model `id` preserves the complete Infer selector sent on the wire.

Parse the merged JSON or JSONC before reporting success. A parse pass is configuration evidence only. Do not launch a paid OpenCode session unless the user explicitly authorizes it after seeing current status and the selected route.

## Diagnose safely

Check, in order:

1. The selected model exists in the current Infer catalog.
2. The same model and policy report an operational route in current status.
3. The provider package is `@ai-sdk/openai`.
4. `baseURL` is exactly the API root ending in `/v1`, not `/v1/responses` or `/v1/v1`.
5. `apiKey` is `{env:INFER_API_KEY}` and the environment variable exists locally without printing its value.
6. The outer provider/model alias and nested full Infer selector have not been conflated.

Use `https://infer.flow7.org/tools/codex-provider-doctor` only as a bounded provider-neutral Responses check. Its safe pass reads no credential and sends no prompt. A passing doctor is not an OpenCode certification.

Do not retry an indeterminate paid result. If a request may have reached the endpoint before the connection failed, report a possible charge and stop.

## Preserve the evidence boundary

- Infer was locally checked with OpenCode `1.18.16`: direct Responses requests, an isolated SSE text response, and a mocked read-only tool round trip completed.
- On 11 August 2026, OpenCode `1.18.16` completed one bounded production run through Infer with selector `infer/gpt-5.6-terra:balanced`. OpenCode made two streamed Responses requests (automatic title plus task); Infer recorded receipts `rcpt_a6c71c8185c857a13ebd68e5` and `rcpt_af1f0ca4362fc87d813adb7c`, totaling `$0.013617`. The temporary key was revoked after the run.
- The production record proves only those two requests, that client version, and that selector. It does not certify current availability, model weights, upstream provider identity, cancellation, retries, long streams, live tool use, every tool schema, or future OpenCode versions.
- OpenCode `1.18.16` sends `x-session-affinity`; Infer can use it only when no explicit body session value is present. Do not promise this behavior for another OpenCode version without a new check.
- `response.model` is provider self-report, not proof of weights, snapshot, upstream vendor, or route origin.
- Infer's proprietary charge record is not proven to appear in OpenCode terminal output.
- Infer registration is public paid beta. Email verification and live-wallet funding are required before paid live inference, and current status remains the callability source.
- Public paid-beta route checks and Infer's stricter supplier-evidence readiness are separate standards; do not describe the beta route as supplier-certified.

End with the observed status, exact OpenCode version, exact selector, files changed or reviewed, whether any credential was read, whether any paid request was sent, and the next bounded action.
