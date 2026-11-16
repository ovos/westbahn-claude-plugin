---
name: find-cheapest-westbahn-fares
description: Find the cheapest day to travel with WESTbahn. Use when the user has flexible dates and asks when a WESTbahn trip is cheapest, wants to compare WESTbahn fares across several days, a week or a month, or looks for the best price on a route rather than a specific train.
---

Use the WESTbahn connector's `get_cheapest_prices` tool for every fare comparison across dates. Never answer from memory: fares change, and the tool returns live data.

## Call the tool

- Pass the whole date range in **one** call, at most 31 days. Don't split a range into several calls to get around the limit; if the user asks for more than 31 days, the tool returns a message to pass on, and you can suggest narrowing the range.
- If the user gives a vague span such as "next week" or "in March", turn it into concrete dates within that limit.
- If the origin or destination is missing, ask for it before calling the tool. Follow the connector's own instructions for station names and the Vienna station choice.

## Present the result

- The connector shows the result as a price card, one cheapest fare per day, with the best-price days highlighted. Don't repeat the prices as a list. Add one or two sentences naming the cheapest day or days and any pattern worth knowing, such as weekdays being cheaper.
- If the user then picks a day, call `get_timetable` for that day to show the actual trains (see the find-westbahn-connections skill).
- Booking happens on westbahn.at; don't ask for payment or personal details.
- Answer in the user's language.
