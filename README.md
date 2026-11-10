# leergut-agent

Konversationeller Datenanalyse-Agent (Mistral Agents SDK) für die Leergut-Bestandsführung.
Der Agent führt den Bestand in einer Markdown-Tabelle innerhalb der Session, bucht
Zugänge/Abgänge, beantwortet Fragen mit den echten Zahlen und hat keine Werkzeuge und
keine Sandbox (keine Codeausführung). Deployte Sessions werden von Mistral gespeichert,
inklusive des Gesprächsverlaufs.

## Lokal testen

```bash
uv lock
uv run --env-file .env agents chat
```

## Auf Mistral Cloud bereitstellen (verwaltete Bereitstellung)

Projekt in ein GitHub-Repository pushen, GitHub-Connector in Mistral Studio verbinden,
dann:

```bash
uv run --env-file .env agents deploy
```

## Mit dem Agenten sprechen

- CLI: `uv run --env-file .env agents chat leergut-agent`
- Vibe Code Web: Link, den `agents deploy` ausgibt (`https://chat.mistral.ai/managed-agents/leergut-agent`)
- Programmatisch: `agents.Agent.load_from(agent_name="leergut-agent")` und `start_session()` / `session.run(...)`
