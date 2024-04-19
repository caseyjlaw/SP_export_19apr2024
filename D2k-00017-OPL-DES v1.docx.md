DSA-2000 Document No. 00017

Observation Planner Design

Vanessa Moss^1^, Steve Myers^2^, Rick Hobbs^3^

^1^CSIRO, ^2^NRAO, ^3^Caltech

+-----------------------------------------------------------------------+
| +--------------------------------+--------------------------------+   |
| | Version:                       | 1                              |   |
| +--------------------------------+--------------------------------+   |
| | Version date:                  | 8/15/23                        |   |
| +--------------------------------+--------------------------------+   |
| | Original date:                 | 2023-08-15                     |   |
| +--------------------------------+--------------------------------+   |
| | Controlled document:           | No                             |   |
| +--------------------------------+--------------------------------+   |
| | WBS Level 2:                   | OPL--Observation Planner       |   |
| +--------------------------------+--------------------------------+   |
| | Document type:                 | DES--Design Report             |   |
| |                                |                                |   |
| |                                | Design Report                  |   |
| +--------------------------------+--------------------------------+   |
+=======================================================================+
|                                                                       |
+-----------------------------------------------------------------------+

Revision History

  --------------------------------------------------------------------------------
  **Ver.**   **Date**     **Sections   **Reasons / Remarks** **Author(s)**
                          Affected**                         
  ---------- ------------ ------------ --------------------- ---------------------
  1          yyyy-mm-dd   All          Original              

  --------------------------------------------------------------------------------

#   {#section .TOC-Heading}

# Table of Contents {#table-of-contents .TOC-Heading .unnumbered}

