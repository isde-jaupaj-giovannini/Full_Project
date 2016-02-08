# Full_Project

This repository contains all of our other repository as submodules.

To clone all of them in one command use:

 `git clone --recursive git@github.com:isde-jaupaj-giovannini/Full_Project.git`

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

---

## Technologies used
 * All the web services are hosted on [Heroku](https://www.heroku.com/)
 * We used Postgress and the HerokuPostgress addon for our internal datasource
 * [Lombok](https://projectlombok.org/)
 * [Retrofit](https://square.github.io/retrofit/) for our REST clients
 * Jersey was used for the RESTfull service
 * for the telegram bot we used [this library](https://github.com/pevdh/telegram-bots-java-api) and [this frp library](https://github.com/SodiumFRP/sodium)

## Notes

Initially all of our repository could be run calling the default ant target running `ant` from the main directory.
This would have called if necessary `wsimport` to autogenerate the wsdl client where needed.

This approach turned out to not work with the ant buildpack on Heroku and in the end due to time constraints we had to include the generated classes inside the repositories.

We also initially used Java 1.8 and some of it's new features but we had to revert to Java 1.7 because the [custom buildpack](https://github.com/davideUnitn/heroku-buildpack-ant) we had created to use Java 8 got broken with some recent changes of Heroku.
