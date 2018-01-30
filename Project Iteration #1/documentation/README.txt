this README is for: SYSC3303 assingment 1
by: Luke Newton (100999309)
lab section: L1
date: 1/20/2018

----------------------
FILES IN THIS PROJECT
----------------------
Client.java: 
	represents the client in the system.
ReqestType.java: 
	Enum used by client to specify the format of message requests when creating DatagramPacket contents.
IntermediateHost.java: 
	represents the intermdeiate host in the system.
Server.java:
	represents the server in the system.
InvalidMessageFormatException.java:
	subclass of Exception which is thrown when the server attempts to parse a message of invalid format.
	
----------------------
TO RUN THE ASSIGNMENT
----------------------
The assignment is run by excuting three programs: Client.java, IntermediateHost.java, and Server.java.

Open the project in Eclipse and run each in the following order:
1. Server.java (in server package)
2. IntermediateHost.java (in intermediateHost package)
3. Client.java (in client package)
NOTE: by default, each program will timeout after 5 seconds of waiting for a message, so programs must
be opened in rapid succession (or see section below for how to disable timeouts)

At this point, the programs will likely have completed the eleven requiired iterations and all information
will be able to be seen in the console. The the drop down next to the option "Display selected Console"
 in the top right corner of the console window will allow you to switch between the console outputs for 
the client, server, and intermediate host. Additional consoles can be opend with the "Open Console" option 
in the top right corner of the  console by selecting "Open Console" -> "3 New Concole View" to view multiple
outputs at once.

----------------------------------
EDITING PARAMTERS OF THE PROGRAMS
----------------------------------
At the top of Client.java, Server.java, and IntermediateHost.java there are several constants defined which
can be changed to alter the program.

1)Client.java
NUMBER_OF_CLIENT_MAIN_ITERATIONS:
	This integer value is the number of times the client will send out a request packet. Requests will always
	alternate between read and write, and the final request will always be invalid format.
INTERMEDIATE_HOST_PORT_NUMBER:
	This integer value is the port number that the intermediate host will be found at.
	NOTE: if this value is changed in the client, it must be changed to the same value in the intermediate
		  host as well!
MAX_PACKET_SIZE:
	This integer value specifies the maximum size of the data portion of a DatagramPacket.
FILENAME:
	This string value is the file name that is sent in each request.
MODE
	This string value is the mode that is sent in each request.
TIMEOUTS_ON:
	This boolean value specifies whether or not timeouts for recieves are active for the client. Originally timouts
	be on; set this value to false to deactivate them.
TIMEOUT_MILLISECONDS:
	This integer value sets the timeout length in milliseconds.
	
2)IntermediateHost.java
SERVER_PORT_NUMBER:
	This integer value is the port number that the server will be found at.
	NOTE: if this value is changed in the intermedaite host, it must be changed to the same value in the server
		  as well!
INTERMEDIATE_HOST_PORT_NUMBER:
	This integer value is the port number that the intermediate host will be found at.
	NOTE: if this value is changed in the intermediate host, it must be changed to the same value in the client
		  as well!
MAX_PACKET_SIZE:
	This integer value specifies the maximum size of the data portion of a DatagramPacket.
TIMEOUTS_ON:
	This boolean value specifies whether or not timeouts for recieves are active for the client. Originally timouts
	be on; set this value to false to deactivate them.
TIMEOUT_MILLISECONDS:
	This integer value sets the timeout length in milliseconds.
	
3)Server.java
SERVER_PORT_NUMBER:
	This integer value is the port number that the server will be found at.
	NOTE: if this value is changed in the server, it must be changed to the same value in the intermedaite
		  host as well!
	NOTE: This value was specified to be 69 in the assignment
TIMEOUTS_ON:
	This boolean value specifies whether or not timeouts for recieves are active for the client. Originally timouts
	be on; set this value to false to deactivate them.
TIMEOUT_MILLISECONDS:
	This integer value sets the timeout length in milliseconds.
MAX_PACKET_SIZE:
	This integer value specifies the maximum size of the data portion of a DatagramPacket.
	
---------------
DESIGN CHOICES
---------------
While all three of the client, server, and intermedaite host have many of the same functionality (send, recieve, many 
identical constants), the decision was made to not use a superclass/interface to reduce this repetition. 

This is because these are three seperate programs which theoretically should be able to run on different computers with 
little additional work required. If this assignment were one single program, a superclass or interface would certainly 
have been used here.

ADDITIONAL DOCUMENTATION CAN BE SEEN IN THE 'doc' FOLDER IN THE JAR FILE