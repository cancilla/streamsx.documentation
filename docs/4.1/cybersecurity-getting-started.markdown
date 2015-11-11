---
layout: docs
title: Cybersecurity Toolkit - Getting Started
weight: 20
---

# Cybersecurity Toolkit - Getting Started

## Introduction
The Cybersecurity Toolkit provides operators that are capable of analyzing network traffic and detecting suspicious behaviour.

In order to get started with using the Cybersecurity Toolkit, it is ***highly recommended*** that the sample applications be used as a baseline for building cybersecurity applications. In many cases, the analytics require that specific filters and enrichment be performed prior to being analyzed. The sample applications contain the necessary filters and enrichments to allow the analytics to work properly. 

In order to use the cybersecurity toolkit, you must download and install the com.ibm.streamsx.network toolkit, found in the [streamsx.network](https://github.com/IBMStreams/streamsx.network) GitHub repository. The build.xml file contained in each of the sample applications will automatically download the latest release of the com.ibm.streamsx.network toolkit and place it in the same directory as the samples. 


## Download Quick Start Edition VM
See the [Installing Streams Quick Start Edition VM Image](http://ibmstreams.github.io/streamsx.documentation/docs/4.1/qse-install-linux/) for more information.

## Download Docker
See the [Installing Streams Docker VM Image - NEED LINK!!!](NEED_LINK) for more information

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
 
 <pre class="terminal">
 <span class="command">git clone https://github.com/IBMStreams/samples.git</span>
 <span class="command">cd samples/cybersecurity</span>
 <span class="command">ls -l</span>
 <span class="output">DomainProfilingSamples  HostProfilingSamples  PredictiveBlacklistingSamples</span></pre>
 
 2. Navigate to the DomainProfilingSamples directory. The directory contains a build.xml file that will download any necessary dependencies (including the networking toolkit) and compile one of the applications. Run the `ant` command to kick off the build. 
 ~~~~~~
 $ ant 
 ~~~~~~
 
 3. Use the Streams Console to submit the application to the instance. To get the URL for the Streams Console, run the following command:
 
 ~~~~~~
 $ st -d <domain_name> -i <instance_name> geturl
 https://myhost:9222/streams/domain/console
 ~~~~~~
 
 4. Once the Streams Console is open, you should be presented with a screen that looks like the following: 
 
 ***INSERT IMAGE OF STREAMS CONSOLE*** 

 5. At the top of the Streams Console, click the "Submit Job" button. Select the *.sab file found in the 'output/' directory in the sample application. For example, for the DomainProfilingSample application, you would select this file: `/path/to/DomainProfilingSample/output/DomainProfilingBasic_Output/com.ibm.streams.cybersecurity.sample.DomainProfilingBasic.sab`
 
 6. Once the application has been submitted, the Streams Console should display the running application:
 
 ***INSERT IMAGE OF STREAMS CONSOLE WITH APP RUNNING***
 

### Analyze Output
The sample applications will output the results of the analytics to the data directory. There will be two files generated in this directory: 

 - **suspicious.txt** - lists the domains that were classified as suspicious
 - **benign.txt** - lists the domains that were classified as benign

For the DomainProfilingBasic application, only the classified domains are written to the file. However, generally you will want to output additional information, such as the IP addresses of the hosts that accessed these domains. The 'DomainProfilingExtended' sample application demonstrates how to collect a set of the unique IPs that accessed the domain. 


### Importing into Streams Studio
The cybersecurity sample applications can be imported into Streams Studio as SPL Projects. When importanting the cybersecurity samples, you must add the **com.ibm.streamsx.network** toolkit location to Streams Explorer. If you are planning on using the PredictiveBlacklisting samples, you must add the **com.ibm.spss.streams.analytics** toolkit to Streams Explorer as well. 
