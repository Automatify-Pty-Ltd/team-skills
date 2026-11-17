# Team skills

A catalog of links to the agent skills the Automatify team uses. Each entry points to the skill at its source repo. The skill files live at their sources, and this repo records where to find them.

## Why

Most Automatify repos run coding agents. When each repo picks its own skill set, agents behave differently on the same task across repos. This catalog is the one list the team installs from. Skill files stay at their sources, so attribution and updates stay with the authors.

## Quick start

1. Pick a skill from the catalog below.
2. Install it. The source repo documents its install command. The common path is the skills registry CLI:

   ```bash
   npx skills add <owner>/<repo> --skill <skill-name>
   ```

   Or copy the skill folder into the skills directory your agent reads:

   ```text
   pi:          ~/.pi/agent/skills/ or ~/.agents/skills/
   Codex:       ~/.agents/skills/ or ~/.codex/skills/
   Claude Code: ~/.claude/skills/
   ```

   Sample download for one skill, using the grilling entry:

   ```bash
   git clone --depth 1 https://github.com/mattpocock/skills /tmp/skills
   mkdir -p ~/.agents/skills
   cp -r /tmp/skills/skills/productivity/grilling ~/.agents/skills/
   rm -rf /tmp/skills
   ```

   The shared `~/.agents/skills/` directory works for pi and Codex.

3. Invoke the skill in your agent chat. Say "grill me" for grilling, or "/show-me" for show-me, or name the skill and its task.

Command line tools install their own way. See the section for slop-scan below.

## Catalog

### Reviews and pull requests

| Skill | What it does | Source |
|---|---|---|
| [pr-writing](https://github.com/telepath-computer/team-skills/tree/main/pr-writing) | Write a pull request description for squash merge review. It describes the net change against the merge base. | [telepath-computer](https://github.com/telepath-computer/team-skills) |
| [visual-pr](https://github.com/humanlayer/skills/tree/main/plugins/visual-pr/skills/visual-pr) | Create or update a pull request with a compact visual outline of the change. | [humanlayer](https://github.com/humanlayer/skills) |
| [ponytail-review](https://github.com/DietrichGebert/ponytail/tree/main/skills/ponytail-review) | Review a change for logic, safety, load, tests, speed, and lines nobody needs. It reads the code around the diff. | [DietrichGebert](https://github.com/DietrichGebert/ponytail) |
| [ponytail-audit](https://github.com/DietrichGebert/ponytail/tree/main/skills/ponytail-audit) | Audit a whole repo. It ranks bugs, security gaps, untested risky code, slow paths, and code to delete. One-shot report. | [DietrichGebert](https://github.com/DietrichGebert/ponytail) |

### Code discipline

| Skill | What it does | Source |
|---|---|---|
| [ponytail](https://github.com/DietrichGebert/ponytail/tree/main/skills/ponytail) | Write the smallest change that fully solves the task. Levels: lite, full, ultra. | [DietrichGebert](https://github.com/DietrichGebert/ponytail) |
| [ponytail-debt](https://github.com/DietrichGebert/ponytail/tree/main/skills/ponytail-debt) | List every `shortcut:` comment as a debt ledger. One-shot report. | [DietrichGebert](https://github.com/DietrichGebert/ponytail) |
| [ponytail-gain](https://github.com/DietrichGebert/ponytail/tree/main/skills/ponytail-gain) | Show ponytail's measured code, cost, and speed savings. One-shot display. | [DietrichGebert](https://github.com/DietrichGebert/ponytail) |
| [ponytail-help](https://github.com/DietrichGebert/ponytail/tree/main/skills/ponytail-help) | Show a quick reference for ponytail levels, skills, and commands. | [DietrichGebert](https://github.com/DietrichGebert/ponytail) |
| [slop-scan](https://github.com/modem-dev/slop-scan) | Scan JavaScript or TypeScript code for AI slop patterns from the command line. | [modem-dev](https://github.com/modem-dev/slop-scan) |

Ponytail stays active for the rest of the session after you start it. Switch level with `/ponytail ultra`, and switch it off with "stop ponytail".

slop-scan is a command line tool, so install it with npm: `npm install -g slop-scan`, then run `slop-scan scan .`.

### Writing

| Skill | What it does | Source |
|---|---|---|
| [cold-reader](https://github.com/telepath-computer/team-skills/tree/main/cold-reader) | Write documents for readers who hold no history with the project. | [telepath-computer](https://github.com/telepath-computer/team-skills) |
| [unslop](https://github.com/cursor/plugins/tree/main/pstack/skills/unslop) | Remove AI writing patterns from text and add human voice. | [cursor](https://github.com/cursor/plugins) |

### Skill authoring

| Skill | What it does | Source |
|---|---|---|
| [skill-creator](https://github.com/mgechev/skills-best-practices/tree/main/skill) | Write and structure agent skills that follow the agentskills.io spec. | [mgechev](https://github.com/mgechev/skills-best-practices) |

### Explaining and deciding

| Skill | What it does | Source |
|---|---|---|
| [grilling](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling) | Interview the user in numbered rounds until every decision in a plan is settled. | [mattpocock](https://github.com/mattpocock/skills) |
| [show-me](https://github.com/humanlayer/skills/tree/main/plugins/show-me/skills/show-me) | Explain the current topic with pseudocode, call trees, component trees, Mermaid diagrams, or one small HTML artifact. | [humanlayer](https://github.com/humanlayer/skills) |

## Adding a skill

Open a pull request with:

1. One row in the matching table. Link straight to the skill folder at its source.
2. One sentence that says what the skill does.
3. No copied skill files. The source repo owns the files, the updates, and the license text.

## Credits

| Source | Author | License at source |
|---|---|---|
| [telepath-computer/team-skills](https://github.com/telepath-computer/team-skills) | Telepath | MIT |
| [humanlayer/skills](https://github.com/humanlayer/skills) | HumanLayer | MIT |
| [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | Dietrich Gebert | MIT |
| [modem-dev/slop-scan](https://github.com/modem-dev/slop-scan) | modem-dev | MIT |
| [cursor/plugins](https://github.com/cursor/plugins) | Cursor | none published |
| [mattpocock/skills](https://github.com/mattpocock/skills) | Matt Pocock | MIT |
| [mgechev/skills-best-practices](https://github.com/mgechev/skills-best-practices) | Minko Gechev | none published |

Each linked skill keeps the license of its source repo. The catalog text in this repo is MIT.

## License

MIT. See [LICENSE](LICENSE).
