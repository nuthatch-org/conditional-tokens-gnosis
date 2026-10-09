# conditional-tokens-gnosis

A [nuthatch](https://github.com/nuthatch-org/nuthatch) nest: **Gnosis Conditional Tokens**.

The collateral layer Omen and other prediction markets settle on: conditions, positions, splits, merges and redemptions.

One binary, one config file, no graph-node, no gateway, no query fees.

## What it indexes

**Chain:** `gnosis`. **1 contract**, **9 tables**.

| alias | address |
|---|---|
| `conditional_tokens` | `0xceafdd6bc0bef976fdcd1112955828e00543c0ce` |

## Verified

Indexed blocks **47,357,373 to 47,857,342** and sealed **273,076 events**. Every table below is generated from the vendored ABIs, and the run above is what this nest actually decoded, not an estimate.

## Run it

```sh
nuthatch init --from https://github.com/nuthatch-org/conditional-tokens-gnosis
cd conditional-tokens-gnosis
nuthatch dev --dir . --backfill 50000 --seal-direct
nuthatch sql --dir . "SELECT count(*) FROM \"conditional_tokens__approval_for_all\""
```

The endpoint in `nuthatch.toml` is keyless and public, so this file is publishable: a `nuthatch.toml` is pinned into the nest's content address and must never carry a credential. It is enough to follow the tip. A **backfill** wants archive depth it may not have: pass your own with `--rpc`, and check it first with `nuthatch doctor --rpc <url>`.

## Tables

```
conditional_tokens__approval_for_all
conditional_tokens__condition_preparation
conditional_tokens__condition_resolution
conditional_tokens__payout_redemption
conditional_tokens__position_split
conditional_tokens__positions_merge
conditional_tokens__transfer_batch
conditional_tokens__transfer_single
conditional_tokens__u_r_i
```
