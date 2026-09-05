# Configuration Directory

This directory contains configuration files for the Kofaraziki Data platform.

## Configuration Files

### Environment Configuration
- `.env` - Environment variables (not tracked in git)
- `.env.example` - Example environment configuration

### Database Configuration
- `database.config.js` - Database connection settings

### Payment Gateway
- `payment.config.js` - Palmpay and other payment settings

### Application Settings
- `app.config.js` - General application settings
- `logger.config.js` - Logging configuration

## Setup Instructions

1. Copy `.env.example` to `.env`
2. Fill in your configuration values
3. Ensure sensitive data is in `.env` (never commit)
4. Load configuration in your application startup

## Important Security Notes

⚠️ **DO NOT commit `.env` files**
⚠️ **DO NOT commit API keys or secrets**
⚠️ **Keep sensitive data in environment variables**

---
*Configuration Management Guide*
