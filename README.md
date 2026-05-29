# Healthcare Threat Modelling: Human-Layer Vulnerabilities

A case study in applying cybersecurity thinking to a real-world healthcare system.

## Overview

This project applies cybersecurity concepts to a healthcare system (NSW “Between the Flags”) to model how human factors, system design, and operational pressures create risk.

The Between the Flags system was selected as it is specifically designed to detect early and late clinical deterioration through structured vital sign monitoring and escalation thresholds, making it well suited to modelling detection and response mechanisms in cybersecurity.

It demonstrates how:

- Threat modelling extends beyond technical systems
- Human behaviour forms part of the attack surface
- Data accuracy and interpretation directly impact outcomes

This work draws on prior clinical experience to map newly learned cybersecurity concepts to a real-world system, and is adapted from a Foundations of Cyber Security (COMP1337) project.

---

## Poster

The full visual model of this analysis can be viewed below

[View Poster (PDF)](poster.pdf)

---

## System Context: Between the Flags (BTF)

The Between the Flags system is used in NSW hospitals to monitor patient vital signs and trigger escalation based on predefined thresholds:

- **Yellow zones** -> early deterioration
- **Red zones** -> urgent deterioration

These act similarly to:

- Detection systems
- Threshold-based alerting
- Escalation mechanisms

---

## Core Security Concepts

### Threat Modelling

- **Asset:** Patient safety and clinical outcomes
- **Adversaries:**
  - Disease / injury
  - Human error under workload and cognitive pressure
- **Risks:**
  - Delayed detection
  - Clinical deterioration
  - Complications and mortality

---

### CIA Triad (Applied)

- **Confidentiality:**  
  Access and visibility of patient data and practitioner actions

- **Integrity:**  
  Accuracy of clinical documentation and recorded observations

- **Availability:**  
  Access to timely, accurate, and usable patient information

---

### Authentication & Data Trust

Clinical documentation systems assume that:

- Recorded observations were actually performed
- Signatures represent completed work

However, this introduces a limitation where:

- Recorded data cannot always be independently verified as accurate or reflective of performed actions

This reflects a real-world **authentication and non-repudiation challenge** in human-driven systems.

---

## Human-Layer Vulnerabilities

This project focuses on **non-malicious insider risk**, including:

- Cognitive biases in decision-making
- Prioritisation under workload pressure
- Over-reliance on protocols or automated systems
- Manual data capture gaps (side channels)
- Reduced situational awareness under cognitive load

---

## Theoretical Failure Scenarios

The following scenarios are **theoretical models used for system-level analysis**:

1. **Missing Side-Channel Information**  
   Critical observations (e.g. respiratory rate) are not reliably captured due to manual dependency

2. **Documentation Integrity Degradation**  
   Recorded data may not fully reflect real observations under operational pressure

3. **Protocol Over-Reliance**  
   Decisions are made based on thresholds without sufficient clinical context

4. **Delayed or Missed Escalation**  
   Deterioration is present but escalation is delayed or not initiated

5. **Failed Compensation Detection**  
   Interdependent physiological signals are not interpreted holistically

---

## Additional Security Concepts Demonstrated

This project integrates multiple foundational cybersecurity concepts into a single applied model:

- Human error and cognitive vulnerabilities
- Side channels (missing or unrecorded information)
- Type 1 vs Type 2 errors (false positives / false negatives)
- Defence in depth (systems, procedures, and documentation)
- Risk modelling (likelihood vs impact)
- Insider risk (non-malicious actors under pressure)

This reflects a holistic application of foundational cybersecurity principles within a real-world system.

---

## Key Insight

Human behaviour is a major source of risk in complex systems.

Failures often emerge from the interaction between:

- People (cognition, bias, workload)
- Processes (protocols and escalation rules)
- Systems (data capture and monitoring design)

rather than from isolated technical weaknesses.

---

## Mitigations (High-Level Controls)

- Reduce reliance on manual data capture where possible
- Improve context-aware decision support systems
- Enhance training in pattern recognition and escalation
- Increase reliability and auditability of critical observations
- Encourage active participation from system users (patients)

---

## Disclaimer

All scenarios are theoretical models designed to analyse system-level behaviour.  
This project does not attribute intent or blame to individuals and recognises real-world constraints such as workload, system complexity, and operational pressures.

---

## Why This Matters

This project demonstrates that:

- Security is not purely technical
- Human cognition is a critical component of system reliability
- Failures emerge from complex interactions between people and systems

This approach is applicable to:

- Healthcare systems
- Financial systems
- Any safety-critical or human-driven environment

> Security in real-world systems is as much about people as it is about technology.
