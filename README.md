# Project Name

Projet pour la formation AI Advisor
Participants : Virgile, Vladimir, Remi, Vincent

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://example.com) [![License: MIT](https://img.shields.io/badge/license-MIT-blue)](./LICENSE)

## Table of Contents

- [About](#about)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
<!-- 
//- [Configuration](#configuration)
//- [Usage](#usage)
//- [Development](#development)
//- [Contributing](#contributing)
//- [License](#license)
//- [Contact](#contact)
// - [Acknowledgements](#acknowledgements)
 -->
## About

Screencaps + files for the demo

## Features

-personnas.json : liste de collaborateur de la société cible
-index.html + index.v2.html : render de la matrice de compéténce generée par LLM
-recrutement vs formation.pdf : analyse comparative des couts des differentes solutions recrutement vs formation

## Requirements

- OS: cross-platform (Windows / macOS / Linux)
- Runtime: e.g., Node.js >= 14, Python 3.8+, etc.
- Other prerequisites (database, services)

## Installation

1. Clone the repository:

## Prompts

> [!NOTE]
> <parametrage>
> <nombre_personas>50</nombre_personas>
> <competence_persona>5</competence_persona>
> <secteur_entreprise>Banque de Détail</secteur_entreprise>
> <output_format>json</output_format>
> <persona_caracteristiques>nom complet, profession, seniorité</persona_caracteristiques>
> </parametrage>
> 
> <requete_principale>
> Générer la liste complète des nombre_personas personas  au format output_format, 
> chaque persona doit posseder competence_persona competences,
> chaque competence doit etre evaluée avec un score allant de 1(junior) a 5(expert) representant le niveau de seniorite de la persona dans la competence
> chaque persona doit posseder les caractéristiques persona_caracteristiques
> pour une entreprise du type secteur_entreprise,
> </requete_principale>

> [!NOTE]
> <user_request>
> <objectif>Générer un site web (HTML/CSS/JS) affichant les données du fichier JSON 'personas.json' dans un tableau.</objectif>
> 
> <contraintes_techniques>
>     <chargement_donnees>Le JSON doit être chargé en JavaScript comme un fichier externe ('personas.json', via Fetch API).</chargement_donnees>> 
>     <framework_design>Utilisation de l'esthétique Material UI (couleurs, ombres) pour la représentation visuelle.</framework_design>
> </contraintes_techniques>
> 
> <contraintes_tableau>
>     <colonnes_figees type="nombre">3</colonnes_figees>
>     <colonnes_a_figer>Nom Complet, Profession, Séniorité</colonnes_a_figer>
>     <defilement>Seules les colonnes de compétences doivent pouvoir défiler horizontalement.</defilement>
>     <affichage_texte>Aucune troncature (pas d'ellipsis) pour les intitulés de lignes ou de colonnes.</affichage_texte>
>     <interactivite_hover>Effet de survol simultané sur la ligne complète ET sur la colonne survolée (y compris sur les colonnes figées).</interactivite_hover>
> </contraintes_tableau>
> 
> <contraintes_pied_tableau>
>     <ligne_statistique nom="Score total">Somme des scores de chaque colonne de compétence.</ligne_statistique>
>     <ligne_statistique nom="Experts">Nombre de personnes possédant la compétence (score &gt; 0) par colonne.</ligne_statistique>
>     <ligne_statistique nom="Expertise moyenne">Moyenne du score par rapport au nombre d'experts (score total / nombre d'experts).</ligne_statistique>
>     <alertes_experts>La cellule 'Experts' doit être mise en ORANGE si le nombre d'experts est inférieur à 3.</alertes_experts>
>     <alertes_moyenne>
>         <seuil_critique>La cellule 'Expertise moyenne' doit être mise en ROUGE si le score moyen est inférieur à 3.00.</seuil_critique>
>         <seuil_avertissement>La cellule 'Expertise moyenne' doit être mise en ORANGE si le score moyen est inférieur à 3.75 (mais n'est pas déjà ROUGE).</seuil_avertissement>
>     </alertes_moyenne>
> </contraintes_pied_tableau>
> 
> <exclusion>Ne pas générer le JSON ni proposer le téléchargement des fichiers.</exclusion>
> </user_request>