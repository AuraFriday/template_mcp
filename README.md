# Template — Echo Tool & Development Template

The starting-point for writing new tools of your own

> **Echo text back. Test tool infrastructure. Template for new tools.** Simple, documented, ready to clone.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg)](https://github.com/AuraFriday/mcp-link-server)

---

## Benefits

### 1. 🧪 Infrastructure Testing
**Not production tool — testing utility.** Verify tool-calling works, test parameter passing, debug MCP integration. Essential for development.

### 2. 📋 Development Template
**Not just echo — blueprint for new tools.** Complete example of MCP tool structure, token system, parameter validation, error handling. Copy and customize.

### 3. ✅ Parameter Validation Example
**Not minimal code — production patterns.** Shows proper validation, error handling, documentation structure. Learn by example.

---

## Why This Tool Matters

**Testing tool infrastructure is essential.** Before building complex tools, verify the basics work. Can tools be called? Do parameters pass correctly? Are responses formatted properly?

**Creating new tools requires boilerplate.** Token generation, parameter validation, error handling, documentation structure — every tool needs these patterns.

**This tool provides both.** Use it to test infrastructure. Clone it to create new tools. Production-ready patterns included.

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

## Why This Tool is Unmatched

**1. Testing Utility**  
Verify tool infrastructure works before building complex tools.

**2. Development Template**  
Complete example of production-ready tool structure.

**3. Documentation Example**  
Shows proper documentation format and content.

**4. Security Patterns**  
Token system prevents unauthorized use.

**5. Validation Example**  
Proper parameter checking and error handling.

**6. Ready to Clone**  
Copy, rename, customize — instant new tool.

---

## Powered by MCP-Link

This tool is part of the [MCP-Link Server](https://github.com/AuraFriday/mcp-link-server).

### Get MCP-Link

Download: [GitHub Releases](https://github.com/AuraFriday/mcp-link-server/releases/latest)

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

