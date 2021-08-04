# Microsoft Windows Defender ATP Status Check Add-on for Splunk

### Download from Splunkbase
TODO


OVERVIEW
--------
The Microsoft Windows Defender Status Check Add-on for Splunk is a Splunk App that allows users to check Defender ATP configuration status check on windows machines. It uses registry to find the configuration status for Defender ATP Configuration on the machine. The Add-on does not contain any dashboard or savedsearches.


* Author - CrossRealms International Inc.
* Version - 1.0.0
* Build - 1
* Creates Index - False
* Compatible with:
   * Splunk Enterprise version: 8.2, 8.1, 8.0, 7.3, 7.2, 7.1
   * OS: Platform Independent
   * Browser: Google Chrome, Mozilla Firefox, Safari



TOPOLOGY AND SETTING UP SPLUNK ENVIRONMENT
------------------------------------------
This app can be set up in two ways: 
  1. Standalone Mode: 
     * Install the `Defender ATP Status Check Add-on`.
  2. Distributed Mode:
     * The Add-on is not required on search head.
     * Install the `Defender ATP Status Check Add-on` on the universal forwarders on Windows.
        * Configure the Add-on on universal forwarder.
     * Install the Add-on on Indexer or Heavy forwarder. (First full Splunk instance after UF in data flow.)
       * Input configuration is not required on Heavy Forwarder and Indexers.


DEPENDENCIES
------------------------------------------------------------
* The Add-on does not have any external dependencies.


INSTALLATION
------------------------------------------------------------
* From the Splunk Web home screen, click the gear icon next to Apps. 
* Click on `Browse more apps`.
* Search for `Defender ATP Status Check Add-on` and click Install. 
* Restart Splunk if you are prompted.


DATA COLLECTION & CONFIGURATION
------------------------------------------------------------
### Enable Data Inputs ###
* Add below stanzas in the `TA-defender-atp-status-check/local/inputs.conf` file and deploy to all required Windows hosts.
```
[powershell://generate_defender_atp_status_logs]
disabled = 0

[monitor://$SPLUNK_HOME\var\log\TA-defender-atp-status-check\DefenderATPStatus.log]
disabled = 0
```



UNINSTALL APP
-------------
To uninstall app, user can follow below steps:
* SSH to the Splunk instance.
* Go to folder apps($SPLUNK_HOME/etc/apps).
* Remove the `TA-defender-atp-status-check` folder from `apps` directory.
* Restart Splunk.


RELEASE NOTES
-------------
Version 1.0.0 (Aug 2021)
* Created Add-on with powershell script and inputs.conf.



OPEN SOURCE COMPONENTS AND LICENSES
------------------------------
* NA


CONTRIBUTORS
------------
* Vatsal Jagani
* Bhavik Bhalodia



SUPPORT
-------
* Contact - CrossRealms International Inc.
  * US: +1-312-2784445
* License Agreement - https://d38o4gzaohghws.cloudfront.net/static/misc/eula.html
* Copyright - Copyright CrossRealms Internationals, 2021
