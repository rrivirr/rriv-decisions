# Storage of calibration timestamp

* Status: proposed
* Deciders: @jakehosen, @zavenarra, @pleacavee 
* Date: 2022/05/06

Technical Story: {description | ticket/issue URL} <!-- optional -->

## Context and Problem Statement

Calibration timestamp is a very common parameter to save for almost every driver.  Currently we store this in the driver specific configuration.  Should this parameter be stored in the common configuration?

## Decision Drivers <!-- optional -->

* Only place parameters in common configuration if they are truly shared by all drivers
* Do not unduly limit the implementation flexibility of the driver class by constraining the common config

## Considered Options

* Place cal_timestamp in the common config for the SensorDriver class
* Require every driver to store cal_timestamp, if it will be used, in it's specific configuration
* Place cal_timestamp in the common config, but support the concept of alternate common configs

## Decision Outcome


### Positive Consequences <!-- optional -->

* {e.g., improvement of quality attribute satisfaction, follow-up decisions required, …}
* …

### Negative Consequences <!-- optional -->

* {e.g., compromising quality attribute, follow-up decisions required, …}
* …

## Pros and Cons of the Options <!-- optional -->

### {option 1}

{example | description | pointer to more information | …} <!-- optional -->

* Good, because {argument a}
* Good, because {argument b}
* Bad, because {argument c}
* … <!-- numbers of pros and cons can vary -->

### {option 2}

{example | description | pointer to more information | …} <!-- optional -->

* Good, because {argument a}
* Good, because {argument b}
* Bad, because {argument c}
* … <!-- numbers of pros and cons can vary -->

### {option 3}

{example | description | pointer to more information | …} <!-- optional -->

* Good, because {argument a}
* Good, because {argument b}
* Bad, because {argument c}
* … <!-- numbers of pros and cons can vary -->

## Links <!-- optional -->

* {Link type} {Link to ADR} <!-- example: Refined by [ADR-0005](0005-example.md) -->
* … <!-- numbers of links can vary -->
