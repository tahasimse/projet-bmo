# Analyse du Code Java Généré par Modelio

## Introduction
Dans ce rapport, nous analysons le code Java généré automatiquement par Modelio pour notre application de gestion de locations courte durée. L'application doit permettre la gestion de plusieurs résidences avec différentes parties réservables séparément ou en totalité, ainsi que des extras comme du matériel et des prestations optionnelles.

## Analyse des classes générées

### Classe `Address`
Cette classe représente une adresse avec les attributs `street`, `city`, `country` et `postcode` qui sont tous publics. Ces attributs devraient être privés avec des getters/setters pour respecter l'encapsulation.

### Classe `Extras`
Représente les extras comme le petit déjeuner ou le linge de maison mentionnés dans le cahier des charges. Elle a deux attributs privés: `name` et `price`. Les getters/setters sont corrects mais il y a trop de commentaires automatiques.

### Classe `Guest`
Cette classe hérite de `Person` et contient une liste de `RoomBooking` pour gérer les réservations des clients. La méthode `createBooking` n'est pas finie et devrait permettre aux utilisateurs de réserver plusieurs parties de la résidence comme demandé.

### Classe `Owner`
Représente les gestionnaires indépendants mentionnés dans le projet. Hérite de `Person` et a une liste de `RoomBooking`. Les méthodes `addProperty`, `updateProperty` et `removeProperty` ne sont pas terminées et doivent permettre aux gestionnaires de configurer leurs biens.

### Classe `Payment`
Cette classe gère les paiements avec les attributs `Total` et `paymentType`. Elle devrait intégrer les systèmes sécurisés (carte bancaire, PayPal) mentionnés dans les fonctionnalités et permettre le paiement partiel.

### Classe `Person`
Classe parent pour `Guest` et `Owner` avec les attributs: `name`, `email`, `address` et `phone`. Cette classe est importante pour la gestion des communications entre locataires et gestionnaires.

### Classe `Property`
Représente les résidences du projet avec les attributs `name` et `propertyLocation`. Cette classe devrait gérer les différentes parties réservables mentionnées dans la description.

### Classe `PropertyLocation`
Représente l'emplacement des propriétés avec les attributs `name`, `location` et `room`. La méthode `getRooms` ne fonctionne pas correctement et devrait renvoyer la liste des chambres/studios disponibles.

### Classe `Room`
Représente les éléments configurables (chambre rose, studio vue mer) avec les attributs `roomName`, `status`, `price0`, `price1`, `price2` (probablement pour les tarifs haute, moyenne et basse saison) et `extras`. La méthode `isRoomAvailable` doit être complétée pour la gestion des disponibilités en temps réel.

### Classe `RoomBooking`
Gère les réservations avec les attributs `reservationId`, `startDate`, `durationInDays`, `room` et `payment`. Cette classe est centrale pour implémenter la fonctionnalité de réservation.

### Enumération `RoomStatus`
Définit les états d'une chambre: `Available`, `Reserved`, `Occupied` et `NotAvailable`, essentielle pour la gestion des disponibilités en temps réel.

## Conclusion
En conclusion, ce projet nous a permis d'explorer la transition entre modélisation UML et implémentation Java concrète grâce au code généré par Modelio. Nous avons acquis une meilleure compréhension des relations entre classes dans un système de réservation et de l'importance de l'encapsulation dans la programmation orientée objet. L'analyse du code nous a aidés à établir des liens entre les concepts théoriques vus en cours et leur application pratique, tout en nous familiarisant avec la structure d'une application multi-utilisateurs. Cette expérience constitue une base solide pour nos futurs projets de développement.
