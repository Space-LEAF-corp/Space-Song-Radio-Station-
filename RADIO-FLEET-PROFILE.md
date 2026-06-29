RADIO-FLEET-PROFILE.md
Space LEAF Corp — Fleet Radio Profile Specification
Version 1.0
1. Purpose
Defines how fleets (schools, medical, mission, commercial) configure radio behavior across all vehicles.

2. Fleet Profile Structure
json
{
  "fleet_id": "FLEET-001",
  "policies": {
    "kids_safe": true,
    "distraction_reduction": true,
    "allowed_channels": ["calm-001", "edu-101"],
    "restricted_channels": ["talk-999"],
    "emergency_behavior": "strict"
  }
}
3. Fleet Policy Types
3.1 Safety Policies
Mandatory Kids‑Safe

Distraction‑Reduction Mode

Calm‑Mode driving playlists

Emergency strict mode

3.2 Content Policies
Allowed channel list

Restricted channel list

Educational priority mode

No‑advertising mode

3.3 Operational Policies
Telemetry frequency

Offline cache size

Satellite fallback priority

Fleet‑wide announcements

4. Fleet Overrides
Fleet policies override:

Regional policies

Vehicle preferences

Fleet policies do not override:

Emergency broadcasts

Global Kids‑Safe enforcement

5. Fleet Telemetry
Compliance logs

Policy violations

Emergency override behavior

Connectivity reports

Playback statistics

6. Fleet Provisioning
Create fleet profile

Assign vehicles

Push policies to CRS units

Verify policy sync

Monitor fleet telemetry
