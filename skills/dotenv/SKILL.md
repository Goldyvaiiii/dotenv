---
name: dotenv
description: Loads environment variables from a .env file into process.env.
---

# Use `dotenv` to Load Environment Variables

`dotenv` is a zero-dependency module that loads environment variables from a `.env` file into `process.env`. Storing configuration in the environment separate from code is based on [The Twelve-Factor App](https://12factor.net/config) methodology.

## When to Use
- You need to manage application configuration like API keys, database URLs, or feature flags.
- You want to keep secrets out of source control.
- You are developing locally and want a simple way to simulate environment variables.

## How to Use

### 1. Install
```bash
npm install dotenv --save
```

### 2. Create a `.env` file
Create a `.env` file in the root of your project:
```ini
# .env
API_KEY="your_api_key_here"
DB_URL="postgres://localhost:5432/mydb"
```

### 3. Load in Code
As early as possible in your application, import and configure `dotenv`:

**CommonJS:**
```javascript
require('dotenv').config()
```

**ES6 Modules:**
```javascript
import 'dotenv/config'
```

### 4. Access Variables
The variables are now available on `process.env`:
```javascript
const apiKey = process.env.API_KEY
```

## Best Practices for AI Agents
- **Never commit `.env` files**: Ensure `.env` is in your `.gitignore`.
- **Use `.env.example`**: Create a template file with dummy values to show which variables are required.
- **Prefer `dotenvx`**: For production or shared environments, consider using `dotenvx` for encryption.
