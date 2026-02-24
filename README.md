# 🎰 Casino Testing Skills

Welcome to the **Casino Testing Skills** repository! This project is AI-driven test automation and network debugging framework specifically designed for testing cross-platform Casino applications.

### North star Prompt: "Use Proxyman to intercept the /api/wallet/balance endpoint and return a mock JSON response with a balance of $99,999, show me how the game screen looks like with a 5 digit wallet response."

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/1a8c0985-2127-4f9f-b39d-23d70df2b6bd" />

---

## 🚀 Tech Stack

This framework combines industry-leading automation tools with intelligent AI context servers:
By leveraging the power of the **Model Context Protocol (MCP)**, this repository integrates AI assistants directly into the testing and debugging workflows across iOS, Android, and Web platforms.

* **📱 Mobile Automation:** [Appium MCP](https://github.com/appium/appium-mcp)
* Automated UI interactions for **iOS Simulators** (XCUITest) and **Android Emulators** (UiAutomator2).
* AI-powered locator generation and natural language test execution.


* **🌐 Web Automation:** [Playwright](https://playwright.dev/)
* Fast, reliable, and headless end-to-end testing for the Casino web application.


* **🕵️ Network Debugging:** [Proxyman MCP](https://docs.proxyman.com/mcp)
* Inspect HTTP/HTTPS traffic, manipulate odds/balances via Mocking (Map Local/Remote), and create breakpoints entirely through AI conversations.


* **🧠 AI Integration:** Cursor IDE / Claude Code
* Acts as the brain, bridging your natural language prompts with Playwright, Appium, and Proxyman.



---

## ✨ Key Features

* **Cross-Platform Casino Testing:** Write and execute tests seamlessly across web browsers, Android emulators, and iOS simulators.
* **AI-Driven Mobile Actions:** Use Appium MCP to say *"Place a $5 bet on Blackjack"* and let the AI find the locators and execute the clicks.
* **Hands-Free Network Interception:** Use Proxyman MCP to ask your AI to *"Show me the last 10 API requests to the betting endpoint"* or *"Create a breakpoint to modify the user's wallet balance response."*
* **End-to-End Web Flows:** Robust Playwright scripts for web-based slot machines, live dealer lobbies, and user account management.
* **Smart Locators & Page Objects:** Automatically generated locators and tests that follow the Page Object Model (POM) best practices.

---

## 📋 Prerequisites

Ensure you have the following installed before getting started:

* **Node.js** (v22+) & npm/yarn
* **Java JDK** (v8+)
* **Android Studio & SDK** (For Android Emulators)
* **Xcode & Command Line Tools** (For iOS Simulators - macOS only)
* **Proxyman** (macOS app)
* An MCP-compatible AI Assistant IDE/CLI (e.g., **Cursor IDE** or **Claude Desktop**)

---

## 🛠️ Installation & Setup

**1. Clone the repository:**

```bash
git clone https://github.com/your-username/casino-testing-skills.git
cd casino-testing-skills
npm install

```

**2. Configure Appium MCP (Mobile):**
Add the Appium MCP server to your Cursor/Claude configuration:

```json
{
  "mcpServers": {
    "appium-mcp": {
      "command": "npx",
      "args": ["-y", "appium-mcp@latest"],
      "env": {
        "ANDROID_HOME": "/path/to/your/android/sdk",
        "CAPABILITIES_CONFIG": "./config/capabilities.json"
      }
    }
  }
}

```

**3. Configure Proxyman MCP (Network):**
Open Proxyman → Settings → MCP → Toggle **Enable MCP Server**. Add it to your AI client:

```json
{
  "mcpServers": {
    "proxyman": {
      "command": "/Applications/Proxyman.app/Contents/MacOS/mcp-server"
    }
  }
}

```

**4. Install Playwright Browsers (Web):**

```bash
npx playwright install

```

---

## 🎮 Usage Examples

Because this framework uses MCP, you can drive your testing using natural language inside Cursor or Claude!

### 📱 Mobile Testing (Appium MCP)

Open your AI prompt and type:

> *"Boot the iPhone 15 Pro simulator, launch the Casino app, and tap the 'Spin Roulette' button."*
> *"Generate a Java TestNG script for the Android emulator that logs into the casino app and checks the account balance."*

### 🌐 Web Testing (Playwright)

Run the standard Playwright test suite:

```bash
npx playwright test tests/web/slots.spec.ts

```

### 🕵️ API & Network Mocking (Proxyman MCP)

Ask your AI assistant:

> *"Use Proxyman to intercept the `/api/wallet/balance` endpoint and return a mock JSON response with a balance of $99,999."*
> *"Show me the captured network flow when I click the 'Cash Out' button in the iOS simulator."*

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.
