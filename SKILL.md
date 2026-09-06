---
name: "oktoeight-remote-levels-standard"
description: "Classify industrial remote monitoring, support, control, and unattended operation from Level 0 through Level 4."
---

# Oktoeight Remote Levels Standard

Classify an operating mode, not an entire product or facility. The same system can have different levels in different modes.

## Levels

| Level | Name | Definition |
| --- | --- | --- |
| 0 | Local operation | A field operator controls the equipment locally. No remote function changes control responsibility. |
| 1 | Remote monitoring | A remote user has read-only process visibility. A field operator retains control. |
| 2 | Remote support | A remote specialist analyzes, advises, or performs approved engineering support. A field operator authorizes and executes process actions. |
| 3 | Remote control | A remote operator controls the process. Local personnel are available to override, intervene, or perform physical work. |
| 4 | Unattended remote operation | A remote operator controls or supervises the process without relying on personnel at the equipment. The local system reaches a defined safe state without remote or field action. |

## Required inputs

Obtain these facts:

- the system or function and operating mode;
- the remote role and field role;
- who has control authority;
- required field presence;
- the communications path;
- the defined safe state;
- responses to loss of communications, supervision, power, and critical sensors;
- evidence for each claim;
- known limitations.

Do not infer a capability from installed technology alone. Classify the function that is in use.

## Procedure

1. Confirm the scope and operating mode.
2. Identify who controls the process during normal operation.
3. Identify every action required from field personnel.
4. Identify the fallback owner and the loss-of-link response.
5. Compare the evidence with the five level definitions.
6. Assign the lowest level that describes the complete mode.
7. State every missing requirement that prevents a higher classification.
8. Record automation separately.

A remote dashboard alone is Level 1. Remote advice with local execution is Level 2. A remote desktop connection is Level 3 only when the remote operator has approved control authority. Level 4 requires no field action to reach or maintain the safe state.

Do not credit the remote channel as a safety protection layer. Safety actions must remain local and automatic.

## Automation

Remote operation and automation are separate properties.

Remote operation identifies where the responsible human works and how control authority crosses distance. Automation identifies which tasks the system performs without continuous human input.

Do not increase a remote level because a system is automated. Do not decrease a remote level because a remote operator controls the system manually.

## Output

Return one classification record:

```text
System or function:
Operating mode:
Remote level: [0-4 and name]
Remote role:
Field role:
Control authority:
Field presence:
Communications path:
Safe state:
Loss-of-link response:
Automation: [separate description]
Evidence:
Limitations:
Requirements for next level:
```

If evidence is incomplete, return a provisional classification and name the missing evidence. Do not claim certification or compliance with another standard.
