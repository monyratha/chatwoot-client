# Chatwoot Client Demo

This project contains a simple HTML page that loads the Chatwoot widget and automatically opens any existing conversation for the current visitor.

## Usage

1. Serve `index.html` from any static web server.
2. Copy `.env.example` to `.env` and adjust the values to match your Chatwoot installation:
   - `CHATWOOT_BASE` – the base URL of your Chatwoot instance.
   - `WEBSITE_TOKEN` – the website token generated in Chatwoot.
   
   The `token` query parameter can still override `WEBSITE_TOKEN` at runtime.
3. Open the page in your browser. If a `uid` query parameter is present, that value is used as the visitor ID. Otherwise a UUID is stored in `localStorage` so returning visitors see their previous conversation.

## Development

You can launch a basic server with Python for local testing:

```bash
python3 -m http.server 8080
```

Then browse to <http://localhost:8080>.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
