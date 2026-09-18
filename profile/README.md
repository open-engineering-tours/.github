Open Engineering Tours

Open Engineering Tours is the definitions repository for guided tours through Open Engineering Architecture scenes.

A tour takes a viewer step-by-step through an architectural scenario. Each step can move the viewer to one or more cameras in a Babylon.js scene, allowing the viewer to understand not only what the architecture looks like, but also how it works over time.

Open Engineering Tours turns architectural scenes into guided experiences.

What is an Open Engineering Tour?

An Open Engineering Tour describes a guided journey through an Open Engineering Architecture scene.

A tour consists of an ordered sequence of steps. Each step can reference a camera, architectural element, transition, explanation, or other information that helps the viewer understand the scenario.

For example, an External Account Binding (EAB) tour can guide the viewer through the sequence of the EAB process:

External Account Binding
        │
        ▼
┌──────────────────────────────┐
│ Open Engineering Architecture│
│             Scene            │
└──────────────┬───────────────┘
               │
        ┌──────┴──────┐
        ▼             ▼
    Camera 01      Camera 02
        │             │
        ▼             ▼
   External       Identity
    Account       Provider
        │
        ▼
    Camera 03
        │
        ▼
   Account Binding
        │
        ▼
    Camera 04
        │
        ▼
  Binding Verified

The viewer therefore experiences the architecture as a sequence, rather than as a static diagram.

Separation of Concerns

Open Engineering Tours does not own the architectural scene.

Instead, the Open Engineering ecosystem separates the concerns:

Open Engineering Architecture
            │
            │ provides
            ▼
       Babylon.js Scene
            │
       ┌────┴────┐
       │ Cameras │
       │ Models  │
       │ Elements│
       └────┬────┘
            │
            │ referenced by
            ▼
   Open Engineering Tours
            │
            ▼
       Tour Definition
            │
            ▼
      Guided Experience

Architecture defines the world.

Tours define the journey through that world.

This allows one architectural scene to support multiple tours.

For example:

                         Architecture Scene
                                │
             ┌──────────────────┼──────────────────┐
             │                  │                  │
             ▼                  ▼                  ▼
          EAB Tour       Deployment Tour     Security Tour
             │                  │                  │
             ▼                  ▼                  ▼
          Steps              Steps              Steps
             │                  │                  │
             ▼                  ▼                  ▼
          Cameras            Cameras            Cameras

Definitions

Open Engineering Tours defines concepts such as:

* Tour — a guided journey through an Architecture scene
* Scenario — the architectural situation being explained
* Step — one stage in the journey
* Camera — a viewpoint into the Architecture scene
* Target — an architectural element that a step can focus on
* Transition — movement between viewpoints or states
* Narration — explanatory information associated with a step

The definitions are intended to remain independent of the rendering technology used to execute them.

Babylon.js

The primary visualization experience uses Babylon.js.

Babylon.js provides the runtime environment in which a tour can:

1. Load an Open Engineering Architecture scene.
2. Resolve the cameras referenced by a tour.
3. Position the viewer at the appropriate viewpoint.
4. Focus attention on architectural elements.
5. Move through the ordered tour steps.
6. Present explanatory information.
7. Allow the viewer to move forward and backward through the experience.

The Tour definition itself does not need to contain Babylon.js implementation details.

Example

A conceptual tour definition might look like:

id: external-account-binding
title: External Account Binding
scene: external-account-binding
steps:
  - id: external-account
    title: Identify the external account
    camera: external-account
  - id: identity-provider
    title: Connect to the identity provider
    camera: identity-provider
  - id: account-binding
    title: Establish the account binding
    camera: account-binding
  - id: verify-binding
    title: Verify the binding
    camera: control-plane

The identifiers connect the tour to the corresponding Architecture scene and its cameras.

The implementation can then resolve those identifiers against the actual Babylon.js scene.

Tours as Architectural Storytelling

Architecture diagrams traditionally answer:

What is connected to what?

An interactive Architecture scene can answer:

Where is everything?

A Tour adds another dimension:

What happens, and in what sequence?

This makes Tours particularly useful for explaining:

* authentication flows
* account binding
* provisioning
* deployments
* reconciliation
* infrastructure workflows
* security flows
* data flows
* distributed processes
* operational procedures
* architectural scenarios

Open Engineering Ecosystem

Open Engineering Tours is part of the Open Engineering ecosystem.

Open Engineering
       │
       ├── Architecture
       │      └── Scenes and architectural models
       │
       ├── Models
       │      └── 3D elements and representations
       │
       └── Tours
              └── Guided journeys through Architecture

Tours therefore build upon the architectural vocabulary and models defined elsewhere in Open Engineering.

Design Principle

Open Engineering Tours follows a simple principle:

Define the journey, don’t duplicate the world.

A Tour should reference the Architecture scene rather than recreate it.

This keeps:

* architectural models reusable
* scenes independent from tours
* tours composable
* implementations replaceable
* definitions portable
* visualization experiences consistent

Repository

This repository contains the definitions for Open Engineering Tours.

Implementations may consume these definitions and provide the runtime experience in applications such as the Open Engineering Architecture Babylon.js viewer.

⸻

Open Engineering Tours
Guided journeys through architectural worlds.
