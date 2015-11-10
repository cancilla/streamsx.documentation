# Cybersecurity Toolkit - Getting Started

## Introduction
The Cybersecurity Toolkit provides operators that are capable of analyzing network traffic and detecting suspicious behaviour.

In order to get started with using the Cybersecurity Toolkit, it is ***highly recommended*** that the sample applications be used as a baseline for building cybersecurity applications. In many cases, the analytics require that specific filters and enrichment be performed prior to being analyzed. The sample applications contain the necessary filters and enrichments to allow the analytics to work properly. 

In order to use the cybersecurity toolkit, you must download and install the com.ibm.streamsx.network toolkit, found in the [streamsx.network|https://github.com/IBMStreams/streamsx.network] GitHub repository. The build.xml file contained in each of the sample applications will automatically download the latest release of the com.ibm.streamsx.network toolkit and place it in the same directory as the samples. 


## Download Quick Start Edition VM
See the [Installing Streams Quick Start Edition VM Image|http://ibmstreams.github.io/streamsx.documentation/docs/4.1/qse-install-linux/] for more information.

## Download Docker
See the [Installing Streams Docker VM Image|NEED_LINK] for more information

## Install Dependencies - VM
TBD

## Install Dependencies - Docker
TBD

## Install SPSS (Optional)
TBD

## Sample Applications
The cybersecurity toolkit sample applications should be used as a baseline for building cybersecurity applications on Streams. The samples contain the necessary filter and enrichment operators that allow the analytics to work properly. 

By default, the sample applications will use the PacketFileSource operator (found in the com.ibm.streamsx.network toolkit) to read sample PCAP files packaged with the toolkit. However, this operator can easily be replaced with the PacketLiveSource operator, which allows for ingesting and parsing live data. 

The three introductory sample projects are: 
 - DomainProfilingSample
 - HostProfilingSample
 - PredictiveBlacklistingSample

### Download/Build/Run
The following steps can be taken to download, compile and run the cybersecurity samples:

 1. From the command-line, clone the samples github repository and navigate to the 'cybersecurity' directory. Here you will find directories containing the sample applications:
 
 ```
 $> git clone https://github.com/IBMStreams/samples.git
 $> cd samples/cybersecurity
 $> ls -l
 DomainProfilingSamples  HostProfilingSamples  PredictiveBlacklistingSamples
 ```
 
 2. Navigate to the DomainProfilingSamples directory. The directory contains a build.xml file that will index the toolkit and download any necessary dependencies. Simply run `ant` to start the build.

```
$> ant 
```
 
 3. 
 
 

The samples can be downloaded from the cybersecurity folder in the samples GitHub repository: [https://github.com/IBMStreams/samples/tree/master/cybersecurity].







### Build

### Run

### Analyze Output

