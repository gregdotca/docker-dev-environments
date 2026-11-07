# Changelog

## 2026-11-06

- Rename environment 03 to `dev-php.8.2.35.mariadb.11.8.9--03` to match its new versions, keeping its existing database volume.
- Environment 03: update PHP to 8.2.35 (matching DomainMOD's production image) and MariaDB to 11.8.9 LTS, with automatic in-place upgrade of the existing database.
- Environment 03: replace MailHog, unmaintained since 2020, with Mailpit 1.33.0 on the same ports, keeping every message.
- Environment 03: install `plocate` instead of `mlocate`, which Debian 13 dropped.
- Environment 03: read the database root password from a `.env` file instead of the compose file, and refuse to start without one; `.env` files are now ignored by git.
- Environment 03: generate 16 more locales (including Arabic, Chinese, Hindi, Japanese, and Portuguese (Brazil)) and create a writable `/tmp/domainmod.log`.
- Remove the obsolete `version:` line from every environment's compose file.
