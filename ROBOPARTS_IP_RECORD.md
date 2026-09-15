ROBOPARTS — IP RECORD
IP-001 — ROBOPARTS Project

Project Name: ROBOPARTS

Original Development Period: 2025

Date of Documentation: September 15, 2026

Description:
ROBOPARTS is a software and infrastructure project associated with the identification, organization, mapping, and digital representation of physical components used within robotics and machine ecosystems.

The project addresses the problem that the same physical component may be represented differently across manufacturers, distributors, OEMs, bills of materials, enterprise resource planning systems, asset-management systems, service systems, and other operational databases.

The underlying concept is to provide persistent digital identity and relationship infrastructure for physical components as they move through manufacturing, distribution, assembly, installation, operation, service, replacement, refurbishment, and end-of-life processes.

1. CORE IP CONCEPT
Persistent Identity for the Physical Robotics Economy

The robotics economy consists of components, machines, manufacturers, OEMs, integrators, operators, distributors, and service organizations.

Physical components are frequently represented by different identifiers in different systems.

A manufacturer may use a part number.

A distributor may use a SKU.

An OEM may use a BOM reference.

A customer may use an asset number.

A service organization may use a work-order reference.

When the same physical component crosses organizational or system boundaries, its identity may need to be located, translated, mapped, verified, and reconciled.

ROBOPARTS/PITN addresses this information and identity problem by providing a persistent machine-oriented identity layer intended to connect these otherwise fragmented identifiers and records.

The fundamental concept is:

PITN NAMESPACE
      ↓
COMPONENT IDENTITY
      ↓
MANUFACTURER
      ↓
PART / SKU
      ↓
LOT / SERIAL
      ↓
BOM / ASSEMBLY
      ↓
ROBOT / MACHINE
      ↓
INSTALLATION
      ↓
SERVICE
      ↓
LIFECYCLE
2. THE IDENTITY PROBLEM

The system is designed around fundamental questions concerning physical components:

What is it?
Who made it?
Where is it?
What machine is it installed in?
What does it belong to?
What happened to it?
What replaces it?

These questions can require information from multiple enterprise systems, integrations, databases, spreadsheets, manual mappings, and human processes.

Typical enterprise systems may include:

ERP
PLM
MES
QMS
BOM systems
Inventory systems
Asset-management systems
Service systems

The proposed identity layer is intended to provide continuity across these systems rather than replace them.

3. SYSTEM ROLE

ROBOPARTS/PITN is intended to function as an identity layer between existing systems of record.

                    PITN IDENTITY
                          │
           ┌──────────────┼──────────────┐
           ▼              ▼              ▼
          ERP            PLM            MES
           │              │              │
           └──────────────┼──────────────┘
                          ▼
                   COMPONENT ID
                          │
           ┌──────────────┼──────────────┐
           ▼              ▼              ▼
          BOM           MACHINE        SERVICE
           │              │              │
           └──────────────┼──────────────┘
                          ▼
                       LIFECYCLE

The intended architecture provides identity continuity across systems that were not originally designed to share a common physical identity.

4. NAMESPACE INFRASTRUCTURE

PITN.ai has described a portfolio of Web3 TLD namespaces, including .actuator and other robotics-oriented namespaces.

Verification required:
The specific registration status, registration dates, ownership, registry/operator information, and applicable rights associated with each namespace should be independently documented and linked to supporting evidence.

The intended role of these namespaces is to provide dedicated address space for physical-component and machine-related digital identities.

The conceptual structure is:

.actuator
    ↓
Manufacturer
    ↓
Product / Model
    ↓
Part Number
    ↓
Lot / Serial
    ↓
Physical Component
    ↓
Machine
    ↓
Service
    ↓
Lifecycle

The namespace represents the address space.

The component identity represents the digital reference.

The relationship graph provides machine and ecosystem context.

Enterprise systems remain authoritative for the operational data they manage.

5. COMPONENT IDENTITY MODEL

A core identity chain can be represented as:

PITN NAMESPACE
       ↓
BROWSE CATEGORY
       ↓
PHYSICAL MACHINE CATEGORY
       ↓
SYSTEM / ASSEMBLY
       ↓
COMPONENT / PART
       ↓
MANUFACTURER
       ↓
MODEL
       ↓
SKU / PART NUMBER
       ↓
LOT / SERIAL NUMBER
       ↓
BOM POSITION
       ↓
CONFIGURATION
       ↓
TEST / CALIBRATION
       ↓
PROVENANCE
       ↓
SERVICE / LIFECYCLE
       ↓
DIGITAL ASSET ID

The fundamental model is:

NAMESPACE → identifies what category the thing belongs to.

