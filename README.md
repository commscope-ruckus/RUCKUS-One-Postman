# RUCKUS-One-Postman
Use these collections to assist in the development of scripts and applications using RUCKUS One. This API uses JSON Web Token for authentication.
First you need to generate an API KEY in the RUCKUS One UI, then use the cliend ID and client secret to obtain a token in the call **get jwt**.

Many variables will be assigned automatically by the scripts in this collection, using Pre-request Script and Tests in Postman. Change the variable values as appropriate (for instance, the AP and ICX switch serial number, network ssid, etc)

Note: Many RUCKUS One write-APIs are asynchronous. A response of 202 indicates an asynchronous 
call. That needs to be considered when writing API calls using python or any other language. 
Please see examples in the repository RUCKUS-One-Python for details.
Any other response indicates a synchronous response. The read-APIs are always synchronous.

The collection named **RUCKUS One** uses a regular R1 account. It is a walkthrough shows several common tasks executed using API calls.
- June 25, 2025 - Removed four deprecated endpoints for traffic monitoring and client session history.

The collection named **RUCKUS One MSP** has two folders. The first folder contains a walkthrough using an MSP account which has delegated accounts. The last call picks one MSP-EC.
The second folder is a walkthrough using the MSP-EC.
In order to access a delegated account, besides using the jwt token for authentication, you need to add another header named **x-rks-tenantid**, whose value is the tenant id for the managed account.

The collecion named **RUCKUS One Hospitality Edition** also contains two folders, because it is also for an instance that uses delegated accounts. The top level is the MSP or LSP, which is the brand, and the bottom level is the REC (RUCKUS End Customer), which are the properties managed by a brand. As with the MSP-EC, in order to access a property, besides using the jwt token for authentication, you need to add the header **x-rks-tenantid** to the request, whose value is the tenant id for the property.
- June 25, 2025 - Fixed incorrect Base URL at endpoint List Brand Properties. Removed deprecated endpoint to retrieve client session history.

The collection named **RUCKUS One WISPr** has three API calls using the WISPr interface. You need to edit the tenantId in Scripts/Pre-Requests, and the Integration Key in the body. Change the UE-IP, UE-MAC, UE-Username and UE-Password to match the information of the client device and user credentials.

The collection named **RUCKUS One DPSK** includes endpoints to manage DPSK pools, passphrases and devices. At the get jwt request, you need to edit the tenantId in Scripts/Pre-Requests, and the client_id and client_secret in the body. 

The collection named **RUCKUS One Resident Portal** includes endpoints to see all resident portals, navigate to a specific portal (it uses a different Base URL), and reset the resident portal's token.
