## Samsung ARTIK cloud

#### ARTIK Cloud Overview

![ARTIK Cloud Architecture](http://www.simband.io/documentation/images/docs/simband/simband-documentation/sami-architecture.jpg)
ARTIK Cloud Architecture

* An open and interoperable data exchange platform for the IoT
* Provides data analytics and data visualization capabilities
* Enables ARTIK based devices to communicate with:
  * ARTIK-based Hardware devices
  * non-ARTIK-based Hardware devices
  * Applications
  * Cloud services
* Data types ARTIK Cloud can handle:
  * Discrete
  * Continuous
  * real time
  * historic
* ARTIK Cloud Connectors
  * Allow users to easily integrate an existing cloud with ARTIK cloud
* ARTIK cloud is designed to accelerate device interoperability and enable new data insights.

ARTIK cloud can receive data from both physical devices and from the device clouds.

1. Communicate with physical devices
  * Clients can use many different protocols to send and receive data
  * Example protocols include:
    * REST
    * WebSocket
    * MQTT
    * CoAP

2. Communicate with device clouds
  * ARTIK Cloud can receive data from devices that are communicating with third party clouds
  * ARTIK Cloud can manage communication between different IoT devices on ARTIK or non-ARTIK clouds
  * Example:
    1. Smartwatch sends data to a non-ARTIK cloud
    * A user on the ARTIK cloud wants to use the data from the Smartwatch
    * The user is authorized to request data from this Smartwatch non-ARTIK cloud
    * The non-ARTIK cloud sends data to the ARTIK cloud
    * User can accesses data about the Smartwatch from the ARTIK cloud

#### ARTIK Cloud - Basics

###### APIs Authorization model
* Set of Permissions: READ and WRITE
* Reading and writing happens on users and other entities in the system
* Only a user has access to her/his data
* Admin privileges on the user, allow the admin to perform limited actions on behalf of the user, such as:
  * getting the user's profile information
  * changing the user's application properties

###### Messages
* Applications and devices store data as a message
* ARTIK Cloud recognizes two message types: data and actions
* Each message in ARTIK cloud is associated with a set of identifying metadata, such as:
  * device ID
  * user ID
  * application ID
* An access token generates during authentication, the token contains metadata
* To record a message, an application must provide the payload and the device ID
  * ARTIK Cloud can automatically infer the user ID and the application ID from the access token

###### User ID
* ARTIK Cloud defines a user ID and assigns it to the user on account creation
* An application may obtain the user's profile and device list using the user ID
* Application may request to manage an application profile for the user using the user ID
  * users can choose to grant an application access to their data
  * Once an application has been granted access, it may also request data from the users devices

###### Device ID and types
* ARTIK Cloud defines a Device ID and assigns it to the device
* Every device has a unique Device ID
* In ARTIK Cloud, a device is any source of data
  * Ex: Sensors, Applications, Appliances, services, etc.
* Devices can send messages to ARTIK Cloud
* A device type defines a category of device in  ARTIK cloud
  * Ex: Samsung Galaxy Gear Fit is a device type and Farah's Samsung Galaxy gear fit has a unique device ID
* Only the owner, vendor, or an Original Equipment Manufacturer (OEM) needs to create a device type
  * Owner of a device type are responsible for keeping the name and description of a device type updated

###### Application ID
* ARTIK Cloud defines the unique ID for each application
* An application ID is required to obtain an OAuth2 access token
* An application ID is required to request data from an application
  * provided that the user has granted access to the application
* Developers can request as many application IDs as needed
* If the developer has multiple application IDs, data can be shared among the applications
  * provided that the user has granted access to these applications
* OAuth2 is an authorization framework that enables applications to obtain limited access to user accounts on an HTTP service

###### Raw and Normalized  Data
* Data collected by ARTIK Cloud is called raw data
* Raw data refers to the original format and structure unmodified by the system
* After collection of data by an Application, raw data is processed and becomes normalized data.
  * JSON formatted with standardized field names and values

###### Manifest
* Associated with a device type
* Describes the structure of the data
* Must be updated when providing or updating the device types

###### Actions
* A specific type of an ARTIK Cloud message
* Sends a command to a devices
* Intended to be executed in near real time
* Actions are defined in the manifest
* Examples:
  * turn a device on
  * turn a device off
  * change a color value
  * Sending a text

###### Rules
* User defined
* Send actions to devices when triggered by incoming messages
* One of the most powerful ARTIK Cloud features

#### ARTIK Cloud - Tools

###### Developers Dashboard
* An interface for users to create and manage device types and Applications
* Convenient

###### Console API
* Lets users execute API Calls, and see the results from the browser

#### ARTIK Cloud - Hello, World!

Go to the hands-on ARTIK Cloud tutorial on "Hello, World!" [here](https://developer.artik.io/documentation/artik/tutorials/say-hello.html)

_ARTIK is out of business, so I will skip their tutorial;_ __I will also skip studying them__
