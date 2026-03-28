<!-- ShellRPG Comment Banner | Revisionsänderung: Windows-/Startfix -->

# Standalone-Client

Der Standalone-Client kombiniert:
- Terminaleingabe
- eingebettetes WWW-Dashboard

Start:

## Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
python -m shellrpg_client --standalone
```

## Bash / Zsh

```bash
source .venv/bin/activate
python -m shellrpg_client --standalone
```

Das Dashboard wird lokal ausgeliefert, während derselbe Prozess die Terminalschicht bedient.
