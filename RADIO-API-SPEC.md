RADIO-API-SPEC.md
Space LEAF Corp — SSRS ↔ CRS API Specification
Version 1.0
1. Purpose
Defines the API surface between SSRS (server) and CRS (client).
All endpoints use HTTPS with JSON payloads.

2. Authentication
Token‑based (Bearer)

Fleet tokens for multi‑vehicle groups

Vehicle tokens for individual CRS units

Optional parental tokens for Kids‑Safe overrides

3. Endpoints
3.1 GET /channels
Returns list of available channels.

Response:

json
{
  "channels": [
    {
      "id": "calm-001",
      "name": "Calm Mode",
      "safety_level": "low",
      "region": "global",
      "kids_safe": true
    }
  ]
}
3.2 POST /subscribe
CRS subscribes to a channel.

Request:

json
{
  "channel_id": "calm-001",
  "vehicle_id": "SC-2026-001"
}
Response:

json
{ "status": "subscribed" }
3.3 GET /stream/:channel_id
Returns HLS/DASH manifest URL.

Response:

json
{
  "manifest": "https://ssrs.spaceleaf/streams/calm-001/manifest.m3u8"
}
3.4 POST /telemetry
CRS sends playback and safety events.

Request:

json
{
  "vehicle_id": "SC-2026-001",
  "event": "emergency_override",
  "timestamp": 1782670000
}
3.5 GET /policy
Returns current global/regional/fleet/vehicle policies.

3.6 WebSocket /policy-stream
Real‑time policy updates:

Emergency flags

Kids‑Safe enforcement

Channel restrictions

Priority changes

4. Error Codes
Code	Meaning
401	Unauthorized
403	Policy Restriction
409	Conflict (e.g., cannot switch during emergency)
503	Stream Unavailable


END OF FILE
