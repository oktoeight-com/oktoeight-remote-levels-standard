# The Oktoeight Remote Levels Standard

The Oktoeight Remote Levels Standard classifies how an industrial operation is monitored, supported, and controlled from outside the field location. It defines five levels from fully local operation to unattended remote operation.

The standard classifies an operating mode, not an entire product or facility. One system can operate at different levels under different conditions.

## Use this standard when

Use this standard when you need to:

- classify an industrial operating mode by remote control authority;
- define the field presence and fallback required for that mode;
- distinguish remote monitoring, remote support, remote control, and unattended operation; or
- record a classification that another person can review and reproduce.

Do not use this standard as a substitute for a safety lifecycle, risk assessment, cybersecurity requirements, or an automation taxonomy. Those properties and controls must be assessed separately.

## The five levels

| Level | Name | Control authority | Field presence | Required fallback |
| --- | --- | --- | --- | --- |
| **0** | Local operation | A field operator controls the equipment locally. | Required by the local operating mode | The field operator or local control system brings the equipment to a safe state. |
| **1** | Remote monitoring | A remote user has viewer-only process visibility and no process-response responsibility. A field operator retains control. | Required by the local operating mode | The local system and field operator remain unaffected by loss of the remote link. |
| **2** | Remote support | An assigned remote specialist analyzes or advises without remote process, configuration, alarm, or software changes. A field operator authorizes and executes process actions. | Required by the local operating mode | The field operator continues locally without remote support. |
| **3** | Remote control | A remote operator controls the process. Local personnel are available and able to override, intervene, or perform physical work during the operating mode. | Defined presence, continuous or intermittent, during the operating mode | Local personnel take control, or the local control system reaches a defined safe state. |
| **4** | Unattended remote operation | A remote operator controls or supervises the process without relying on personnel at the equipment. | None required during the defined operating mode | The local control system reaches and maintains a defined safe state without the remote link or a field action. |

## Classification rules

Assign the highest level for which every mandatory condition is supported by evidence. A higher level includes the lower-level functions available in the same operating mode, but a capability that is not in use does not raise the classification.

1. Classify the function in use, not the maximum technical capability.
2. Identify who has control authority during normal operation.
3. Distinguish viewer-only monitoring from an assigned remote-support responsibility.
4. Identify whether field personnel must monitor, approve, override, or intervene.
5. Define what happens when communications, remote supervision, power, or a critical sensor fails.
6. Do not credit a remote connection as an independent protection layer. Safety instrumented functions and risk-assessed failure responses must remain local and automatic unless the applicable risk assessment explicitly permits another action.
7. Classify each materially different mode separately.

If a requirement for a higher level is missing, use the lower level only when that lower level's complete definition is met. If no level is fully met, return an unclassified result. If evidence is missing, return a provisional result and name the missing evidence. A remote desktop connection alone does not establish remote control. Remote changes to configuration, alarms, or software are not remote support under this standard.

## Boundary example

A remote operator can start, stop, and adjust an industrial process. Local personnel are available and able to take control if the remote link fails. This is **Level 3: Remote control**. If no field person is required and the local control system reaches and maintains the safe state without the remote link or field action, the same operating concept is **Level 4: Unattended remote operation**.

## Automation is a separate property

Remote operation and automation are related but different. Remote describes where the responsible human works and how authority crosses distance. Automation describes which tasks the system performs without continuous human input.

A highly automated system can operate locally at Level 0. A manually controlled system can operate remotely at Level 3 or Level 4. Record automation separately instead of treating it as the highest remote level.

## Minimum classification record

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

## Relationship to existing guidance

This standard adapts the clarity of established automation taxonomies without copying their domain-specific levels.

- [SAE J3016](https://saemobilus.sae.org/standards/j3016_202104-taxonomy-definitions-terms-related-driving-automation-systems-road-motor-vehicles) classifies driving automation by the sustained driving task and fallback responsibility. It does not classify industrial remote operation.
- [IMO autonomous shipping guidance](https://www.imo.org/en/mediacentre/hottopics/pages/autonomous-shipping.aspx) distinguishes onboard control, remote control with personnel onboard, remote control without personnel onboard, and full autonomy. Its scope is ships.
- [IOGP Report 627](https://www.iogp.org/bookstore/product/iogp-report-627-selection-of-system-and-security-architectures-for-remote-control-engineering-maintenance-and-monitoring/) defines remote monitoring, control, engineering, and maintenance for industrial control systems. It provides architectures and security guidance, but not one cross-industry maturity scale.
- IEC 62443 addresses IACS cybersecurity through zones, conduits, and security levels. Those security levels do not classify remote operation.
- IEC 61511 and related functional-safety standards govern safety instrumented systems. A remote level does not replace a safety lifecycle or risk assessment.

The gap is a compact, location-neutral classification that separates monitoring, support, remote control, and unattended operation while naming control authority, field presence, and fallback behavior.

## Origin

The model generalizes operational evidence from industrial remote monitoring and remote operation. It separates viewer-only monitoring and assigned remote support from remote control, then distinguishes remote control with available field personnel from unattended remote operation.

## Agent skill

This repository is also a portable [Agent Skill](https://agentskills.io). Copy or clone the repository into the skills directory used by an Agent Skills-compatible client. Keep the directory name `oktoeight-remote-levels-standard` so it matches the skill name in `SKILL.md`.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) to propose a change.

## License

This work is available under the terms in [LICENSE](LICENSE).
