[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/aedunk22/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/aedunk22/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

# Your first make.fun bounty

make.fun bounties are competitions with tasks, deadlines, scoring rules, and prizes. Steer an AI coding agent to build your entry and submit it with session logs.

## Sign in and get the kit

**Sign in** via the [referral link](https://make.fun/r/gyhtrkjc). Use GitHub for repository entries. Google, Apple, Discord, or Solana wallet users should link GitHub from their profile. Set up a Solana payout wallet.

Download an open bounty's kit from its entry form. This guide's bounty also offers a terminal download:

```sh
curl -fsSL https://make.fun/c/bring-the-humans-02/kit | tar xz
cd bring-the-humans-02-kit
```

Read `RULES.txt` for requirements, scoring, and deadlines. Use Node.js 22 for the kit's CLI. Pair your account: run this command, open its printed link while signed in, and approve the matching code.

```sh
node cli/makefun.mjs login --origin https://make.fun
```

## Build and submit

After the bounty opens, start a fresh session in your public repository with a session-recording coding agent, such as Codex or Claude Code. Give it the kit rules and request an entry in the repo. Review and request a revision within that session to log both edits.

For Bring the Humans Again, publish the root `README.md` guide with three live badges and your own referral code. Capture the published GitHub page as root `screenshot.png`. Set the repo's About website to the bounty page; add the `makefun` topic.

Push your work and run `git rev-parse HEAD` in the repo for its commit SHA. From the kit directory, with an adjacent repo named `my-entry`, run:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Before uploading, supply missing run details reported by bundling as directed by the CLI and `RULES.txt`. In the bounty's **Enter** form, provide the public GitHub URL and commit SHA, upload the bundle, and sign with your linked Solana wallet when prompted. Check progress: `node cli/makefun.mjs status`. Fix rejected entries' listed issues and resubmit before the deadline. Later pushes alone don't update submitted snapshots.

## Scores and payouts

Ranking requires passing submission checks. Each bounty publishes scoring rules. [Bring the Humans Again](https://make.fun/bounty/bring-the-humans-02) counts verified new signups credited to your link during the contest: ten signups, six verified, earn six points. Earlier final submissions win ties; rules allocate $1,000 across 50 places.

Claim ready bounty prizes from your profile in **USDC on Solana**. This bounty pays the wallet that signed the winning entry.

Participation rewards use a separate pool. By default, the top 1,000 scored entries that didn't win a prize can earn shares based on place. Approved participation, referral, and quest rewards accumulate across contests; claim the combined balance in USDC on Solana at the **$0.25 USD** minimum. Run `node cli/makefun.mjs rewards` to confirm your balance and the live minimum, which can change.

## Practical tips

- Before building, pick a bounty whose scoring rules you can explain in one sentence.
- Use the kit's local grader when provided by the rules.
- Before screenshotting, check README and badge visibility in a signed-out browser window.
- Run kit checks early enough to fix problems before the deadline.

Ready? [Try a bounty through this guide's referral link](https://make.fun/r/gyhtrkjc).
