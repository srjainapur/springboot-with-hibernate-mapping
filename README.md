This example demonstrate One to One mapping.

The User(Table name O2O_USER) and ShippingAddress(O2O_SHIPPING_ADDRESS) tables exhibit a one-to-one relationship between each 
other. The relationship is mapped using a foreign key called fk_shippingAddress in the user table.

This relationship is unidirectional i.e we can get the shipping information from user table. If you have shipping information and 
you want to get User details then it's not possible, we have to use bi directional relationship in this case.

Tables 
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Tables will get created automatically when the server is started because of the configuration in the application.properties file. 

application.properties
# Database Configuration
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:oracle:thin:@localhost:1521:XE
spring.datasource.username=system
spring.datasource.password=Admin12345
spring.datasource.driver-class-name=oracle.jdbc.driver.OracleDriver


Testing
+++++++++++++++++++++++++++++++++++++++++++++++++++++++
Open Postman tool

To insert the new record
++++++++++++++++++++++++++++++++++++++++++++++++
Method  POST
URL     http://localhost:8099/user
in Body tab select raw(radio button) & from drop down select JSON(application/json)

Paste the below json in the Text Area
{
	"firstName":"EVI",
	"lastName":"Occonell",
	"email":"evi@gmail.com",
	"password":"eviocconell@20",
	"shippingAddress":
		{
			"streetAddress1":"4th cross",
			"streetAddress2":"2nd Main",
			"city":"London",
			"state":"London",
			"zipcode":10,
			"country":"England"
		}	
}

To Get all the record
++++++++++++++++++++++++++++++++++++++++++++++++
Method  GET
URL     http://localhost:8099/users
