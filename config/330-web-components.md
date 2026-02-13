# Frontend (Web Components)

## When to Use What
- Use web components when the logic conerns the DOM.
- Use Drupal behaviors when the logic is not DOM-related or requires too many DOM nodes.

## Web Components

### APIs
- Prefer explicit public APIs for web components:
  - Attributes / properties in
  - Custom events out

### Collaboration
- If state is shared across multiple components, 
  - use a parent component and call it Orchestrator
  - let child components register themselves via custom event; never select children from the
    Orchestrator.
- Ensure that the order in which the components' JavaScript is executed does not matter.

### Scope
- Don't select / modify any elements outside of the component.

## Libraries
- When logic exists in https://github.com/helga-agentur/ui-components, use it.
