# Sample plan: sidereal tracking

This file is a format sample. Copy it when a real software slice starts, then replace every `[decide]` with a project decision.

| | |
| --- | --- |
| Status | Sample |
| Owner | Software planning |
| Depends on | Mechanical design of the SPM mount |

## Goal

Point the telescope at a sky coordinate and hold that pointing while the Earth rotates.

## Background

SAERO is a spherical parallel manipulator. The platform orientation is produced by several actuated legs, so a sky coordinate has to become a set of leg commands. The mapping depends on link lengths, joint layout, and which frame is fixed to the base. Those come from the CAD.

## Scope of this slice

- Accept a target in a stated sky frame.
- Convert that target into a platform orientation.
- Convert the platform orientation into actuator setpoints for the current mount model.
- Update the setpoints on a fixed cadence so the target stays centered.

## Mechanical inputs this slice needs

| Input | Why software needs it | Status |
| --- | --- | --- |
| Base frame and platform frame | So pose means the same thing in CAD and in code | `[decide]` |
| Leg count and joint order | So setpoint index *i* matches actuator *i* | `[decide]` |
| Actuator type and units | Degrees, millimeters, or steps | `[decide]` |
| Travel limits | So commands stay inside the mechanism | `[decide]` |
| Home pose | So the software and the assembled mount share a zero | `[decide]` |

## Milestones

1. **Frame agreement.** Write down the base frame, platform frame, and sky frame, with a sketch from the CAD.
2. **Pose map.** Implement the orientation-to-actuator map for the agreed geometry, with one worked numerical example checked against the model.
3. **Tracking loop.** Advance the sky target with time and refresh actuator setpoints.
4. **Limit handling.** Refuse or stop a command that would leave the travel range, and record which limit was hit.

## Open questions

- Which sky frame is the user-facing one: altitude-azimuth, or equatorial?
- Does the mount sit on a fixed pier with a known north reference?
- Are the actuators position-controlled, or does the software close a feedback loop?
- What pointing error is acceptable at the eyepiece or sensor?

## Decision log

| Date | Decision | Reason |
| --- | --- | --- |
| — | — | — |
