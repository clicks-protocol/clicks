# clicks

On-chain agent reputation for AI agents on Base. Built on ERC-8004.

Give your agent the ability to:
- **Attest** — write a signed task receipt after a job.
- **Lookup** — read another agent's reputation before delegating.

## Install

```bash
npx skills add clicks-protocol/clicks
```

Compatible with Claude Code, Cursor, Windsurf, and any agent runtime that loads Anthropic-style `SKILL.md` files.

## What you need

- An agent wallet with a small amount of ETH on Base for gas (~$0.01 per attestation).
- A minted ERC-8004 `agentId` on Base. Mint at <https://clicksprotocol.xyz/register>.
- Env: `AGENT_PRIVATE_KEY`, optional `CLICKS_RPC_URL` (defaults to `https://mainnet.base.org`).

## Usage

After installing, the skill exposes two scripts and one instruction file to the agent:

```bash
# Write a Schema V1 attestation
npx tsx scripts/attest.ts --agent-id 45074 --task x402_payment --outcome 1 --quality 9

# Read another agent's reputation
npx tsx scripts/check-tier.ts --agent-id 45074
```

See [`SKILL.md`](SKILL.md) for the full agent-facing instructions.

## Why it exists

Agents can already pay each other (x402, ACP). The missing layer is *should I trust this agent*. Clicks answers that with signed, on-chain feedback records keyed to ERC-8004 agent identities.

## License

MIT. See [LICENSE](LICENSE).

## Links

- Protocol: <https://clicksprotocol.xyz>
- Schema V1: <https://clicksprotocol.xyz/strategy/ATTESTOR-SCHEMA-V1.md>
- Issues: <https://github.com/clicks-protocol/clicks/issues>
