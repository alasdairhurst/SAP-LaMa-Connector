# API-Builder SAP Landscape Management Connector

Use this connector to communicate with the [SAP Landscape Management](https://www.sap.com/products/landscape-management.html) and make it part of your API-Management platform.  

## Installation
To install it into you API-Builder project execute: 
```npm
npm install @axway-api-builder-ext/SAP-LaMa-Connector
```
To install a specific version please use: 
```npm
npm install @axway-api-builder-ext/SAP-LaMa-Connector@1.0.0
```
  
This connector is using the Swagger-Flow node:  
https://docs.axway.com/bundle/API_Builder_4x_allOS_en/page/swagger_flow-node.html  


## Configuration
After restarting your API-Builder project you get the following connector:  
![XML Node Settings](https://github.com/Axway-API-Builder-Ext/SAP-LaMa-Connector/blob/master/misc/images/SAP-Landscape-Management-Connector.png)   
Depending on the selected method different options appear on the right, when using the connector as part of the flow.   
![XML Node Settings](https://github.com/Axway-API-Builder-Ext/SAP-LaMa-Connector/blob/master/misc/images/SAP-Landscape-Management-Connector-Settings.png)   

## Setup SAP Landscape Management Host and Login
A new config file has been automatically created for the SAP Landscape Management Connector which can be used to setup the connection details:  
![XML Node Settings](https://github.com/Axway-API-Builder-Ext/SAP-LaMa-Connector/blob/master/misc/images/SAP-Landscape-Management-Connector-Config.png)  
Additional details can be found here: https://docs.axway.com/bundle/API_Builder_4x_allOS_en/page/swagger_flow-node.html#Swaggerflow-node-ConfiguretheSwaggerplugin  


Please note, that the connector is configured to use HTTP-Basic to communicate with the SAP Landscape Management. In order to use that, please configure the Authentication-Credentials as described here:  
https://docs.axway.com/bundle/API_Builder_4x_allOS_en/page/http_basic_credentials.html  
Alternatively you can pass on externally given user-credentials with the flow node. 

```javascript
module.exports = {
	// The configuration settings for your Swagger service.
	pluginConfig: {
		'@axway/api-builder-plugin-fn-swagger': {
			'sap-lama-api': {
				// It is possible to override Swagger URI options when constructing
				// outbound requests from the Swagger plugin.
				uri: {
					// protocol: 'https',
					// host: 'hostname',
					// port: 443,
					// basePath: '/api'
				}
			}
		}
	},
	// The following authorization credentials needed to use the Swagger service.
	// Please follow this guide to manually configure the credentials:
	// https://docs.axway.com/bundle/API_Builder_4x_allOS_en/page/api_builder_credentials.html
	authorization: {
		credentials: {
			'LaMa API Basic Authentication': {
				type: 'basic',
				username: yourusername,
				password: yourpassword
			}
		}
	}
};
```

## Compatibility
Tested with SAP Landscape Management 3.0

## Changelog
- 1.0.0 - 11.12.2019
  - Initial version 
  
## Limitations/Caveats
- Nothing known

## Contributing

Please read [Contributing.md](https://github.com/Axway-API-Management-Plus/Common/blob/master/Contributing.md) for details on our code of conduct, and the process for submitting pull requests to us.  


## Team

![alt text][Axwaylogo] Axway Team

[Axwaylogo]: https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png  "Axway logo"


## License
[Apache License 2.0](/LICENSE)
