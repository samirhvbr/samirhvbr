# Version — GitHub Profile — samirhvbr

**Current version:** `1.0.8`

GitHub profile README (@samirhvbr), terminal aesthetic.

> Default branch: **`master`**. What lives here shows up on the profile page, so a
> layout change is a public change — it earns the bump.

> This file is the **source of truth** for the project version: anything that needs
> to show or report the version extracts the **first semver number (`X.Y.Z`)** found
> here. Keep the **"Current version"** line as the first occurrence of a number.
>
> `0.1.0` marks the start of **versioning**, not the start of the project — whatever
> came before stays in the `git log`.

---

## 1. Versioning Convention (`X.Y.Z`)

| Component | Meaning | How it moves |
|---|---|---|
| **X** | Stable release | Manual |
| **Y** | Structural change — new section in the set, scope change, structural reorganization. | Manual |
| **Z** | Increment on every delivery (see triggers) | Every delivery |

### `Z` bump triggers

- Creating or removing a **document** from the set.
- Changing a **rule, decision or procedure** already published.
- Altering **structure or format** that another tool consumes.
- Adding or changing **data/examples** that serve as reference.

> Text fixes, comments and formatting do **not** require a bump.

---

## 2. Mandatory Commit Format

```
X.Y.Z - Short description in English
```

**Non-negotiable rules:**

1. The version **always** comes from this `version.md` — bump it **in the same commit**
   as the change.
2. Message in **English**, specific enough for `git log --grep` — see §2.1.
3. Conventional Commits (`feat:`, `fix:`, `chore:`…) and vague messages ("tweak",
   "update", "wip") are **forbidden**.
4. One objective per commit.

### 2.1. Language — English on GitHub

**Everything that lands on GitHub is written in English.** Not just the commit
message: this `version.md` and its changelog, the README, `CLAUDE.md` / `AGENTS.md`,
branch names, PR and issue titles and bodies, and Release notes.

