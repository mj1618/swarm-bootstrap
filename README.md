# Swarm Bootstrap

This helps you run a pipeline of ralph loops from scratch to build a project in a zero-shot way.

Do this:

1. Update PLAN.md with your project requirements
2. Ask Claude to implement "SEED.md" - which creates the tool to run the pipeline
3. Ask Claude to run the pipeline

# View the logs

```bash
{ declare -A s; while sleep 2; do for f in logs/*.log; do [[ ${s[$f]} ]] || { tail -n10 -F "$f" & s[$f]=1; }; done; done; } | grep --line-buffered -E '^\s*[\[{]' | npx @khanacademy/format-claude-stream
```
