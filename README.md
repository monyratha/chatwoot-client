# Chatwoot Client Demo

This project contains a simple HTML page that loads the Chatwoot widget and automatically opens any existing conversation for the current visitor.

## Usage

1. Serve `index.html` from any static web server.
2. Copy `.env.example` to `.env` and adjust the values to match your Chatwoot installation:
   - `CHATWOOT_BASE` – the base URL of your Chatwoot instance.
   - `WEBSITE_TOKEN` – the website token generated in Chatwoot.
   - `IDENTIFIER_HASH` – optional hash to verify the visitor when calling `setUser`.

   The values above are read from `.env` at runtime. `WEBSITE_TOKEN` and `IDENTIFIER_HASH` can be overridden by `token` and `hash` query parameters if needed.
3. Open the page in your browser. If a `uid` query parameter is present, that value is used as the visitor ID and persisted in `localStorage`. Otherwise a UUID is generated and stored so returning visitors see their previous conversation.

   If you load the page without a `uid`, the script automatically appends the generated ID to the URL. Copy this URL to access the same conversation from another browser.

   The widget also stores the conversation ID in `localStorage` and restores it when the same `uid` is used. Providing the same `uid` and matching `hash` lets Chatwoot reopen the conversation in any browser or device.

## Development

You can launch a basic server with Python for local testing:

```bash
python3 -m http.server 8080
```

Then browse to <http://localhost:8080>.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
