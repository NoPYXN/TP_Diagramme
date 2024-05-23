Diagramme use case fait sur plantUML :
```
@startuml
left to right direction

actor Client
actor Réceptionniste
actor Directeur

usecase "Réserver une chambre" as UC1
usecase "Enregistrement" as UC2
usecase "Départ" as UC3
usecase "Gérer les réservations" as UC4

Client --> UC1 : Réserve une chambre en ligne
Réceptionniste --> UC2 : Enregistre le client
Réceptionniste --> UC3 : Fait le départ du client
Directeur --> UC4 : Gère toutes les réservations

@enduml
```

![image](https://github.com/NoPYXN/TP_Diagramme/assets/124778566/d228d89c-36bb-43b0-b8ba-9af57ec25646)

Diagramme de classe : 

```mermaid
%%{init: {'theme': 'base', 'themeVariables': { 'fontSize': '16px', 'primaryColor': '#ffaa00', 'primaryBorderColor': '#ffcc00', 'primaryTextColor': '#000000', 'lineColor': '#000000', 'secondaryColor': '#ffdd66', 'tertiaryColor': '#ffee99'}}}%%
classDiagram
    class Hotel {
        +int id
        +String nom
        +String adresse
        +int etoiles
        +ajouterChambre()
        +supprimerChambre()
    }

    class Chambre {
        +int id
        +String categorie
        +int capacite
        +String confort
        +boolean estDisponible
        +reserver()
        +liberer()
    }

    class Reservation {
        +int id
        +Date dateReservation
        +Date dateDebut
        +Date dateFin
        +boolean estConfirmee
        +float arrhes
        +confirmer()
        +annuler()
    }

    class Client {
        +int id
        +String nom
        +String adresse
        +String telephone
        +String email
        +faireReservation()
        +annulerReservation()
    }

    Hotel "1" --> "0..*" Chambre : contient
    Chambre "1" --> "0..*" Reservation : estReserveePar
    Reservation "1" --> "1" Client : faitePar
    Client "0..*" --> "0..*" Reservation : fait
```

Diagramme d'activité du processus de réservation : 

```mermaid
%%{init: {'theme': 'base', 'themeVariables': { 'fontSize': '16px', 'primaryColor': '#ffaa00', 'primaryBorderColor': '#ffcc00', 'primaryTextColor': '#000000', 'lineColor': '#000000', 'secondaryColor': '#ffdd66', 'tertiaryColor': '#ffee99'}}}%%
---
title: Diagramme d'activité
---
flowchart TD
    A[Début] --> B[Remplir le formulaire de réservation]
    B --> C{Vérifier la disponibilité}
    C -->|Disponible| D[Créer la réservation]
    C -->|Non disponible| E[Notifier le client]
    D --> F[Payer les arrhes]
    F --> G[Confirmer la réservation]
    G --> H[Fin]
    E --> H
```
