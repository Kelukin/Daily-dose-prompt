# Scenario
When you open a browser page that contains your flight/hotel/concert etc. information and you would like to create a event in your Outlook calendar to track it. I usually use it with my Edge browser's copilot.

# Instruction
Generate a MS Graph event payload for the page. I'd like to add it into my Outlook Calendar. 
Please consider of the timezone based on the place location. I hope: 
* its address can be recognized by Apple Map. Hence, its location information should contains coordinates.
* Include {somebody's email address} as an required attendee.
* Extract the exact time!
* Remind me {time_period} before.

# Example payload

```json
{
  "subject": "Flight: {AIRLINE} {FLIGHT_NUMBER} — {DEP_IATA} → {ARR_IATA}",
  "body": {
    "contentType": "HTML",
    "content": "Booking Ref: {PNR}<br/>Seat: {SEAT}<br/>Terminal/Gate: {TERMINAL}/{GATE}<br/>Notes: {NOTES}"
  },
  "start": {
    "dateTime": "{DEPARTURE_LOCAL_DATETIME}",  // e.g., 2026-05-10T08:35:00
    "timeZone": "{DEPARTURE_AIRPORT_TIMEZONE}" // e.g., Asia/Shanghai
  },
  "end": {
    "dateTime": "{ARRIVAL_LOCAL_DATETIME}",    // e.g., 2026-05-10T12:15:00
    "timeZone": "{DEPARTURE_AIRPORT_TIMEZONE}" // keep departure airport timezone per your instruction
  },
  "location": {
    "displayName": "{DEP_IATA} {DEP_AIRPORT_NAME}",
    "locationType": "default",
    "coordinates": {
      "latitude": {DEP_LAT},
      "longitude": {DEP_LON}
    }
  },
  "attendees": [
    {
      "emailAddress": { "address": "sudong-han@outlook.com", "name": "Sudong Han" },
      "type": "required"
    }
  ],
  "isAllDay": false,
  "showAs": "busy",
  "reminderMinutesBeforeStart": 120,
  "allowNewTimeProposals": false
}

```