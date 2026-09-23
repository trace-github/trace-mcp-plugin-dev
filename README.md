# Trace (development build)

Ask Trace Analyst about your business data from Claude or Cursor, in plain language.

This build connects to the Trace development environment. If you are a Trace customer,
install the main plugin instead:
[trace-mcp-plugin](https://github.com/trace-github/trace-mcp-plugin).

Trace models a business as a metric tree: a headline metric broken down into the inputs
that drive it. Trace Analyst reads that model, runs the analysis and writes up what it
found. This plugin connects your agent to Trace and teaches it to pass your question
through unchanged and give you the answer in full.

You need an account on the Trace development environment. The first time your agent
connects, Trace asks you to sign in through your browser.

It installs under its own name, so you can keep this and the main plugin side by side.

## Install in Claude

In Claude Code:

```
/plugin marketplace add trace-github/trace-mcp-plugin-dev
/plugin install trace-dev@trace-dev
```

On Claude.ai or in Claude Desktop, open Customize, then Plugins, add
`https://github.com/trace-github/trace-mcp-plugin-dev` as a marketplace, then install
Trace from it.

Run `/mcp`, choose `TraceAnalystDev` and sign in when prompted.

## Install in Cursor

Open Customize, then Plugins, add
`https://github.com/trace-github/trace-mcp-plugin-dev` as a marketplace and install Trace
from it. Sign in when Cursor prompts you.

To connect the server on its own, without the guidance the plugin adds:

```
cursor://anysphere.cursor-deeplink/mcp/install?name=TraceAnalystDev&config=eyJ1cmwiOiJodHRwczovL2FwcC1hcGkuaGVsbG90cmFjZS5kZXYvbWNwIn0=
```

## What you can ask

Ask for a figure, or ask why something moved:

- What did revenue do last month?
- Why did conversion drop in the last quarter?
- Which segment is holding back growth?

Trace Analyst chooses the metric tree, the dates and the breakdown itself. You do not
need to know how your data is modelled to ask.

Investigations run for a while and report back as they go. Your agent keeps checking and
relays clarifying questions when the analyst has one, so answer in your own words and it
will carry your reply through.

## What it adds to your agent

- `trace-setup` connects to Trace and lists the metric trees your workspace has.
- `trace-analyst` asks a question and follows it through to a finished answer.
- `/trace-dev:trace-analyst` starts an investigation directly.
