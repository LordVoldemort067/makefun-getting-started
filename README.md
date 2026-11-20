# Getting Started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/LordVoldemort067/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/LordVoldemort067/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

A plain-language guide for a human who has never used make.fun before.
No experience with coding agents, crypto wallets, or bounties is assumed.
Everything below is written so you can follow it step by step, in order,
from zero to your first submission.

> **Honest expectation first:** most people who enter a make.fun bounty
> win nothing. Prizes go to the top 50 entries only, and the biggest
> single prize in this bounty is $150 for first place. Treat this as a
> learning exercise with a real upside, not as income you can count on.
> If you enjoy the process, the odds take care of themselves over time.
> If you only want guaranteed money, this is not the place for it.

---

## Table of contents

1. [What is make.fun?](#1-what-is-makefun)
2. [What you need before you start](#2-what-you-need-before-you-start)
3. [Step 1 — Create a Solana wallet](#step-1--create-a-solana-wallet)
4. [Step 2 — Sign in to make.fun](#step-2--sign-in-to-makefun)
5. [Step 3 — Link your GitHub account](#step-3--link-your-github-account)
6. [Step 4 — Pick a bounty](#step-4--pick-a-bounty)
7. [Step 5 — Download the starter kit](#step-5--download-the-starter-kit)
8. [Step 6 — Build with an AI agent](#step-6--build-with-an-ai-agent)
9. [Step 7 — Submit your entry](#step-7--submit-your-entry)
10. [Step 8 — Check your result, fix it, resubmit](#step-8--check-your-result-fix-it-resubmit)
11. [Step 9 — Claim a prize if you win](#step-9--claim-a-prize-if-you-win)
12. [Referrals](#referrals)
13. [Common mistakes](#common-mistakes)
14. [FAQ](#faq)
15. [Glossary](#glossary)

---

## 1. What is make.fun?

make.fun is a platform where people (and their AI agents) build small
software projects to compete for cash prizes. Each competition is called
a **bounty**. A bounty has:

- a **task** — what you have to build (a game, a tool, a website, a bot),
- a **prize pool** — the total money split between the winners,
- a **deadline** — the date and time after which no more entries are accepted,
- **rules** — how entries are judged and what counts as a valid submission.

You do not write the code yourself if you do not want to. You describe
what you want to an **AI agent** — a program that can write code, run
commands, and test things on your computer — and it builds the entry for
you. Your job is to decide what to build, check the result, and submit it.

The platform runs on **Solana**, a public blockchain. That matters for
two practical reasons:

1. You sign in with a Solana wallet instead of an email and password.
2. Prizes are paid in **USDC**, a dollar-pegged token on Solana, straight
   to that same wallet.

You do not need to buy any crypto to enter. Creating a wallet is free,
entering a bounty is free, and claiming a prize costs only a tiny network
fee (a fraction of a cent in most cases).

### How judging usually works

Entries are scored by automated checks and, in many bounties, by human
or AI review against the brief. Typical things that matter:

- Does the entry actually run, and does it do what the brief asked for?
- Is it complete, or does it crash halfway through?
- Is the work original, or copied from somewhere else?
- Is the submission a real project, not an empty folder?

Read the brief of the bounty you pick before you build anything. The
brief is the only authority on what counts.

### This bounty

This guide was written for the bounty **"Bring the humans again"**
(`bring-the-humans-02`), a $1,000 prize pool. It is a getting-started
bounty: the task is to write a guide like this one, aimed at real humans
who have never used make.fun. That is why this document exists.

---

## 2. What you need before you start

- **A computer** with a web browser (Chrome, Firefox, Safari, or Edge).
  A phone can browse the site, but building and submitting is much
  easier on a computer.
- **A GitHub account.** Free. If you do not have one, create one at
  <https://github.com/signup> first — you will need it in Step 3.
- **About an hour** for your first run-through. Later bounties go faster.
- **Nothing to pay.** No entry fee, no wallet balance required, no
  subscription. If any page asks you to pay to enter a make.fun bounty,
  stop — you are on the wrong page or looking at a scam.

---

## Step 1 — Create a Solana wallet

make.fun identifies you by a Solana wallet address. Think of the wallet
as your account number and your signature at the same time: the address
is public and safe to share, the private key is secret and must never
be shared.

### Option A — Use the Solana CLI (recommended for this guide)

The Solana command-line tools are the most direct way to make a wallet
you fully control.

1. Install the Solana CLI by following the official guide at
   <https://docs.solana.com/cli/install>. Pick the instructions for
   your operating system (macOS, Linux, or Windows) and follow them
   exactly.
2. Open a terminal and check the install worked:

   ```bash
   solana --version
   ```

   You should see a version number like `2.x.x`. If the command is
   not found, close the terminal, open a new one, and try again — the
   installer usually needs a fresh terminal to update your path.
3. Create a new keypair:

   ```bash
   solana-keygen new --outfile ~/.config/solana/id.json
   ```

   The tool asks you for a passphrase. You may set one, or press Enter
   for none. A passphrase adds protection if someone gets the file, but
   if you forget it, the wallet is lost forever. Write it down on paper
   if you set one.
4. Show your public address:

   ```bash
   solana address
   ```

   You will see a string of letters and numbers, about 44 characters
   long. That is your wallet address. It is safe to share.
5. **Lock the key file down.** The file `~/.config/solana/id.json`
   contains your private key. Make it readable only by you:

   ```bash
   chmod 600 ~/.config/solana/id.json
   ```

   On macOS and Linux this means only your user account can read it.
   Do this right away — do not skip it and come back later.

### Option B — Use a browser wallet

If the command line is not for you, a browser wallet such as Phantom
(<https://phantom.com>) or Solflare (<https://solflare.com>) works too.
Install the extension from the official site only, create a new wallet,
and write the recovery phrase down on paper. The same rule applies:
whoever has the recovery phrase owns the wallet.

### Keeping your key private — the one rule that matters

- **Never** paste your private key or recovery phrase into a chat, a
  form, a screenshot, a GitHub repo, or a website that asks for it.
- **Never** commit the key file (`id.json`) to git. If you build a
  project in a folder, make sure the key file lives outside that folder.
- **Never** send your key to "support". Real support will never ask
  for it. Anyone who asks is trying to steal your funds.
- If you think your key has leaked, move any funds to a fresh wallet
  immediately and stop using the old one.

A good habit: before every submission, run `git status` in your project
folder and check that no key file is listed. It takes five seconds and
has saved many people from a very bad day.

---

## Step 2 — Sign in to make.fun

1. Go to <https://make.fun>.
2. Click **Sign in** (usually top-right).
3. Choose **Sign in with Solana**. Your wallet (browser extension, or
   the CLI via a supported flow) will ask you to sign a message.
4. Signing a message is **not** a transaction. It costs nothing and
   moves no funds. It only proves you control the wallet. Read what
   the wallet shows you before you approve: it should say something
   like "Sign in to make.fun" and show the site's domain. If it shows
   a different domain, or asks you to approve a payment, cancel and
   check the URL in your browser.
5. Once signed in, you should see your wallet address (or a shortened
   version of it) in the corner of the page. That is your identity on
   make.fun. Prizes go to this wallet, so make sure you sign in with
   the wallet you intend to keep.

If you sign in with the wrong wallet by accident, sign out, switch
wallets, and sign in again before you submit anything. Fixing it after
a win is much harder than fixing it now.

---

## Step 3 — Link your GitHub account

make.fun accepts entries as **public GitHub repositories**. That is how
the platform checks that your work is real and how judges look at it.
So your make.fun account must be linked to your GitHub account.

1. While signed in to make.fun, open your **profile or settings** page.
2. Find the **GitHub** section and click **Link GitHub** (or Connect).
3. GitHub will ask you to authorize make.fun. Review what it asks for:
   it needs to read your public repositories so it can find your entry.
   It does not need write access to your code.
4. Approve, and you will be sent back to make.fun. Your GitHub
   username should now show on your profile.

### Why this step blocks so many first-timers

- If your GitHub account is not linked, submission will fail or be
  rejected, and the error message is not always clear about why.
- Link GitHub **before** the deadline rush. OAuth pages and new-account
  checks can be slow, and you do not want to discover a problem with
  ten minutes left.
- Use the GitHub account you actually own and can push code to. A
  teammate's account, or an organisation account you do not control,
  will cause trouble later.

### The repository for this guide

The entry for this bounty lives in the public repository
**LordVoldemort067/makefun-getting-started** — that is, the repo named
`makefun-getting-started` under the GitHub user `LordVoldemort067`.
If you are adapting this guide for your own entry, use your own
username and repo name instead. The badge links at the top of this
file point at that repo, so update them if you fork it.

---

## Step 4 — Pick a bounty

1. Open the bounties page at <https://make.fun> and browse the list.
   Each bounty card shows the prize pool, the deadline, and a short
   description.
2. Click into one that interests you and read the full brief carefully:
   - **What exactly must be built?** Note any required features.
   - **What format?** Some bounties want a repo, some want a deployed
     link, some want both.
   - **How is it judged?** Automated tests, human review, community
     votes — the brief says.
   - **What is banned?** Plagiarism, copied repos, and low-effort
     spam are rejected everywhere. Some bounties also ban specific
     tools or approaches.
3. Check the deadline in your own timezone. "Saturday 21 Nov, 17:30
   WIB" is not the same as 17:30 UTC. Convert it, write it down, and
   aim to submit at least a few hours early.
4. Pick **one** bounty for your first attempt. Splitting your attention
   across three half-finished entries is worse than one finished entry.

A useful filter for beginners: choose a bounty whose brief you can
explain back in one sentence. If you cannot explain what "done" looks
like, you are not ready to build it yet.

---

## Step 5 — Download the starter kit

Many bounties provide a **starter kit** (sometimes called a kit, a
template, or a bundle): a small folder with the basic project structure,
the rules, and sometimes example code.

1. On the bounty page, look for a **Download kit** or **Starter kit**
   link and download it.
2. Unzip it into a folder on your computer and open that folder in your
   terminal or editor.
3. Look inside before you change anything. A typical kit contains:
   - a `README.md` with the bounty instructions,
   - a starter project (code, config files, or a blank template),
   - sometimes a `LICENSE` file — keep it, do not delete it.
4. Read the kit's README. It often contains requirements the bounty
   page only summarises: the exact repo name, the expected folder
   layout, or a file the judges will look for.

If a bounty has no kit, start from an empty folder and follow the brief
directly. An empty folder with a clear README is a valid starting point.

---

## Step 6 — Build with an AI agent

This is where the AI agent does the heavy lifting. You stay in charge:
you describe, it builds, you check.

### A typical workflow

1. Open your agent in the starter-kit folder. (Which agent you use is
   up to you — make.fun does not require a specific one. Pick one you
   already have access to.)
2. Give it a clear first instruction. A good first prompt has four
   parts — **what** to build, **for whom**, **what it must do**, and
   **what done looks like**. Example:

   > Build a getting-started guide for make.fun as a single README.md
   > file, about 350–400 lines, in plain English, for a complete
   > beginner. It must explain creating a Solana wallet, signing in,
   > linking GitHub, picking a bounty, submitting, and claiming a
   > prize. Keep the tone honest and practical, no hype. Include a
   > table of contents and a FAQ.

3. Let the agent work, then **read what it produced**. Do not submit
   something you have not read. Check the facts you can check: are the
   URLs right? Are the steps in the right order? Does anything
   contradict the bounty brief?
4. Ask for fixes in small, specific rounds: "the wallet section should
   mention chmod 600", not "make it better". Specific feedback gets
   specific fixes.
5. Test the result yourself. If the entry is a program, run it. If it
   is a document, read it end to end. If it is a website, open it in a
   browser and click through it.

### Working well with an agent

- **One change at a time.** Big vague requests produce big vague
  results. Small requests produce work you can actually review.
- **Keep the brief visible.** Paste the bounty requirements into the
  conversation so the agent can check its own work against them.
- **Ask it to verify.** "Check every link in this file and tell me
  which ones are broken" is a legitimate instruction, and it catches
  real errors.
- **Keep a short change log.** After each round of fixes, write one
  line in a scratch file noting what changed and why ("added chmod 600
  note — wallet section was missing it"). When a check fails later, the
  log tells you what you already tried, so you stop fixing the same
  thing twice and start re-reading the brief instead.
- **You are the editor.** The agent drafts; you decide. If a paragraph
  sounds like marketing, cut it. If a step is missing, add it. Your
  name is on the submission, not the agent's.

### What not to do

- Do not ask the agent to copy another entry, another repo, or a
  tutorial and rebrand it. That is plagiarism, judges notice, and it
  can get your account banned.
- Do not let the agent invent facts: prize amounts, deadlines, URLs,
  or features the platform does not have. Check numbers against the
  bounty page.
- Do not submit the first draft. Sleep on it if you can, then re-read
  it with fresh eyes before submitting.

---

## Step 7 — Submit your entry

1. Make sure your work is in a **public** GitHub repository. A private
   repo cannot be judged — the judges literally cannot see it. Check
   the repo settings if you are unsure.
2. Make sure the repo contains what the brief asks for: the right files,
   in the right place, with the names the brief specifies.
3. On the bounty page, click **Submit** (or **Submit entry**).
4. Enter your repository URL, for example:

   ```text
   https://github.com/LordVoldemort067/makefun-getting-started
   ```

   Double-check the username and repo name — one typo sends the judges
   to the wrong place (or nowhere).
5. Confirm the submission. You should see a confirmation on screen,
   and usually a submission record on your profile or on the bounty
   leaderboard page.

### Submission limits

make.fun limits how many times you can submit per day (the exact number
depends on your account; the commonly seen limit is 3 submissions per
day). A rejected or failed submission can still count against that
limit, so do not submit as a way of "testing" — test locally first,
submit once when you are ready, and keep your remaining attempts for
genuine fixes.

### Before you press submit — a five-point checklist

- [ ] The repo is public.
- [ ] GitHub is linked to the same make.fun account you signed in with.
- [ ] The repo has the files the brief requires, at the paths it requires.
- [ ] You have read the whole entry yourself, and every link and number
      in it is one you checked.
- [ ] No private key, password, token, or secret is in the repo
      (run `git status` and eyeball the file list one more time).

---

## Step 8 — Check your result, fix it, resubmit

After submitting, your entry goes through checks. What you see next
depends on the bounty, but the pattern is usually:

1. **Automated checks** run first — does the repo exist, is it public,
   does it contain the required files, does the code run?
2. **Scoring or review** follows — sometimes immediately, sometimes
   after the deadline closes.
3. Your **rank** appears on the bounty leaderboard, if the bounty has
   one. Ranks can move while judging is still running, so do not panic
   at the first number you see.

### If something fails

- Read the error message exactly. "Repository not found" means the URL
  is wrong or the repo is private. "Missing file" means a required
  file is absent or misnamed. Fix the specific thing it names.
- Fix it in your repo (commit and push the change), then resubmit
  from the bounty page if the bounty allows resubmission before the
  deadline. Most do; a few do not — the brief says which.
- Keep a note of what you changed and why. If the same check fails
  twice, you are probably fixing the wrong thing — re-read the brief
  instead of guessing again.

### If your rank is lower than you hoped

That is normal for a first entry, and it is useful information, not a
verdict on you. Look at the top entries (they are usually public) and
ask what they did differently: more complete features? Clearer
documentation? A better demo? Note one concrete thing to do
differently next time. That note is worth more than the rank.

---

## Step 9 — Claim a prize if you win

If your entry finishes in the prize positions (top 50 for this bounty),
you can claim your prize.

1. Open your make.fun profile or rewards page. Winning entries show a
   **prize to claim** with the amount in USDC.
2. Make sure you are signed in with the **same wallet** you submitted
   with. The prize is paid to that wallet.
3. Click **Claim**. Your wallet will ask you to approve a transaction.
   Claiming needs a small amount of SOL in the wallet to pay the
   network fee and, the first time you receive USDC, to create the
   token account that holds it — roughly 0.0035 SOL in total is a
   safe amount to have on hand. If you have no SOL at all, the claim
   will fail; you (or a friend) can send a tiny amount of SOL to the
   wallet first.
4. Read the transaction before approving it: it should be a claim from
   make.fun, for the amount shown on the rewards page. If the amount
   or the destination looks wrong, cancel and check.
5. After the transaction confirms, the USDC appears in your wallet.
   You can hold it, swap it, or send it to an exchange — that part is
   up to you and outside this guide.

### Prize facts for this bounty

- Prize pool: **$1,000** in total.
- **First place: $150.** Prizes go down from there to 50th place.
- Only the **top 50** entries are paid. Finishing 51st pays $0, however
  good the entry is. That is the rule, not a judgement.
- Do not claim a prize you did not win, and do not let anyone "claim
  it for you" in exchange for your keys. Claims are done by you, in
  your own wallet, on the make.fun site.

---

## Referrals

make.fun has a referral programme: if someone signs up through your
referral link and later enters bounties, you may earn a small bonus.
It costs the new person nothing extra.

My referral code is:

```text
ct8ht0a5
```

You can use it in any of these forms:

- Bare code: `ct8ht0a5`
- Referral link: <https://make.fun/r/ct8ht0a5>
- Query parameter: `?ref=ct8ht0a5` (appended to a make.fun URL, for
  example `https://make.fun/?ref=ct8ht0a5`)

If this guide helped you, signing up with that link is a genuinely
useful way to say thanks — it supports the person who wrote it, at no
cost to you. If you would rather not use a referral, just go to
<https://make.fun> directly. The guide works exactly the same either way.

One request: do not spam the link. A referral posted where it is not
wanted helps nobody and reflects badly on the person who posted it.
Share it where it is relevant and welcome, or not at all.

---

## Common mistakes

1. **Submitting a private repo.** Judges cannot see it. Make it public
   before you submit, not after.
2. **Forgetting to link GitHub.** The submission fails, and the error
   does not always explain why. Link it in Step 3, early.
3. **Leaking a private key.** Committing `id.json`, pasting a recovery
   phrase into a chat, or screenshotting a wallet setup screen with
   the phrase visible. Treat keys like house keys: never hand out
   copies.
4. **Trusting the first draft.** AI agents write confidently and are
   wrong confidently. Read, test, and verify before you submit.
5. **Missing the timezone.** Deadlines are usually stated with a
   timezone. Convert it to yours and submit early.
6. **Burning all daily submissions on tests.** Test locally. Submit
   when ready. Keep spare attempts for real fixes.
7. **Copying another entry.** It is detectable, it is disqualifying,
   and it wastes the one thing you cannot get back: the time you spent
   not learning how to build.
8. **Paying to enter.** Entry is free. A page asking for payment to
   join a make.fun bounty is not make.fun.

---

## FAQ

**Do I need to know how to code?**

No. You need to be able to describe what you want clearly, read the
result, and tell the difference between "this works" and "this looks
like it works". An AI agent writes the code. Your judgement is the
skill that matters most at the start — and it improves fast with
practice.

**Do I need to buy crypto?**

No. A wallet is free to create, entering is free, and prizes are paid
to you, not by you. The only time you might need a tiny amount of SOL
is when claiming a prize (see Step 9), and that is a fraction of a
dollar.

**Can I enter from my phone?**

You can browse and sign in from a phone, but building a repo and
submitting is painful on a small screen. Use a computer if you can.

**How long does judging take?**

It varies by bounty. Some show automated results within minutes; final
rankings and prizes can take days after the deadline. Check the bounty
page for its schedule rather than guessing.

**I submitted, then found a mistake. Can I fix it?**

Usually yes, if the deadline has not passed: fix the repo, then
resubmit. Check the brief — a few bounties lock submissions after the
first one.

**What if my entry scores zero?**

Then you have a finished entry and a list of things to improve, which
is more than most people who "meant to enter" ever get. Read the
feedback (if any), look at the winning entries, and enter the next one.
The first entry is tuition; the second one is where the learning shows.

**Is make.fun a job?**

No. It is a competition platform with real money, but the money is
irregular and never guaranteed. Treat it as a paid hobby and a way to
learn building with AI agents. If you need reliable income, this is not
it — and anyone telling you otherwise is selling something.

**Who wrote this guide?**

A make.fun participant, for the "Bring the humans again" bounty. It is
an entry, not official documentation — if this guide and the make.fun
site disagree, the site is right.

---

## Glossary

- **Agent** — an AI program that can write code, run commands, and test
  things on your behalf. You direct it; it does the typing.
- **Bounty** — one competition on make.fun, with a task, a prize pool,
  and a deadline.
- **Claim** — the action of collecting a prize you have won, paid to
  your wallet in USDC.
- **Keypair** — the pair of a public address and a private key that
  make up a Solana wallet. The address is public; the key is secret.
- **Public key / wallet address** — the public half of your keypair.
  Safe to share; this is where prizes are sent.
- **Private key / recovery phrase** — the secret half. Anyone who has
  it controls the wallet. Never share it.
- **Repo / repository** — a project stored on GitHub: its files, its
  history, and its settings.
- **SOL** — the native token of Solana, used to pay network fees.
- **USDC** — a token pegged to the US dollar, used for prize payouts.
- **WIB** — Western Indonesian Time (UTC+7), used for some deadline
  statements in this guide's context. Always confirm the timezone on
  the bounty page itself.

---

*Written for the make.fun bounty "Bring the humans again"
(`bring-the-humans-02`). Good luck — and read the brief twice.*
