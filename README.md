# AI Registry — TypeFox GmbH

Vendor repository for the [AI Registry](https://github.com/eclipsefdn-ai-registry/ai-registry-core), maintained by [TypeFox GmbH](https://www.typefox.io). Contains approvals for AI artifacts published or approved by TypeFox.

## Approvals

| File | Artifacts |
| :--- | :-------- |
| [`skills/io.github.typefox.json`](skills/io.github.typefox.json) | All skills under `skills/` in [TypeFox/agent-skills](https://github.com/TypeFox/agent-skills), published as `io.github.typefox/<skill-name>` |
| [`skills/io.github.eclipse-langium.json`](skills/io.github.eclipse-langium.json) | All skills under `skills/` in [eclipse-langium/langium-ai](https://github.com/eclipse-langium/langium-ai), published as `io.github.eclipse-langium/<skill-name>` |

The skills approvals use a glob and track the default branch, so a skill added to the source repo is picked up by the next consolidation run without a change here.

## Contributing

1. Add one JSON file per approved artifact to `mcp/`, `skills/`, `plugins/`, `agents/`, or `sandbox-extensions/`. The file name is the artifact ID with `/` replaced by `--`. The central repository provides agent skills that generate these files: [MCP](https://github.com/eclipsefdn-ai-registry/ai-registry-core/blob/main/skills/create-mcp-approval/SKILL.md), [skill](https://github.com/eclipsefdn-ai-registry/ai-registry-core/blob/main/skills/create-skill-approval/SKILL.md), [plugin](https://github.com/eclipsefdn-ai-registry/ai-registry-core/blob/main/skills/create-plugin-approval/SKILL.md), and [agent](https://github.com/eclipsefdn-ai-registry/ai-registry-core/blob/main/skills/create-agent-approval/SKILL.md) approvals.
2. Validate locally:

   ```sh
   npm run validate           # standalone — clones the central repo automatically
   npm run validate:local     # fast — requires ai-registry-core checked out as a sibling
   ```

3. Open a pull request to `main`. CI runs the same validation, and a push to `main` triggers the central consolidation.

TypeFox does not declare any tools in `organization.json`, so approvals here omit `installConfigs`.

## Documentation

See the [Vendor Guide](https://github.com/eclipsefdn-ai-registry/ai-registry-core#vendor-guide) in the central repository for how vendor repos work, how to add approvals, and how validation runs.
