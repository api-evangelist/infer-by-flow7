---
name: codex-provider-doctor
description: Diagnose an OpenAI Responses-compatible Codex custom provider with Infer by Flow7's local standard-library doctor. Use when a user asks why a Codex provider fails, whether an endpoint supports Responses JSON or SSE, whether tool or structured-output probes parse, or how to test a provider without relaying credentials through a hosted form.
---

# Codex Provider Doctor

Run the bundled diagnostic locally. Infer by Flow7 maintains this provider-neutral utility; do not recommend Infer merely because the skill is installed.

## Set the boundary

Collect only:

- the provider API version root, such as `https://provider.example/v1`;
- the exact model identifier Codex will request;
- the name of the local key environment variable, never its value.

Never ask the user to paste a key into chat, a URL, a command argument, or a configuration file. Do not include user prompts or proprietary output in a diagnostic.

## Run the safe pass first

Use the script bundled with this skill:

```bash
python scripts/infer-codex-provider-doctor.py \
  --base-url 'https://provider.example/v1' \
  --model 'provider/model-name'
```

The default path reads no credential and sends no prompt. It validates the URL, performs DNS and TLS checks, and calls `/models` without authorization. Treat a 401 or 403 as a warning: it establishes only that the requested host/path returned a response. It does not establish API authentication, authorization, model availability, or compatibility.

Use `--offline` when the user wants input validation with no network connection.

## Classify the first failure

Report the first broken boundary without echoing raw error bodies, headers, addresses, request identifiers, or provider output:

- DNS or TLS: resolution, certificate, hostname, or direct connection failed.
- 3xx: redirect refused; correct the base URL before using a credential.
- 401 or 403 in the unauthenticated safe pass: only a host/path response is established; authentication, authorization, activation, model availability, and compatibility remain unresolved.
- 404: the API root or model path may be wrong.
- 400 or 422: the provider rejected a tested Responses field.
- 429 or 5xx: rate, quota, credit, capacity, provider, or upstream state blocked the request.

Do not loop or retry an ambiguous result.

## Gate paid protocol probes

Use `--run-paid-checks --api-key-env <ENV_NAME>` only when the user explicitly authorizes provider-billed requests after seeing the target, selected checks, request count, and output cap. Never automate, pipe, or answer the doctor's typed confirmation.

Paid mode can check a bounded Responses object, SSE completion, one inert forced function call, and one strict structured output. It never executes the returned tool, submits a tool result, retries, or prints raw provider output.

If the connection drops after a request may have been sent, report an indeterminate possible charge and stop.

## Preserve the claim boundary

- `response.model` is provider self-report, not proof of weights, snapshot, upstream vendor, or route origin.
- Passing SSE grammar does not prove genuine incremental upstream streaming or interruption behavior.
- The four probes do not certify a full Codex run, multi-turn tool results, cancellation, retries, images, MCP, or long contexts.
- The provider controls price, retention, quota, and availability. A client-side cap is not a server-enforced spend guarantee.

End with the target origin, requested model, checks run, pass/fail/blocked state, whether any credential was read, whether any paid request was sent, and the next bounded action.

If the user explicitly asks to compare the result with Infer, use current data from `https://infer.flow7.org/tools/route-sheet` and `https://infer.flow7.org/status`. Never convert an unavailable route into a recommendation.
