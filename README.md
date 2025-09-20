# Changelog – Locify Chat App

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## \[Unreleased]

### \[v0.1.0] - 2025-09-19

* setup basic express server with initial project folder structure
* configure typescript support with ts-node and compiler options
* update nodemon configuration for smooth local development

### \[v0.2.0] - 2025-09-20

### added
* added `@types/node` and prisma as dev dependencies
* setup database orm, installed and generated prisma client
* authentication model and initial migration
* global error handler for improved readability
* http configuration module
* environment sanitation with default values
* logging system to track user activity
* authentication, mfa, and session system with middlewares
* email sender integration using resend
* enhanced security mechanisms

### changed
* fixed spelling typo in `tsconfig.json`
* renamed folder `config` → `configs`

### removed
* `.gitkeep` placeholders in:
  * `/src/@types`
  * `/src/common/constants`
  * `/src/common/enums`
  * `/src/common/interfaces`
  * `/src/common/strategies`
  * `/src/common/utils`
  * `/src/common/validators`
  * `/src/common`
  * `/configs`
  * `/models`
  * `/modules`
* deprecated `/models` directory

## \[Released]

### \[v0.0.0] - YYYY-MM-DD

* Example add some features
* Example bug fixed
