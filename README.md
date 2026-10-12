# SBTDF204_CaseStudy3_Memory_Forensics
Digital forensics investigation of a Windows memory image using Volatility 2.6.1, focusing on process analysis, command history, USB storage artefacts, network evidence, and suspected file transfer.
# SBT-DF204 Case Study 3: Investigating Suspected Illegal File Transfer From Memory Evidence

## Overview

This project documents a memory forensics investigation conducted as part of the SBT-DF204 Computer Forensics Case Studies course.

The investigation examined a Windows memory image to identify evidence of user activity, command execution, network artefacts, removable USB storage, and a suspected file transfer.

## Objectives

- Analyse Windows memory using Volatility Framework 2.6.1.
- Identify relevant processes and command history.
- Examine network and USB storage artefacts.
- Correlate registry records with drive-letter mappings and user-profile activity.
- Develop a UTC timeline and document findings, limitations, and conclusions.

## Tools Used

- Kali Linux
- Volatility Framework 2.6.1
- Linux command-line utilities
- Windows registry artefact analysis

## Investigation Findings

The recovered console history contained the command:

`copy secret_file.docx F:`

The console output also showed:

`1 file(s) copied.`

Registry artefacts associated drive letter `F:` with a removable device identified as General UDisk USB Device. Additional MountPoints2 and ShellBags artefacts provided context for the drive and folder paths.

The available network evidence did not establish a successful network file transfer.

The findings support a reported local copy operation to removable storage. However, the investigation did not independently verify the destination file's contents, establish the exact time of the copy command, or determine authorisation, intent, or the identity of the operator.

## Evidence Integrity

The original memory image, evidence copy, and working copy were verified using SHA-256 hashing. The recorded hashes matched.

The original memory image is not included in this repository.

## Repository Contents

- `README.md` — Project overview, objectives, tools, and summary of findings.
- `SBTDF204_CaseStudy3_2025-FWSD-11486.pdf` — Completed forensic investigation report with labelled screenshots, timeline, and evidence log.


## Limitations

The findings are limited to the artefacts recovered from the supplied memory image. Registry and ShellBags records do not independently prove file transfer, and the recovered console output does not establish the real-world identity or intent of the operator.

## Academic Use

This project was completed for educational purposes as part of digital forensics training. The findings are based on the available forensic evidence and are not a determination of criminal responsibility.
