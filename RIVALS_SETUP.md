# The Rivals event bot — customization notes

This package is a customized copy of the uploaded open-source event registration bot.

## Included changes
- Docker timezone changed to `Europe/London`.
- Event/calendar timezone fallback changed to `Europe/London`.
- Registration automatically closes **10 minutes before** the event's configured start time.
- `REGISTRATION_CLOSE_MINUTES_BEFORE` environment setting is available (default `10`).

## Registration opening
The original bot already supports a per-event registration start time. To open registration 30 minutes before the event, set each event's registration start time to **30 minutes before its event start time** in the event creation wizard (or event editor). This version does not yet add a dedicated `/roster` command or automatically derive that opening time from the event start.

## Important differences from the requested full bot
- The existing command is `/create_event`, not `/roster`.
- This project is designed around squad/event registration and may need further UI and workflow customization for a simple one-person-per-slot Grand RP roster.
- Role application tickets are not included.
- Hosting and Discord bot registration are not configured. Add your bot token privately to `.env`; never share it in chat.

## Run (Docker)
1. Copy `.env.dist` to `.env`.
2. Add your Discord bot token in `.env` as `DISCORD_BOT_TOKEN=...`.
3. Run `docker compose up -d --build`.
4. Use `/setup` in your Discord server, then `/create_event` in the desired event channel.

Check the upstream license before redistributing or deploying modified code.
