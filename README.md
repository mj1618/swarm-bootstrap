# Swarm Bootstrap

This helps you run a pipeline of ralph loops from scratch to build a project in a zero-shot way.

Do this:

1. Update PLAN.md with your project requirements
2. Ask Claude to implement "SEED.md" - which creates the tool to run the pipeline
3. Ask Claude to run the pipeline

# View the logs

```bash
tail -n 10 -F swarm-cli/logs/*.log | grep --line-buffered -E '^\s*[\[{]' | npx @khanacademy/format-claude-stream
```
