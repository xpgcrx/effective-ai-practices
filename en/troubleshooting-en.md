# Troubleshooting

## Failed to read Confluence URL using Atlassian MCP

### Date and Tool Version

Date: 2025/12/29
Tool and Version: Gemini CLI, v0.22.4

### Issue

Even when a Confluence URL is provided, it doesn't attempt to read it using Atlassian MCP.
It tries to use Web fetch and fails.

### Cause

The Confluence URL is a shortened URL.

### Solution

Ensure you provide a non-shortened Confluence URL.
