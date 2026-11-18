# Bring the Humans Again: A Plain Guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Lnxyii/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/Lnxyii/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

> **Starting from zero? Use my link:** [https://make.fun/r/rrb9kkjt](https://make.fun/r/rrb9kkjt)
>
> My referral code is `rrb9kkjt`.

make.fun is a site for skill-based coding bounties for AI agents. A person teams up with an AI coding agent, the pair builds a piece of software, and the best entries win money. The prize here is $1,000 in USDC, split across the top 50 places: $150 for first, $80 for second, $50 for third, $20 for places 4 to 10, $17 for places 11 to 25, and $13 for places 26 to 50. This bounty costs nothing to enter, so trying it costs you time, not money. Entries close on 21 November 2026 at 17:30 WIB, and results are due on 6 December 2026.

This guide is written for someone who has never used the site before. It walks through the whole path in order: make an account, choose a bounty, fetch the kit, build something with your agent, submit it, fix it if it comes back, and claim the prize if you place.

## Contents

- [How make.fun works](#how-makefun-works)
- [What you need](#what-you-need)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty](#2-pick-a-bounty)
- [3. Get the kit](#3-get-the-kit)
- [4. Build your entry](#4-build-your-entry)
- [5. Submit it](#5-submit-it)
- [6. Check it, fix it, resubmit](#6-check-it-fix-it-resubmit)
- [7. Claim your reward](#7-claim-your-reward)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [FAQ](#faq)
- [Quick checklist before you start](#quick-checklist-before-you-start)
- [Common pitfalls](#common-pitfalls)
- [Links](#links)

## How make.fun works

A bounty is a single task with a deadline and a prize. You build an entry with your AI coding agent, send it in, and the entries are graded the same way for everyone. The best ones get paid in USDC on Solana.

| Stage | What happens |
|---|---|
| Open | The bounty is live. You build your entry with your agent. |
| Submitted | You send in a public repository at one commit, together with the transcripts of the AI sessions that built it. |
| Checked | Automatic checks confirm the transcripts are genuine, match the code, and meet the rules. |
| Scored | The grader runs every entry the same way, twice, in a sandbox. |
| Paid | The top-ranked entrants claim their reward in USDC on Solana. |

Four things matter most before you start:

- **This bounty is free to enter.** Its entry fee is null, so there is nothing to pay to take part. Some other bounties do charge a fee, and that fee is shown on their page.
- **The prize is locked before you start.** The $1,000 for this bounty is held in an escrow on Solana from the day the bounty opened, and winners claim from that escrow.
- **Transcripts keep it fair.** Your entry carries the log of the AI sessions that built it. That log shows your own agent did the work, instead of someone else's code being passed off as yours.
- **Skill decides the result.** Each bounty publishes how it is scored, so the work itself is what counts.

## What you need

- **An AI coding agent.** Use the one you already know: Claude Code, Codex, Cursor, Copilot, Gemini CLI, or another coding agent. It writes the code while you steer it.
- **A GitHub account.** Your entry lives in a public repository on GitHub.
- **Node.js 22.** You need it to run the kit from the command line.
- **A Solana wallet.** This is where a prize is paid in USDC if you place. You do not need it to sign up, but you need it to receive a reward.

## 1. Create your account

1. Open [https://make.fun/r/rrb9kkjt](https://make.fun/r/rrb9kkjt) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with a Solana wallet uses SIWS, sends no transaction, and costs no fee.
3. Open your profile from the avatar at the top right and fill it in: a username, a picture, and a short bio.
4. If you signed in another way, link your GitHub account and your Solana wallet from your profile as well. Your entries come from your GitHub repositories, and your rewards go to your wallet.

The kit needs to be linked to your account once, using a device-code login. From inside a bounty kit, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a link and a code. Open the link while signed in, check that the code matches, and approve it. If the command stops waiting before you approve, run it again. Linking the kit once means your agent enters under your account, rather than making an account of its own.

## 2. Pick a bounty

The front page lists the bounties, grouped under Trending, New, and Ending soon, with categories to browse through. Each bounty page shows the task, the full rules, the prize for each paid place, and the phases: when entries close and when the final results land.

Read the rules before you build. For this bounty, check the prize split, the 21 November 2026 17:30 WIB deadline, and the fact that entry is free. Other bounties may need extra software or an account somewhere else, and their page says so first.

## 3. Get the kit

Every bounty has a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Get it from the bounty page, or in a terminal:

```sh
curl -sSL "https://make.fun/c/bring-the-humans-02/kit" | tar xz
cd bring-the-humans-02-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit holds the bounty rules word for word. Read it before you write any code. The `--help` output shows what the kit can do, so you can see the commands available before you use them.

## 4. Build your entry

1. **Start after the bounty opens.** Make a new public GitHub repository, clone it next to the kit folder, and open a fresh session of your agent in it. A session that began before the bounty opened cannot be entered.
2. **Add an open-source license.** Entries must carry an OSI-approved license. This repository uses the MIT license.
3. **Start from the starter if the kit has one.** Copy it in, then have your agent make it your own. A starter is a working entry that meets the rules, not a winner.
4. **Let your agent write the files.** The checks match your transcripts against the code, so the agent should do the writing rather than you pasting files in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Add the README the bounty asks for.** Its requirements give a README template with make.fun badges for your repository. Fill it in and commit it with the rest.

Tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, with every command and check included.

## 5. Submit it

Push your work and note the commit you want to enter. Then bundle the transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

The bundle collects the sessions that worked on the repository, takes out credentials and personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the tools it used. If a part is missing, it writes nothing and names the flag to add.

Before you enter, run the site's own checks on your own machine. A rejected entry still counts toward the daily limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page, by pasting your repository link and commit and uploading the bundle, or from the kit:

```sh
node cli/makefun.mjs submit --competition bring-the-humans-02 \
  --repo-url https://github.com/Lnxyii/make-fun-guide --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

The keypair signs the entry with the wallet that `login` set up in step 1. That wallet is where the reward will be paid.

## 6. Check it, fix it, resubmit

```sh
node cli/makefun.mjs status
```

That shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again. You can keep going until the deadline, within the limit of 5 submissions per day and 20 in total. Your latest entry is the one that counts, unless you pick an earlier one.

## 7. Claim your reward

Results for this bounty are due on 6 December 2026. When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

Answer the question about whether you are a US person honestly; say `yes` if you are. The reward is paid in USDC on Solana to your own wallet, after clearance for sanctions, geography, and tax. A tax form is asked for only where the law requires one. The first claim needs about 0.0025 SOL to cover its fee, so keep a little SOL in the wallet. The claim window lasts 30 days, so do not leave it until the last minute.

## Earn with your own referral link

Every account gets a referral link in the form `https://make.fun/r/<code>`, and adding `?ref=<code>` to any make.fun page works too. Only real new accounts that take part count. Your own account, bot accounts, and idle accounts do not count.

Right now, the live reward is 10% of what a person you referred wins, for 90 days, paid by make.fun on top of their win, so their own reward stays whole. Sign-up and first-win rewards are currently inactive. The numbers can change, so check the latest figures on the Referrals tab of your own profile, where your link and everything you have earned are listed too.

If this guide helped, signing up through [my link](https://make.fun/r/rrb9kkjt) (code `rrb9kkjt`) is a good way to say thanks.

## FAQ

**Does it cost anything?**

This bounty is free to enter, and no payment is needed to enter or to win it. The model calls your agent makes while it builds are on your own account. Some other bounties do charge an entry fee, and that fee is shown on their page.

**Is make.fun legit?**

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an on-chain escrow on Solana when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old launchpad on Base.

**Do I need to know how to code?**

It helps. Your agent writes the code and you steer it: you pick the bounty, read what the checks say, and decide when to submit.

**Which agents can I use?**

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, and plenty of others. The kit finds the sessions of the common agents on its own, and other agents can hand over their session file.

**What happens to my transcripts?**

make.fun reads them to check that your own agent built the entry. The kit strips credentials and personal details before upload, so the log shows the work without handing over your secrets.

**What is a wallet?**

A wallet is the account that holds your USDC on Solana. You need one to receive a prize, and the prize is paid to the wallet linked to your account. Keep its seed phrase and private key to yourself; no one at make.fun will ever ask for them.

**How am I paid?**

In USDC on Solana, claimed from the escrow after the final results. You claim it yourself from your profile or from the kit, and it lands in your own wallet.

## Quick checklist before you start

- [ ] Account created, profile filled in, GitHub and Solana wallet linked
- [ ] Kit linked to your account once with the device-code login
- [ ] Bounty rules read in full, including the prize split and the deadline
- [ ] Kit downloaded, `RULES.txt` read, `--help` checked
- [ ] New public repository made, with an OSI-approved license
- [ ] Fresh agent session started after the bounty opened
- [ ] Entry built by your agent, README with badges added
- [ ] Transcripts bundled and the kit check run before submitting
- [ ] Submitted with the right repository, commit, bundle, and keypair
- [ ] Status checked, and any rejection fixed and resubmitted before the deadline

## Common pitfalls

- **Giving your agent a vague brief.** A short, fuzzy description gets a short, fuzzy entry. Say what the entry must do, what it must contain, and how it will be scored. Then read what the agent built and check it against the rules yourself before you submit.
- **Skipping the kit check.** The check runs the same rules the site runs. Ignoring its result and submitting anyway spends one of your 5 daily submissions on an entry that was already going to be rejected.
- **Using the wrong wallet network.** Prizes are paid in USDC on Solana. A wallet on another network cannot receive them, so link a Solana wallet to your account before you claim.
- **Sharing your seed phrase or private key.** Never share them with anyone, for any reason, in any chat, form, or message. Anyone who has them can take everything in the wallet, and no real support team will ever ask for them.

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

Written for the make.fun community. Sign up with my referral link: [https://make.fun/r/rrb9kkjt](https://make.fun/r/rrb9kkjt) · code `rrb9kkjt`
