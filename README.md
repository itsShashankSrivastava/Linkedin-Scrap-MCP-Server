# Linkedin-Scrap-MCP-Server

Easily fetch real-time LinkedIn profile information using our MCP (Model Context Protocol) server. This server integrates with the Fresh LinkedIn Profile Data API to return profile details like skills and other basic settings. It exposes a single tool—get_profile—that accepts a LinkedIn profile URL and responds with structured JSON data.

---

## 🚀**Features**

- Real-Time LinkedIn Data: Retrieve up-to-date profile info including skills and core public data (additional extended fields are disabled by default).
- Asynchronous Requests: Built with httpx for efficient, non-blocking HTTP calls.
- Secure API Key Handling: Uses environment variables via dotenv for safe configuration of your RAPIDAPI_KEY.

---

## ⚙️**Requirements**

Before you get started, make sure you have:

- **Python 3.7+**
- **MCP Framework** installed
- **Required libraries**: httpx, python-dotenv
- **RAPIDAPI_KEY**: Sign up at RapidAPI and subscribe to the Fresh LinkedIn Profile Data API, then grab your API key.

---

## 📦**Installation**

### **1. Clone the repository:**

```bash
git clone https://github.com/itsShashankSrivastava/Linkedin-Scrap-MCP-Server
```

### **2. Install dependencies:**

```bash
uv add mcp[cli] httpx requests
```

### **3. Set up your environment variables:**

```bash
RAPIDAPI_KEY=your_rapidapi_key_here
```

---

## **▶️ Running the Server**

To start the MCP server:

```bash
uv run linkedin.py
```

This will launch the server and begin listening for incoming requests over standard I/O.

---

## **🤖 MCP Client Configuration**

To connect your MCP client to the server, update your config.json with the following:

```bash
{
  "mcpServers": {
    "linkedin_profile_scraper": {
      "command": "C:/Users/shashank.srivastava/.local/bin/uv", 
      "args": [
        "--directory",
        "C:/Users/shashank.srivastava/Desktop/linkedin-scrap",  
        "run",
        "linkedin.py" 
      ]
    }
  }
}
```

💡 Adjust the paths as necessary based on where your server is located.

---

## **🧠 How It Works**

- **Environment Setup**: Uses dotenv to load your RAPIDAPI_KEY.
- **API Integration**: Makes asynchronous GET requests to the Fresh LinkedIn Profile Data API using httpx.
- **MCP Tool** - get_profile: Wraps the API logic and returns either a clean JSON object or an error message if the request fails.
- **Execution**: Runs using the standard I/O (stdio) transport method of the MCP server framework.

---

## **🛠 Troubleshooting**

- **Missing RAPIDAPI_KEY**: If not set, the server will raise a ValueError. Double-check your .env file or system environment variables.
- **API Call Errors**: If the LinkedIn API request fails, the tool will return a clear error message indicating what went wrong.

---

Feel free to ⭐️ the repo if you find it helpful or open an issue if you need support!
