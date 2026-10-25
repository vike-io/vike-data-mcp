# Installing the Vike Data API MCP server

The server is remote and hosted by Vike: there is nothing to clone, build or run locally.

1. Ask the user for a Vike API key. If they have none, they create one at
   https://vike.io/account?tab=api-keys (it starts with `vk_`).
2. Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`), keeping any
   existing servers:

   ```json
   {
     "mcpServers": {
       "vike-data": {
         "type": "streamableHttp",
         "url": "https://data.vike.io/mcp",
         "headers": { "X-API-KEY": "vk_..." }
       }
     }
   }
   ```

   The key goes in the `X-API-KEY` header. An `Authorization: Bearer` header with a `vk_` key is
   refused.
3. Reload the MCP servers and confirm that `vike-data` lists its tools.
4. Check the connection with a read-only call, for example the Hyperliquid market tool for `BTC`
   or a Polymarket markets search.

Docs: https://vike.io/docs/ai/data/
