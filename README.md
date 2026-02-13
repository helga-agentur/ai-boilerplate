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
    ````
