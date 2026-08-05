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
2. **Write the note as a summary, not a transcript.** Once the idea is
   developed, elaborate a proper note out of the *whole conversation* —
   organized by theme, not by Q&A turn. Don't paste the raw dialogue.
3. **File name**: matches the note's `# 标题` (heading), saved as
   `notes/<标题>.md`. Chinese filenames are fine; spaces are fine too.
4. **Frontmatter** at the top of every note:
   ```yaml
   ---
   created: <YYYY-MM-DD>
   tags: []
   ---
   ```
5. **Link liberally.** Use Obsidian wikilinks (`[[笔记名]]`) to connect a
   new note to existing related notes, and add a reciprocal link back from
   those existing notes if it makes sense.
6. **Update `Home.md` immediately** — every time a note is added, renamed,
   or removed, update `Home.md` in the same turn so its links never go
   stale. Group links under topical headings (create a new heading if the
   note doesn't fit an existing one); don't just append to a flat list.
7. Once the note is written and `Home.md` updated, no permission needed —
   that's expected behavior. But *do* ask before writing the note itself
   if the conversation hasn't gone deep enough yet to summarize well.

# Conventions

- Keep notes atomic: one idea/topic per note. Split a note that's grown
  into multiple unrelated topics rather than letting it sprawl.
- Prefer linking to a related note over duplicating its content.
- No comments-about-the-process inside notes (e.g. "Claude added this on
  ...") — notes should read as the user's own knowledge base.
