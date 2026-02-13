# Frontend (JavaScript)

## General
- Prefer functional style (e.g. .map) over loops.

## Naming
- Constants use camelCase, not SCREAMING_SNAKE_CASE (e.g. #myConst = 17).
- Event names use camelCase, not kebab-case.

## Logs
- If there is a logger alreay in use, use it.
- If not, write a simple log wrapper
  - that takes scopes from the URL's hash (e.g. #debug=ads,filter)
  - that logs to the console only when the scope is active
  - and document it and the scopes used in the README.

## Testing
- Test all relevant business logic automatically.
- Use AVA when already in use; else, use Jest.
