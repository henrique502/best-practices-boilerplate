---
title: React Best Practices
inclusion: fileMatch
fileMatchPattern: '*.tsx,*.jsx,*react*'
---

# React Best Practices (React 19+)

## Component Structure
- Use functional components with hooks
- Keep components small and focused (single responsibility)
- Use TypeScript for all React components
- Prefer named exports over default exports
- Use `"use client"` directive only when the component needs client-side interactivity
- Default to Server Components when possible — they reduce JavaScript sent to the client

## Hooks
- Use `useState` for local component state
- Use `useEffect` for side effects (prefer server-side data fetching when possible)
- Use `useTransition` for async operations and non-urgent UI updates
- Use `useActionState` for form submission state and server action results
- Use `useOptimistic` for optimistic UI updates during async operations
- Use `useFormStatus` to access form pending state in child components
- Use `use()` for conditional reading of promises and context
- Create custom hooks for reusable logic
- Follow the rules of hooks (only call at top level)

## React Compiler
- Enable React Compiler for automatic memoization at build-time
- Avoid manual `useMemo`, `useCallback`, and `React.memo` — the compiler handles this automatically
- If the compiler is not yet adopted, use manual memoization as a fallback
- Follow the Rules of React strictly — the compiler relies on them for correct optimizations
- Use `"use memo"` directive only when you need to explicitly hint the compiler

## Refs
- Pass `ref` directly as a prop — `forwardRef` is deprecated in React 19
- Use ref callbacks with cleanup functions for setup/teardown logic
- Prefer `useRef` for mutable values that don't trigger re-renders

## Forms and Actions
- Use the `action` prop on `<form>` for form submissions (replaces manual `onSubmit` + `preventDefault`)
- Use `useActionState` to manage form state, pending status, and error handling
- Use `useFormStatus` in child components to access the form's pending state
- Use `useOptimistic` for instant UI feedback before server response
- Use Server Actions (`"use server"`) for data mutations that run on the server

## Server Components and Actions
- Default to Server Components — they render on the server and send zero JavaScript to the client
- Use `"use client"` directive only for components that need browser APIs, event handlers, or hooks with state
- Use `"use server"` directive to define Server Actions for data mutations
- Colocate data fetching in Server Components using `async/await` directly
- Keep the client boundary as low as possible in the component tree

## Props and State
- Define prop types with TypeScript interfaces
- Use destructuring for props
- Avoid deeply nested state objects
- Use state updater functions for complex state updates
- Use `useTransition` with async functions for non-blocking state updates

## Document Metadata
- Render `<title>`, `<meta>`, and `<link>` tags directly in components — React 19 hoists them to `<head>` automatically
- No need for external libraries (react-helmet) for basic metadata management

## Performance
- Prefer React Compiler over manual memoization
- Implement proper key props for lists (avoid index as key for dynamic lists)
- Use `React.lazy` and `Suspense` for code splitting and lazy loading
- Use `useTransition` to keep the UI responsive during expensive updates
- Use Server Components to reduce client-side bundle size
- Avoid creating objects/functions inline in JSX when the compiler is not enabled

## Styling
- Avoid inline styles for complex styling
- Use consistent naming conventions
- Implement responsive design patterns

## Testing
- Test component behavior, not implementation
- Use React Testing Library
- Test user interactions and accessibility
- Mock external dependencies
- Test Server Components and Actions with appropriate mocking strategies
