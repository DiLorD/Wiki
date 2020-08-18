# Android Agent Documentation

## Operating principe

**OCS Inventory NG Agent for Android can run as a service** automatically at boot
time. **It can also work as a stand alone application** launched manually.

## Which version: Service or Standalone ?

The Windows service version will automatically communicate with the OCS-NG
system and perform inventories based on parameters set on the server
(Inventory Frequency). The standalone client is used for computers that
cannot communicate with the server, or where the service version is not
wanted or allowed.

When an inventory is done, agent uses and writes in files stored in directory
"SDCARD/ocs". This directory is **/mnt/sdcard/ocs**.

## Prerequisites

Have a device under Android 4.0 or higher.

## Installation of Android Agent

2 solutions to install Android agent.

[From OCS repository on Github](https://github.com/OCSInventory-NG/AndroidAgent/releases)
: Download and decompress the lastestversion of Android Agent from download page of our website.

Place this file on SDCARD and launch it.

* From PlayStore : Download application and launch installation.

![Download of android agent](../../img/agent/android/android_agent_download.png)

At the end of installation, icon is created on desktop, and a message prevents your application was installed
correctly. Click on **Open** to quit the playstore and launch application.

![Windows agent installed](../../img/agent/android/android_agent_install_down.png)

**`Note: On android v6.0 and more when you launch the app you can authorize the application to access to the different information and data on your device`**

![Authorize appli to acces ](../../img/agent/android/android_agent_acces_1.png)
![Authorize appli to acces ](../../img/agent/android/android_agent_acces_2.png)
![Authorize appli to acces ](../../img/agent/android/android_agent_acces_3.png)

Now you see the main screen of the application, which allows you to:

* send an inventory (you will have to fix the configuration before)
* display inventory (section by section)
* store inventory on your SDCARD (/mnt/sdcard/ocs/inventory.xml)
* edit the configuration, using configuration standard menu of Android

![Homescreen of android agent](../../img/agent/android/android_agent_homepage.png)

## Configuration of Agent

By clicking on configuration standard button of Android (different depending on the device),
4 menus are available:

* **Configuration** : Access to agent configuration
* **About : About OCS** Inventory NG agent installed
* **Import configuration** : Import a configuration file if present in directory ocs
* **Export configuration** : Export the configuration to backup or using on others devices

![Options of android agent](../../img/agent/android/android_agent_homepage_settings.png)

### **General Configuration of agent**

![General configuration of android agent](../../img/agent/android/android_agent_config_1.png)

* **TAG** : Cathegory TAG in OCS
* **DEBUG** : possible to generate a trace file in the **ocslog.txt** agent directory
* **AUTOMATIC** : define if agent works as a service or a standalone application
* **DEPENDING ON NETWORK STATUS** : Define using mobile internet connection or Wifi
* **INVENTORY FREQUENCY** : define frequency between 2 inventories (in hours)
* **WAKE FREQUENCY** : define time between 2 verifications of time since last inventory
* **CACHE** : possible to recordd inventory cache on device
* **CACHE LIFETIME** : define cache timelife (in minutes)
* **SYSTEM SOFTWARE** : Exclude or include software like clock
* **USERAGENT COMPATIBILITY** : Active this option for old OCS Inventory Server under 2.X
* **HIDE NOTIFICATION** : Show off or on the notification from OCS android agent
### **Configuration concerning server**

![Server's configuration of android agent](../../img/agent/android/android_agent_config_2.png)

* **SERVER URL** : define URL address of OCS Inventory NG server(By default:
``http://ocsinventory-ng/ocsinventory``).

    **`Note: If your OCS Inventory NG server listens on an other port than classic port, you have to define it in serveur URL.
    Example : ``https://ocsinventory-ng:443/ocsinventory`` **

* **SSL CONTROL** : possible to active and desactive SSL control.
* **BASIC AUTHENTIFICATION** : define if server needs authentification. If yes, you have to define
**Login** and **Password**.
* **HTTP PROXY** : define if agent use a proxy. If yes, you have to define **Address** and
**port** of proxy server.

**`Warning: To work with SSL control, you have to import CA in Android. To do this, use menu Localisation
and security/Import certificate from SDCARD. Certificates MUST BE in the root of SDCARD. Extensions .crt and .cer are detected. Extension
.pem isn't always.`**

## Feature of import/export configuration

This feature allows to export agent configuration when defined, to import in other devices.
**org.ocsinventory.android.agent_preferences.xml** file containing configuration parameters to
import/export is stored in directory "ocs".

**`Note: To import/export configuration, the device (phone/tablet) should not be connected
via USB to a computer.`**

It's possible to edit the file manually as you want.

    <?xml version='1.0' encoding='utf-8' standalone='yes' ?>
    <map>
    <boolean name="k_strictssl" value="false" />
    <boolean name="k_debug" value="false" />
    <string name="k_freqmaj">24</string>
    <long name="k_lastupdt" value="1361266849907" />
    <boolean name="k_automode" value="true" />
    <boolean name="k_cache" value="true" />
    <string name="k_devicetag">SONY ERICSSON</string>
    <string name="k_cachelen">900000</string>
    <string name="k_freqwake">30</string>
    <string name="k_serverurl">https://ocsinventory-ng/ocsinventory</string>
    </map>
