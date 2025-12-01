# OpenG2P Social Registry Portal API

[![Pre-commit Status](https://github.com/OpenG2P/openg2p-registry-portal-api/actions/workflows/pre-commit.yml/badge.svg?branch=develop)](https://github.com/OpenG2P/openg2p-registry-portal-api/actions/workflows/pre-commit.yml?query=branch%3Adevelop)
[![Build Status](https://github.com/OpenG2P/openg2p-registry-portal-api/actions/workflows/test.yml/badge.svg?branch=develop)](https://github.com/OpenG2P/openg2p-registry-portal-api/actions/workflows/test.yml?query=branch%3Adevelop)
[![codecov](https://codecov.io/gh/OpenG2P/openg2p-registry-portal-api/branch/develop/graph/badge.svg)](https://codecov.io/gh/OpenG2P/openg2p-registry-portal-api)
[![openapi](https://img.shields.io/badge/open--API-swagger-brightgreen)](https://validator.swagger.io/?url=https://raw.githubusercontent.com/OpenG2P/openg2p-registry-portal-api/develop/api-docs/generated/openapi.json)
![PyPI](https://img.shields.io/pypi/v/openg2p-registry-portal-api?label=pypi%20package)
![PyPI - Downloads](https://img.shields.io/pypi/dm/openg2p-registry-portal-api)

This module implements the G2P Social Registry Portal APIs, providing backend services for managing registrant groups and their members in a social registry system.

## Features

### Authentication & Authorization
- **JWT Bearer Authentication**: Secure API access using JWT tokens
- **OAuth Integration**: OAuth-based authentication flow via `AuthController` and `OAuthController`
- **API-level Authorization**: Configurable authorization settings for each API endpoint

### Group Management
- **Get Group by Partner ID** (`GET /group/{partner_id}`): Retrieve group details for groups where the specified partner is a member, including:
  - Group information (name, email, phone, address, registration date)
  - Group kind/type
  - List of all group members with their details
- **Update Group Members** (`PUT /group/{group_id}`): Manage group membership by:
  - Adding new members to a group
  - Removing existing members from a group
  - Creating new partner records for members if they don't exist

### Member/Partner Management
- **Partner Information**: Manage individual registrant data including:
  - Basic information (name, email, phone)
  - Personal details (birthdate, gender)
  - Registration IDs
- **Household Member Updates**: Update household member information with partner field validation

### Database Models
- **Group Membership**: Track relationships between groups and individuals
- **Group Kind**: Categorize groups by type
- **Membership Kind**: Define roles or types within group memberships

## Dependencies

This project depends on:
- `openg2p-fastapi-common`: Common FastAPI utilities
- `openg2p-fastapi-auth`: Authentication and authorization
- `openg2p-portal-api-common`: Shared portal API components

## Configuration

Environment variables can be set with the `portal_sr_` prefix (e.g., `portal_sr_db_dbname`). Key configuration options include:
- Database connection settings (`db_dbname`)
- API authentication settings

## Getting Started

```bash
# Install dependencies
pip install openg2p-registry-portal-api

# Run the application
python main.py
```

## Licenses

This repository is licensed under [MPL-2.0](LICENSE).
