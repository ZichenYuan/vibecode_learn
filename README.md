# Learn Mode — A Claude Code Skill for Growing Developers

**Turn every AI coding session into a learning opportunity.**

Learn Mode is a Claude Code skill that watches what the AI does during your session, then explains the concepts, saves structured notes, and helps you build a personal knowledge base over time — all with a single command.

---

## Why Learn Mode?

Most AI coding tools solve your problem and move on. You get working code, but you don't always understand *why* it works. Over time, you're shipping code you can't explain.

Learn Mode fixes this. After the AI completes a task, say `/learn` and it becomes your mentor — breaking down what happened, naming the concepts, and saving notes you can revisit later.

### The Problem It Solves

| Without Learn Mode | With Learn Mode |
|---|---|
| AI writes code, you copy-paste it | AI writes code, then teaches you the concepts behind it |
| You forget what you learned last week | Notes are saved, organized, and reviewable |
| Scattered bookmarks and screenshots | One searchable knowledge base at `~/learning-notes/` |
| No sense of progress | Review mode shows your growth over time |

---

## Quick Start

### 1. Install

Copy this skill into your Claude Code skills directory:

```bash
cp -r vibecode_learn ~/.claude/skills/
```

### 2. Use It

After the AI completes any task in your session:

```
/learn
```

That's it. Learn Mode will:
1. Analyze what just happened in your session
2. Explain the key concepts in plain English
3. Save a structured note to `~/learning-notes/`
4. Update your index so everything stays organized

### 3. Review What You've Learned

```
/learn review my notes
```

Get a summary of your recent learning, spaced repetition prompts, and suggestions for topics to revisit. Great as a weekly habit.

### 4. Keep Notes Organized

```
/learn organize my notes
```

Finds duplicates, adds cross-links between related notes, and cleans up miscategorized entries. Run this monthly or after a learning sprint.

---

## What Makes It Smart

### Built on Cognitive Science

Learn Mode isn't just a note-taker. Every design decision is grounded in how the brain actually learns:

- **Chunking** — Each note covers one concept well, not five concepts poorly. Complex topics get split into focused, digestible pieces.

- **Elaborative Interrogation** — Notes don't just state facts. They ask *why* and *how*, which forces deeper processing and stronger memory encoding.

- **Dual Coding** — Every explanation is paired with a concrete code example. The brain encodes verbal and visual information through separate channels — having both strengthens recall.

- **Progressive Summarization** — Notes have layers: a one-line TL;DR for quick revisits, key takeaways for a 30-second refresher, and a full explanation for deep study. You access the right level of detail for your current need.

- **Spaced Repetition** — Review mode tracks when you learned each concept and prompts you to revisit at optimal intervals (1 day, 3 days, 1 week, 2 weeks, 1 month).

- **Active Recall** — During review, you're prompted to explain concepts *before* seeing the answer. This retrieval practice is one of the most effective study techniques known.

- **Interleaving** — Reviews mix topics from different categories rather than grouping by subject. This builds your ability to distinguish between concepts and apply the right one in context.

- **Connection Over Isolation** — Every note links to related concepts. The brain stores knowledge in networks, not lists — isolated facts are forgotten faster.

### Note Maturity Tracking

Notes grow with you through three stages:

| Status | Meaning | When |
|--------|---------|------|
| `seedling` | Just learned, still fresh | First encounter |
| `growing` | Revisited, understanding deepening | After review or re-encounter |
| `evergreen` | Solid understanding, reliable reference | Confident knowledge |

This gives you an honest picture of what you actually know vs. what you've only seen once.

---

## Works With Your Tools

### Obsidian

Notes use YAML frontmatter (`title`, `date`, `category`, `tags`, `difficulty`, `status`) that Obsidian reads natively. You get:

- **Graph view** — See how your concepts connect visually
- **Dataview queries** — Filter notes by tag, difficulty, status, or date
- **Search** — Tags and frontmatter make everything findable
- **Wikilinks** — Notes link to each other with `[[Note Title]]` syntax

Just point your Obsidian vault at `~/learning-notes/` and everything works.

### Notion

Import the markdown files into Notion and the YAML frontmatter becomes database properties automatically. Tags, categories, and dates all map cleanly.

### Plain Markdown

No tools needed. Notes are well-structured markdown files organized in folders. Browse them in any text editor, GitHub, or VS Code.

### Search

```bash
# Find all notes about async programming
grep -r "async" ~/learning-notes/

# Find all beginner-level notes
grep -r "difficulty: beginner" ~/learning-notes/
```

---

## How Notes Are Organized

Notes are categorized by **skill area**, not specific technology — so they map to how you actually think about programming:

```
~/learning-notes/
├── README.md              # Auto-maintained index of all notes
├── language/              # Python decorators, Go goroutines, JS promises
├── data-structures/       # Hash maps, linked lists, trees
├── algorithms/            # Binary search, BFS/DFS, Big-O
├── debugging/             # Stack traces, breakpoints, log analysis
├── git/                   # Branching, merging, resolving conflicts
├── terminal/              # Bash basics, piping, environment variables
├── apis/                  # REST, GraphQL, auth tokens, status codes
├── databases/             # SQL JOINs, indexes, schema design
├── testing/               # Unit tests, TDD, mocking
├── architecture/          # Design patterns, MVC, system design
├── errors/                # Error handling, validation, edge cases
├── tooling/               # VS Code, linters, Docker, build tools
├── web/                   # HTML/CSS, responsive design, accessibility
├── devops/                # CI/CD, deployment, containers
├── security/              # Auth, XSS, SQL injection, secrets
├── general/               # Code review, reading docs, career skills
└── reviews/               # Weekly review summaries
```

An auto-maintained `README.md` index keeps everything browsable with dates and one-line descriptions.

---

## Example Session

```
You:   "Help me set up a REST API with Express"
AI:    [sets up routes, middleware, error handling]

You:   "/learn"
AI:    ### What happened
       We built a REST API with Express.js using route handlers,
       middleware for JSON parsing, and centralized error handling.

       ### Key Concepts
       1. **Middleware** — Functions that run between receiving a request
          and sending a response. Think of them as checkpoints...
       2. **Route handlers** — Functions mapped to URL patterns...
       3. **Error handling middleware** — A special 4-parameter function...

       ### Key Takeaways
       - Middleware runs in order — sequence matters
       - Always add error handling middleware last
       - Use `express.json()` to parse request bodies

       Note saved to ~/learning-notes/apis/express-rest-api-setup.md
```

---

## Commands Reference

| Command | What It Does |
|---------|-------------|
| `/learn` | Analyze the current session, teach concepts, save a note |
| `"what did you just do?"` | Same as `/learn` |
| `"explain the changes"` | Same as `/learn` |
| `"review my notes"` | Summarize recent learning, suggest topics to revisit |
| `"quiz me"` | Active recall prompts on past notes |
| `"organize my notes"` | Deduplicate, cross-link, and clean up the knowledge base |

---

## License

MIT — use it, share it, learn from it.
