# Description of commands for setting up and executing workflows in RRIV

* Status: proposed
* Deciders: Zaven Arra, Jake Hosen, Ken Chong
* Date: 2022-05-02

Technical Story: {description | ticket/issue URL} <!-- optional -->

## Context and Problem Statement

RRIV is a system for logging data from environmental sensors. To facilitate rapid calibration and deployment of many sensors, a workflow system has been developed. These workflows can execute sets of commands to automate repetitive tasks involved in setting up and using a logger before deployment.

## Decision Drivers

* Users need a way to run reptitive workflows in a consistent manner.
* Workflows will vary depending on application, requiring the need to have customizable workflows that can be built.
* Workflows need to be validated to ensure that broken workflows are not submitted to a waterbear logger.

## Considered Options

* list-workflow [*regex match*]: This command will list workflows available on the local computer that are available to be executed. To facilitate selecting workflows from long lists, an option that includes a regex search term can be added.
* run-workflow [name]: This runs a given workflow. The workflow to be used is named as a command option.
* show-workflow [name]: This displays a given workflow. The workflow to be used is named as a command option.
* validate-workflow [name]: This checks that the workflow commands are valid and have correct syntax. The workflow to be used is named as a command option.
* create-workflow [name]: This creates a blank workflow and generates metadata for the workflow (e.g., the cli protocal version with which the workflow is compatible). The workflow to be used is named as a command option.  The blank workflow also contains a comment with a URL pointing to the full CLI command documentation.
* edit-workflow [name]: This loads the named workflow in a VIM environment for text editing.

## Decision Outcome

This system is being developed to address the need for replicable setup processes

### Positive Consequences

* Less time spent setting up devices.
* Reduced potential for human error.

### Negative Consequences

* Workflows must be compatible with the version of the firmware that is installed on the waterbear logger.
* Workflows muts be built manually via text-editing at this point.
