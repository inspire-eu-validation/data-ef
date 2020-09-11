# Code lists

**Purpose**: Verify that code lists extensions can be accessed.

**Prerequisites**

**Test method**

* Verify that any code list extensions are publicly accessible via HTTP, i.e. inspect extensible code list values property elements. If a reference (@xlink:href) has a value that does not start with http://inspire.ec.europa.eu/codelist/, verify that a HTTP GET request to the URI retrieves a document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following empty code lists:

* [MeasurementRegimeValue](#MeasurementRegimeValue) : http://inspire.ec.europa.eu/codelist/MeasurementRegimeValue

* [MediaValue](#MediaValue) :  http://inspire.ec.europa.eu/codelist/MediaValue

* [ProcessTypeValue](#ProcessTypeValue) : http://inspire.ec.europa.eu/codelist/ProcessTypeValue

* [PurposeOfCollectionValue](#PurposeOfCollectionValue) : http://inspire.ec.europa.eu/codelist/PurposeOfCollectionValue

* [ResultAcquisitionSourceValue](#ResultAcquisitionSourceValue) : http://inspire.ec.europa.eu/codelist/ResultAcquisitionSourceValue

* [ResultNatureValue](#ResultNatureValue) : http://inspire.ec.europa.eu/codelist/ResultNatureValue

* [SpecialisedEMFTypeValue](#SpecialisedEMFTypeValue) : http://inspire.ec.europa.eu/codelist/SpecialisedEMFTypeValue

**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)

**Test type**: Automated

**Notes**

Data providers may use the values specified in the INSPIRE Technical Guidance document on Environmental Monitoring Facilities and available in the INSPIRE Registry.

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression      |Multiplicity   |Voidable
---------------------------------------------------------- | -----------------------|---------------|---------------------------------
MeasurementRegimeValue <a name ="MeasurementRegimeValue"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:measurementRegime/@xlink:href | 1 | Yes
MediaValue <a name ="MediaValue"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:mediaMonitored/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:mediaMonitored/@xlink:href  <br> //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:mediaMonitored/@xlink:href | 1..\* | No
ProcessTypeValue <a name ="ProcessTypeValue"></a>	| //schema-element(ef:ObservingCapability)/ef:processType/@xlink:href | 1 | Yes
PurposeOfCollectionValue <a name ="PurposeOfCollectionValue"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:purpose/@xlink:href <br> //schema-element(ef:EnvironmentalMonitoringNetwork)/ef:purpose/@xlink:href  <br> //schema-element(ef:EnvironmentalMonitoringProgramme)/ef:purpose/@xlink:href | 0..\* | Yes
ResultAcquisitionSourceValue <a name ="ResultAcquisitionSourceValue"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:resultAcquisitionSource/@xlink:href | 0..\* | Yes
ResultNatureValue <a name ="ResultNatureValue"></a>	| //schema-element(ef:ObservingCapability)/ef:resultNature/@xlink:href | 1 | Yes
SpecialisedEMFTypeValue <a name ="SpecialisedEMFTypeValue"></a>	| //schema-element(ef:EnvironmentalMonitoringFacility)/ef:specialisedEMFType/@xlink:href | 0..1 | Yes
