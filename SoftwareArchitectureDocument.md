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
Träwelling uses the MVC-Scheme of Laravel. You can see this [here](./images/OverallUsecaseDiagram.png)

## 3.Architectural Goals and Constraints 
We decided to use [DB-Rest](https://github.com/derhuerst/db-rest/) as an API-wrapper for the API of the Deutsche Bahn. 
For social logins we're using Laravel's [socialite](https://github.com/laravel/socialite) with our own [extension for mastodon](https://github.com/HerrLevin/socialite-mastodon).
For tweeting abraham's [twitteroauth](https://github.com/abraham/twitteroauth), for tooting revolution's [mastodon-api](https://github.com/revolution/laravel-mastodon-api).

The frontend is realized with the [Bootstrap](https://getbootstrap.com) framework on top of Laravel's blade engine.

## 4. Use-Case View 
n/a

## 5. Logical View
Templates aren´t no classes, in our project they are only HTML files.
Our classes were only in model.py

Our overall class diagram can be found [here](images/MVC-Class-diagramm.png).


## 6. Process View
n/a

## 7. Deployment View
n/a
## 8. Implementation View
n/a

## 9. Data View
We're using the MariaDB database to store our data. 


## 10. Size and Performance
tbd

## 11. Quality
