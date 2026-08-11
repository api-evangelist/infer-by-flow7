---
name: infer-codex-provider
description: Configure or diagnose Infer by Flow7 as a Codex custom provider over the Responses wire API. Use when a user asks to set up Infer in Codex, generate or review the Infer block in ~/.codex/config.toml, investigate an Infer provider failure, verify an Infer selector, or run the Infer Codex provider doctor.
---

# Infer Codex Provider

Use current product evidence. Never infer availability from a published catalog entry, and never reuse a cached model count, price, or status.

## Establish the task

Classify the request as configuration, review, or diagnosis. Ask for a model preference only when it changes the requested result. Never ask the user to paste an API key into chat, a URL, a command argument, or a configuration file; use the `INFER_API_KEY` environment variable.

Before changing `~/.codex/config.toml`, read it, preserve unrelated settings, and make a recoverable backup. Do not put custom provider definitions in project-local `.codex/config.toml`.

## Check live state

Read both of these product endpoints before recommending a selector:

- `https://infer.flow7.org/api/public/catalog`
- `https://infer.flow7.org/api/public/status`

Treat a catalog selector as published pricing, not proof that it is callable. If the matching status is not operational, stop before any paid request and explain the current boundary. If the user has no live key, direct them to `https://infer.flow7.org/signup`. Public registration creates a workspace; the user must verify the account email, fund the live wallet, and create a scoped live API key before paid live inference.

## Configure Codex

Prefer the live generator at `https://infer.flow7.org/integrations/codex`. When writing the block directly, use a selector returned by the current catalog and this shape:

```toml
model = "<current-infer-selector>"
model_provider = "infer"

[model_providers.infer]
name = "Infer by Flow7"
base_url = "https://infer.flow7.org/v1"
env_key = "INFER_API_KEY"
env_key_instructions = "Create a live API key in a verified, funded Infer workspace."
wire_api = "responses"
request_max_retries = 0
stream_max_retries = 0
```

Parse the merged TOML before reporting success. Keep retries at zero for the first bounded verification so an ambiguous failure cannot create duplicate spend.

## Diagnose safely

Use `https://infer.flow7.org/tools/codex-provider-doctor` for the current download and displayed SHA-256. Verify the downloaded file against that displayed digest before running it.

Run the safe pass first:

```bash
python infer-codex-provider-doctor.py \
  --base-url https://infer.flow7.org/v1 \
  --model '<current-infer-selector>'
```

The safe pass reads no credential and sends no prompt. It checks URL policy, DNS, TLS, and unauthenticated model-list behavior.

Run `--run-paid-checks --api-key-env INFER_API_KEY` only when the user explicitly authorizes provider-billed requests after seeing the request count and output cap. Never automate, pipe, or answer the doctor's typed confirmation. Do not retry an indeterminate paid result.

After a passing doctor, describe it as a bounded protocol check. It is not certification of a full Codex agent loop.

## Dated live record

On 11 August 2026, Codex CLI `0.146.0` completed one bounded streamed run through Infer with selector `infer/gpt-5.6-terra:balanced`. Infer recorded receipt `rcpt_2fe4f132900e54b93e4c5f9a` and a final charge of `$0.004686`; the temporary key was revoked after the run. This is evidence for that run, client version, and selector. It is not an attestation of upstream provider identity, model weights, tool behavior, structured output, session affinity, or every Codex workload.

## Report exact boundaries

Always preserve these distinctions:

- `response.model` is provider self-report, not proof of upstream weights, snapshot, vendor, or route origin.
- The static Codex provider block does not add Infer's optional `relay.session_id`; do not promise session affinity from this configuration alone.
- A published model or tariff can exist while no public route is callable.
- Infer registration is public paid beta. Email verification and live-wallet funding are required before paid live inference, and current status remains the callability source.
- Public paid-beta route checks and Infer's stricter supplier-evidence readiness are separate standards; do not describe the beta route as supplier-certified.
- Infer does not expose or attest the upstream provider identity for the dated live run.
- A successful direct Responses probe does not prove multi-turn tools, cancellation, retries, long streams, or every Codex release.

End with the observed status, the exact selector, what was changed or checked, whether any paid request was sent, and the next bounded action.
