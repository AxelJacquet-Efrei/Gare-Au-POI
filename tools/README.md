# AI assistant

`AI-assistant` is a Git submodule containing the optional project-coherence
tool. It is intended to help the team organise and check project documentation;
it is not part of the web application's frontend or backend.

## Get started

After cloning this repository, initialise the tool once:

```bash
git submodule update --init --recursive
```

The tool can be used without an OpenAI API key. Use `uv` to run the
deterministic checks from the project root:

```bash
uv run --project tools/AI-assistant coherence start --root .
uv run --project tools/AI-assistant coherence check --root .
```

Do not run `coherence ask`, `coherence propose`, or `coherence audit` unless the
team later decides to configure an API key. Never commit `.venv/`, API keys, or
other secrets.

## Team workflow

Keep the assistant submodule at the version recorded by this repository. When
the team intentionally updates it, use `git submodule update --remote
tools/AI-assistant`, review the change, and commit the updated submodule
reference together with the reason for the upgrade.
