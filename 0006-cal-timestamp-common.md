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

* Place cal_timestamp in the common config for the SensorDriver class

### Positive Consequences <!-- optional -->

* We want to encourage people to use calibrations and we want them to use timestamps with those so this is a good way to support and standardize this practice.

### Negative Consequences <!-- optional -->

* If it's not used it would take up space that was not needed in the common config and ultimately EPROM.