SKU / Part Number → identifies which commercial product it is.

Serial / Lot → identifies which physical unit or batch it is.

Digital Asset ID → identifies the corresponding digital record.

6. EXAMPLE COMPONENT IDENTITY

Example product identifier:

ACT-4721

This can identify a product or commercial model.

Example physical identifier:

SN-100238

This can identify a specific physical component.

A complete identity relationship may therefore be represented as:

.actuator
     ↓
Manufacturer X
     ↓
ACT-4721
     ↓
Lot 8742
     ↓
SN-100238
     ↓
Robot #1008
     ↓
Right Hip
     ↓
Installation
     ↓
Service
     ↓
Replacement

The conceptual change is from asking:

Which database contains this part?

to asking:

What physical component is this, and what is it connected to?

7. EXAMPLE ROBOTICS NAMESPACE MAP

An example 17-namespace machine map has been defined around major robotics component categories.

                         PHYSICAL MACHINE
                                │
       ┌────────────────────────┼────────────────────────┐
       │                        │                        │
       ▼                        ▼                        ▼
   ACTUATORS                 SENSORS                  POWER
       │                        │                        │
   .actuator              .sensingmodule         .batterymodule
   .mechanicalinterface   .torquesensor          .batterycell
   .encoder               .forcesensor           .powerconverter
   .fastener              .safetysensor
       │                        │
       │                        ▼
       │                      VISION
       │                        │
       │                  .visionmodule
       │                  .visionsensor
       │                  .cameramodule
       │
       ▼
   CONTROLLERS
       │
   .controlsystem
   .robotcontroller
       │
       ▼
   GRIPPERS
       │
   .endeffector
       │
       ▼
   PHYSICAL WORK
8. CORE BROWSE CATEGORIES
Category	Associated namespaces
Grippers	.endeffector
Actuators	.actuator, .mechanicalinterface, .encoder, .fastener
Sensors	.sensingmodule, .torquesensor, .forcesensor, .safetysensor
Controllers	.controlsystem, .robotcontroller
Power Systems	.batterymodule, .batterycell, .powerconverter
Vision Modules	.visionmodule, .visionsensor, .cameramodule

These categories should be treated as project concepts/design information unless and until supporting registration, implementation, or publication evidence is attached.

9. ECOSYSTEM PARTICIPANTS

The intended identity infrastructure is applicable to organizations that make, build, sell, operate, service, or manage physical machines and components.

Component Manufacturers

Provide persistent identity for products and serialized components beyond the factory.

Robot and Machine OEMs

Connect components, BOMs, configurations, machines, customers, service events, and lifecycle information.

Robotics and Industrial Integrators

Connect components from multiple manufacturers to machines and assemblies.

Distributors

Connect manufacturer part numbers, distributor SKUs, customer references, and product information.

Robot and Fleet Operators

Identify components installed in specific machines and fleets.

Service Organizations

Identify installed components, service history, and replacement requirements.

Advanced Manufacturing, Automotive, EV, Battery, Aerospace, and Equipment Organizations

Apply persistent physical identity to complex assets with long and distributed lifecycles.

10. ECONOMIC / OPERATIONAL VALUE PROPOSITION

The proposed value is not limited to the namespace itself.

The intended value is the information and relationships connected through persistent identity.

Potential workflows include:

Find → Identify → Map → Verify → Trace → Service → Replace

Potential operational benefits include:

reduced manual reconciliation;
reduced identifier mapping;
faster engineering and procurement discovery;
faster service and replacement;
improved component traceability;
improved warranty administration;
faster recall investigation;
improved visibility into machine configurations;
improved lifecycle management.

The economic value of these workflows should be measured through documented before-and-after operational metrics where available.

11. NETWORK EFFECT

The intended network expands as additional organizations participate.

MANUFACTURERS
      ↓
COMPONENTS
      ↓
DISTRIBUTORS
      ↓
OEMs
      ↓
INTEGRATORS
      ↓
MACHINES
      ↓
OPERATORS
      ↓
SERVICE
      ↓
REPLACEMENT
      ↓
REFURBISHMENT
      ↓
RECYCLING

Each participating organization can contribute additional identities and relationships.

The resulting architecture is intended to function as an identity network connecting physical objects within the robotics economy.

12. STRATEGIC POSITION

The project is based on the proposition that the robotics industry requires persistent identity not only for robots themselves, but also for the components, assemblies, systems, and physical objects that comprise and support those machines.

The intended architecture separates four functions:

Manufacturers provide products.

Enterprise systems provide operational data.

PITN provides persistent identity.

The ecosystem provides relationships and lifecycle context.

Together, these components form an identity fabric for physical machines and their components.