This is a **deliberate deviation from the fleet default**. The norm in
[repodocs](https://github.com/samirhvbr/repodocs) is Portuguese and the other repos
keep it; this repo is the profile page, read by a mostly international audience, so
it should not switch languages between what it shows and how it is written.

Whoever writes here in Portuguese is not making a small style slip — they are reading
a stale rule. The rule lives in **three** places that must agree: this section,
`CLAUDE.md` and `AGENTS.md`. If they ever disagree, the agent docs are what an agent
actually reads before committing, so fix those first.

> **Known exception, left on purpose:** commit `1.0.1` is in Portuguese. It was
> written while `CLAUDE.md` still said `versão - comentário em português`, and it is
> not worth rewriting published history to fix — the tag and the Release point at it.
> `1.0.2` is what closes that gap in the docs.

> **The COMMITTER skill commits for you in this repo** (there is a `.committer.yml`
> at the root). Write the changelog entry below when you finish the delivery: that is
> **where** the commit message comes from, at no model cost. Without the entry, the
> skill falls back to a path that burns tokens and describes the work worse than you
> would. Details in the PS block of `CLAUDE.md`.

---

## 3. Changelog

> Descending order (most recent on top).

### `1.0.3` — 2026-09-02 — Agent doc: Releases rule and the English-only language rule

Marked echo of the single source at samirhvbr/repodocs. Two rules land here:

1. The `version.md` of the default branch ON GITHUB is what the GitHub Releases
   show, and a commit that bumps it is not finished until that version has a
   tag, a Release and the `Latest` badge — same push, not "later".
2. Everything in this repository is English (US): documents, commit messages,
   pull requests, issues, code comments. The only carve-out is end-user-facing
   product strings. History is not rewritten.

Delimited by a marker, so re-running replaces instead of duplicating.

### `1.0.2` — 2026-09-03 — English on GitHub is stated where agents read it; default branch back to master

`0.1.2` put "message in English" in `version.md` and stopped there. `CLAUDE.md` and
`AGENTS.md` — the files an agent reads *before* it commits — still said
`versão - comentário em português`. So the rule existed and was contradicted at the
exact moment it applied, and commit `1.0.1` came out in Portuguese. That is not a
slip by whoever committed; it is what the docs told them to do.

Both agent docs now carry the language rule, and `version.md` gains **§2.1**, which
widens it past commit messages to everything that lands on GitHub: changelog, README,
agent docs, branch names, PR and issue text, Release notes.

`1.0.1` stays in Portuguese on purpose — rewriting published history to fix a commit
subject is not worth it when a tag and a Release already point at it. It is recorded
as a known exception in §2.1 instead of being quietly cleaned up.

The default branch is renamed **`main` → `master`** in this same delivery, aligning
this repo with the rest of the fleet, and `.committer.yml` follows it
(`branch_only: master`). The rename goes through GitHub's own branch-rename, which
retargets open PRs and leaves a redirect, rather than a push-new/delete-old that would
drop both. `release.yml` already listened on `[master, main]`, so the automation needed
no change.

Note on the `0.1.1` entry below: it originally said "master", `1.0.2` of this file had
corrected it to "main" because that was the branch at the time, and the branch is now
`master` again. The entry is left describing what was true when it was written — the
changelog is a record, not a live mirror of the current layout.

_Triggers:_ published rule changed; document of the set changed; structure another tool
consumes altered (`.committer.yml`).

### `1.0.1` — 2026-09-02 — Regra de Releases no doc de agente: bump e Release sao um ato so

Eco marcado da norma unica em samirhvbr/repodocs (docs/versioning.md). O
`version.md` da branch padrao NO GITHUB e o que as Releases no GitHub mostram, e
um commit que bumpa o `version.md` nao esta terminado ate aquela versao ter tag,
Release e o badge `Latest`.

Bloco delimitado por marcador: rodar de novo substitui, nao duplica.

### `1.0.0` — 2026-09-02 — First stable release of the profile

Declares the profile stable at `1.0.0`. The three pieces that make it one are in
place: the content is in English, the versioning convention is documented and
followed, and the Release automation publishes a tag per version without anyone
asking it to.

Content change in this delivery: the ecosystem section header reads
`$ cat ~/ecosystem.md` instead of `.mmd`. Both are defensible — `.mmd` is the
conventional extension for a raw Mermaid file — but what the section actually shows
is a fenced `mermaid` block inside a Markdown document, which a bare `.mmd` would
not carry. `.md` is the honest description of what is being `cat`-ed.

_Triggers:_ stable release (manual **X** bump); reference content changed.

### `0.1.2` — 2026-09-02 — Everything in English, including the commit convention

The profile README is the page a mostly international audience lands on, so it is now
written in English: the `fastfetch` block, the Mermaid ecosystem graph, the product
and open-source tables, `stack.toml` and the badge labels.

The convention docs follow the content: this `version.md` and the comments in
`.committer.yml` are in English too, and rule 2 of the commit format now reads
**English** instead of Portuguese. This repo deliberately diverges from the rest of
the fleet on commit language — the norm elsewhere stays Portuguese.

Also fixed: the `0.1.1` entry said the Releases follow "the `version.md` on **master**",
but the working branch here is **`main`** — `.committer.yml` pins `branch_only: main`.
The workflow already listened on both, so nothing was broken in practice; the text was.

_Triggers:_ published rule changed (commit language); format that another tool consumes
altered.

### `0.1.1` — 2026-09-02 — Automatic releases: the version.md on main becomes a tag and a Release

GitHub does not infer a version from a commit message: without a tag, the number is a
string in the `git log` and a `git diff` between versions does not exist. Enter
`.github/workflows/release.yml` and `tools/release.sh`.

**The rule:** the `version.md` on the default branch **on GitHub** is what the Releases
**on GitHub** reflect. A local checkout does not enter the calculation. A PR publishes
nothing; on merge, the push of `version.md` triggers the workflow and the Release
becomes that version.

Tag and title = the bare version, no `v` prefix. Norm:
[samirhvbr/repodocs](https://github.com/samirhvbr/repodocs/blob/master/docs/versioning.md).

### `0.1.0` — 2026-07-30 — Adopts the house versioning

Starts following the pattern of the other repositories: `version.md` as the source of
truth, commits in the `X.Y.Z - Description` format and a changelog as the delivery
record.

The trigger was practical: the repo already took part in the **COMMITTER** skill, but
without a `version.md` there was no house format — the cycle reported and did **not**
commit. With this file, the skill starts operating here through the deterministic path
(at no model cost), reading the message from the changelog entry.

_Triggers:_ adoption of versioning infrastructure.
