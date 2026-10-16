# Sample documentation: mount pose interface

This file is a format sample. A real page replaces it once the mechanical design settles the frames, actuator order, and units. Until then, values below stay as `[from CAD]`.

## Purpose

Define the pose the software sends to the mount, so a sky target and a SolidWorks configuration describe the same orientation.

## Where it sits

```text
sky target  →  platform orientation  →  actuator setpoints  →  mount
```

This page covers the last arrow: actuator setpoints and the frames they are measured in. The tracking plan covers how a sky target becomes a platform orientation.

## Frames

| Frame | Fixed to | Origin | Axes |
| --- | --- | --- | --- |
| Base | Mount base / pier | `[from CAD]` | `[from CAD]` |
| Platform | Moving telescope platform | `[from CAD]` | `[from CAD]` |

Platform orientation is the rotation of the platform frame relative to the base frame.

## Actuator setpoints

| Index | Joint in the CAD | Unit | Zero | Travel |
| --- | --- | --- | --- | --- |
| 0 | `[from CAD]` | `[from CAD]` | `[from CAD]` | `[from CAD]` |
| 1 | `[from CAD]` | `[from CAD]` | `[from CAD]` | `[from CAD]` |
| 2 | `[from CAD]` | `[from CAD]` | `[from CAD]` | `[from CAD]` |

Index order matches the actuator order in the assembly. A setpoint is a position command in the unit above. The software publishes a full set together.

## Home

Home is the platform orientation `[from CAD]`, reached when every actuator is at its zero. Assembly instructions and the software both use this pose as the starting configuration.

## Assumptions

- The base does not move relative to the pier during a tracking run.
- Joint names in this page match the SolidWorks component names.
- Travel limits are hard stops of the mechanism. Software stops at or before them.

## Related

- Planning format: [sample plan](planning/sample-plan.md)
