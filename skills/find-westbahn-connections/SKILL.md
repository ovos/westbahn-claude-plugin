---
name: find-westbahn-connections
description: Find WESTbahn train connections for a specific day. Use when the user asks for WESTbahn train times, the next train, whether WESTbahn connects two stations (for example Wien, St. Pölten, Linz, Salzburg, Innsbruck, Graz, Villach or München), a return trip, or the fares for a particular day.
---

Use the WESTbahn connector's `get_timetable` tool for every time, connection and fare on a given day. Never answer these from memory: schedules and fares change, and the tool returns live data.

## Call the tool

- **One day or "the next train"**: call `get_timetable` once. For a connecting route, that single call already returns every leg and the transfer; don't call it again for the individual legs.
- **Return trip**: call `get_timetable` twice, once for the outbound journey and once for the return journey with the stations swapped and the return date. Present the outbound journey first.
- If the origin or destination is missing, ask for it before calling the tool. Follow the connector's own instructions for station names, the Vienna station choice, and when to ask for a time of day.
- If the user doesn't know which day yet and wants the cheapest one, use `get_cheapest_prices` first (see the find-cheapest-westbahn-fares skill).

## Present the result

- The connector shows the result as a connections card with the trains, times and fares. Don't repeat the card's contents as a list. Add one or two sentences: the best fit for what the user asked (earliest arrival, fewest changes, lowest fare) and anything the card makes easy to miss, such as a station change during a transfer.
- Booking happens on westbahn.at through the links in the card. Say so when the user wants to book; don't ask for payment or personal details.
- Answer in the user's language.
- If the tool finds no WESTbahn route between two places, say that WESTbahn does not serve that connection and, if it helps, name the nearest WESTbahn station.
