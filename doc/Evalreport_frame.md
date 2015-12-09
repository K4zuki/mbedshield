---
title:  '150 - Prototype evaluation report'
author: 'Kazuki Yamamoto'
date: '$Date: 2015-11-04 16:29:16 +0900 (Wed, 04 Nov 2015) $'
keywords: keywords
identifier: identifier
creator: creator
contributor: contributor
lang: lang
subject: subject
description: description
type: type
format: format
relation: relation
coverage: coverage
rights: rights
...

# Abstract{-}
This document contains detailed evaluation results of the _DEVICE_NAME_,
based on the functionality and the parameters specified in the data sheet.

# Approvals{-}

| Role                            | Signature | Date          |
|:--------------------------------|:----------|:--------------|
| Technical Project Lead          | _Name_    | _DD-Mon-YYYY_ |
| Application Engineering Manager | _Name_    | _DD-Mon-YYYY_ |

<!--
\pagebreak

# Table of Contents{-}
References -> Table of contents -> Automatic Table 1

\pagebreak

# TODO{-}
## first time
- mkdir yourdir
- cd yourdir
- cp Makefile .
- make init

## afterwards
- make all INPUT=yourmarkdown.md

## old way
`pandoc -s .\Evalreport_frame.md --read=markdown+ignore_line_breaks --reference-docx=.\150.docx -o .\OUTPUT.docx;.\OUTPUT.docx`  

## after "made"
- change style of Abstract and Approvals to "Abstract"
- insert table of contents above
- correct header contents;
- correct footer contents - copy 1st page footer and replace 2nd page footer
- correct table font style:

|          Table Head Centre          |
|:-----------------------------------:|
|           set All borders           |
|          Table Body Centre          |
| Merge table row/column if necessary |
|    AutoFit -> AutoFit to window     |

- remove this section

\pagebreak
-->

# General
## Summary

Describe the overall results of the evaluation.

## Hardware and Device information

Specify the device(s) that were used for the evaluation.

Table: **Device(s) under test**

|    Parameter     |    Device #1     |    Device #2     |    Device #3     |
|:----------------:|:----------------:|:----------------:|:----------------:|
|    **Corner**    |        TT        |        TT        |        TT        |
|     **FAB**      |        12        |        12        |        12        |
|   **Marking**    |     1508PHAQ     |     1508PHAQ     |     1508PHAQ     |
|     **Mask**     |        AA        |        AA        |        AA        |
|     **Trim**     |  dev23TT_PS.txt  |  dev24TT_PS.txt  |  dev25TT_PS.txt  |
|  **Board Type**  | Evaluation Board | Evaluation Board | Evaluation Board |
|  **Board Code**  |     240-01-A     |     240-01-A     |     240-01-A     |
| **Board Number** |       0002       |       0002       |       0002       |

-   _Package type_
-   _Batch number_
-   _Date code_

## Software

- Python 2.6

## References

List documents that are relevant for the evaluation of the device or
design block(s).

1. _TYPENUMBER_, Data sheet, Dialog Semiconductor
1.  _DXXXX_ Objective Specification (110), version _M.m_,
    _DD-Mon-YYYY_
1.  <span id="_Ref352937158" class="anchor"></span>_DXXXX_
    Application Engineering Plan (155), version _M.m_,
    _DD-Mon-YYYY_
1.  _DXXXX_ Design For Test specification (112), version
    _M.m_, _DD-Mon-YYYY_
1.  _Author_, _Title_, _Publication_,
    _Publisher_, _YYYY_

## Equipment

List any non-standard or uncalibrated measuring instruments used for the
evaluation.

-   Equipment used: see Ref. \[3\]
-   _Special equipment reference_

\pagebreak

# Standard tests
## Introduction

Optional introductory information about the measured parameter(s) and
the measurement conditions.

|             ![][1]             |
|:------------------------------:|
| **Test setup: standard tests** |

[1]: .\temp_image.png

## Continuity

