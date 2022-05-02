# Reimplementation of debug system for CLI version

* Status: proposed
* Deciders: ZavenA, JakeH, KenC
* Date: 2022-05-02

## Context and Problem Statement
The debug system has been out of commission since implementing the command structure / RRIV CLI. We have now discussed the issue and how we would improve our old debug system which was essentially on or off, with optionally writing debug messages to the generated .csv on MicroSD card.

## Decision Drivers

* Need a debug system for current and future development
* Would like an improved system with more options of customizability and utility
* Improve debugging options for users who are using RRIV to develop novel sensor systems

## Overview

* feature: debug levels [trace, debug, info, warn, error]
* feature: tags
* decision: tag implementation
* implementation: in each .cpp #define TAG "tag decision"
* command: debug-level {debug level} {TAG/regex}
* command: persist-log-level [boolean]
* command: debug-to-file [boolean]
* command: clear-log-level
* command: list-log-level
* feature: cli client can clean debug messages
* feature: support multiple concurrent regex tag filters during debugging
* feature: colorize messages per level

## Description and Reasoning

* Debug levels: multiple levels indicating severity of output message, to add customizability to user view, as opposed to displaying every single debug message
* Tags: module specific debug messages, to allow customizability to users working on specific modules
* Tag implementation: need to decide a file naming convention for tags, but they should exist as #define in each .cpp, ideally we can use a regex to scan and then also use that as flexibility for displaying messages
* debug-level {debug level} {TAG/regex}: a command that takes a tier of debug level, and a TAG/regex and toggles whether they are active or not to determine precisely which debug messages are outputted
* persist-log-level: command to toggle a boolean that controls whether the log level should be retained between different modes (ie, interactive to deployment)
* debug-to-file: command to toggle a boolean that controls whether debug messages are written to output file or only to serial
* clear-log-level: command to clear any debug flags (including level, and tags)
* list-log-level: command to list which debug flags are currently active
* Cli client can clean debug messages, by splitting the raw file into debug messages only and raw data, while retaining the original file, this would facilitate the ease of processing data, and locating specific debug messages
* Support multiple tags: allow for multiple debug levels and tags to be active at once for additional flexibility
* Colorize messages per level: to allow for more visibility in serial output [note that this would not be reflected in .csv output]

### Positive Consequences

* Not only allow for debugging again, but extreme control over feedback necessary for development

### Negative Consequences

* Implementation will take additional memory which we are currently short on
* Implementation will need documentation for consequent users to take full advantage of
* Will consume more power to run
* Will need to make a decision on TAG/module naming conventions to take advantage of regex
