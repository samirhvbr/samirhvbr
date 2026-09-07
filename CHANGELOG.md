# Changelog

Entries in the commit-message format (`version - short description in English`),
newest first. **Each `##` heading is literally the commit subject** — the entry
is written *before* the commit, so the sentence that lands in `git log` is one
that was weighed rather than improvised at `git commit` time.

Bodies are narrative: what changed, why, and what was measured. This file is
never rewritten.

> **The record starts here.** This file was created after the repository was:
> earlier versions are in `git log` and are deliberately not back-filled, because
> reconstructing them now would produce a plausible history rather than a true
> one.


## 1.0.8 - the git hooks are regenerated from repodocs

Both hooks of the standard now run here: `commit-msg`, which checks the shape of
the subject (`X.Y.Z - description`), refuses a Conventional Commits prefix and a
vague message, **and checks that the subject's `X.Y.Z` is the version this commit
carries in `version.md`**; and `pre-push`, which compares the local `version.md`
against the remote default branch for a repeated version and for one that moves
backwards.

The hook does **not** check the language and could not: what it measures is the
shape and the number.

Until now the commit rule lived here only as prose in `CLAUDE.md`, and prose is
what gets forgotten at the end of a long session. On 07/09/2026 the hooks were
enabled in 3 clones out of 58, and two repositories of the fleet were measurably
off the norm with nothing to say so.

Escape hatch, declared in both: `REPODOCS_NO_HOOK=1`. It exists so the hooks stay installed —
a guard with no declared bypass gets bypassed with `--no-verify`, which switches
off every guard at once. In a fresh clone, enable them with
`git config core.hooksPath tools/git-hooks`.