13. POTENTIAL INTELLECTUAL PROPERTY CATEGORIES

The following areas should be evaluated independently for potential intellectual-property significance:

Persistent physical-component identity architecture
Namespace-based component identification
Mapping of manufacturer part numbers to persistent identities
Mapping of distributor SKUs to persistent identities
Mapping of OEM BOM references to component identities
Mapping of customer asset numbers to component identities
Mapping of lot and serial information
Component-to-machine relationships
Component-to-BOM relationships
Installation relationships
Service and lifecycle relationships
Replacement relationships
Cross-system identity reconciliation
Robotics-specific namespace taxonomy
Digital asset identity architecture
Component browse/category architecture
Machine/component relationship graph
Integration architecture with ERP/PLM/MES/service systems
Software implementing these concepts
Documentation, diagrams, interface designs, and other original expressive works

Important: Listing an item here does not mean that it is legally patentable, copyrightable, trademarkable, or otherwise protected. Each item requires separate legal and technical evaluation.

14. EVIDENCE LOG

Evidence should be attached to each significant IP item.

Recommended evidence fields:

Evidence ID:
Source:
Repository / System:
File / URL / Record:
Commit / Version:
Original Date:
Date Retrieved:
Description:
Screenshot / Export:
Related IP Entry:

Examples of evidence sources include:

GitHub repository history
Git commits
Source-code files
Supabase project records
Database migrations
Database schemas
Technical documentation
Architecture diagrams
Original design files
Domain/namespace registration records
Emails or project records documenting development
Demonstrations or prototypes
Product specifications
Historical project files
15. DEVELOPMENT HISTORY

The project originated in or around 2025.

The existing 2025 GitHub repository history should be preserved without rewriting commits.

Historical commits should be reviewed to identify:

original concepts;
first implementation;
significant architecture changes;
new functionality;
namespace-related development;
database development;
integrations;
prototypes;
documentation;
contributors;
dates of creation and modification.

Each significant discovery should receive an individual IP entry and evidence reference.

16. OWNERSHIP AND CONTRIBUTOR RECORD

Project: ROBOPARTS

Original development period: 2025

Known creators/contributors:
[TO BE DOCUMENTED]

Repository owner:
[TO BE DOCUMENTED]

Organizations involved:
[TO BE DOCUMENTED]

Assignment agreements:
[TO BE DOCUMENTED]

Work-for-hire agreements:
[TO BE DOCUMENTED]

Third-party contributions:
[TO BE DOCUMENTED]

Open-source components:
[TO BE DOCUMENTED]

Ownership should be verified from actual agreements, employment/contractor relationships, repository history, and applicable law rather than inferred solely from repository ownership.

17. DIGITAL FOOTPRINT PRESERVATION

The GitHub repository and its historical commit history should be preserved as part of the project's development record.

This document is intended to create an organized record connecting:

Project → Concept → Implementation → Evidence → Date → Contributor → IP Category

New discoveries should be added as separate dated entries rather than overwriting historical information.

18. MASTER IP INDEX
ID	IP / Asset	Category	Evidence	Status
IP-001	ROBOPARTS Project	Project / Architecture	GitHub / Supabase	Documented
IP-002	Persistent component identity concept	Architecture	To be documented	Review
IP-003	Namespace identity architecture	Architecture / Namespace	Registration + project records	Verification required
IP-004	Component identity mapping	Software / Architecture	Code + diagrams	Review
IP-005	Machine/component relationship model	Architecture	Code + diagrams	Review
IP-006	Robotics namespace taxonomy	Architecture / Taxonomy	Project records	Review
IP-007	Digital asset identity model	Architecture	Code + documentation	Review
IP-008	ROBOPARTS software implementation	Software	GitHub	Review
IP-009	ROBOPARTS database architecture	Software / Database	Supabase	Review
IP-010	User interface / browse architecture	Software / Design	GitHub / design files	Review
19. IMPORTANT RECORDKEEPING NOTE

This document is a technical and historical IP inventory.

It is intended to preserve and organize information concerning the ROBOPARTS project and associated technology.

It should not be interpreted as a legal opinion or as proof that any particular concept qualifies for patent, copyright, trademark, trade-secret, or other legal protection.

Where legal rights are important, supporting evidence should be preserved and the relevant assets should be reviewed by qualified intellectual-property counsel.

20. PRIMARY PROJECT STATEMENT

ROBOPARTS/PITN is based on the concept of providing persistent digital identity infrastructure for the physical components of the robotics economy, connecting identifiers, components, machines, organizations, operational systems, and lifecycle events across organizational boundaries.

The intended architecture gives physical components an identity layer capable of remaining connected across systems, machines, transactions, service events, and lifecycles.
