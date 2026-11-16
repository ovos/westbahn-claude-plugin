# WESTbahn for Claude

Plan train trips on WESTbahn with Claude. Ask for a connection, the next train, or the cheapest day to travel, and Claude answers with live WESTbahn data, shown as interactive cards with departure and arrival times, travel time, transfers and fares per class. Booking happens on westbahn.at through the links in the cards.

## What you can ask

- "When is the next train from Wien to Salzburg?"
- "Trains from Linz to Wien tomorrow morning for two adults"
- "I need to get from Graz to Salzburg on Friday" (connecting routes with a transfer are included)
- "When is it cheapest to travel from Salzburg to St. Pölten next week?"
- "Wien to Innsbruck on the 12th, back on the 14th"

## What it includes

- **WESTbahn connector**: two read-only tools served from `mcp.westbahn.at`.
  - `get_timetable`: the connections between two WESTbahn stations on a given day, with fares per class for the travellers you name. Shown as a connections card.
  - `get_cheapest_prices`: the cheapest fare per day across a date range of up to 31 days. Shown as a price card.
- **Two skills**, one per tool, that tell Claude how to use them well:
  - `find-westbahn-connections`: trains on a given day, including round trips planned as an outbound and a return journey.
  - `find-cheapest-westbahn-fares`: the cheapest day across flexible dates, then that day's trains once you pick one.

## Where it works

The plugin works in Claude on the web, in the desktop and mobile apps, and in Cowork. After installing it, connect the WESTbahn connector on the plugin's Connectors tab. It needs no account and no sign-in.

Claude Code is not supported: the WESTbahn server only accepts connections from Claude's own infrastructure, and Claude Code connects from your computer instead.

## Data

The plugin sends the details of each trip question to WESTbahn's server at `mcp.westbahn.at`: the two stations, the date or date range, the time of day if you give one, and the number and type of travellers and any discount you mention. The server uses them to look up timetables and fares from WESTbahn and returns the results to Claude. For operating the service, the server keeps technical logs of these requests and results. The plugin needs no account and asks for no personal or payment details; booking and payment happen on westbahn.at.

Privacy policy: https://westbahn.at/datenschutzerklaerung/
Support: https://westbahn.at/kontakt/

## License

MIT, see [LICENSE](LICENSE).