[1 Introduction [4](#introduction)](#introduction)

[2 Requirements for scheduling
[4](#requirements-for-scheduling)](#requirements-for-scheduling)

[3 Survey concept [4](#survey-concept)](#survey-concept)

[4 OPL structure and vision
[5](#opl-structure-and-vision)](#opl-structure-and-vision)

[5 Development plan [5](#development-plan)](#development-plan)

[6 Relevant documentation
[6](#relevant-documentation)](#relevant-documentation)

Abstract

This document outlines the high-level design plans for the Observation
Planner (OPL) subsystem, which is intended to form the central hub for
scheduling and management of survey observations using the array. We
cover the overview of the OPL, the expected requirements for this
subsystem and implications for its design, the current survey concept,
an architectural overview of OPL and the development plan, drawing on
relevant information from existing documentation.

# Introduction

The scale and complexity of DSA-2000 requires a unique operational
approach informed by the experience of contemporary survey instruments,
with a strong emphasis on automation and autonomy. Our intent is that
the OPL subsystem will sit at the centre of science operations and be
primarily responsible for the execution of full survey operations, with
suitable input and management where necessary from relevant human
experts. The OPL will have access to all the required contextual
information (e.g., the observational survey pool, environmental data,
hardware data and other system constraints) that will inform its dynamic
decision-making and will generally operate in an autonomous mode during
surveys. We also intend to adopt a collaborative intelligence (CINTEL)
approach in designing the OPL, such that we incorporate via its design
ways in which relevant human experts can interact usefully with the
scheduler.

# Requirements for scheduling

As noted in the concept of operations document, the high-level
requirements of OPL are:

-   **Robust:** able to be trusted with reliably and effectively making
    appropriate scheduling decisions that are comparable to the
    decision-making processes of equivalent human operators

-   **Autonomous**: capable of making decisions without direct human
    input in the majority of cases, unless human oversight or
    collaboration is required (e.g., in the case of safety of the
    system)

-   **Dynamic**: designed to make decisions about what to observe next
    based on its understanding of the current environmental conditions,
    live system constraints, content of the observation pool, required
    sky/field constraints and a series of weightings which determine
    priority

-   **Reactive**: able to react to changing conditions (e.g., weather,
    hardware failure, etc) and change course in an appropriate way at
    all hours of the day to maximize science output and data quality

-   **Deterministic**: given the same initial conditions and system
    status, the scheduler will make the same decision in each case,
    ensuring decisions are explicable and predictable given constraints

-   **Communicative**: notifies relevant people as appropriate as part
    of standard operational workflows or in the case of issues requiring
    human attention or expertise to resolve

-   **Transparent:** via appropriate interfaces, the decisions made by
    the scheduler are logged and able to be understood by human experts,
    who in the ideal case can contribute to improving or adjusting the
    decision-making process of the scheduler as required

To meet these requirements, there are strong interconnections with the
monitoring and control (MNC) and data processing (DAT) subsystems.
Primarily, OPL will need to access relevant information from these
subsystems to make reliable decisions, but it will also broadcast
information about its decisions and status to a centralised platform
that is shared amongst relevant subsystems across the array.

# Survey concept

The DSA-2000 Commensal All-Sky Survey (CASS) comprises 65% of the
observing time on the array, scanning \~75% of the sky (δ\>−30°) 16
times over 5 years. As detailed in the Survey Implementation Plan (SIP),
the survey area will be covered using \~8600 individual pointings spaced
by approximately 2° grouped into tiles containing 20-25 pointings. The
Tiles cover a contiguous area of the sky representing 72-90 deg^2^ that
can be mosaicked together into images spanning 140-170 deg^2^ for
archiving.

For scheduling, in the vast majority of cases the pointings in a tile
will need to be observed nearby in time, ideally contiguously, at least
within a few days. This allows the tile mosaics to represent a distinct
"epoch" in the time domain, and to clear the pointing data off the
intermediate storage after they are combined into the tiles. The other
observation modes (deep fields, pulsars, TOO fields, etc.) would be
interspersed between CASS observations. Flexibility to prioritize fields
for scheduling is important to optimize array use and respond to
weather, RFI, and other conditions.

# OPL structure and vision

To meet the science requirements via the survey concept, the OPL
subsystem will be designed in a way to give it oversight of all the
relevant information needed to make a dynamic scheduling decision. This
collection of information available will include:

-   System information and status of the array

-   Environmental conditions including weather and RFI situation

-   Status of the survey observation pool

-   Constraints associated with different surveys within the observation
    pool

-   Conditions which affect feasibility of scheduling if not met (e.g.,
    solar distance)

-   Weightings which help determine which specific field to select next
    (more subjective)

As noted above, OPL will thus have key dependencies on other providers
of information that it needs in order to make decisions. It will be
important for these information sources to be available as early as
possible during the construction period such that OPL can rapidly occupy
and evolve its core role in the scheduling and commissioning of the
array.

# Development plan

The general development plan for OPL is outlined in the WEP spreadsheet
and summarised below. For OPL to maximise its usefulness and ensure a
firm connection to the reality of array operations, it is intended that
core modules (e.g., a direct scheduling layer over the low-level MNC
interface) will be available for use as soon as possible alongside
construction. The complexity of OPL can then grow over time alongside
the extension of the array. To the greatest extent possible, OPL will be
designed based on experience with existing arrays (e.g., LWA, DSA-110,
ASKAP, etc) and we intend to test its functionality in practice as early
as possible.

**By 30 June 2024**

-   High level components and architecture design for OPL available

-   Impact of science requirements on OPL is clear and finalised

**By 30 June 2025**

-   Early modules and stages of OPL available during early commissioning
    observations with partial array

**By 23rd July 2025**

-   Initial design of OPL architecture complete

**By 27th October 2025**

-   First stage of subsystem engineering complete, with all relevant
    documentation finalised prior to in-depth construction phase of OPL
    software

**By 30th June 2026**

-   Early form of OPL capable of delivering pilot survey test
    observations available for use in limited (not final) form

**By 29th January 2027**

-   First final form of OPL software at completion of development phase

**By 13th May 2027**

-   Final stage of subsystem engineering with relevant documentation
    updated based on development progress and modified where necessary

-   Update of architecture overview based on development progress

**By 31st August 2027**

-   Final form of OPL software prior to construction completion based on
    updates required from earlier verification testing

# Relevant documentation

-   DSA-2000 Concept of Operations, document number D2k-00003-PRJ-MGT.
