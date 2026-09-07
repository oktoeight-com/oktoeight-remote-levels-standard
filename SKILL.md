---
name: "oktoeight-remote-levels-standard"
description: "Classify industrial remote monitoring, support, control, and unattended operation from Level 0 through Level 4."
---

# Oktoeight Remote Levels Standard

Classify an industrial operating mode by remote control authority, field presence, and fallback behavior. Do not classify an entire product or facility. The same system can have different levels in different modes.

## Invocation and scope

Use this standard when a user asks to classify or review an industrial operating mode involving remote monitoring, support, control, or unattended operation.

Do not use it as a substitute for a safety lifecycle, risk assessment, cybersecurity requirements, or an automation taxonomy. Assess those properties separately.

## Levels

| Level | Name | Definition |
| --- | --- | --- |
| 0 | Local operation | A field operator controls the equipment locally. Field presence is required by the local operating mode. |
| 1 | Remote monitoring | A remote user has viewer-only process visibility and no process-response responsibility. A field operator retains control. |
| 2 | Remote support | An assigned remote specialist analyzes or advises without remote process, configuration, alarm, or software changes. A field operator authorizes and executes process actions. |
| 3 | Remote control | A remote operator controls the process. Local personnel are available and able to override, intervene, or perform physical work during the operating mode. |
| 4 | Unattended remote operation | A remote operator controls or supervises the process without relying on personnel at the equipment. The local system reaches and maintains a defined safe state without the remote link or field action. |

## Required inputs

Obtain these facts:

- the system or function and operating mode;
- the remote role and field role;
- who has control authority;
- required field presence;
- the communications path;
- the defined safe state;
- responses to loss of communications, supervision, power, and critical sensors;
- evidence for each claim; and
- known limitations.

Do not infer a capability from installed technology alone. Classify the function that is in use.

## Procedure

1. Confirm the scope and operating mode.
2. Identify who controls the process during normal operation.
3. Distinguish viewer-only monitoring from an assigned remote-support responsibility.
4. Identify every action required from field personnel.
5. Identify the fallback owner and the response to each required communications, supervision, power, and critical-sensor failure.
6. Compare the evidence with the five level definitions.
7. Assign the highest level for which every mandatory condition is supported by evidence.
8. State every missing requirement that prevents a higher classification.
9. Record automation separately.

A remote dashboard alone is Level 1. Assigned remote advice with local execution is Level 2. A remote desktop connection is Level 3 only when the remote operator has approved control authority and field personnel are available and able to intervene. Level 4 requires no field action and a local safe-state response independent of the remote link. Remote changes to configuration, alarms, or software are not remote support under this standard.

If no level is fully met, return an unclassified result. If evidence is missing, return a provisional result only when the missing evidence is clearly named and the result is bounded by the available facts.

Do not credit the remote channel as an independent protection layer. Safety instrumented functions and risk-assessed failure responses must remain local and automatic unless the applicable risk assessment explicitly permits another action.

## Boundary example

A remote operator can start, stop, and adjust an industrial process. Local personnel are available and able to take control if the remote link fails. This is **Level 3: Remote control**. If no field person is required and the local control system reaches and maintains the safe state without the remote link or field action, it is **Level 4: Unattended remote operation**.

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
Loss-of-communications response:
Loss-of-supervision response:
Loss-of-power response:
Critical-sensor-failure response:
Automation:
Evidence:
Limitations:
Requirements for next level:
```

Do not claim certification or compliance with another standard.
