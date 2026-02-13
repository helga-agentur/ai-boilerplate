# Git workflow
- Use atomic commits: 
  - Single purpose (fix one bug, add one feature, refactor one thing)
  - Revertable without breaking other things
- Branch naming: `feature/`or `fix/`, then the issue number and a short description, 
  e.g. `feat/412-add-email-input-validation`
- Use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/):
  - Commit naming: `feat(module): short description of the commit (#issue)`
  - If breaking, add `!` to the type
  - Ensure that commit messages are parseable
- Before committing anything, make sure that Definition of Done is met.
