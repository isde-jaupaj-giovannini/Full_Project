# Full_Project


## Architecture

![alt tag](https://github.com/isde-jaupaj-giovannini/Full_Project/blob/master/images/architecture.png)

The architecture of our project is shown in the picture above.

The 6 components are:


### Telegram Bot

Our user interface is provided as a Telegram Bot with which the user can interact.

### Process Centric Service
This SOAP based web service handles simple request from the client and dispatches them to the storage services.

[WSDL](https://mysterious-dawn-60268.herokuapp.com/ws/blservice?wsdl)

[API description](https://github.com/isde-jaupaj-giovannini/process_centric_service/blob/master/README.md)
### Business Logic Service
This SOAP based web service handles registration request from the client and the two integration logics.

[WSDL](https://mysterious-dawn-60268.herokuapp.com/ws/blservice?wsdl)

[API description](https://github.com/isde-jaupaj-giovannini/business_logic_service/blob/master/README.md)
### Storage Service
This SOAP based web service provides an abstraction over the internal and external datasources of our application.

[WSDL](https://radiant-chamber-78838.herokuapp.com/ws/storage?wsdl)

[API description](https://github.com/isde-jaupaj-giovannini/storage_service/blob/master/README.md)
### LocalDatabase Service
This SOAP based web service handles our internal datasource which is a Postgress database on Heroku.

[WSDL](https://nameless-forest-62807.herokuapp.com/ws/localdb?wsdl)

[API description](https://github.com/isde-jaupaj-giovannini/local_database/blob/master/README.md)
### Adapter Service
This RESTfull web service provides an abstraction over our external datasources, which are  [Random quotes](https://market.mashape.com/andruxnet/random-famous-quotes)  - [TodoLy](http://todo.ly/apiwiki/) - [Xkcd webcomic](http://xkcd.com/json.html) -
[GoogleCharts API](https://developers.google.com/chart/).

[API description](https://github.com/isde-jaupaj-giovannini/adapter_service/blob/master/README.md)
