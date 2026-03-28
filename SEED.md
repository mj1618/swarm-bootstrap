# Overview

Look at @swarm/swarm.yaml

Your job is to look for a programming language that is available to you on this machine, and to build a small CLI tool in ./swarm-cli/ that will run and manage the agent pipeline defined in swarm.yaml
swarm.yaml defines a pipeline with dependencies, each task in the pipeline is an agent run with a fresh context window.
The prompt is fed into the agent and run to completion.
Once an agent completes the next agent in the pipeline is run.
When the pipeline reaches the end it loops back to the first agent for the set number of iterations.

Make a CLEAR seperation between the folder this cli tool is running in, and the source code of the project itself.

Finally test the script out and make sure it works properly.

# Model

Look at whether there is codex or claude available on the local machine.
Each agent should be run with skip permissions and in streaming mode.
It should use the Opus model if in claude, or codex-5.3 if in codex.

# Features

The user should be able to see the progress of all agents, and be able to stop all of them from running and then restart when ready.

Ensure there is a stop command which also kills all agents created by the CLI.

Ensure the tool kills everything when a user ctrl-c's out of the npm start command.
Make sure agents started by the tool are also force-killed.

Run the agent with streaming output and write this to log files.
The log files should be gitignore'd.
Ensure it is indicated to the user where the log files are and how to access them.

Make sure the claude agent exits if claude sends a "type":"result" message.

# Docs

Save instructions to swarm-cli/README.md on how to run the script, or stop the agents, etc.

Update .gitignore so that nothing is committed to the repo that shouldn't be.

# Programming Language

Prefer using the following in order:

- Typescript/Node
- Golang
- Python
- fall back to whatever scripting is available on the machine
