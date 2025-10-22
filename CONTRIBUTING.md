# Contributing to RooCMS 🚀

Thanks for your interest in contributing to RooCMS! This document outlines the process and standards for contributing to the project.

## Quick Start

1. **Fork the repository** on GitHub
2. **Create a feature branch** from `dev`: `git checkout -b feature/my-feature`
3. **Follow the coding standards** (described below)
4. **Write tests** if necessary
5. **Submit a pull request** to the `dev` branch

## Bug Reporting

If you found a bug, please follow these steps:

1. Check if the bug has already been reported in the [Issues](https://github.com/roocms/roocms/issues)
2. Create a new issue with a detailed description:
   - Steps to reproduce
   - Expected behavior
   - Actual behavior
   - PHP version, web server, OS
   - Error logs (if any)

## Feature Proposals

For new features:
1. Create an issue with a description of the proposal
2. Discuss the approach with the project team
3. Implement only after approval

## Coding Standards

### PHP
- **PHP 8.1+** - code must be compatible with PHP 8.1 and above
- **Strict typing** - use type declarations for parameters and return values
- **Modern syntax** - use match expressions, nullsafe operator, constructor property promotion
- **Naming**:
  - snake_case for functions, methods, variables, and arrays
  - CamelCase for classes, controllers, etc.
- **No frameworks** - only pure PHP
- **No ORM** - use direct SQL queries via Db class (PDO)

### Architecture
- **Custom MVC** - implement the MVC pattern from scratch
- **Dependencies** - manage dependencies via the DependencyContainer class
- **Autoloading** - use custom autoloading or simple require/include

### Frontend
*These standards apply to the frontend code of RooCMS directly in the development project.
End users can use any frameworks and build tools at their discretion.*
- **CSS**: Tailwind CSS 4.x
- **JavaScript**: Alpine.js 3.x (CSP compatible)
- **No frameworks**: React, Vue, Angular - prohibited
- **No build tools**: webpack, Vite - prohibited
- **CSP compatibility**: use CSP nonce

### Database
- **Direct SQL queries** - with Db class (PDO)
- **DbConnect class** - for database connections
- **Migration** - use the migration system for schema changes

## Structure of the Project

```
roocms/
├── config/          # Configuration files
├── database/        # Migrations and backups
├── helpers/         # Helper functions
├── modules/         # Classes and modules
│   ├── db/         # Database classes
│   ├── di/         # Dependency injection
│   └── ui/         # UI components
├── services/        # Business logic
└── ...

api/                 # API endpoints
themes/              # Themes
storage/             # Files and assets
```

## Testing

Examples of testing with `curl`:
```bash
# Testing API endpoints
curl https://dev.roocms.com/api/

# Checking pages
curl https://dev.roocms.com/path/to/page
```

## Pull Request Process

1. **Update the dev branch** before creating a PR:
   ```bash
   git checkout dev
   git pull origin dev
   git checkout -b feature/my-feature
   ```

2. **Write a meaningful commit message**:
   ```
   feat: add user authentication module
   fix: resolve database connection timeout
   docs: update API documentation
   ```

3. **Describe the changes** in the PR:
   - What was changed
   - Why the changes are needed
   - How to test the changes

4. **Pass the code review** from the project team

### Verification Checklist
Before opening a pull request, please verify:
- Branch is up-to-date with `dev` (rebased or merged)
- Tests and linters pass locally / CI passes
- Commit messages are clear and follow the project style
- PR description includes testing steps and any required env info

## Documentation

- Update the documentation when making changes
- Use English for comments in the code
- Add PHPDoc blocks for new functions/classes

## Security

- Follow security best practices
- Do not commit sensitive data (passwords, API keys)
- Use CSP nonce to protect against XSS
- Validate all input data

- For confidential vulnerability reports see: .github/SECURITY.md or email info@roocms.com

## Communication

- **Issues**: for bugs and feature requests
- **Discussions**: for general questions
- **Email**: support@roocms.com for confidential inquiries

## License

By contributing to this project, you agree that your contributions will be licensed under the same license as the project (see LICENSE.md).

Thank you for contributing to RooCMS! Your help makes the project better for everyone. 🙏
