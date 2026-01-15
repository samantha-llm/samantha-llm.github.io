# Samantha LLM

`samantha-llm` is a persona and processes for memory management intended to
be bootstrapped into agentic LLMs supercharging their capabilities with a
consistent personality and long-term memory.

She will supercharge your agentic LLM experience, enabling it to work on
larger, more complex projects over time, with a consistent personality and
long-term memory.

## Agentic LLMs Supported

Out of the box, `samantha-llm` supports the following agentic LLM tools:
- [Claude Code](https://code.claude.com/docs/en/overview)
- [Abacus.ai Deep Agent](https://deepagent.abacus.ai/)
- [Github Copilot CLI](https://github.com/features/copilot/cli)

However, `samantha-llm` can operate with any agentic LLM tool. See below for
more details on manual setup.

## Quickstart

1. Clone the repository:
    ```bash
    git clone git@github.com:criswell/samantha-llm.git
    ```

2. Navigate to the project directory:
    ```bash
    cd samantha-llm
    ```

3. Install the samantha-llm script:
    ```bash
    ./samantha-llm install
    ```

4. Set up your preferred Agentic LLM tool:
    ```bash
    samantha-llm setup
    ```

5. Change to the directory where you want to work (this could be a git repo or
    anything else an agentic LLM can work with):
     ```bash
     cd /path/to/your/project
     ```

6. Start your agent:
    ```bash
    samantha-llm start
    ```

## Making the most of Samantha LLM

When you first bootstrap Samantha into your agentic LLM, she will have no
memories or project/tasks. It's up to you to direct her to work on tasks.

Adding a new project/task typically involves some variation of the following
phrase:

```
"Hi Samantha, I would like to start a new project with you. <project details>"
```

Samantha will then create a new project/task in her memory and either begin
working on it or ask you for more details.

My advice is to request her to come up with a comprehensive plan for what she
will be working on. Work with her to refine the plan until you are satisfied
with it. Once you have a solid plan, Samantha can begin executing it.

Samantha can handle multiple projects/tasks at once. Simply ask her to create
a new project/task, or ask her to switch between existing projects/tasks:

```
"Let's switch gears for the moment and work on <project name>."
```

### MCP Servers and Integrations

Because Samantha LLM is just a persona and process for memory management, she
can work with any MCP server or other integrations that you have set up for
your agentic LLM tool.

One MCP I highly recommend is [Serena](https://github.com/oraios/serena), which
provides your agentic LLM IDE-like tools, giving your agentic LLM the ability
to use semantic code retrival and editing on your codebase.

## Manual Setup

If your preferred Agentic LLM tool is not supported out of the box, you can
still use `samantha-llm` by manually launching your agentic LLM with the
`samantha-llm/BOOTSTRAP_PROMPT.md` prompt.

Proceed with the quickstart steps above, but when you get to step 6, starting
your agent, you will need to first link Samantha's cerebrum to your working
directory:

```bash
samantha-llm link
```

Then, launch your agentic LLM tool manually, starting your session
with the `samantha-llm/BOOTSTRAP_PROMPT.md` prompt.

## Tips

### Add `.ai-cerebrum` to your `.gitignore`

Samantha operates by symlinking her cerebrum into your working directory.
She will do this automatically when you run `samantha-llm start`, but you can
also do it manually with `samantha-llm link`.

To avoid accidentally committing Samantha's memories and project/tasks to
your git repository, be sure to add `.ai-cerebrum` to your `.gitignore` file.

### Setup multiple agents

If you want to set up multiple agents with different LLM tools, you can run
the `samantha-llm setup` command multiple times, selecting a different LLM
tool each time. `samantha-llm` will append the new agent configuration to the
configuration file without overwriting existing agents.

However, the last agent you set up will be the default agent used when you run
the `samantha-llm run` command without specifying an agent. If you want to
change your preferred default agent, you can run the `samantha-llm setup`
command with `--default` flag:

```bash
samantha-llm setup --default <agent_name>
```

Where `<agent_name>` is the name of the agent you want to set as the default.
I.e., `claude` or `abacus`.

You can then specify which agent to use when starting your agentic LLM with the
`samantha-llm start` command:

```bash
samantha-llm start <agent_name>
```

Where `<agent_name>` is the name of the agent you want to use for that session.

### Memory processes and LLM Models

Samantha can work with any LLM model supported by your agentic LLM tool.
However, not all LLM models are created equal.

Samantha is instructed to always update her memories after key events, such as
completing a task, making a significant change to a project, or just planning a
project with you. However, some LLM models are better at following these types
of instructions than others.

As such, I recommend periodically prompting Samantha to review and update her
memories to ensure they are accurate and up to date.

```
"Hi Samantha, please review and update your memories to ensure they are
accurate and up to date."
```

I also stongly advise asking her to ensure her memories are up to date at the
end of each work session.

## Maintenance

COMING SOON

This will be an automated way to keep your `samantha-llm` memories and
project/tasks up to date. Samantha has short term and long term memory.
There will eventually be an automated way to ensure that her short term 
memories are properly moved and compressed to long term memory.

This is a planned feature and is not yet implemented.

## Uninstall

To uninstall `samantha-llm`, run the following command from the command line:

```bash
samantha-llm uninstall
```

