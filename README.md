# Healthcare Threat Modelling: Human-Layer Vulnerabilities

A case study in applying cybersecurity thinking to a real-world healthcare system.

## Overview

This project applies cybersecurity principles to a socio-technical healthcare system (NSW Between the Flags) to model how human factors, system design, and operational pressures create risk.

The Between the Flags (BTF) system is designed to detect clinical deterioration using structured vital sign monitoring and escalation thresholds. This makes it well-suited to modelling:

- Detection systems
- Threshold-based alerting
- Escalation and response mechanisms

This work reframes healthcare safety through a cybersecurity lens, demonstrating that:

- Threat modelling extends beyond technical systems
- Human behaviour is part of the attack surface
- Data integrity and interpretation directly influence outcomes

This work is informed by prior clinical experience, grounding the analysis in real-world system behaviour alongside theoretical modelling. It originated from a COMP1337 Foundations of Cyber Security assessment (poster component) and was extended to explore real-world system behaviour in greater depth.

---

## Poster

The full visual model of this analysis is available below:

[View Poster (PDF)](poster.pdf)

---

## System Context: Between the Flags (BTF)

The Between the Flags system is used in NSW hospitals to monitor patient vital signs and trigger escalation based on predefined thresholds:

- **Yellow zones** -> early deterioration
- **Red zones** -> urgent deterioration

These functions are analogous to:

- Intrusion detection systems
- Threshold-based alerting mechanisms
- Incident escalation workflows

---

## Threat Modelling

### Assets

- Patient physiological stability
- Clinical decision accuracy
- Timely escalation and intervention
- Integrity of clinical documentation

---

### Adversaries

- Primary: Biological processes (disease, injury)
- Secondary: Human operators under cognitive and workload constraints
- Contributing: System design limitations

This system defends against **stochastic, time-evolving adversarial processes** rather than intelligent attackers. Unlike traditional cybersecurity systems, the “adversary” here is non-intentional, meaning system resilience depends on managing uncertainty, variability, and human limitations rather than preventing deliberate exploitation.

---

### Attack Surface

- Manual vital sign measurement and entry
- Documentation workflows
- Threshold-based decision systems
- Clinical handover and communication pathways

---

### Trust Boundaries

- Observation -> Documentation
- Documentation -> Interpretation
- Interpretation -> Escalation

---

### Failure Modes

- Data integrity degradation (inaccurate observations)
- Signal loss (missing or unrecorded data)
- Misclassification (false negatives / false positives)
- Delayed or missed escalation
- Incomplete situational awareness

Failures commonly occur at these boundaries due to **loss of fidelity or misinterpretation**.

---

## Core Security Concepts

### CIA Triad (Applied)

- **Confidentiality:**  
  Controlled access to patient data and clinical actions

- **Integrity:**  
  Accuracy and reliability of recorded observations

- **Availability:**  
  Timely access to usable, relevant clinical information

---

### Authentication & Data Trust

Clinical documentation systems assume that:

- Observations were performed as recorded
- Signatures represent completed actions

However:

- Observations are not always independently verifiable
- Recorded values may not fully reflect real conditions

This represents a **real-world authentication and non-repudiation limitation** in human-driven systems.

---

### Preventative Controls

- Standardised observation protocols
- Structured documentation systems

---

### Detective Controls

- Yellow/Red zone thresholds
- Pattern-based identification of deterioration

---

### Responsive Controls

- Escalation protocols
- Rapid response teams

---

### Human-Layer Vulnerabilities

This project focuses on **non-malicious insider risk**, including:

- Cognitive bias under uncertainty
- Prioritisation under workload pressure
- Over-reliance on protocols or automated systems
- Reduced situational awareness under cognitive load
- Manual data capture gaps (side channels)

---

## Theoretical Failure Scenarios

The following scenarios are **theoretical models used for system-level analysis**:

1. **Missing Side-Channel Information**
2. **Documentation Integrity Degradation**
3. **Protocol Over-Reliance**
4. **Delayed or Missed Escalation**
5. **Failed Compensation Detection**

---

## Failure Chain Example (Attack Path Analogy)

- Respiratory rate not measured (side-channel loss)
- Observation recorded as normal (integrity failure)
- No Yellow Zone trigger (detection failure)
- No escalation initiated (response failure)
- Condition deteriorates unnoticed
- Late intervention required (high-impact outcome)

This parallels a **cybersecurity attack chain**, where small, individually non-critical failures compound into a high-impact outcome.

---

## Risk Framing

Risk emerges from the interaction between likelihood and impact.

Likelihood increases under:

- High patient-to-staff ratios
- Frequent interruptions
- Time pressure and workload
- Handover transitions

Impact includes:

- Delayed detection significantly increases risk of complications and mortality

---

## Additional Security Concepts Demonstrated

- Side channels (missing or unrecorded signals)
- Type 1 vs Type 2 errors (false positives / false negatives)
- Defence in depth (systems + processes + human judgement + education + culture)
- Insider risk (non-malicious actors under pressure)
- Socio-technical system failures

---

## Mitigations (Security-Framed Controls)

**Reduce side-channel loss:**

- Automate high-risk data capture where possible

Improve detection quality:

- Context-aware decision support systems

**Mitigate cognitive failure**:

- Training in pattern recognition and escalation triggers

**Increase data integrity**:

- Verifiable logging and auditability of observations

**Add redundancy**:

- Incorporate patient-reported signals as external validation

---

## Key Insight

Failures in complex systems emerge from interactions between:

- People (cognition, bias, workload)
- Processes (protocols and escalation rules)
- Systems (data capture and monitoring design)

Rather than from isolated technical weaknesses.

---

## Why This Matters

This project demonstrates that:

- Security is not purely technical
- Human cognition is a critical system dependency
- Risk emerges from socio-technical interactions

These principles apply broadly to:

- Healthcare systems
- Financial systems
- Critical infrastructure
- Any human-driven, high-reliability environment

---

## Limitations

- This model is conceptual and not based on formally collected hospital datasets
- It is informed by prior clinical experience rather than controlled study conditions
- Assumes typical operational environments rather than rare or extreme scenarios
- Does not model organisational or policy-level constraints in detail

Despite these limitations, the model reflects practical clinical realities and observed system behaviours, providing a structured way to analyse how human factors and system design interact to produce risk.

---

## Disclaimer

All scenarios are theoretical system-level models.
This project does not attribute fault to individuals and recognises real-world constraints including workload, system limitations, and operational complexity.

> Security in real-world systems is as much about people as it is about technology.
