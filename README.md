# Oktoeight Remote Levels Standard

The Oktoeight Remote Levels Standard classifies how an industrial operation is monitored, supported, and controlled from outside the field location. It defines five levels from fully local operation to unattended remote operation.

The standard classifies an operating mode, not an entire product or facility. One system can operate at different levels under different conditions.

## The five levels

| Level | Name | Control authority | Field presence | Required fallback |
| --- | --- | --- | --- | --- |
| **0** | Local operation | A field operator controls the equipment locally. | Continuous | The field operator brings the equipment to a safe state. |
| **1** | Remote monitoring | A remote user can view data but cannot change the process. A field operator retains control. | Continuous when operation requires it | The local system and field operator remain unaffected by loss of the remote link. |
| **2** | Remote support | A remote specialist analyzes, advises, or performs approved engineering support. A field operator authorizes and executes process actions. | Continuous when operation requires it | The field operator continues locally without remote support. |
| **3** | Remote control | A remote operator controls the process. Local personnel are available to override, intervene, or perform physical work. | Continuous or defined intermittent presence | Local personnel take control, or the local control system reaches a defined safe state. |
| **4** | Unattended remote operation | A remote operator controls or supervises the process without relying on personnel at the equipment. | None required during the defined operating mode | The local control system reaches and maintains a defined safe state without the remote link or a field action. |

## Classification rules

Assign the lowest level that describes the complete operating mode.

1. Classify the function in use, not the maximum technical capability.
2. Identify who has control authority during normal operation.
3. Identify whether field personnel must monitor, approve, override, or intervene.
4. Define what happens when communications, remote supervision, power, or a critical sensor fails.
5. Do not credit a remote connection as a safety protection layer. Safety functions must remain local and automatic.
6. Classify each materially different mode separately.

If a requirement for a higher level is missing, use the lower level. A remote desktop connection alone does not establish remote control. A dashboard alone does not establish remote support.

## Automation is a separate property

Remote operation and automation are related but different. Remote describes where the responsible human works and how authority crosses distance. Automation describes which tasks the system performs without continuous human input.

A highly automated system can operate locally at Level 0. A manually controlled system can operate remotely at Level 3 or Level 4. Record automation separately instead of treating it as the highest remote level.

## Minimum classification record

```text
System or function:
Operating mode:
Remote level: [0-4]
Remote role:
Field role:
Control authority:
Field presence:
Communications path:
Safe state:
Loss-of-link response:
Evidence:
Limitations:
```

## Relationship to existing guidance

This standard adapts the clarity of established automation taxonomies without copying their domain-specific levels.

- [SAE J3016](https://saemobilus.sae.org/standards/j3016_202104-taxonomy-definitions-terms-related-driving-automation-systems-road-motor-vehicles) classifies driving automation by the sustained driving task and fallback responsibility. It does not classify industrial remote operation.
- [IMO autonomous shipping guidance](https://www.imo.org/en/mediacentre/hottopics/pages/autonomous-shipping.aspx) distinguishes onboard control, remote control with personnel onboard, remote control without personnel onboard, and full autonomy. Its scope is ships.
- [IOGP Report 627](https://www.iogp.org/bookstore/product/iogp-report-627-selection-of-system-and-security-architectures-for-remote-control-engineering-maintenance-and-monitoring/) defines remote monitoring, control, engineering, and maintenance for industrial control systems. It provides architectures and security guidance, but not one cross-industry maturity scale.
- IEC 62443 provides security requirements for industrial automation and control systems. Its architectural levels are network zones, not remote-operation levels.
- IEC 61511 and related functional-safety standards govern safety instrumented systems. A remote level does not replace a safety lifecycle or risk assessment.

The gap is a compact, location-neutral classification that separates monitoring, support, remote control, and unattended operation while naming control authority, field presence, and fallback behavior.

## Origin

The model generalizes operating experience from FourPhase remote monitoring and remote operation of industrial well-service equipment. It replaces an earlier four-level internal model by separating read-only monitoring and remote support from remote control.

## Agent skill

This repository is also a portable [Agent Skill](https://agentskills.io). Copy or clone the repository into the skills directory used by an Agent Skills-compatible client. Keep the directory name `oktoeight-remote-levels-standard` so it matches the skill name in `SKILL.md`.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) to propose a change.

## License

This work is available under the terms in [LICENSE](LICENSE).
