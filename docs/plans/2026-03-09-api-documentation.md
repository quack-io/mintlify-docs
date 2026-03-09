# AUI API Documentation Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Create Stripe-quality API documentation for AUI's three products (Messaging API, Agent Builder API, CLI) using Mintlify, styled with aui.io's dark design language.

**Architecture:** Mintlify docs project with MDX pages organized by product. Custom theming via mint.json to match aui.io's #121212/#F1F0E0/#fcdf71 palette. Content based on real codebase naming conventions with polished representative examples.

**Tech Stack:** Mintlify, MDX, mint.json configuration

---

### Task 1: Initialize Mintlify Project

**Files:**
- Create: `api-docs/mint.json`
- Create: `api-docs/logo/dark.svg`
- Create: `api-docs/logo/light.svg`

**Step 1: Create mint.json with AUI theming and full navigation**

```json
{
  "$schema": "https://mintlify.com/schema.json",
  "name": "AUI Documentation",
  "logo": {
    "dark": "/logo/dark.svg",
    "light": "/logo/light.svg"
  },
  "favicon": "/favicon.svg",
  "colors": {
    "primary": "#fcdf71",
    "light": "#fcdf71",
    "dark": "#fcdf71",
    "background": {
      "dark": "#121212",
      "light": "#ffffff"
    }
  },
  "modeToggle": {
    "default": "dark"
  },
  "tabs": [
    { "name": "Messaging API", "url": "messaging-api" },
    { "name": "Agent Builder", "url": "agent-builder" },
    { "name": "CLI", "url": "cli" }
  ],
  "topbarLinks": [
    { "name": "Playground", "url": "https://playground.aui.io" }
  ],
  "topbarCtaButton": {
    "name": "Console",
    "url": "https://console.aui.io"
  },
  "anchors": [
    { "name": "API Status", "icon": "signal", "url": "https://status.aui.io" },
    { "name": "Community", "icon": "discord", "url": "https://discord.aui.io" }
  ],
  "navigation": [
    {
      "group": "Getting Started",
      "pages": ["introduction", "quickstart", "authentication", "sdks"]
    },
    {
      "group": "Messaging API",
      "pages": [
        "messaging-api/overview",
        "messaging-api/send-message",
        "messaging-api/conversations",
        "messaging-api/channels",
        "messaging-api/webhooks",
        "messaging-api/errors"
      ]
    },
    {
      "group": "Agent Builder",
      "pages": [
        "agent-builder/overview",
        "agent-builder/create-agent",
        "agent-builder/agent-tools",
        "agent-builder/knowledge-bases",
        "agent-builder/workflows",
        "agent-builder/testing"
      ]
    },
    {
      "group": "CLI",
      "pages": [
        "cli/overview",
        "cli/installation",
        "cli/commands",
        "cli/configuration",
        "cli/plugins"
      ]
    }
  ],
  "footerSocials": {
    "github": "https://github.com/aui-io",
    "linkedin": "https://linkedin.com/company/aui-io",
    "twitter": "https://twitter.com/aui_io"
  }
}
```

**Step 2: Create placeholder SVG logos**

Simple "AUI" text logos for dark and light modes.

**Step 3: Verify mint.json is valid JSON**

---

### Task 2: Shared Pages — Introduction & Quickstart

**Files:**
- Create: `api-docs/introduction.mdx`
- Create: `api-docs/quickstart.mdx`

**Step 1: Write introduction.mdx**

Overview of AUI platform, card links to all 3 products, key value props.

**Step 2: Write quickstart.mdx**

Get API key, install SDK, make first request in under 5 minutes. Code samples in Node.js, Python, cURL.

---

### Task 3: Shared Pages — Authentication & SDKs

**Files:**
- Create: `api-docs/authentication.mdx`
- Create: `api-docs/sdks.mdx`

**Step 1: Write authentication.mdx**

Based on real auth patterns: auth-token header, account-id, organization-id, API key auth. Include Bearer token and API key examples.

**Step 2: Write sdks.mdx**

SDK overview for Node.js, Python, with installation and basic usage.

---

### Task 4: Messaging API Pages

**Files:**
- Create: `api-docs/messaging-api/overview.mdx`
- Create: `api-docs/messaging-api/send-message.mdx` (full detail)
- Create: `api-docs/messaging-api/conversations.mdx` (full detail)
- Create: `api-docs/messaging-api/channels.mdx` (stub)
- Create: `api-docs/messaging-api/webhooks.mdx` (stub)
- Create: `api-docs/messaging-api/errors.mdx` (stub)

Based on real codebase patterns: `/messages`, `/task-interactions`, kebab-case routes, snake_case fields.

---

### Task 5: Agent Builder API Pages

**Files:**
- Create: `api-docs/agent-builder/overview.mdx`
- Create: `api-docs/agent-builder/create-agent.mdx` (full detail)
- Create: `api-docs/agent-builder/agent-tools.mdx` (full detail)
- Create: `api-docs/agent-builder/knowledge-bases.mdx` (stub)
- Create: `api-docs/agent-builder/workflows.mdx` (stub)
- Create: `api-docs/agent-builder/testing.mdx` (stub)

Based on real Agent type, Parameter type, Integration type, Rule type from CLI types.

---

### Task 6: CLI Pages

**Files:**
- Create: `api-docs/cli/overview.mdx`
- Create: `api-docs/cli/installation.mdx` (full detail)
- Create: `api-docs/cli/commands.mdx` (full detail)
- Create: `api-docs/cli/configuration.mdx` (stub)
- Create: `api-docs/cli/plugins.mdx` (stub)

Based on real CLI commands: agents, create-agent, sync, rag, add-integration, connect, pull, status, diff, chat, serve.

---

### Task 7: Verify & Test

**Step 1: Install Mintlify CLI and run dev server**

```bash
cd api-docs && npx mintlify dev
```

**Step 2: Verify all pages render, navigation works, theming applies**
