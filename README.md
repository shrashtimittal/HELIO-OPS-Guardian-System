# HELIO-OPS Guardian System (HOGS)

## Overview

HELIO-OPS Guardian System (HOGS) is a Python-based space weather monitoring and satellite risk assessment framework designed to model how solar activity impacts satellite operations. The system integrates concepts from astronomy, aerospace engineering, and software engineering to simulate real-world decision-making used in satellite mission operations.

This project was developed as an educational and research-oriented tool, emphasizing clean system architecture, object-oriented programming (OOP), and interpretable risk modeling rather than raw numerical accuracy.

---

## Motivation

The Sun is an active astrophysical body that frequently emits solar flares, coronal mass ejections (CMEs), and associated magnetic disturbances. These events can degrade satellite electronics, disrupt communication and navigation systems, and force operators to place spacecraft into protective safe modes.

Existing space-weather monitoring systems are often complex, proprietary, or inaccessible for students and early researchers. HELIO-OPS addresses this gap by providing a lightweight, transparent, and extensible model that demonstrates how solar hazards can be translated into operational risk for satellites.

---

## System Architecture

The system follows a modular, layered design inspired by real aerospace software stacks:

### 1. Hazard Modeling Layer

* **SolarEvent** class encapsulates solar phenomena such as flares and CMEs.
* Handles event metadata, severity classification, and serialization.

### 2. Vulnerability Modeling Layer

* **Satellite** class represents orbital assets with attributes such as orbit type, shielding level, and operational state.
* **HardenedSatellite** extends Satellite to model radiation-hardened spacecraft using inheritance and polymorphism.

### 3. Risk Engine

* Computes satellite-specific risk as a function of:

  * Solar event magnitude
  * Orbital exposure (LEO, MEO, GEO)
  * Shielding and hardening factors
* Produces both numerical risk scores and qualitative risk categories.

### 4. Persistence Layer

* JSON-based storage enables saving and restoring system state.
* Object serialization and reconstruction allow repeatable simulations and long-term analysis.

### 5. Application Layer

* Menu-driven console interface for interaction.
* Dashboards for space weather overview and satellite health assessment.

---

## Risk Model

The risk calculation follows a simplified but structurally realistic formulation:

Risk = Event Magnitude × Orbit Exposure × (1 − Shielding)

For hardened satellites, an additional reduction factor is applied:

Adjusted Risk = Base Risk × (1 − Hardening Factor)

Final risk levels are categorized as:

* Low
* Moderate
* High

This abstraction mirrors operational decision logic used in satellite mission control environments.

---

## Software Engineering Principles

HELIO-OPS demonstrates several core software engineering concepts:

* **Encapsulation**: Each class manages its own data and logic.
* **Abstraction**: Risk and severity logic are hidden behind clear interfaces.
* **Inheritance**: Specialized satellite types extend base functionality.
* **Polymorphism**: Risk evaluation adapts automatically based on satellite type.
* **Single Responsibility Principle**: Each function performs one well-defined task.

---

## Features

* Solar event creation and classification
* Satellite registration and fleet management
* Risk assessment for individual or multiple events
* Automatic generation of realistic test scenarios
* Space weather and satellite health dashboards
* Safe mode simulation for operational response
* JSON-based persistence

---

## Use Cases

* Educational demonstrations of space weather effects
* Introductory aerospace systems modeling
* Software architecture examples for scientific applications
* Precursor framework for real-time space weather tools

---

## Future Work

Planned extensions include:

* Integration with real-time NASA / NOAA space weather APIs
* Graphical dashboards and data visualization
* More physically accurate radiation and plasma interaction models
* Web-based or mobile interfaces
* Coupling with orbital propagation and mission simulation tools

---

## Project Status

Current version: **Conceptual / Educational Prototype**

The system prioritizes clarity, extensibility, and architectural correctness over operational deployment.


