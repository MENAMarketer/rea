# Working in this repository

This is Wade Eagar's fork of [morluto/rea](https://github.com/morluto/rea), REA, Reverse Engineer Anything. It exists for two reasons. It pins the version of REA that the Marketing Intelligence System depends on, through the `rea` plugin in `MENAMarketer/Marketing-Intelligence-System`. And it is where Wade reads REA's code and documentation, and where any change he wants to propose upstream starts. It is not a second REA.

Everything below is about how Wade works. The sister file, `AGENTS.md`, is upstream's and is about how REA is built. Where the two meet, this file says which wins.

## Two kinds of file

Upstream's files are REA's: the source under `src/`, `bridge/`, `scripts/` and `tests/`, the documentation under `docs/`, the skill under `.agents/skills/`, `AGENTS.md`, `CONTRIBUTING.md` and the rest. They follow upstream's conventions, including American spelling and Conventional Commit subjects, and they stay as upstream wrote them so that merging from upstream stays clean. Do not restyle them to Wade's voice. A change to one of them is a change Wade intends to send upstream, made the way `CONTRIBUTING.md` asks, on a branch, with the verification it names.

Ours are this file and anything Wade writes here in his own name: an issue, a pull request description, a note, a proposal to the maintainers. Those are in Wade's voice. Load `wade-voice:wade-voice` before drafting any of them and run `wade-voice:wade-editor` before they go anywhere. The register is client for anything that leaves the building, including an upstream issue or pull request, and internal for a note to himself.

## How Wade works, and how that applies here

**Show the plan and wait for yes.** Nothing writes configuration, installs an analysis engine, runs `rea setup`, changes an MCP registration or touches a device without the exact plan being shown first: the paths, the backups, what changes. Then wait. REA's own rule in `AGENTS.md` says the same for `rea setup`, so the two agree; this file extends it to everything. Never install or upgrade unrelated software to repair anything. That includes Node.js, npm, Homebrew, Java, Ghidra and IDA.

**Evidence stays labelled.** REA separates observations, derivations, inferences and unknowns and keeps the provenance of each. Keep them separate in anything written here. When a finding from REA travels into MIS work it takes the MIS labels: an observation is Observed, a derivation is Estimated with the working shown, an inference is Hypothesis for review, an unknown is Unknown with what was tried, and a product's own claim about itself is Vendor stated. Static analysis never implies that execution was observed. A finding carries the artifact, the version, the platform and the date, or it is not a finding.

**Entitlement outranks the brief.** REA's `DISCLAIMER.md` is the rule. Public artifacts and public pages, and Wade's own or a client's own property with permission, are in scope to observe. Anything behind a login the work has no account of its own for, a paywall, a licence check, tamper protection or bot protection is not. Nothing proprietary from a target is copied into anything we write. Where a target sits close to the line, ask Wade one question before touching it.

**Ask one question when unsure.** Which target, which app, which question. Never choose an example target on Wade's behalf, never fill a gap with a guess, and never fill it with a hedge. Upstream's skill says the same about "my app"; it holds for everything.

**Nothing changes silently.** A change to this repository is a commit with a message that says what changed and why. A change that affects the MIS plugin is recorded in that repository's `changes/CHANGELOG.md` as well.

## Marketing questions do not run here

A question about a competitor's app, site or stack, a martech read, a journey teardown or a feature check is Marketing Intelligence System work. It runs through `rea:rea-marketing-teardown`, the MIS product research agent in the `rea` plugin, which reads the brief, holds the entitlement rule, maps REA's evidence onto the MIS labels and saves in the MIS file conventions with an editor pass. Open the client folder or the MIS repository for that work, not this one. This repository is for REA itself.

## Keeping in step with upstream

The remotes are `origin`, this fork, and `upstream`, morluto. To take upstream's latest:

```bash
git fetch upstream && git merge upstream/main && git push origin main
```

Then refresh the plugin: copy `.agents/skills/reverse-engineer-anything` over `plugins/rea/skills/reverse-engineer-anything` in the MIS repository, change the version in `plugins/rea/.mcp.json` to the matching npm release of `rea-agents`, update the commit recorded in `plugins/rea/NOTICE.md`, bump the plugin, and record it in `changes/CHANGELOG.md` there. Pin to one exact version; REA's own guidance says the same and the plugin follows it.

## Skills to load here

`rea:reverse-engineer-anything` is the operating manual for REA's tools and is loaded for any investigation. `wade-voice:wade-voice` is loaded for anything Wade signs. Upstream's `AGENTS.md` is read before any change to upstream's files, and `docs/tool-design.md` and `docs/testing.md` before a tool or test change.
