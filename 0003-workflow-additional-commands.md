# Description of commands for setting up and executing workflows in RRIV

* Status: proposed
* Deciders: Zaven Arra, Jake Hosen, Ken Chong
* Date: 2022-05-02

Technical Story: {description | ticket/issue URL} <!-- optional -->

## Context and Problem Statement

RRIV is a system for logging data from environmental sensors. To facilitate rapid calibration and deployment of many sensors, a workflow system has been developed. These workflows need additional commands that can be used to facilitate options and commenting of workflows.

## Decision Drivers

* Users need a way to run reptitive workflows in a consistent manner.
* Workflows will vary depending on application, requiring the need to have customizable workflows and commands that allow for workflows to be modified with optional variables.

## Considered Options

* echo: This displays information to the terminal to provide information for the users about setup and prompt user input.
* input-float $[*var name*]: This command allows the user to insert variables into the workflow that may be needed to customize the setup for a given deployment.
* confirmation: A command that prompts the user to respond before proceeding.
* cli-version: This displays the version of the command line interface (CLI) installed on the computer. The workflow to be used is named as a command option.
* # (comment): The pound symbol ("#") is used to identify lines that are not to be executed.

## Decision Outcome

This system is being developed to address the need for replicable setup processes

### Positive Consequences

* There is a system for 
* Workflows can be easily annotated.

### Negative Consequences
