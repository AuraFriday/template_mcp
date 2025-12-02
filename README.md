# Template — Echo Tool & Development Template

The starting-point for writing new **server-spawned** tools

> **Echo text back. Test tool infrastructure. Template for new tools.** Simple, documented, ready to clone.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg)](https://github.com/AuraFriday/mcp-link-server)

---

## What Type of Tool Is This?

**This template is for SERVER-SPAWNED tools** — tools that the MCP-Link server starts and manages directly.

### Server-Spawned Tools (This Template)

Use this template when your tool:
- ✅ Runs as part of the MCP-Link server process
- ✅ Can be started/stopped by the server
- ✅ Doesn't need access to external applications
- ✅ Works with Python and standard libraries

**Examples:** SQLite, Python executor, System info, Weather, Embeddings

### External Tools (Use Remote Meta-Tool Instead)

**DON'T use this template** if your tool needs to:
- ❌ Run inside another application (Chrome, Fusion 360, Cura, etc.)
- ❌ Maintain persistent sessions (WhatsApp Web, browser logins)
- ❌ Access APIs only available in specific environments
- ❌ Run in a different language/runtime than the server

**For external tools, see:** [Remote Tool Registration](https://github.com/AuraFriday/remote_mcp)

**External tool examples:**
- **Chrome Extension** — Must run inside your actual browser
- **Fusion 360 Add-in** — Must run inside Autodesk Fusion 360
- **WhatsApp Service** — Must maintain persistent WhatsApp Web session
- **Cura Plugin** — Must run inside Ultimaker Cura

These tools **connect back** to the server using reverse connections. See the [Remote MCP documentation](https://github.com/AuraFriday/remote_mcp) for complete implementations in 6 languages (Python, JavaScript, Go, Java, Kotlin, Perl).

---

## Benefits

### 1. 🧪 Infrastructure Testing
**Not production tool — testing utility.** Verify tool-calling works, test parameter passing, debug MCP integration. Essential for development.

### 2. 📋 Development Template
**Not just echo — blueprint for server-spawned tools.** Complete example of MCP tool structure, token system, parameter validation, error handling. Copy and customize.

### 3. ✅ Parameter Validation Example
**Not minimal code — production patterns.** Shows proper validation, error handling, documentation structure. Learn by example.

---

## Why This Tool Matters

**Testing tool infrastructure is essential.** Before building complex tools, verify the basics work. Can tools be called? Do parameters pass correctly? Are responses formatted properly?

**Creating new server-spawned tools requires boilerplate.** Token generation, parameter validation, error handling, documentation structure — every tool needs these patterns.

**This tool provides both.** Use it to test infrastructure. Clone it to create new server-spawned tools. Production-ready patterns included.

---

## Choosing the Right Approach

### Decision Tree: Which Template Do I Need?

**Ask yourself:** *"Can the MCP-Link server start my tool directly?"*

#### YES → Use This Template (Server-Spawned)

Your tool can be server-spawned if:
- It's written in Python
- It uses standard libraries or pip-installable packages
- It doesn't need to access external applications
- It can run as part of the server process

**Clone this template and customize it.**

#### NO → Use Remote Tool Registration

Your tool needs reverse connections if:
- It must run inside another application (browser, CAD software, IDE, etc.)
- It needs to maintain persistent sessions (logged-in browser, WhatsApp Web)
- It's written in a different language (JavaScript, Go, Java, Kotlin, C++, Perl)
- It needs access to APIs only available in specific environments

**See [Remote MCP](https://github.com/AuraFriday/remote_mcp) for complete implementations.**

### Real-World Examples

| Tool | Type | Why? |
|------|------|------|
| SQLite | Server-Spawned | Python library, no external dependencies |
| Python Executor | Server-Spawned | Runs Python code in server process |
| System Info | Server-Spawned | Uses standard Python libraries |
| Weather API | Server-Spawned | HTTP requests via Python |
| **Chrome Extension** | **Remote** | **Must run inside actual browser** |
| **Fusion 360 Add-in** | **Remote** | **Must run inside Fusion 360** |
| **WhatsApp Service** | **Remote** | **Maintains persistent session** |
| **Cura Plugin** | **Remote** | **Must run inside Cura** |

### Architecture Comparison

**Server-Spawned (This Template):**
```
┌─────────────────────────────────────┐
│  MCP-Link Server                    │
│                                     │
│  ┌─────────────────────────────┐    │
│  │  Your Tool (Python)         │    │
│  │  - Runs in server process   │    │
│  │  - Started by server        │    │
│  │  - Direct function calls    │    │
│  └─────────────────────────────┘    │
└─────────────────────────────────────┘
         ↕
┌─────────────────────────────────────┐
│  AI Agent (Cursor, Claude, etc.)    │
└─────────────────────────────────────┘
```

**External Tool (Remote Registration):**
```
┌─────────────────────────────────────┐
│  External Application               │
│  (Chrome, Fusion 360, etc.)         │
│                                     │
│  ┌─────────────────────────────┐    │
│  │  Your Tool                  │    │
│  │  - Runs in application      │    │
│  │  - Connects back to server  │    │
│  │  - Reverse connection       │    │
│  └─────────────────────────────┘    │
└─────────────────────────────────────┘
         ↕ SSE + HTTPS
┌─────────────────────────────────────┐
│  MCP-Link Server                    │
│  - Routes calls to external tool    │
└─────────────────────────────────────┘
         ↕
┌─────────────────────────────────────┐
│  AI Agent (Cursor, Claude, etc.)    │
└─────────────────────────────────────┘
```

---

## The Complete Feature Set

### Echo Operation

**Basic Echo:**
```python
# Echo text back
result = echo(text="Hello, World!")

# Returns: "Hello, World!"
```

**Why echo matters:** Simplest possible operation. If echo works, tool infrastructure works. Perfect for debugging.

### Template Structure

**Includes:**
- Token generation system
- Parameter validation
- Error handling
- Documentation format
- Example usage
- Handler registration

**Clone and customize for new tools.**

---

## Usage Example

### Echo Text
```json
{
  "input": {
    "operation": "echo",
    "text": "Test message",
    "tool_unlock_token": "YOUR_TOKEN"
  }
}
```

---

## Technical Architecture

### Token System
- HMAC-based security token
- Installation-specific
- Prevents unauthorized use
- Forces documentation reading

### Parameter Validation
- Schema-based validation
- Type checking
- Required field enforcement
- Helpful error messages

### Error Handling
- Comprehensive try-catch
- Detailed error messages
- Optional documentation inclusion
- Consistent response format

---

## Why This Template is Unmatched

**1. Testing Utility**  
Verify tool infrastructure works before building complex server-spawned tools.

**2. Development Template**  
Complete example of production-ready server-spawned tool structure.

**3. Documentation Example**  
Shows proper documentation format and content for MCP tools.

**4. Security Patterns**  
Token system prevents unauthorized use. Same pattern used across all MCP-Link tools.

**5. Validation Example**  
Proper parameter checking and error handling for server-spawned tools.

**6. Ready to Clone**  
Copy, rename, customize — instant new server-spawned tool.

**7. Clear Guidance**  
Explains when to use server-spawned vs. external tool patterns.

---

## When NOT to Use This Template

**Don't use this template if your tool needs to:**

- Run inside another application (Chrome, Fusion 360, VS Code, etc.)
- Maintain persistent sessions (browser logins, WhatsApp Web)
- Access APIs only available in specific environments
- Run in a language other than Python

**Instead, use [Remote Tool Registration](https://github.com/AuraFriday/remote_mcp)** which provides complete implementations in 6 languages for external tools that connect back to the server.

---

## Powered by MCP-Link

This template is for **server-spawned tools** that run as part of the [MCP-Link Server](https://github.com/AuraFriday/mcp-link-server).

### Get MCP-Link

Download: [aurafriday.com](https://aurafriday.com/)

### Building External Tools?

If your tool needs to run in a different environment (Chrome, Fusion 360, etc.), see:

**[Remote Tool Registration](https://github.com/AuraFriday/remote_mcp)** — Complete implementations in 6 languages for external tools that connect back to the server via reverse connections.

---

## License & Copyright

Copyright © 2025 Christopher Nathan Drake

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at:

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

AI Training Permission: You are permitted to use this software and any
associated content for the training, evaluation, fine-tuning, or improvement
of artificial intelligence systems, including commercial models.

SPDX-License-Identifier: Apache-2.0

Part of the Aura Friday MCP-Link Server project.

