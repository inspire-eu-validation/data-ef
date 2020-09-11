# Feature references

**Purpose**: Verify that referenced features can be retrieved.

**Prerequisites**

**Test method**

* Verify that any feature reference in an association role is publicly accessible via HTTP, i.e. inspect all relevant properties. If a reference (@xlink:href) has a value that starts with "#", verify that an element with a `gml:id` attribute with the referenced identifier exists in the same document. If the reference starts with "http", verify that a HTTP GET request to the URI retrieves an XML document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following association roles:

* [EnvironmentalMonitoringFacility.involvedIn](#Finv): ef:EnvironmentalMonitoringActivity
* [EnvironmentalMonitoringNetwork.involvedIn](#Ninv): ef:EnvironmentalMonitoringActivity

* [EnvironmentalMonitoringFacility.hasObservation](#Fobs): ef:OM_Observation
* [EnvironmentalMonitoringNetwork.hasObservation](#Nobs): ef:OM_Observation

* [EnvironmentalMonitoringFacility.observingCapability](#FobCap): ef:ObservingCapability
* [EnvironmentalMonitoringNetwork.observingCapability](#NobCap): ef:ObservingCapability
* [EnvironmentalMonitoringProgramme.observingCapability](#PobCap): ef:ObservingCapability

* [EnvironmentalMonitoringFacility.broader](#Fbroader): ef:EnvironmentalMonitoringFacility
* [EnvironmentalMonitoringNetwork.broader](#Nbroader): ef:EnvironmentalMonitoringNetwork
* [EnvironmentalMonitoringProgramme.broader](#Pbroader): ef:EnvironmentalMonitoringProgramme

* [EnvironmentalMonitoringFacility.narrower](#Fnarrower): ef:EnvironmentalMonitoringFacility
* [EnvironmentalMonitoringNetwork.narrower](#Nnarrower): ef:EnvironmentalMonitoringNetwork
* [EnvironmentalMonitoringProgramme.narrower](#Pnarrower): ef:EnvironmentalMonitoringProgramme

* [EnvironmentalMonitoringFacility.supersedes](#Fsupersedes): ef:EnvironmentalMonitoringFacility
* [EnvironmentalMonitoringNetwork.supersedes](#Nsupersedes): ef:EnvironmentalMonitoringNetwork
* [EnvironmentalMonitoringProgramme.supersedes](#Psupersedes): ef:EnvironmentalMonitoringProgramme

* [EnvironmentalMonitoringFacility.supersededBy](#FsupersededBy): ef:EnvironmentalMonitoringFacility
* [EnvironmentalMonitoringNetwork.supersededBy](#NsupersededBy): ef:EnvironmentalMonitoringNetwork
* [EnvironmentalMonitoringProgramme.supersededBy](#PsupersededBy): ef:EnvironmentalMonitoringProgramme

* [EnvironmentalMonitoringActivity.setUpFor](#AsetUpFor): ef:EnvironmentalMonitoringProgramme
* [EnvironmentalMonitoringActivity.uses](#Auses): ef:EnvironmentalMonitoringFacility or ef:EnvironmentalMonitoringNetwork

* [EnvironmentalMonitoringFacility.relatedTo](#FrelatedTo): ef:EnvironmentalMonitoringFacility
* [EnvironmentalMonitoringFacility.belongsTo](#FbelongsTo): ef:EnvironmentalMonitoringNetwork

* [EnvironmentalMonitoringNetwork.contains](#Ncontains): ef:EnvironmentalMonitoringFacility

* [EnvironmentalMonitoringProgramme.triggers](#Ptriggers): ef:EnvironmentalMonitoringActivity

* [ObservingCapability.observedProperty](#OCobservedProperty): GF_PropertyType
* [ObservingCapability.featureOfInterest](#OCfeatureOfInterest): GFI_Feature
* [ObservingCapability.procedure](#OCprocedure): OM_Process

**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)

**Test type**: Automated

**Notes**

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                         |  XPath expression    | Multiplicity    | Voidable
------------------------------------ | ---------------------|-----------------|------------
EnvironmentalMonitoringFacility.involvedIn <a name ="Finv"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:involvedIn/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringNetwork.involvedIn <a name ="Ninv"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:involvedIn/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringFacility.hasObservation <a name ="Fobs"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:hasObservation/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringNetwork.hasObservation <a name ="Nobs"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:hasObservation/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringFacility.observingCapability <a name ="FobCap"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringNetwork.observingCapability <a name ="NobCap"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringProgramme.observingCapability <a name ="PobCap"></a>	| //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:observingCapability/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringFacility.broader <a name ="Fbroader"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:broader/@xlink:href | 0..1 | Yes
EnvironmentalMonitoringNetwork.broader <a name ="Nbroader"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:broader/@xlink:href | 0..1 | Yes
EnvironmentalMonitoringProgramme.broader <a name ="Pbroader"></a>	| //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:broader/@xlink:href | 0..1 | Yes
EnvironmentalMonitoringFacility.narrower <a name ="Fnarrower"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:narrower/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringNetwork.narrower <a name ="Nnarrower"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:narrower/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringProgramme.narrower <a name ="Pnarrower"></a>	| //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:narrower/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringFacility.supersedes <a name ="Fsupersedes"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:supersedes/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringNetwork.supersedes <a name ="Nsupersedes"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:supersedes/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringProgramme.supersedes <a name ="Psupersedes"></a>	| //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:supersedes/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringFacility.supersededBy <a name ="FsupersededBy"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:supersededBy/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringNetwork.supersededBy <a name ="NsupersededBy"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:supersededBy/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringProgramme.supersededBy <a name ="PsupersededBy"></a>	| //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:supersededBy/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringActivity.setUpFor <a name ="AsetUpFor"></a>	| //schema-element(ef:EnvironmentalMonitoringActivity)/ef:setUpFor/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringActivity.uses <a name ="Auses"></a>	| //schema-element(ef:EnvironmentalMonitoringActivity)/ef:uses/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringFacility.relatedTo <a name ="FrelatedTo"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:relatedTo/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringFacility.belongsTo <a name ="FbelongsTo"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:belongsTo/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringNetwork.contains <a name ="Ncontains"></a>	| //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:contains/@xlink:href | 0..\* | Yes
EnvironmentalMonitoringProgramme.triggers <a name ="Ntriggers"></a>	| //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:triggers/@xlink:href | 0..\* | Yes
ObservingCapability.observedProperty <a name ="OCobservedProperty"></a>	| //schema-element(ef:ObservingCapability)/ef:observedProperty/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/ef:ObservingCapability/ef:observedProperty/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/ef:ObservingCapability/ef:observedProperty/@xlink:href  | 1 | No
ObservingCapability.featureOfInterest <a name ="OCfeatureOfInterest"></a>	| //schema-element(ef:ObservingCapability)/ef:featureOfInterest/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/ef:ObservingCapability/ef:featureOfInterest/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/ef:ObservingCapability/ef:featureOfInterest/@xlink:href   | 0..1 | Yes
ObservingCapability.procedure <a name ="OCprocedure"></a>	| //schema-element(ef:ObservingCapability)/ef:procedure/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringFacility)/ef:observingCapability/ef:ObservingCapability/ef:procedure/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:observingCapability/ef:ObservingCapability/ef:procedure/@xlink:href   | 1 | No
