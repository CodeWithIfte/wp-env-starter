# 🚀 WP Env Starter

A **starter repository** for quickly spinning up a WordPress development environment using [`@wordpress/env`](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-env/).  
It comes with **MySQL** and **phpMyAdmin** support out of the box, so you can focus on building plugins or themes without worrying about setup.

---

## 📦 Features

- ⚡ One-command WordPress local environment (`npm run start`)
- 🗄️ MySQL database with exposed port
- 🛠 phpMyAdmin UI for managing the database
- 🔌 Easy plugin & theme development
- 🐞 Debugging enabled (`WP_DEBUG`, `WP_DEBUG_DISPLAY`, `WP_DEBUG_LOG`)

---

## 📂 Project Structure

```
wp-env-starter/
├── wp-content/
│   ├── plugins/   # Add your custom plugins here
│   ├── themes/    # Add your custom themes here
│   └── uploads/   # Media uploads (mapped for persistence)
├── .wp-env.json   # Environment configuration
├── package.json   # Scripts & dependencies
```

---

## ⚙️ Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/wp-env-starter.git
cd wp-env-starter
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Start the Environment
```bash
npm run start
```

This will:
- Start WordPress at **http://localhost:3000**
- Start MySQL at **localhost:13306**
- Start phpMyAdmin at **http://localhost:9001**

---

## 🔌 Adding Plugins & Themes

1. Place your plugin inside:
   ```
   wp-content/plugins/my-plugin/
   ```
   or your theme inside:
   ```
   wp-content/themes/my-theme/
   ```

2. Update `.wp-env.json` with the path:

```json
{
  "plugins": [
    "./wp-content/plugins/my-plugin"
  ],
  "env": {
    "development": {
      "themes": ["./wp-content/themes/my-theme"],
      "port": 3000,
      "mysqlPort": 13306,
      "phpmyadminPort": 9001
    }
  }
}
```

3. Restart the environment:
```bash
npm run start
```

---

## 🧪 Test Environment

This repo also provides a separate **test environment**:

- WordPress: `http://localhost:3001`
- MySQL: `localhost:13307`
- phpMyAdmin: `http://localhost:9002`

Useful for running automated tests or experimenting with code safely.

---

## 🐞 Debugging

- `WP_DEBUG`, `WP_DEBUG_DISPLAY`, and `WP_DEBUG_LOG` are enabled by default.
- Logs are stored in `wp-content/debug.log`.

---

## 🛑 Stopping the Environment

```bash
npm run stop
```

## ♻️ Resetting the Environment

If you want a fresh environment:

```bash
npm run destroy
```

---

## 🤝 Contribution

Feel free to fork, improve, and submit PRs!  
This repo is meant to help developers **get started quickly with WordPress development**.

---

## 📜 License

MIT License © 2025
