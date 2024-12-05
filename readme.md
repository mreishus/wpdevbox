# wpdevbox

Local WordPress development environment using devbox. Provides an isolated MariaDB, PHP-FPM, and Nginx stack with automated setup and teardown.

## Requirements

- devbox 0.13.6+
- macOS (tested on macOS, may work on Linux)

## Installation

```bash
git clone https://github.com/mreishus/wpdevbox
cd wpdevbox
devbox run setup:all
```

## Usage

### First Time Setup
```bash
devbox run setup:all    # Downloads WordPress, configures DB and web server
```

### Daily Use
```bash
devbox services up      # Start all services
devbox services stop    # Stop all services
```

### Management Commands
```bash
devbox run setup:db     # Only set up the database
devbox run setup:web    # Only set up WordPress files
devbox run setup:reset  # Reset everything for a fresh start
```

### Service Details

- WordPress: http://localhost:8081
- MariaDB:
  - Database: wordpress
  - User: wpuser
  - Password: wppass
- PHP-FPM running on port 8082
- All configs in `devbox.d/`

## Directory Structure

```
.
├── devbox.d/
│   ├── mariadb/      # DB init scripts
│   ├── nginx/        # Nginx config
│   ├── php/          # PHP-FPM config
│   ├── wordpress/    # WP config templates
│   └── web/          # Web root
└── .devbox/          # devbox managed files
```

## Known Issues

- SSL not configured

## Contributing

PRs welcome!
