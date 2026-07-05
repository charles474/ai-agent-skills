---
name: squash-and-push
description: A skill that implements the squash-and-push workflow to manage commits and maintain a clean Git history.
license: MIT
compatibility: opencode
---

## Squash and push workflow

This skill implements the process of squashing and pushing commits to the remote repository.

---

## When to use

Use this workflow when:

- A user has asked to squash commits and push to the remote repository.

---

## Steps

1. Ask the user to provide the commit message that they want to use for the squashed commit.

2. Ask the user if this branch has already been committed to the remote repository.

3. Squash all commits in this branch into a single commit and push up with the commit message the user provided.

4. Push the squashed commit to the remote repository.

5. Verify that the commit has been successfully pushed and is visible in the remote repository.
