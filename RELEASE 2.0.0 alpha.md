# RooCMS v2.0.0 Alpha

> **Статус релиза:** Alpha 🚀  
> **Дата релиза:** TBD  
> **Совместимость:** PHP 8.1+  
> **Версия:** 2.0.0 alpha  

![API Status](https://img.shields.io/badge/API-Healthy-brightgreen)
[![PHP Version](https://img.shields.io/badge/PHP-8.1%2B-blue)](https://www.php.net/)
![Database](https://img.shields.io/badge/DB-MySQL%20%7C%20PostgreSQL%20%7C%20Firebird-orange)

### Notice
> Documents are temporarily in Russian language.   
> They will be translated into English later.

## Overview of the release

RooCMS 2.0 Alpha represents a major update with a complete rewrite of the architecture. The main focus is on modern technologies, security, performance, and an API-first approach for creating not only websites, but also any applications.

## Update from previous versions

- Not supported

## Database migrations

- CLI-interface for managing database migrations: `roocms/database/migrate_cli.php`
- Supported commands: `migrate`, `rollback [steps]`, `status`, `version`, `help`
- Migration files: `roocms/database/migrations/migrate_YYYYMMDD_NN.php`

Examples:
```bash
# Execute all pending migrations
php roocms/database/migrate_cli.php migrate

# Rollback the last 2 migrations
php roocms/database/migrate_cli.php rollback 2

# View the status
php roocms/database/migrate_cli.php status
```

## Backup system

- CLI-interface for managing database backups: `roocms/database/backup_cli.php`
- API endpoints: `/api/v1/backup/*`
- Supported commands: `create`, `restore`, `list`, `delete`, `status`, `help`
- Multilevel protection of backup files

Examples:
```bash
# Create a backup
php roocms/database/backup_cli.php create --compress

# Restore from backup
php roocms/database/backup_cli.php restore --filename=backup_20241226_143022.sql.gz

# List all backups
php roocms/database/backup_cli.php list
```

Recommendations:
- Always make a backup before migrations
- Test on staging, then on production
- Do not edit already executed migration files - create new ones

### Known issues (Alpha)

- Limited support for PostgreSQL/Firebird in edge-cases of types and indexes
- Possible warnings/limitations when rolling back complex migrations


## 🚀 Key features

### 🔥 New architecture
- ✅ **Complete rewrite on PHP 8.1+** with modern language features
- ✅ **API-First approach** - RooCMS is now not only a CMS, but also a powerful API platform
- ✅ **File management system** - trait-based architecture for handling different types of files
- ✅ **Without frameworks and ORM** - clean PHP code for maximum performance
- ✅ **Strict typing** and modern PHP 8+ practices

### 🌐 RESTful API
- ✅ **Fully functional REST API** (`/api/v1/`) for integration with any applications
- ✅ **Routing system** with support for dynamic parameters (`{id}`, `{param}`)
- ✅ **Middleware system** for authentication and authorization
- ✅ **Health Check endpoints** for monitoring the system state
- ✅ **Backup API endpoints** for managing backups
- ✅ **Standardized JSON responses** with error handling

### 🗄️ Universal work with DB
- ✅ **PDO parameter binding** for safe work with the database without SQL injections
- ✅ **Multi-database support** - MySQL, PostgreSQL, Firebird in one code
- ✅ **Migration system** with CLI interface and automatic versioning
- ✅ **Database Health Monitoring** - monitoring the state of the DB in real time
- ✅ **Backup system** - fully functional system backup/restore with CLI and API
- ✅ **Transaction safety** in operations

### 🔐 Security and authentication
- ✅ **Modern authentication system** with tokens and roles
- ✅ **CSP (Content Security Policy)** support
- ✅ **Protection from SQL injections** through PDO parameter binding
- ✅ **Validation and sanitization** of all input data

### 🎨 Theme system and frontend
- ✅ **Modular theme system** with support for multiple themes
- ✅ **Two types of template engines** - PHP and HTML with placeholders
- ✅ **Alpine.js integration** for interactivity without complexity
- ✅ **CSP compatibility** frontend components
- ✅ **Modular JS architecture** with separation by pages
- ✅ **Tailwind CSS 4.x** for rapid development of the user interface
- ✅ **Modern stack** without dependencies on heavy frameworks

### ⚡ Performance
- ✅ **Optimized queries** with counting and monitoring
- ✅ **Minimum memory consumption** (~2MB peak usage)
- ✅ **Fast response time** (8-15ms for API requests)
- ✅ **Resource consumption reduction** for high-load scenarios



## 📊 Performance and statistics

### API benchmarks (on test server)
- **Health Check response time**: 8-15ms
- **Memory consumption**: ~2MB peak usage
- **Database requests**: ---
- **Supported RPS**: 1000+ (depends on the server)

### Code statistics
- **Total size**: ~762KB PHP code (without dependencies)
- **Classes**: 23 main classes + 14 traits + 4 interfaces = 41 components
- **API controllers**: 11 controllers with ~70+ public methods
- **Supported databases**: 3 (MySQL, PostgreSQL, Firebird)
- **Services**: 10 business services (Auth, User, Settings, Backup, Email, Files, etc.)

### Compatibility
- ✅ **PHP 8.1, 8.2, 8.3, 8.4**
- ✅ **MySQL 5.7+, 8.0+**
- ✅ **MariaDB 10.10+, 11.x**
- ✅ **PostgreSQL 14+, 15+, 16+**
- ✅ **Firebird 3.0+**
- ✅ **Apache 2.4, nginx**

## 🔮 Roadmap

- ➕ **Extended user system** - profiles, groups, activity
- ➕ **Content system** - posts, categories, tags, multi-language
- 🔄 **File manager API** - loading and managing files
- ➕ **Caching** - Redis/Memcached support
- ➕ **Plugin system** - extensibility through plugins
- ➕ **Theme extension** - additional themes and components
- ➕ **WebSocket support** - real-time notifications
- ➕ **Docker containerization** - ready Docker images

## 🧪 Plugins and extensions (in the future)

### Planned official plugins
- 🔧 **roocms-blog** - Blog system with comments
- 🔧 **roocms-shop** - E-commerce functionality  
- 🔧 **roocms-forum** - Forum and discussions
- 🔧 **roocms-analytics** - Web analytics and statistics
- 🔧 **roocms-seo** - SEO optimization and meta-tags

### Plugin system (in development)
- 📦 **Composer integration** - installation through Composer
- 🔌 **Hook system** - events and filters
- ⚙️ **Plugin configuration** - settings through admin panel
- 🔒 **Plugin security** - sandbox and code checking


## 🆕 What's new in version 2.0

### Completely new components
- ✨ **Backup system** - complete replacement of the old system with CLI and API
- ✨ **Dependency Injection container** - managing dependencies by SOLID principles
- ✨ **Modular settings system** - dynamic settings with type validation
- ✨ **Cryptography authentication** - modern system of tokens and roles
- ✨ **Health Check system** - monitoring the state of all components

### Improved components
- 🔄 **API router** - complete rewrite with support for middleware
- 🔄 **Theme system** - support for multiple rendering engines
- 🔄 **Security** - multi-level protection and CSP

### ⚠️ Important information

- ℹ️ **Alpha status** - Some functions may work unstable, test before production
- ℹ️ **Migrations are mandatory** - For the system to work, you must perform database migrations
- ℹ️ **New documentation** - API documentation is available in `api/README.md` and Swagger schemas
- ℹ️ **Backward incompatibility** - version 2.0 is not compatible with previous versions


## 🛠️ Technical requirements

### Minimal requirements
- **PHP**: 8.1+ 
- **Web server**: Apache 2.4+ / nginx
- **Database**: MySQL 5.7+ / MariaDB 10.10+ / PostgreSQL 14+ / Firebird
- **Browser**: Modern browser with JavaScript ES6+ support
- **PHP extensions**: PDO, JSON, mbstring, openssl, curl, gd

### Recommended configuration
- **PHP**: 8.4
- **Database**: MariaDB 11.7
- **Memory**: 1GB+ RAM
- **Web server**: Apache 2.4 with mod_rewrite

### 🎨 Frontend technologies
- **Tailwind CSS 4.x**: Utility-first CSS framework for rapid UI development
- **Alpine.js**: Lightweight JavaScript framework (~15KB)
- **Modular architecture**: Code separation by pages and components
- **CSP Ready**: Full compatibility with Content Security Policy
- **Without builders**: Ready-to-use files without webpack/gulp
- **Modern ES6+**: Use modern JavaScript features
- **Any technologies**: React, Vue, Angular, vanilla HTML+JS or built-in PHP template engine

## 🚀 Quick start

### 1. Installation
```bash
# Download release
wget (link later)

# Unpack to the root of the site
unzip roocms-2.0.0-alpha.zip -d /var/www/html/

# Set access permissions
chmod -R 755 /var/www/html/roocms/
chmod -R 777 /var/www/html/storage/
```

### 2. Database configuration
```bash
# Execute migrations
cd /var/www/html/
php roocms/database/migrate_cli.php migrate

# Check status
php roocms/database/migrate_cli.php status
```

### 3. Check API
```bash
# Check system health
curl -X GET https://your-domain.com/api/v1/health -k

# Get detailed information
curl -X GET https://your-domain.com/api/v1/health/details -k
```

## 📚 Examples of use

### API requests
```javascript
// JavaScript - check API
fetch('https://your-domain.com/api/v1/health')
  .then(response => response.json())
  .then(data => {
    if (data.success && data.data.status === 'healthy') {
      console.log('RooCMS works normally');
    }
  });
```

```php
// PHP - Optimized direct SQL queries (used in the core)
$db = new Db();
$users = $db->fetch_all(
  'SELECT * FROM users WHERE status = ? ORDER BY created_at DESC LIMIT 10',
  ['active']
);
```

```bash
# CLI - managing migrations
php roocms/database/migrate_cli.php migrate    # Execute migrations
php roocms/database/migrate_cli.php rollback 2 # Rollback 2 migrations
php roocms/database/migrate_cli.php status     # Show status

# CLI - managing backups
php roocms/database/backup_cli.php create --compress --universal
php roocms/database/backup_cli.php restore --filename=backup.sql.gz
php roocms/database/backup_cli.php list        # List all backups
```

```html
<!-- HTML - use Alpine.js in your themes -->
<div x-data="{ open: false }">
  <button @click="open = !open" class="button">
    Show/Hide
  </button>
  <div x-show="open" x-transition>
    <p>Content with animation</p>
  </div>
</div>
```

## 🔗 Useful links

- 📖 [Main documentation](README.md)
- 🏗️ [Project structure](structure.md)
- 🔌 [API documentation](api/README.md)
- 🗄️ [Migration system](roocms/database/README_Migrate.md)
- 💾 [Backup system](roocms/database/README_Backup.md)
- 📊 [Swagger API schema](api/v1/docs/swagger.yaml)
- 📮 [Postman collection](api/v1/docs/postman.json)
- ⚖️ [License GPL v3](LICENSE.md)
- 🌐 [Official website](https://www.roocms.com)
- 📧 [Support](mailto:info@roocms.com)

## 🤝 Participation in development

We welcome your contribution to the development of RooCMS:

1. **Bug reports**: Create an issue with a detailed description
2. **Pull requests**: Small, focused changes with tests
3. **Follow the rules**: PHP 8.1+, without frameworks/ORM, strict typing

## 🔒 Security

If you have found a security vulnerability, please report it responsibly to: **info@roocms.com**

---

<div align="center">

**RooCMS v2.0.0 Alpha** - Modern CMS and API platform  
© 2010-2025 alex Roosso. All rights reserved.

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![PHP Version](https://img.shields.io/badge/PHP-8.1%2B-blue)](https://www.php.net/)

</div>