# Setup

Add this repo as a submodule to your project and link the required config files.

1. In your project root, add the submodule:
   ```
   git submodule add git@github.com:helga-agentur/ai-boilerplate.git .ai-boilerplate
   ```
2. Create a `CLAUDE.md` file in your project root. This is the config file Claude Code reads on startup. Add the imports you need:
    ```
    @import .ai-boilerplate/config/120-basics.md
    @import .ai-boilerplate/config/130-architecture.md
    @import .ai-boilerplate/config/150-playbook.md
    @import .ai-boilerplate/config/200-definition-of-done.md
    @import .ai-boilerplate/config/310-drupal.md
    @import .ai-boilerplate/config/320-javascript.md
    @import .ai-boilerplate/config/330-web-components.md
    @import .ai-boilerplate/config/340-twig.md
    @import .ai-boilerplate/config/350-bem.md
    @import .ai-boilerplate/config/420-documentation.md
    @import .ai-boilerplate/config/430-logs-errors.md
    @import .ai-boilerplate/config/440-i18n.md
    @import .ai-boilerplate/config/450-accessibility.md
    @import .ai-boilerplate/config/500-git-workflow.md
    @import .ai-boilerplate/config/600-security.md
    @import .ai-boilerplate/config/700-coding-standards.md
    ```
   Only include what's relevant for your project (e.g. leave out `310-drupal.md` for non-Drupal projects).
3. Create symlinks so Claude Code picks up the shared settings and commands:
    ```
    ln -s .ai-boilerplate/.claudeignore .claudeignore
    mkdir -p .claude
    ln -s .ai-boilerplate/.claude/settings.json .claude/settings.json
    ln -s ../.ai-boilerplate/.claude/commands .claude/commands
    ```
   Symlinks mean these files stay in sync automatically whenever the submodule is updated — no manual copying needed.

# Updating

When the boilerplate changes, pull the latest version:
```
cd .ai-boilerplate && git pull && cd ..
```

# Usage

Start Claude Code from your project root:
```
claude
```

Then invoke the commands in order:
1. `/write-spec` — define what to build
2. `/plan-architecture` — plan how to build it
3. `/write-code` — implement it

# Röbi's Chapter

**First time only:**

1. Open the terminal (the black window with the monospaced font — search for «Terminal» in Spotlight).
2. [Install Claude Code](https://code.claude.com/docs/en/setup).
3. Navigate to your project folder: type `cd `, then drag the folder from Finder into the terminal window, then press Enter.
4. Clone the boilerplate:
   ```
   git clone git@github.com:helga-agentur/ai-boilerplate.git
   ```
   Then press Enter.
5. Go into the folder: type `cd ai-boilerplate` and press Enter.
6. Start Claude Code: type `claude` and press Enter.
7. Type a command, e.g. `/write-pattern-spec <figma-link>`, and press Enter.

**When the boilerplate has been updated:**

1. Open the terminal and navigate to the `ai-boilerplate` folder (steps 1 and 3 above).
2. Type `git pull` and press Enter.
