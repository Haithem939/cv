Projet : Texte “en orbite”
Idée du projet:
- crée une animation où un texte tourne lentement autour d’un centre, comme une planète autour du soleil.
Par exemple, le mot “Créatif” ou “Bienvenue” tourne autour d’un logo ou d'une image.

 L’objectif: 
 - c'est de donner un effet dynamique et spatial à une page web.
 - Apprendre à utiliser les transformations CSS (rotate, translate)
 - Comprendre les animations continues (boucles infinies)
 - Créer un effet esthétique sans bibliothèque externe.

 Technologies utilisées:
  - HTML → structure du texte et du cercle
  - CSS → animation (rotation, positionnement circulaire)
  - JavaScript → pour contrôler la vitesse ou le sens de rotation (optionnel)

 Résultat attendu:
 un élément central (un logo, un cercle vide, etc.), Autour, je places un texte positionné à une certaine distance du centre et je fais tourner 
ce texte autour du centre en utilisant une animation rotate().

```mermaid
graph TD
    %% Noeuds de départ et fin
    Start([Début du Jeu])
    End([Fin du Programme])

    %% Initialisation
    Init[Initialisation :<br>Score = 0<br>Temps = 30 secondes]
    SpawnRed[Faire apparaître le<br>Rond Rouge (Position aléatoire)]

    %% Boucle de jeu
    Wait(Attente d'une action)
    TimerCheck{Le temps est-il<br>écoulé ?}
    
    %% Gestion du Clic
    InputCheck{Le joueur a-t-il<br>cliqué ?}
    HitCheck{Le clic est-il SUR<br>le Rond Rouge ?}
    
    %% Actions
    ScoreUp[Score + 1]
    MoveRed[Déplacer le Rond Rouge]
    MissAction[Ignorer ou<br>Pénalité de temps]
    
    %% Fin de partie
    GameOver[Afficher Écran de Fin<br>et Score Final]
    Restart{Rejouer ?}

    %% Connexions
    Start --> Init
    Init --> SpawnRed
    SpawnRed --> Wait
    
    Wait --> TimerCheck
    TimerCheck -- Oui --> GameOver
    TimerCheck -- Non --> InputCheck
    
    InputCheck -- Non --> Wait
    InputCheck -- Oui --> HitCheck
    
    HitCheck -- Non (Raté) --> MissAction
    MissAction --> Wait
    
    HitCheck -- Oui (Touché) --> ScoreUp
    ScoreUp --> MoveRed
    MoveRed --> Wait
    
    GameOver --> Restart
    Restart -- Oui --> Init
    Restart -- Non --> End

    %% Styles pour la lisibilité
    style Start fill:#f9f,stroke:#333,stroke-width:2px
    style End fill:#f9f,stroke:#333,stroke-width:2px
    style SpawnRed fill:#ff6b6b,stroke:#333,color:black
    style MoveRed fill:#ff6b6b,stroke:#333,color:black
    style HitCheck fill:#fff,stroke:#ff0000,stroke-width:2px
    style ScoreUp fill:#90ee90,stroke:#333
```
