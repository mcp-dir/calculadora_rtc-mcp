# Instalação detalhada

Calculadora da Reforma Tributária (CBS/IBS) é um servidor MCP remoto. Aponte seu cliente pra `https://api.mcp.ai/p_calculadora_rtc`. Snippets rápidos: [INSTALL.md](../INSTALL.md).

| Cliente | URL | Auth |
|---|---|---|
| Claude Desktop | `https://api.mcp.ai/p_calculadora_rtc` | nenhuma (grátis) |
| Cursor | `https://api.mcp.ai/p_calculadora_rtc` | nenhuma |
| VS Code (Copilot) | `https://api.mcp.ai/p_calculadora_rtc` | nenhuma |

A config JSON é a mesma em todos: só a URL, sem headers.

## Desinstalar

Remova o bloco `mcpServers.calculadora_rtc` (ou `servers.calculadora_rtc` no VS Code) do config do cliente e reinicie.
