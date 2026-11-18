[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/aedunk22/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/aedunk22/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

# Your first make.fun bounty

make.fun runs competitions called bounties. Each one sets a task, a deadline, scoring rules, and prizes. You steer an AI coding agent that builds the entry, then submit the work and the session logs that show how it was made.

## Sign in and get the kit

Open [make.fun through this guide's referral link](https://make.fun/r/szthsggd) and choose **Sign in**. GitHub is a convenient choice for a repository entry. If you use Google, Apple, Discord, or a Solana wallet instead, link GitHub from your profile. Set up a Solana wallet for payouts.

Find an open bounty and download its kit from the entry form. For this guide's bounty, you can also download it from the terminal:

```sh
curl -fsSL https://make.fun/c/bring-the-humans-02/kit | tar xz
cd bring-the-humans-02-kit
```

Read `RULES.txt` for the entry requirements, scoring, and deadlines. Use Node.js 22 to run the kit's CLI. To pair it with your account, run the command below, open the link it prints while signed in, and approve the matching code.

```sh
node cli/makefun.mjs login --origin https://make.fun
```

## Build and submit

Start a fresh session in your public repository after the bounty opens. Use a coding agent that records its sessions, such as Codex or Claude Code. Give it the kit rules and ask it to write the entry in the repo. Review the draft and ask for a revision in the same session so the log shows both edits.

For Bring the Humans Again, publish the guide as the root `README.md` with the three live badges and your own referral code. Once GitHub shows the guide, capture that page and add it at the root as `screenshot.png`. Set the repository's About website to the bounty page and add the `makefun` topic.

Push your work and run `git rev-parse HEAD` in the repo to get the commit SHA. From the kit directory, assuming your repository is next to it and named `my-entry`, run:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

If bundling reports missing run details, supply them as directed by the CLI and `RULES.txt` before uploading. In the bounty's **Enter** form, provide the public GitHub URL and commit SHA, upload the bundle, and sign with your linked Solana wallet when prompted. Use `node cli/makefun.mjs status` to check progress. If checks reject the entry, fix the listed issues and resubmit before the deadline. A later push alone doesn't update the submitted snapshot.

## Scores and payouts

Your entry must pass the submission checks before it can be ranked. Each bounty publishes its scoring rules. In [Bring the Humans Again](https://make.fun/bounty/bring-the-humans-02), the score counts new signups credited to your link during the contest that pass verification. For example, ten signups with six verified count as six points. Ties go to the earlier final submission, and the rules allocate a $1,000 prize pool across 50 places.

Prizes pay in **USDC on Solana**. When a bounty prize is ready, open your profile to claim it. For this bounty, the prize goes to the payout wallet that signed the winning entry.

Participation rewards come from a separate pool. By default, the top 1,000 scored entries among those that didn't win a prize can earn a share based on their place. Approved participation, referral, and quest rewards add up across contests. You can claim that combined balance in USDC on Solana once it reaches the claim minimum of **$0.25 USD**; run `node cli/makefun.mjs rewards` to confirm your balance and the live minimum, which can change.

## Practical tips

- Pick a bounty whose scoring rules you can explain in one sentence before you start building.
- Use the kit's local grader when the rules provide one.
- Open your repo in a signed-out browser window to check that visitors can see the README and its badges before taking the screenshot.
- Run the kit's checks early enough to fix problems before the deadline.

If you're ready to try a bounty, [start here with this guide's referral link](https://make.fun/r/szthsggd).
