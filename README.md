# Setup

1. Add this git repo as a submodule to your project:
`git submodule add git@github.com:helga-agentur/ai-boilerplate.git .ai-boilerplate`
2. Create a local `CLAUDE.md` in your project root
3. Add your imports to `CLAUDE.md`:
    ````
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
    ````
4. Link the relevant settings:
    ````
    ln -s .ai-boilerplate/.claudeignore .claudeignore
    mkdir -p .claude
    ln -s .ai-boilerplate/.claude/settings.json .claude/settings.json
    ln -s ../.ai-boilerplate/.claude/commands .claude/commands
    ````

# Usage
- Start claude (`claude` if you use an outdated code editor)
- Invoke the commands: `/create-spec`, `/plan-architecture` and then `/write-code`.

# Röbi's Chapter
Just once (Setup):
1. Open the terminal (that blackish thing with the monospaced font)
1. [Install Claude Code](https://code.claude.com/docs/en/setup).
1. Switch to some smartish folder (type `cd `, then drag'n'drop it from the Finder and hit [Enter])
1. Copy & paste `git@github.com:helga-agentur/ai-boilerplate.git`, press [Enter] again.
1. Type `cd ai-boilerplate` and hit [Enter] one more time.
1. Start Claude Code: `claude` – and, yes, [Enter]
1. Type your commands, e.g. `/write-pattern-spec <figma-link>`. Yes. [Enter]. Indeed.

Whenever things change
- Repeat steps 1 and 2 from above.
- Type `git pull` – then … [Enter].
