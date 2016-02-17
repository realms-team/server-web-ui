# SOL Web-Interface
Web interface for the server

### Objective
Provide a visual interface to access WSN network information and centralize application data

### Description
As we are deploying more and more WSNs, we want to have a central entity that interconnects all those networks. This centralization will make maintenance easier by having a unique running server code at a given time, and allow us to better exploit data by considering more environments. This platform will provide a unified interface for users to share data and monitor their networks.

### Characteristics
The **users** must be able to:
  * Register a new deployment
  * Display network data (connectivity, stats, etc) and visualize the application data, see Data Visualization
  * Send commands to the network motes

The **administrators** must be able to:
  * Manage users
  * Manage access tokens

### Server
###### Hosting:
The server should be as simple as possible, possibly Python-based unless some turnkey solution is already available.
As a first step, the server will be hosted at Inria or UCB.
As a second step, it could be hosted as a VM image on AWS

###### Code:
The code will be part of the REALMS repositories and thus, freely available and open-source (BSD license).

###### Web-server:
The Web-server will only interact with the MongoDB database to retrieve SOL objects.

### Data Sharing
TO DISCUSS: 
Do we want the data to be shared between users?
  * Thomas: only optionally

Do we allow private deployment? (give the choice to the user)
  * Thomas: yes

Do we share only the connectivity data and not the sensors readings?
  * Thomas: Good idea

Data accessible only by admins?
  * Thomas: All data for sure will be accessible by all admins

### Data Visualization
The **users** must be able to:
  * List all the motes and each of their attached sensors/actuator
  * Display the motes on a map
    * Mote configuration
    * Links between the motes and their corresponding qualities
  * Plot the different data 
    * Example: using [ploty](https://plot.ly/)
    * Others: [Grafana](http://grafana.org/) or [Kibana](https://www.elastic.co/products/kibana)
      * Those two do not work with MongoDB
