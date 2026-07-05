---
name: tdd-workflow
description: Follow the project's Test-Driven Development workflow using vitest, React Testing Library, user-event for modifying behaviour when implementing new features, fixing bugs, modifying existing behaviour, or refactoring behaviour with test coverage added first.
license: MIT
compatibility: opencode
---

## Test driven development workflow

This skill implements the project's Test-Driven Development workflow using vitest, React Testing Library, and user-event for modifying behavior in unit tests.


## When to use

Use this workflow when:

- implementing new features
- fixing bugs
- modifying existing behaviour
- refactoring behaviour with test coverage added first

This project prefers a test-first approach, so tests should be written before the implementation code. This ensures that the implementation is guided by the tests and helps maintain a high level of test coverage throughout the development process.

1. Write a failing test that describes the desired behavior or functionality. This test should be specific and focused on a single aspect of the feature or bug fix.
2. Implement the minimum amount of code necessary to make the test pass. This may involve writing new code or modifying existing code.
3. Run the tests to ensure that the new test passes and that all existing tests still pass. If any tests fail, debug and fix the implementation until all tests pass.
4. Refactor the code if necessary, ensuring that all tests have passed before and after refactoring. This step is optional but can help improve the code quality and maintainability.

The goal is to keep changes safe, incremental and easy to reason about, while maintaining a high level of test coverage and ensuring that the implementation is guided by the tests. This workflow promotes a disciplined approach to development and helps catch issues early in the development process.

## Testing stack

Use the testing tools and libraries that are already set up in the project, which include:

- [vitest](https://vitest.dev/) for running tests and providing a test runner environment.
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) for testing React components in a way that simulates user interactions and focuses on testing the component's behavior rather than its implementation details.
- [user-event](https://testing-library.com/docs/user-event/intro/) for simulating user interactions in tests, such as clicking buttons, typing in input fields, and other common user actions.
- [msw](https://mswjs.io/) for mocking API requests and responses in tests, allowing you to test components that rely on external data without making actual network requests.

Prefer the smallest test level that gives enough confidence.

- use Vitest and Testing Library by default
- use MSW for networking behaviour

### Test file location

Place test files close to the file under test

Example structure:

src/components/button/button.tsx
src/components/button/button.test.tsx


src/components/panel/expanded-panel.tsx
src/components/panel/expanded-panel.test.tsx

For non-React modules:

src/utils/format-date.ts
src/utils/format-date.test.ts


## Naming conventions

### Test file names

Component test files should be named with the `.test.tsx` extension, while non-component test files should use the `.test.ts` extension.


### Describe block names

Use describe blocks to group tests by unit or behaviour.

Example:

```tsx
describe('Button', () => {
  // tests for Button component
  describe('assignee field', () => {
    // tests for Button behavior when clicked
    it('should call onClick handler when clicked', () => {});
    it('should be disabled when disabled prop is true', () => {});
  });
});
```

### Test descriptions

use specification-by-example descriptions for test cases, which should be clear and concise, describing the expected behavior or outcome of the test.


Prefer:

- "hides the assignee field when the user is not a manager"
- "shows loading spinner when the form is submitting"
- "renders the correct error message when the API returns an error"

Avoid vague names like:

- "should work correctly"
- "renders the component"
- "handles user interactions"

Good test names describe:

- the scenario
- the action or condition
- the expected outcome

## Project related information

`pos-lending-application-form-web-pub` project does not use a feature folder structure. Work with the developer to find the best place to add new features.

`pos-lending-merchant-portal` project uses a feature folder structure, with the test files still placed close to the file under test, following the same naming conventions as described above.