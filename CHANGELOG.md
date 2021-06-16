# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.2.1] - 2021-06-16
## fixed
- fixes for xdebug configuration

## [1.2.0] - 2021-05-12
## Changed
- Migrated Xdebug configurations for PHP7.4 for Xdebug 3. and build php74-stable tag from php74 directory.

## [1.1.4] - 2019-06-11
### Added
- autostart off for php7.3

## [1.1.3] - 2019-05-08
### Added
- Xdebug official added to php73

## [1.1.2] - 2019-04-16
### Added
- Xdebug 2.7.1 stable to php73

## [1.1.1.1] - 2019-03-13
### Changed
- Disabled Xdebug's `remote_autostart` setting to speed up non-debugging page loads.

## [1.1.1] - 2018-10-18
### Added
- Reorganized tags and added php72 to master

## [1.1.0] - 2018-04-30
### Added
- PHP 7.0 option

## [1.1.0] - 2018-01-09
### Added
- PHP 7.2 support

## [1.0.0] - 2018-01-09
### Added
- This changelog

### Changed
- New FROM path for base image in Dockerfile `devgeniem/ubuntu-docker-wordpress:latest`
- Correct docker image link in README.md
