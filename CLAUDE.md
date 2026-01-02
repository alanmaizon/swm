# CLAUDE.md - AI Assistant Development Guide

> **Last Updated:** 2026-01-02
> **Repository:** alanmaizon/swm
> **Purpose:** This document provides comprehensive guidance for AI assistants (like Claude) working with this codebase.

---

## Table of Contents

1. [Repository Overview](#repository-overview)
2. [Codebase Structure](#codebase-structure)
3. [Development Workflow](#development-workflow)
4. [Key Conventions](#key-conventions)
5. [Git Practices](#git-practices)
6. [Code Quality Standards](#code-quality-standards)
7. [Testing Guidelines](#testing-guidelines)
8. [Common Tasks](#common-tasks)
9. [Troubleshooting](#troubleshooting)

---

## Repository Overview

### Project Purpose

This repository serves as a comprehensive study resource for the **AWS Certified Cloud Practitioner (CLF-C02)** certification exam.

**Key Features:**
- Complete study guide covering all 13 exam topics
- Practice questions organized by domain
- Quick-reference cheat sheets
- Study progress tracker
- Mock exam templates

**Target Users:**
- Individuals preparing for AWS Cloud Practitioner certification
- Students learning AWS fundamentals
- IT professionals transitioning to cloud computing

**Content Type:**
- Documentation (Markdown files)
- Study materials and educational resources

### Repository Status
- **Current State:** Active exam preparation repository
- **Branch Strategy:** Feature branches following `claude/*` naming convention
- **Remote:** Local proxy configuration
- **Purpose:** Educational content for AWS certification

---

## Codebase Structure

### Directory Organization

```
swm/
├── .git/                          # Git configuration
├── CLAUDE.md                      # AI assistant development guide
├── README.md                      # Main documentation and study plan
├── STUDY-TRACKER.md              # Personal progress tracker
├── docs/
│   └── AWS-Cloud-Fundamentals.md # Comprehensive study guide (all 13 topics)
├── practice/
│   ├── questions-by-domain/      # Practice questions organized by exam domain
│   │   ├── domain1-cloud-concepts.md
│   │   ├── domain2-security-compliance.md
│   │   └── ... (additional domains)
│   └── mock-exams/               # Full-length practice exams
├── cheat-sheets/                  # Quick reference guides
│   ├── 01-cloud-concepts.md
│   ├── 02-services-comparison.md
│   └── ... (additional cheat sheets)
└── tools/                         # Study utilities and scripts
```

### Key Files and Their Purposes

| File/Directory | Purpose | When to Modify |
|---------------|---------|----------------|
| README.md | Study plan, repository overview, exam details | When adding new resources or study plans |
| CLAUDE.md | AI assistant documentation | When workflows change |
| STUDY-TRACKER.md | Track study progress | Throughout exam preparation |
| docs/AWS-Cloud-Fundamentals.md | Main study content | When AWS updates services or exam content |
| practice/questions-by-domain/ | Domain-specific practice | When adding new questions or topics |
| cheat-sheets/ | Quick reference materials | When adding new services or concepts |

---

## Development Workflow

### Before Starting Work

1. **Understand the Task**
   - Read the issue/task description thoroughly
   - Identify affected components
   - Consider edge cases and dependencies

2. **Explore the Codebase**
   - Use search tools to find relevant files
   - Read existing implementations for context
   - Understand current patterns and conventions

3. **Plan Your Approach**
   - For complex tasks, use the TodoWrite tool to create a task breakdown
   - Identify files that need changes
   - Consider backward compatibility

### During Development

1. **Follow Existing Patterns**
   - Match the coding style of surrounding code
   - Use established naming conventions
   - Reuse existing utilities and helpers

2. **Make Focused Changes**
   - Only modify what's necessary for the task
   - Avoid unrelated refactoring or improvements
   - Don't add features that weren't requested

3. **Test Your Changes**
   - Run relevant test suites
   - Manually verify functionality
   - Check for regressions

### After Completing Work

1. **Review Your Changes**
   - Ensure all requirements are met
   - Check for security vulnerabilities
   - Verify code quality

2. **Commit and Push**
   - Write clear, descriptive commit messages
   - Push to the designated feature branch
   - Follow git conventions (see below)

---

## Key Conventions

### Code Style

#### General Principles
- **Simplicity over cleverness:** Write clear, readable code
- **Consistency:** Follow patterns established in the codebase
- **Explicit over implicit:** Make intentions clear
- **DRY (Don't Repeat Yourself):** But avoid premature abstraction

#### Naming Conventions
<!-- TO BE UPDATED: Add language-specific conventions once codebase is populated -->

**Variables:**
- Use descriptive names that explain purpose
- Avoid single-letter names except for loop counters
- Boolean variables should be questions: `isValid`, `hasPermission`, `canEdit`

**Functions:**
- Use verb phrases: `getUserData`, `calculateTotal`, `validateInput`
- Keep functions small and focused
- One responsibility per function

**Classes/Components:**
- Use noun phrases
- Follow framework conventions (e.g., PascalCase for React components)

#### Comments
- Explain **why**, not **what**
- Update comments when changing code
- Remove outdated or incorrect comments
- Document complex algorithms or business logic

### Error Handling
- Validate at system boundaries (user input, API calls, external data)
- Don't add unnecessary error handling for internal code
- Use appropriate error types for the context
- Provide helpful error messages

### Security Practices
- **Never** commit secrets, API keys, or credentials
- Validate and sanitize user input
- Be aware of common vulnerabilities:
  - SQL Injection
  - XSS (Cross-Site Scripting)
  - Command Injection
  - Path Traversal
  - CSRF (Cross-Site Request Forgery)
- Use parameterized queries for database operations
- Escape output appropriately for context

---

## Git Practices

### Branch Strategy

**Branch Naming:**
- Feature branches: `claude/description-SessionID`
- All development branches must start with `claude/`
- SessionID suffix is required for authentication

**Current Branch:**
```
claude/add-claude-documentation-PbyWj
```

### Commit Guidelines

**Commit Message Format:**
```
<type>: <short summary>

<detailed description if needed>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `refactor`: Code restructuring without behavior change
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Example Commit Messages:**
```
feat: add user authentication middleware

docs: update CLAUDE.md with git practices

fix: resolve race condition in data processing
```

### Push Strategy

**Always use:**
```bash
git push -u origin <branch-name>
```

**Retry Logic:**
- If network errors occur, retry up to 4 times
- Use exponential backoff: 2s, 4s, 8s, 16s
- Only retry on network failures, not authentication errors

**Critical:**
- Branch must start with `claude/` and include session ID
- Push will fail with 403 if branch naming is incorrect

### Pull Request Guidelines

When creating PRs:
1. **Title:** Clear, descriptive summary of changes
2. **Description:**
   - Summary of changes (1-3 bullet points)
   - Test plan (checklist of verification steps)
3. **Review:**
   - Self-review the diff before submitting
   - Ensure all tests pass
   - Verify no sensitive data is included

---

## Code Quality Standards

### What to Avoid

❌ **Over-Engineering:**
- Don't add features beyond requirements
- Don't create abstractions for single use cases
- Don't add configuration options "just in case"
- Don't refactor unrelated code during bug fixes

❌ **Unnecessary Complexity:**
- Don't add error handling for impossible scenarios
- Don't use feature flags for simple changes
- Don't add backwards-compatibility for internal APIs
- Don't create helper functions for one-time operations

❌ **Premature Optimization:**
- Focus on correctness first
- Optimize only when performance problems exist
- Profile before optimizing

### What to Embrace

✅ **Simplicity:**
- Three similar lines of code is better than a premature abstraction
- Clear, verbose code is better than clever, terse code
- Duplication is sometimes acceptable

✅ **Focus:**
- Make only the changes requested
- Keep scope limited and well-defined
- Solve the current problem, not future hypotheticals

✅ **Trust:**
- Trust internal code and framework guarantees
- Don't validate data that's already validated
- Remove unused code completely (no `_prefixed` variables)

---

## Testing Guidelines

<!-- TO BE UPDATED: Add specific testing framework and patterns once established -->

### Test Categories

**Unit Tests:**
- Test individual functions and components in isolation
- Mock external dependencies
- Focus on edge cases and error conditions

**Integration Tests:**
- Test interactions between components
- Verify data flow through the system
- Test API contracts

**End-to-End Tests:**
- Test complete user workflows
- Verify critical paths work correctly
- Use sparingly - slower and more brittle

### Running Tests

```bash
# TO BE UPDATED: Add actual test commands
# npm test
# npm run test:watch
# npm run test:coverage
```

### Writing Good Tests

- **Descriptive names:** Test names should explain what they verify
- **Arrange-Act-Assert:** Structure tests clearly
- **One assertion per test:** Keep tests focused
- **Independent tests:** Tests should not depend on each other
- **Fast execution:** Tests should run quickly

---

## Common Tasks

### Adding a New Feature

1. **Understand requirements**
   - Read the feature request carefully
   - Identify affected components
   - Plan the implementation

2. **Create a task list** (using TodoWrite tool)
   ```
   - Research existing code patterns
   - Implement core functionality
   - Add error handling
   - Write tests
   - Update documentation
   ```

3. **Implement incrementally**
   - Start with the simplest working version
   - Add complexity as needed
   - Test frequently

4. **Commit and push**
   - Write clear commit message
   - Push to feature branch

### Fixing a Bug

1. **Reproduce the issue**
   - Understand the expected behavior
   - Identify the actual behavior
   - Find the root cause

2. **Implement the fix**
   - Make minimal, targeted changes
   - Don't refactor surrounding code
   - Add regression tests if appropriate

3. **Verify the fix**
   - Test the specific scenario
   - Check for related edge cases
   - Ensure no new issues introduced

### Refactoring Code

1. **Only refactor when necessary**
   - Avoid refactoring during feature work
   - Ensure tests exist before refactoring
   - Make incremental changes

2. **Keep behavior unchanged**
   - Tests should still pass
   - External interfaces should remain stable
   - Document breaking changes clearly

### Updating Documentation

1. **Keep documentation current**
   - Update docs when changing behavior
   - Document new features
   - Remove outdated information

2. **Write for your audience**
   - User-facing: Focus on what and how
   - Developer-facing: Include why and when
   - Keep examples up-to-date

---

## Troubleshooting

### Common Issues

#### Git Push Fails with 403

**Cause:** Branch name doesn't follow required pattern

**Solution:**
```bash
# Branch must start with 'claude/' and include session ID
git checkout -b claude/your-description-SessionID
git push -u origin claude/your-description-SessionID
```

#### Network Errors During Git Operations

**Solution:**
- Retry with exponential backoff (2s, 4s, 8s, 16s)
- Check network connectivity
- Verify remote URL is accessible

#### Tests Failing After Changes

**Solution:**
1. Read the test failure messages carefully
2. Check if your changes broke assumptions
3. Update tests if requirements changed
4. Fix code if tests are correct

#### Merge Conflicts

**Solution:**
1. Fetch latest changes: `git fetch origin`
2. Rebase or merge as appropriate
3. Resolve conflicts carefully
4. Test after resolving
5. Complete the merge/rebase

---

## File Update Protocol

### When to Update This File

Update `CLAUDE.md` when:
- Project structure changes significantly
- New conventions are established
- Development workflow changes
- Common patterns emerge
- Troubleshooting solutions are discovered

### How to Update

1. Read the entire file first
2. Make targeted, necessary changes
3. Keep formatting consistent
4. Update the "Last Updated" date
5. Commit with message: `docs: update CLAUDE.md - <what changed>`

---

## Additional Resources

<!-- TO BE UPDATED: Add links to relevant resources -->

### Documentation
- [Project README](./README.md) - TBD
- [API Documentation](./docs/api.md) - TBD
- [Architecture Guide](./docs/architecture.md) - TBD

### External Resources
- Git documentation: https://git-scm.com/doc
- Semantic versioning: https://semver.org/
- Conventional commits: https://www.conventionalcommits.org/

---

## Notes for AI Assistants

### Tool Usage Preferences

- **File Search:** Use Task tool with Explore agent for open-ended searches
- **File Operations:** Use Read/Edit/Write tools, not bash commands
- **Multiple Operations:** Run independent operations in parallel
- **Task Planning:** Use TodoWrite for multi-step tasks (3+ steps)

### Communication Style

- Be concise and clear
- Focus on facts over validation
- Provide objective technical information
- Include file references with line numbers: `file.ts:123`
- Avoid emojis unless requested

### Best Practices

1. **Always read files before editing**
2. **Use existing patterns from the codebase**
3. **Make minimal, focused changes**
4. **Test changes before committing**
5. **Write clear commit messages**
6. **Update documentation when needed**
7. **Ask for clarification when requirements are unclear**

### Red Flags to Avoid

- Committing secrets or credentials
- Pushing to wrong branches
- Over-engineering solutions
- Refactoring unrelated code
- Adding unnecessary features
- Copying code without understanding it
- Ignoring test failures

---

## Conclusion

This document serves as a living guide for AI assistants working with this codebase. It should be updated as the project evolves and new patterns emerge.

**Remember:** The goal is to write clean, maintainable code that solves the problem at hand. When in doubt, favor simplicity and clarity over complexity and cleverness.

---

*For questions or suggestions about this document, please discuss with the development team.*
