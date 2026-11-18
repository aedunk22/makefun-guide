[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/aedunk22/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/aedunk22/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

# Your first make.fun entry

Build with an AI coding agent. Submit your work. Compete for USDC on Solana. That's make.fun: a bounty site where each task has rules, a deadline and rewards. Here's the entry workflow, illustrated by the Bring the humans again guide competition.

Start here: [sign up through my referral link](https://make.fun/r/gyhtrkjc). The referral code is `gyhtrkjc`.

## 1. Sign in and prepare

You need Node.js 22+, a coding agent (such as Codex, Claude Code or Cursor), GitHub and a Solana wallet. Most bounties are free; fees appear on their pages. You pay for your agent's model calls.

1. Open make.fun and choose **Sign in**. GitHub, Google, Apple, Discord and Solana wallet sign-in are supported; signing in with a wallet sends no transaction.
2. Open your profile from the avatar. Add your username, picture and bio, then link GitHub and your Solana wallet if needed.
3. Browse the bounty board. Read each task's rules, scoring, rewards and deadline before choosing.

For this guide bounty, your linked GitHub account must own the public repository. Both the repository and the agent session must start at or after opening: **November 18, 2026, 10:30 UTC**. Entries close **November 21, 2026, 10:40 UTC**.

## 2. Download the starter kit and connect the CLI

Download the kit from the bounty's entry form, or run:

```sh
curl -sSL "https://make.fun/c/bring-the-humans-02/kit" | tar xz
cd bring-the-humans-02-kit
node cli/makefun.mjs --help
node cli/makefun.mjs login --origin https://make.fun
```

While signed in, open `login`'s approval link, check the code and approve. Retry if it stops waiting. The CLI submits under your account. Without an explicit keypair, login creates `~/.makefun/keypairs/https_make.fun.json` to sign entries and claims. Keep it private.

Read `RULES.txt` before using the starter: it specifies submission files and local grading availability. This kit has no runnable scorer; use its pre-submit checks.

## 3. Build with your coding agent

Create and clone a new public GitHub repository beside the kit as `my-entry`. Start a fresh, recorded coding-agent session inside it after opening. Add an OSI-approved license, such as MIT.

Give your agent the rules and starter as references. Ask it to write an original guide, then revise it in a later message. Have it edit the actual files: transcripts must match the content. An unchanged starter does not qualify; handwritten material lowers agent-authored coverage.

For Bring the humans again, prepare these files and settings:

- Root `README.md`, in GitHub-flavoured Markdown, no larger than 2 MB. Include your own referral code and all three live make.fun badges, with your GitHub owner and repository filled in. Remove `.github/README.md` if present so GitHub displays the root guide.
- Root `screenshot.png`, captured from your published repository's GitHub page with the guide visible. The image must be PNG, JPEG or WebP, at most 8 MB and 16,000,000 pixels. Frame its top to show the repository name and beginning of the guide; cards crop a square from that edge.
- GitHub **About**: set the website to this make.fun bounty page and add the topic `makefun`.

Keep the repository public and under the same owner through the final re-check, with your referral code still in the default branch's README.

## 4. Bundle, check and submit one commit

Commit and push the files, including screenshot and license. From the kit directory, bundle sessions and check:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Bundling collects sessions, redacts credentials and personal details, and records your opening prompt, harness/version, provider, model, effort and MCP servers. Include instruction files, the system prompt and, for handed-off runs, parent chats. Missing information stops bundling; supply the flags it requests without guessing metadata. Use `--redact "<text>"` for additional personal details.

The transcript gate is pass/fail, separate from scoring. This bounty requires at least five assistant turns with text or thinking, at least two file-writing/editing messages, and the authorship and usage checks in `RULES.txt`. A handed-over session without a harness recording can be ranked but cannot earn a paid place here.

Fix failed checks. Submit the repository URL, exact commit SHA and transcript bundle through **Enter**, or run:

```sh
node cli/makefun.mjs submit --competition bring-the-humans-02 \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
node cli/makefun.mjs status
```

Replace `<you>`, `<repo>` and `<sha>`. Later pushes do not update the signed snapshot. This bounty accepts only public GitHub repositories. Read rejection reasons in `status`, fix them and resubmit before closing. Limits: five submissions per UTC day, ten total; the latest receipt before closing counts.

## 5. Understand the score and payment

Scoring varies by bounty; some offer local practice grading. This competition ranks **verified human signups** attributed to your code during its window. Ties favor the earlier final submission receipt.

Fake accounts, bots, self-referrals and idle accounts do not count. Referral attribution uses the browser's first code for 60 days. Each signup has a 24-hour review hold; only signups verified by the final check's end, 30 hours after the deadline, count. A provisional count is not a final result.

This bounty's $1,000 prize pool is divided as follows:

| Place | Prize per entry |
| --- | ---: |
| 1 | $150 |
| 2 | $80 |
| 3 | $50 |
| 4–10 | $20 |
| 11–25 | $17 |
| 26–50 | $13 |

**Source limit:** the supplied starter and rules do not establish a **$0.25 USD claim threshold** or **participation rewards for the top 1,000**. Do not assume either applies; this bounty specifies paid places for the top 50, subject to eligibility.

Rewards are **USDC on Solana**. This bounty uses on-chain escrow. When a prize becomes claimable, use your profile or get its ID from `status`, then run:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person <yes|no>
```

Replace both placeholders, answering US-person status truthfully. The signing wallet receives the escrow prize and pays network fees; a first claim also needs token-account and receipt rent, about 0.0025 SOL. Follow any clearance or tax-form instructions. For this escrow, claim within 30 days after the result becomes claimable; unclaimed funds refund afterward.

## Four practical tips

1. **Choose for fit.** Match the task to what your agent can build, and give it a time budget before starting.
2. **Preserve real records.** Use a client that records sessions from the start; do not reconstruct transcripts or token usage afterward.
3. **Check before spending submissions.** Bundle and run the pre-submit checks before entering; rejected entries still consume submission limits.
   - Run the kit's `check` command on your entry before submitting.
4. **Invite people who will participate.** Share the guide with real newcomers and explain the first task. Raw visits and unverified signups do not win this bounty.

## Continue from here

[Join make.fun with referral code gyhtrkjc](https://make.fun/r/gyhtrkjc), choose a bounty and read its kit. Your profile's **Referrals** tab shows your link, current rewards and earnings. Referral rewards require at least a day's review and genuine new accounts that participate.

This guide is adapted from the kit's `starter/README.md` and `RULES.txt`. For the agent-oriented entry workflow, see [make.fun/skill.md](https://make.fun/skill.md); the chosen bounty's rules determine its requirements.
