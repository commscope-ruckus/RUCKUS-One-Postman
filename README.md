# RUCKUS-One-Postman
Use this collection to assist in the development of scripts and applications using RUCKUS One. This API uses JSON Web Token for authentication.
First you need to generate an API KEY in the RUCKUS One UI, then use the cliend ID and client secret to obtain a token in the call **get jwt**.

Many variables will be assigned automatically by the scripts in this collection, using Pre-request Script and Tests in Postman. Change the variable values as appropriate (for instance, the AP and ICX switch serial number, network ssid, etc)

Note: Many RUCKUS One write-APIs are asynchronous. A response of 202 indicates an asynchronous 
call. That needs to be considered when writing API calls using python or any other language. 
Please see examples in the repository RUCKUS-One-Python for details.
Any other response indicates a synchronous response. The read-APIs are always synchronous.
