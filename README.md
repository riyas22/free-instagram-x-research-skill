# Free Instagram & X Post Research Skill

**Free agent skill. No API key required.** Get a grounded answer from a specific Instagram reel, Instagram post, or X post. Built for ChatGPT Work, Codex, Claude, Claude Code, Gemini CLI, and other Agent Skills-compatible agents with suitable tools. It helps identify quoted text, summarize captions, trace reply context, and check claims against primary sources. It is designed to answer short questions directly, including “What does this reel say?”

[![Agent Skill](https://img.shields.io/badge/Agent-Skill-blue)](free-instagram-x-research/SKILL.md) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## What it does

- Reads a linked post's public caption or text and attributes it to the author.
- Uses web search first, then a browser for the exact public post when search lacks the needed content and browser access is permitted.
- For X replies, checks the parent post when available so a short reply makes sense.
- For fact-checks, follows the source links and separates the post's claim from the evidence.
- States when only the caption was available; it never pretends to have heard video audio or read an unavailable transcript.

## Supported links

`instagram.com/p/...` · `instagram.com/reel/...` · `x.com/.../status/...` · `twitter.com/.../status/...`

Profiles, feeds, posting, account analytics, and access to private content are outside this skill's scope.

## Supported agents and installation

This is a portable `SKILL.md` Agent Skill. The instructions are designed for **ChatGPT Work, Codex, Claude, Claude Code, Gemini CLI**, and other agents that support the Agent Skills format. Compatibility means the agent can load the instructions; results still depend on whether that agent has usable web search and public browser access.

| Agent | Add the skill |
| --- | --- |
| [ChatGPT Work](https://help.openai.com/en/articles/20001066) | In **Plugins → Skills**, choose **Create → Upload from your computer** and upload the skill package, where your account and workspace permit skills. |
| [Codex](https://developers.openai.com/plugins/build/skills) | Add the `free-instagram-x-research` folder to a Codex skills directory. |
| [Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude) | In **Customize → Skills**, upload a ZIP containing the skill folder, where custom skills are available. |
| [Claude Code](https://code.claude.com/docs/en/skills) | Place the folder at `.claude/skills/free-instagram-x-research/` in a project. |
| [Gemini CLI](https://codelabs.developers.google.com/gemini-cli/how-to-create-agent-skills-for-gemini-cli) | Place the folder at `.agents/skills/free-instagram-x-research/` in a project. |
| Other agents | Follow the agent's Agent Skills installation instructions and provide search and browser tools where available. |

The folder to install or ZIP is:

```text
free-instagram-x-research/
└── SKILL.md
```

The skill itself is free and requires **no API key**, Python package, or bundled fetch script. The agent or its search/browser tools may have their own access requirements or costs. Public websites can restrict access, so the skill reports what it could and could not inspect.

## Try it

```text
Use the free-instagram-x-research skill: What does this reel say?
https://www.instagram.com/reel/...
```

```text
Use the free-instagram-x-research skill: What does this X reply mean in context?
https://x.com/example/status/...
```

```text
Use the free-instagram-x-research skill: Is the claim in this post supported by its sources?
https://www.instagram.com/p/...
```

## How answers stay honest

The skill distinguishes **caption**, **visible text**, and **audio**. If it can only read a caption, it reports what the caption says. If the requested answer depends on inaccessible video or audio, it asks for a screenshot or recording. It does not invent engagement counts, quoted passages, or transcripts, and it does not bypass login or human-verification screens.

## Contributing

Issues and pull requests are welcome for broken retrieval paths, clearer attribution rules, and tested examples. Include a public post URL and describe what the skill should have answered, without sharing private account data.

## License

MIT. See [LICENSE](LICENSE).
