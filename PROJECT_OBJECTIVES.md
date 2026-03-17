# Project Objectives

## Overview

Build a closed-loop BCI-controlled OpenMATB system using Lab Streaming Layer (LSL), where a Brain-Computer Interface dynamically adjusts task difficulty based on real-time cognitive workload estimation.

## Components

1. **OpenMATB** (Python) - Runs multi-attribute tasks (sysmon, tracking, comms, resman)
2. **BCI System** (MATLAB/Simulink, g.tec hardware) - Continuously measures user's EEG to estimate workload and attention levels

## Communication Architecture

Two bidirectional LSL streams:

| Direction         | Data                                      | Status           |
|-------------------|-------------------------------------------|------------------|
| OpenMATB -> BCI   | Task events, performance, user inputs     | Already supported via existing `labstreaminglayer` plugin |
| BCI -> OpenMATB   | Workload/attention levels, difficulty commands | Needs to be built |

## Main Engineering Work

- Build the BCI-to-OpenMATB direction: LSL inlet plugin + difficulty mapping
- Enable OpenMATB to receive workload/attention signals and adjust task difficulty in real time

## Purpose

Create an adaptive task environment where cognitive load is regulated by real-time brain signals, keeping users in an optimal performance zone.
