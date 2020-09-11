# Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following checks are performed for every feature in the dataset.

* Check that if [observation(s)](#observation) are attached to an EnvironmentalMonitoringFacility or an EnvironmentalMonitoringNetwork feature type this shall have an [ObservingCapability](#observingCapability) attached to it. The ObservingCapability shall reference the same [Domain](#Domain), [Phenomenon](#Phenomenon) and [ProcessUsed](#ProcessUsed) as the [observation(s)](#observation). (OCL: hasObservation->notEmpty() implies observingCapability->notEmpty() and hasObservation.OM_Observation.featureOfInterest = observingCapability.featureOfInterest and hasObservation.OM_Observation.observedProperty = observingCapability.observedProperty and hasObservation.OM_Observation.procedure = observingCapability.procedure)

* Check that the [geometry](#geometry) and the [representativePoint](#representativePoint) elements of the EnvironmentalMonitoringFacility feature type are not both empty. (OCL: geometry ->notEmpty() or representativePoint ->notEmpty())


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-EF](./README.md#ref_TG_DS_EF) 5.3.2.1.1 and 5.3.2.1.4

**Test type**: Automated

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression                     |Multiplicity       |Voidable
---------------------------------------------------------- | ------------------------------------- | ------------------|----------
observation <a name ="observation"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:hasObservation/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:hasObservation/@xlink:href| 0..\* | Yes
observingCapability <a name ="observingCapability"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/ef:ObservingCapability <br>  //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/@xlink:href <br>  //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/ef:ObservingCapability | 0..\* | Yes
geometry <a name="geometry"></a> | //schema-element(ef:EnvironmentalMonitoringFacility)/ef:geometry|0..1 |No
representativePoint <a name="representativePoint"></a> | //schema-element(ef:EnvironmentalMonitoringFacility)/ef:representativePoint|0..1 |Yes
Domain <a name ="Domain"></a>	| //schema-element(ef:ObservingCapability)/ef:featureOfInterest/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/ef:ObservingCapability/ef:featureOfInterest/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/ef:ObservingCapability/ef:featureOfInterest/@xlink:href    | 0..1 | Yes
Phenomenon <a name ="Phenomenon"></a>	| //schema-element(ef:ObservingCapability)/ef:observedProperty/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/ef:ObservingCapability/ef:observedProperty/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/ef:ObservingCapability/ef:observedProperty/@xlink:href | 1 | No
ProcessUsed <a name ="ProcessUsed"></a>	| //schema-element(ef:ObservingCapability)/ef:procedure/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/ef:ObservingCapability/ef:procedure/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/ef:ObservingCapability/ef:procedure/@xlink:href | 1 | No