Specify the method used for testing the continuity of all pins.

  Purpose: Check the continuity of each pin

  Details:

In the standard continuity test all pins including power, not connected
and not used pins are set to 0 V. All pins excluding power pins or
special (\*) pins are tested one by one by the following method.

-   The tested pins are sunk with a current between 100 µA and 500 µA
    (sink value depends on external hardware).
-   At the same time the voltage level is compared against limits
    between -0.200 V and -1.500 V. This can be done:
  -   Static: The absolute measured value is compared against the limits.
  -   Dynamic: The functional pass band lies between the limits, using the
    midband qualifier in the pattern file.

(\*) Special pins are pins which are not directly connected to a tester
channel, in case of special test hardware requirements or pins which are
not fitted with a protection diode.

## Supply currents

Specify how to measure the static current and operating current per
power supply domain for all operating modes of the device, including the
active blocks/functions for each mode.

| Mode        | Power supply domain | Blocks |
|:------------|:--------------------|:-------|
| **Digital** |                     |        |
|             |                     |        |
|             |                     |        |
| **Analog**  |                     |        |
|             |                     |        |
|             |                     |        |

Table: **Power supply overview**

_Insert text here_

\pagebreak

# Digital tests

Insert a copy of the standard text in section 9 for each test. Remove
unused sections.

## Introduction

Optional introductory information about the measured parameter(s) and
the measurement conditions.

_Insert text here_

_Insert optional graphic here_

| **Test setup: digital tests** |
|:-----------------------------:|
|      ![](temp_image.png)      |

## Digital I/O pads

## Digital block _X_

## Flash memory

## OTP memory

\pagebreak

# Analog tests

Insert a copy of the standard text in section 9 for each test. Remove
unused sections.

## Introduction

Optional introductory information about the measured parameter(s) and
the measurement conditions.

_Insert text here_

_Insert optional graphic here_

| ![](temp_image.png) |
|:-------------------:|
|                     |

| 1 |
|:--|
| 2 |

Table: **Analog tests**

## Analog supply currents

## Analog block _X_

\pagebreak

# _Block/Function_ evaluation

## Functional evaluation

Purpose of evaluation:
-   Prove functionality (does it work?)
-   Verify simulation results (over temperature, supply voltage,
    frequency, etc.)
-   Explore and optimise settings (analog and RF): input for
    characterisation and application development

Table: **Functional evaluation results of *Block/Function***

| Tested Block/Function | Prio    | Test Description | Result | Date          |
|:----------------------|:--------|:-----------------|:-------|:--------------|
| _Block/Function_      | _L/M/H_ | _Description_    | _P/F_  | _DD-Mon-YYYY_ |

_Insert text here_

| Type | Test Symbol | Specification | Description | N<sub>SMP</sub> | Done |
|:-----|:------------|:--------------|:------------|:----------------|:-----|
|      |             |               |             |                 |      |

Table: **Evaluation tests**

_Insert text here_

## Electrical evaluation

Table: **Electrical evaluation results of _Block/Function_**

| Symbol | N~SMP~ | Comment | Simulation | <   | <   | Evaluation | <   | <   | Unit |
|:-------|:-------|:--------|:-----------|:----|:----|:-----------|:----|:----|:-----|
|        |        |         | Min        | Avg | Max | Min        | Avg | Max |      |
|        |        |         |            |     |     |            |     |     |      |

_Insert text here_

Summarise the changes made to the document that are relevant to the
reader. Optionally show change details for the latest revision in a
separate table row.

\pagebreak

# Revision History{-}
Style = Heading Unnumbered

| Revision | Date          | Who  | Description                                      |
|:---------|:--------------|:-----|:-------------------------------------------------|
| 0.1      | _DD-Mon-YYYY_ | _NN_ | Initial version.                                 |
| _M.m_    | _DD-Mon-YYYY_ | _NN_ | _Latest revision. Summary of important changes._ |

<!--

| SVN             |
|:----------------|
| $Revision: 29 $ |
|                 |

-->
