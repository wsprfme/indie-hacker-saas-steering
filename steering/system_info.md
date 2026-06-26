---
title: PC Environment and Development Tools
inclusion: always
---

# PC Environment and Development Tools

This steering file provides details about the local development PC's environment. The AI agent MUST consult this information to ensure commands (especially PowerShell and shell utilities) are formatted correctly for this specific OS and toolchain.

## Operating System & Shell
*   **Operating System**: Microsoft Windows Server 2025 Standard (Version 10.0.26100, 64-bit)
*   **Shell**: Windows PowerShell 5.1 (Version: 5.1.26100.32860)
    *   *Constraint*: Always use PowerShell 5.1 compatible commands. Avoid commands or parameters that require PowerShell 7+ (Core) unless verified.
    *   *Tip*: Use standard cmdlets like `New-Item`, `Copy-Item`, `Remove-Item`, `Get-ChildItem`, and standard .NET calls if necessary.

## Installed Development Tools
*   **Git**: git version 2.54.0.windows.1
*   **Node.js**: v24.16.0 (NPM is available)
*   **Python**: Python 3.13.14 (use `python`)
*   **Go**: go version go1.26.4 windows/amd64 (use `go`)
*   **PostgreSQL 17**: Active and running (Service name: `postgresql-x64-17`, port `5432`, superuser `postgres`, password `YOUR_DB_PASSWORD_HERE`. Executable path: `C:\Program Files\PostgreSQL\17\bin\psql.exe`)

## Unavailable Tools (Do NOT attempt to use)
*   **Java**: Not Installed
*   **Docker**: Not Installed
*   **DotNet (.NET Core CLI)**: Not Installed
*   **Bash / Linux Shell**: Not configured. Always use PowerShell commands.
