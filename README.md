<h2 align="center"><img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/iconWhite.png" height="64"><br>Ask ChatGPT</h2>
<p align="center"><strong>ChatGPT conversations in Visual Studio Code</strong></p>

[![Badge for version for Visual Studio Code extension gencay.vscode-chatgpt](https://img.shields.io/visual-studio-marketplace/v/gencay.vscode-chatgpt?label=VS%20Code%20Marketplace)](https://marketplace.visualstudio.com/items?itemName=gencay.vscode-chatgpt)

## 📢 New feature - Use Official OpenAI GPT3 APIs or browser integration with zero-config

The extension now supports official APIs from OpenAI along with zero-config browser based integration. Simply switch methods in your settings and use your API Key to ask questions. If you opt-in to use this method, make sure you are aware of the limitations set by OpenAI team [here](https://help.openai.com/en/articles/5955598-is-api-usage-subject-to-any-rate-limits).

# ChatGPT as your copilot to level up your developer experience

- 🤖 Zero-Config setup. Simply login to OpenAI as usual. Or use OpenAI's official GPT3 APIs
- 📎 Detects partial code response and suggests automatic continuation and combination of multiple answers.
- ➡️ Export all your conversation history at once in Markdown format.
- 💭 Preset commands + Customization to use any prompt for a selected code.
- 📝 Create projects/files with one click using built-in actions in the conversation view.
- ⚡ Built-in syntax highlighting for ChatGPT suggested code using the default code-font of your Visual Studio Code!
- 🖼️ Icon is generated by dall-e-2.

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/chatgpt-gif.gif">

# Zero Configuration with Browser Auto Login

### 3 options to run ChatGPT assistant in your vs-code

1. [**Recommended**] Autologin - Uses browser to ask questions to ChatGPT. [Autologin Setup (Default)](#setup). Zero-Config Autologin lets the extension grab the required tokens automatically using `puppeteer`. The extension will use the browser behind the scenes, so you are not expected to receive 4xx errors while asking ChatGPT via extension unless there is OpenAI outages.
2. Use OpenAI's official GPT3 APIs - Use your personal/organizational API Keys. This method provides many parameters to customize your prompt. Check out the GPT3 settings. For more details: [GPT3 OpenAI API Key](#gpt3)
3. [Not recommended due to throttling] Manually login on a browser and grab required tokens. Described in [Manual Setup](#manual-setup). This option has problems due to using unofficial OpenAI API usage and rate-limiting.

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/methods.png">

# Setup

🚀 All you need to do is click Login or ask a question to get started!

1. Click on extension icon on your sidebar and hit `Login` button.

2. A new browser window (Default is `Chrome` but you may override it with any Chromium-based browser) will open up redirected to https://chat.openai.com/. Wait till you see login page, and click on Login on your browser.

3. Solve captchas if you are prompted and continue.

4. After successfully logging in, the browser will be minimized.

ℹ️ You will need to have a browser open and be logged in at all times. If you close the browser or your VS-Code instance, you will be asked to login again in your next session.

📝 You can have the extension auto-fill the email address and/or password during logins. Update the extension settings with those information for quicker login. NOTE: We never store any of this information locally or remotely.

🤖 Below is a sample autologin flow. Simply login & keep your browser minimized for dialogues with ChatGPT:

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/chatgpt-autologin.gif">

---

## Override settings with any Chromium-based browser

1. To use `Edge`, go to this URL: `edge://version` and copy the executable path used by your Edge browser.
2. Override the chromium path by going to vs-code settings and search for `chatgpt:chromiumPath`. Paste the executable path. i.e. `C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe`
3. [Maybe required] Run `ChatGPT: Reset session` command to clear your previous browser selection. This is required only if you have previously authenticated using a different browser.

### Run on Linux or remote - SSH workspace

There are community members who are able to run the extension in WSL, Linux, remote-SSH workspaces. Please check these issues for instructions.

Credits to [@EzyDark](https://github.com/EzYDark)

- [How to get it work in remote workspace (Remote - SSH) #39](https://github.com/gencay/vscode-chatgpt/issues/39#issuecomment-1370272656)
- [How to get it work under WSL2 #25](https://github.com/gencay/vscode-chatgpt/issues/25#issuecomment-1374833026)

## GPT3

### Official OpenAI API - GPT3 Setup

If you prefer using OpenAI's official APIs to communicate, switch your method setting to `GPT3 OpenAI API Key` and get your API Key ready from here: [OpenAI](https://beta.openai.com/account/api-keys)

1. Click `Login` in your extension or ask any coding question by selecting a code fragment.
2. Once asked provide your API Key to the extension
   - [Optional] You could also store your API Key in your settings.json. However, it's highly discouraged due to security reasons.

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/api-key.png">

# Features

The extension comes with context menu commands, copy/move suggested code into editor with one-click, conversation window and customization options for OpenAI's ChatGPT prompts.

## ChatGPT conversation window in vs-code

### 🆕 Export all your conversation history withs one click

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/export-convo.png">

---

### Ad-hoc prompt prefixes for you to customize what you are asking ChatGPT

Customize what you are asking with the selected code. The extension will remember your prompt for subsequent questions.

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/adhoc.png">

---

### Automatic partial code response detection

The extension will detect if ChatGPT didn't complete code in their answer and it will suggest automatic continuation and combination of answers

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/continue-combine.png">

---

### 🍻 Optimized for dialogue

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/conversation-mode-2.png">

---

### Edit and resend a previous prompt

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/edit-resend.png">

---

### Copy or insert the code ChatGPT is suggesting right into your editor.

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/code-actions.png">

---

### Ask free-form text questions that will be listed in the conversation window. The conversation is kept in cache until vs-code instance is closed.

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/rust.png">

# Use defaults or customize your code prompts

- `ChatGPT: Ad-hoc prompt`: Ad-hoc custom prompt prefix for the selected code. Right click on a selected block of code, run command.
  - You will be asked to fill in your preferred custom prefix and the extension will remember that string for your subsequent ad-hoc queries.
- `ChatGPT: Add tests`: Write tests for you. Right click on a selected block of code, run command.
  - "default": "Implement tests for the following code",
  - "description": "The prompt prefix used for adding tests for the selected code"
- `ChatGPT: Find bugs`: Analyze and find bugs in your code. Right click on a selected block of code, run command.
  - "default": "Find problems with the following code",
  - "description": "The prompt prefix used for finding problems for the selected code"
- `ChatGPT: Optimize`: Add suggestions to your code to improve. Right click on a selected block of code, run command.
  - "default": "Optimize the following code",
  - "description": "The prompt prefix used for optimizing the selected code"
- `ChatGPT: Explain`: Explain the selected code. Right click on a selected block of code, run command.
  - "default": "Explain the following code",
  - "description": "The prompt prefix used for explaining the selected code"
- `ChatGPT: Add comments`: Add comments for the selected code. Right click on a selected block of code, run command.
  - "default": "Add comments for the following code",
  - "description": "The prompt prefix used for adding comments for the selected code"

## Other available commands

- `ChatGPT: Ask anything`: Free-form text questions within conversation window.
- `ChatGPT: Reset session`: Clears the current session and resets your connection with ChatGPT
- `ChatGPT: Clear conversation`: Clears the conversation window and resets the thread to start a new conversation with ChatGPT.
- `ChatGPT: Export conversation`: Exports the whole conversation in Markdown for you to easily store and find the Q&A list.

## Customization settings

- Use proxy with autologin puppeteer setup
- Opt-in to use automation to authenticate OpenAI.
- You can configure the commands to use any prompts for the selected code!
- Opt-in to receive notification when ChatGPT sends you a message!

### Using Proxies

The autologin supports setting a proxy server. This is useful if you're running into rate limiting issues or if you want to use a proxy to hide your IP address. Right now this setting only supports http proxies. Don't provide a protocol in the setting.

To use a proxy, update the settings with your proxy server details. For more information on the format, see [here](https://www.chromium.org/developers/design-documents/network-settings).

Format examples:

Authenticated: `myUsername:myPassword@my.proxy.com:3001`

Anonymous: `204.137.172.37:999`

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/proxy-server.png">

## Manual Setup

ℹ️ This method is no longer recommended since hard rate-limiting by OpenAI services. Please use the `AutoLogin` option with Zero-Configuration required.

1. Go to https://chat.openai.com and login.
2. Open your browser's developer tools
   - Hit F12 to open the developer tools in most browsers
   - Alternatively, right click on the browser window and select `Inspect`
3. Go to `Application` -> `Cookies` -> `https://chat.openai.com`. You will need the following cookies:
   - `__Secure-next-auth.session-token`: The extension will use this to send prompts to ChatGPT
   - `cf_clearance`: CloudFlare clearance token. A security measure OpenAI put in place to block automated access.
4. Go to `Console` and type in the following code to get your `user-agent`
   - `navigator.userAgent`: This is your browser's user-agent, needed for CloudFlare clearance. Enter the value of `userAgent` when prompted by the extension. Copy its value **without single or double quotes**.
5. Now that you have all required session variables, run any command using the extension and you'll be asked to enter these values:
   - `__Secure-next-auth.session-token`: An encoded token starting with `ey***`
   - `cf_clearance`: An alpha-numeric token
   - `userAgent`

<img src="https://raw.githubusercontent.com/gencay/vscode-chatgpt/main/images/setup.png">

# Troubleshooting

- It's possible that openai systems may experience issues responding to your queries due to high-traffic from time to time.
- If you get `ChatGPTAPI error 429`, it means that you are making Too Many Requests. Please wait and try again in a few moments. If it persists, restart your vs-code.
- If you see `ChatGPTAPI error terminated`, your requests are being throttled. Please try again later.
- If you encounter persistent issues with your queries
  - Try `ChatGPT: Reset session` command
  - As a last resort try restarting your VS-Code and retry logging in.

# Disclaimer and Credits

- During login you'll notice some warnings on your Chromium-based browser about flags that are used to open the browser. This is required to automate your login and conversations with the browser's network.
- This extension never uses/stores your personally identifiable information locally or remotely. It's up to you to use the extension for ChatGPT conversations and we assume no responsibility of any issues that you may face in ChatGPT. Since this is just an experimental project I work on my freetime for the community.
- 💻 Open AI ChatGPT: https://chat.openai.com/
- 🖼️ Open AI Dall-E-2: https://openai.com/dall-e-2/
- 🧪 The manual setup option uses unofficial OpenAI APIs. https://github.com/transitive-bullshit/chatgpt-api
