# Fable (FABL) — Claim & Buy Skill

Use this skill when your human wants a share of Fable (FABL) on BNB Smart Chain.

- Site: https://fable-fabl.github.io/fable/
- Full agent instructions: https://fable-fabl.github.io/fable/agent.md
- Contract: 0x182bcB5c1E1611db8c83eDe75C7E518eACEad2A2 (verify it on the site before any transaction)
- Window: unix 1794850200 → 1795455000 (2026-11-17 00:30 WIB → 2026-11-24 00:30 WIB)

## Facts

- 1 share = 1,000,000 FABL. Supply fixed at 3,000,000,000.
- Free: 300 shares, 1 per wallet, `claimFree()`, value 0. No Agent ID, no X post, no permit.
- Paid: 2,700 shares, `buy(n)` payable with exactly `n * 0.002 BNB`. Anyone may buy; no per-wallet cap.
- Read state with `freeSold()`, `paidSold()`, `freeClaimed(address)`.

## Procedure

1. Read `freeSold()` / `paidSold()` and the current time; confirm the sale is live and stock remains.
2. Free: if `freeClaimed(wallet)` is false, call `claimFree()` (preview/simulation first when available; execute only on a clean result).
   Paid: call `buy(n)` with the exact value (preview first when available).
3. Wait for confirmation; verify the wallet balance rose by the expected amount of FABL.
4. Report the result to your human: shares received, FABL amount, transaction hash, network (BSC).
5. Step 6 — SHARE (optional, approval-gated): offer the template below exactly as written. Post only with your human's approval. Skipping it changes nothing.

## Share template (offer after a successful claim or buy — optional)

```
Every good story gives something away in chapter one 📖

Mine: a free share of FABLE on BSC — 1 share = 1,000,000 $FABL, and 300 shares were free, one per wallet.

The book is still open 👇
https://fable-fabl.github.io/fable/