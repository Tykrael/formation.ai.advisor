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

> [!NOTE]
> <user_request>
> <objectif>Analyser les données des personas du fichier 'personas.json' pour en tirer des statistiques de compétences et identifier les faiblesses.</objectif>
> <source_donnees>Fichier JSON en pièce jointe (mêmes structure que 'personas.json').</source_donnees>
> 
> <analyse_statistique>
>     <calcul_par_competence>
>         <indicateur nom="Nombre de Personnes">Compter le nombre de personas ayant un score supérieur à 0 pour cette compétence.</indicateur>
>         <indicateur nom="Score Total">Sommer tous les scores de cette compétence.</indicateur>
>         <indicateur nom="Expertise Moyenne">Calculer la moyenne du score en divisant le 'Score Total' par le 'Nombre de Personnes'.</indicateur>
>     </calcul_par_competence>
> </analyse_statistique>
> 
> <identification_faiblesses>
>     <faiblesse nom="Périmètre d'Expertise Réduit">
>         <condition>Lister les compétences pour lesquelles le 'Nombre de Personnes' est inférieur ou égal à 3.</condition>
>         <libelle_resultat>Compétences avec un périmètre d'expertise réduit (≤ 3 personnes)</libelle_resultat>
>     </faiblesse>
>     <faiblesse nom="Niveau d'Expertise à Améliorer">
>         <condition>Lister les compétences pour lesquelles l''Expertise Moyenne' est strictement inférieure à 3.75.</condition>
>         <libelle_resultat>Compétences avec une moyenne d'expertise faible (&lt; 3.75)</libelle_resultat>
>     </faiblesse>
> </identification_faiblesses>
> 
> <format_sortie>
>     <section nom="Synthèse des Statistiques" type="tableau">Afficher les trois indicateurs ('Nombre de Personnes', 'Score Total', 'Expertise Moyenne') pour chaque compétence.</section>
>     <section nom="Analyse des Faiblesses" type="liste">Afficher les deux listes de faiblesses identifiées séparément.</section>
>     <exigence_affichage>Utiliser les intitulés de compétences formatés et lisibles (ex: "Strategie_Bancaire" devient "Stratégie Bancaire").</exigence_affichage>
> </format_sortie>
> 
> </user_request>

> [!NOTE]
> <user_request>
> <objectif>Élaborer un plan de recrutement stratégique et rédiger les fiches de poste associées.</objectif>
> <contexte_prealable>
> <donnees_entree type="resultats_analyse">Utiliser les statistiques de faiblesses précédemment identifiées (Compétences ≤ 3 Experts et Compétences à Moyenne < 3.75) comme base de décision.</donnees_entree>
> </contexte_prealable>
> 
> <role_a_endosser>Recruteur expérimenté, adoptant un ton amical et bienveillant.</role_a_endosser>
> 
> <produits_attendus>
> <produit nom="Plan de Recrutement">Proposer un plan structuré qui regroupe les compétences faibles par "Axe de Recrutement" et définit l'objectif principal de chaque axe.</produit>
> <produit nom="Fiches de Poste">Rédiger au moins deux fiches de poste polyvalentes et ciblées, couvrant les faiblesses les plus critiques.</produit>
> </produits_attendus>
> 
> <contraintes_fiches_de_poste>
> <format>Tableau (Catégorie, Détails) pour chaque fiche.</format>
> <detail_contenu>Inclure les 'Compétences Requises (Must-Have)' et les 'Compétences Souhaitées (Nice-to-Have)' en utilisant les noms de compétences formatés.</detail_contenue>
> <positionnement>Chaque fiche doit clairement indiquer comment le rôle répond aux faiblesses des statistiques (sécurité, support faible, faible nombre d'experts, etc.).</positionnement>
> </contraintes_fiches_de_poste>
> 
> </user_request>