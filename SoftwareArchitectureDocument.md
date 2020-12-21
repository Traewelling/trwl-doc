# Software Architecture Document

## 1. Introduction 
### 1.1 Purpose
This document provides a comprehensive architectural overview of the system, 
using a number of different architectural views to depict different aspects of the system. 
It is intended to capture and convey the significant architectural decisions which have been made on the system.

### 1.2 Scope
The scope of this SAD is to show the architecture of the Träwelling project. Affected are the class structure, the use cases and the data representation.

### 1.3 References
- [GitHub](https://github.com/Traewelling)
- [Blog](https://traewelling.wordpress.com/)
- [Overall Use case diagram](./images/OverallUsecaseDiagram.png)
- [Software Requirements Specification](./SoftwareRequirementsSpecification.md)
- [UC Change profile to private](./UCs/ChangeProfileToPrivate.md)
- [UC Request Follow](./UCs/RequestFollow.md)
- [UC Search User](./UCs/SearchUser.md)


## 2. Architectural Representation
Träwelling uses the MVC-Scheme of Laravel. You can see this [here](./images/ModelViewControllerDiagram.jpg)

## 3.Architectural Goals and Constraints 
We decided to use [DB-Rest](https://github.com/derhuerst/db-rest/) as an API-wrapper for the API of the Deutsche Bahn. 
For social logins we're using Laravel's [socialite](https://github.com/laravel/socialite) with our own [extension for mastodon](https://github.com/HerrLevin/socialite-mastodon).
For tweeting abraham's [twitteroauth](https://github.com/abraham/twitteroauth), for tooting revolution's [mastodon-api](https://github.com/revolution/laravel-mastodon-api).

The frontend is realized with the [Bootstrap](https://getbootstrap.com) framework on top of Laravel's blade engine.

## 4. Use-Case View 
The overall use case diagram can be found [here](images/OverallUsecaseDiagram.png)

## 5. Logical View
Our overall class diagram can be found [here](images/MVC-Class-diagramm.png).
The views are in green, the controllers in red and the models yellow.

## 6. Process View
n/a

## 7. Deployment View
The website is running in a cloud-based shared environment hosted by uberspace.de. We have access to all 20 Cores of the Intel(R) Xeon(R) Silver 4214 CPU @ 2.20GHz and up to 32GB RAM. Our network interface can handle up to 10GB/s over a redundant fiber interface.

## 8. Implementation View
n/a

## 9. Data View
We're using a MariaDB database to store our data. 

You can see our structure [here](images/Database.png)

## 10. Size and Performance
tbd

## 11. Quality
