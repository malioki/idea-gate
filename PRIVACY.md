# Privacy

Idea Gate collects nothing.

- It contains no code that runs on your machine, no MCP servers, no hooks and no network calls. It is plain instructions for Claude.
- It reads files only inside your own Claude session: your profile (`.claude/idea-gate/profile.md` or `~/.claude/idea-gate/profile.md`) and the decision log the profile points to. Those files stay where they are.
- If your profile tells it to, it writes the verdict to your own decision log and task list, in your project. Nothing is sent to the author or to any third party.

What Claude itself does with your conversation is covered by Anthropic's privacy policy, not this plugin.

Questions: [open an issue](https://github.com/malioki/idea-gate/issues).
