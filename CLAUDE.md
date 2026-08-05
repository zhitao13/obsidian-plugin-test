# Project purpose

This repo doubles as an Obsidian vault for capturing and developing ideas
through conversation. The user talks through an idea; Claude elaborates it
into a proper note and files it in the vault, then keeps the vault's hub
note up to date so everything stays reachable by links.

This is on top of (not a replacement for) the repo's other purpose as the
Obsidian Sample Plugin scaffold (`main.ts`, `manifest.json`, etc.) — the
vault content and the plugin code live side by side and don't interact.

# Vault structure

- `notes/` — one Markdown file per idea/topic.
- `Home.md` — the hub note. Every note in `notes/` must be linked from here.

# Workflow: when the user shares an idea

Notes are written in **Chinese** (the user's notes are primarily Chinese).
Headings, body text, and tags should be Chinese unless the idea is
inherently English (e.g. a foreign term, a proper noun, code).

1. **Discuss before writing.** Don't turn the first message straight into a
   note. Ask clarifying/probing questions — what prompted it, what they
   mean by ambiguous terms, edge cases, how it connects to things they
   already think about — and keep the conversation going until the idea
   feels developed enough to write up. This can take several exchanges.
2. **Draft a summary first, before writing/pushing anything.** Post the
   note's content as a chat reply for the user to review. This summary
   must go deeper than restating what the user said — surface patterns,
   implications, tensions, or connections that came out of the back-and-forth
   of the conversation, organized by theme rather than a cleaned-up
   transcript of the Q&A. Ask the user to edit or approve it.
3. **Wait for the user's go-ahead** (approval or edits) before creating the
   note file, updating `Home.md`, committing, or pushing. Fold in any edits
   the user gives before filing.
4. **File name**: matches the note's `# 标题` (heading), saved as
   `notes/<标题>.md`. Chinese filenames are fine; spaces are fine too.
5. **Frontmatter** at the top of every note:
   ```yaml
   ---
   created: <YYYY-MM-DD>
   tags: []
   ---
   ```
   Fill `tags` in — never leave it empty. Pick a handful of concise
   Chinese keywords/themes for the note (topic, domain, concept — whatever
   someone would search by later). Check other notes in `notes/` first and
   reuse an existing tag where it genuinely fits, instead of coining a
   near-duplicate; add a new one when the idea doesn't fit what's there.
6. **Keep tags current on updates too.** Whenever an existing note's
   content changes meaningfully, re-check its `tags` — add any that now
   apply and drop ones that no longer fit. Don't let tags go stale.
7. **Link liberally.** Use Obsidian wikilinks (`[[笔记名]]`) to connect a
   new note to existing related notes, and add a reciprocal link back from
   those existing notes if it makes sense.
8. **Update `Home.md` immediately** — every time a note is added, renamed,
   or removed, update `Home.md` in the same turn so its links never go
   stale. Group links under topical headings (create a new heading if the
   note doesn't fit an existing one); don't just append to a flat list.
9. Once the summary is approved, don't ask permission again for the
   mechanical parts (writing the file, updating `Home.md`, committing,
   pushing) — that's expected on every approved idea. Do check in if an
   idea is too thin to turn into a standalone note (suggest folding it
   into an existing one instead).

# Conventions

- Keep notes atomic: one idea/topic per note. Split a note that's grown
  into multiple unrelated topics rather than letting it sprawl.
- Prefer linking to a related note over duplicating its content.
- No comments-about-the-process inside notes (e.g. "Claude added this on
  ...") — notes should read as the user's own knowledge base.

# Git

This is a personal-use repo. Commit and **push directly to `master`** —
no feature branches, no pull requests.
