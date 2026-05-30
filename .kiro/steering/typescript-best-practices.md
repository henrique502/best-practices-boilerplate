---
title: TypeScript Best Practices
inclusion: always
---

# TypeScript Best Practices

## Code Style
- Use strict TypeScript configuration (`strict: true`)
- Prefer `const` over `let`, avoid `var`
- Use meaningful variable and function names
- Use PascalCase for classes, interfaces, enums, and type aliases
- Use camelCase for variables and functions
- Use UPPER_SNAKE_CASE for constants

## Type Safety
- Always define return types for functions
- Use `unknown` instead of `any` when the type is truly unknown, and union types for known variants
- Prefer interfaces over type aliases for object shapes
- Use generic types for reusable components
- Enable `noImplicitAny` and `strictNullChecks`
- Prefer `readonly` for properties that shouldn't be reassigned
- Use `as const` for literal types
- Avoid type assertions (`as`) unless absolutely necessary
- Prefer discriminated unions for state management

## Error Handling
- For recoverable errors, use Result/Either patterns
- For unrecoverable errors, throw typed custom errors extending Error
- Use optional chaining (`?.`) and nullish coalescing (`??`)

## Imports/Exports
- Use named exports over default exports
- Group imports: external libraries first, then internal modules
- Use absolute imports with path mapping when possible

## Testing
- Write unit tests for all public functions
- Use descriptive test names
- Mock external dependencies
- Aim for high test coverage (>80%)

## Test Execution
- Run tests with minimal verbosity to avoid session timeouts
- Use grep/filter options to run specific tests when debugging
- Prefer `npm test -- --silent` or `yarn test --silent` for automated runs
