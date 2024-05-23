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
