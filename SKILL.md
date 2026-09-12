---
name: readme-truth
description: Vérifie si les instructions et affirmations d'un README correspondent réellement au projet. Utiliser pour détecter commandes inexistantes, mauvais ports, variables d'environnement oubliées, prérequis non documentés, chemins obsolètes, scripts renommés et instructions d'installation qui ne fonctionnent plus.
---

# ReadmeTruth

Confronte le README à la réalité du repo.

## Objectif

Ne fais pas une revue générale de documentation. Cherche uniquement les affirmations **vérifiables** du README et contrôle-les contre les fichiers réels du projet.

## Mode par défaut

Audite sans modifier.

Ne corrige le README que si l'utilisateur demande explicitement de le mettre à jour.

## Procédure

### 1. Identifier les affirmations vérifiables

Repère notamment :

- commandes d'installation et de démarrage ;
- scripts `npm`, `pnpm`, `yarn`, `make`, `cargo`, `poetry`, etc. ;
- versions de runtime ou d'outils ;
- ports et URLs locales ;
- variables d'environnement ;
- fichiers `.env.example` annoncés ;
- migrations, seeds ou étapes de setup ;
- noms de dossiers ou fichiers ;
- services externes requis ;
- commandes de test, lint et build ;
- fonctionnalités annoncées comme présentes si le README les décrit comme utilisables.

Ignore les slogans, opinions et descriptions marketing impossibles à prouver depuis le repo.

### 2. Chercher la preuve

Pour chaque affirmation, vérifie la source la plus pertinente :

- manifests et scripts de package ;
- Docker / compose ;
- fichiers de config ;
- code de démarrage ;
- exemples d'environnement ;
- CI ;
- dossiers réels ;
- scripts de migration ;
- routes et fonctionnalités concernées.

Ne conclus jamais qu'une instruction est fausse uniquement parce que tu n'as pas trouvé la preuve au premier endroit. Cherche raisonnablement dans le projet.

### 3. Classer

Classe chaque écart :

- **🚨 Bloquant** : empêche un nouvel utilisateur d'installer ou lancer le projet.
- **⚠️ Trompeur** : instruction fausse ou obsolète mais contournable.
- **🧹 À nettoyer** : ancien nom, ancien chemin ou information devenue inutile.
- **✅ Vérifié** : affirmation importante contrôlée et correcte.

N'affiche les éléments `✅ Vérifié` qu'en résumé, sauf si l'utilisateur demande un audit exhaustif.

### 4. Cas à ne pas surinterpréter

- Une variable peut être optionnelle.
- Une commande peut être fournie par un outil global.
- Un port peut être configurable.
- Un fichier peut être généré à l'installation.
- Un README peut documenter plusieurs environnements.

Signale l'incertitude au lieu d'inventer une contradiction.

## Sortie

Commence par :

```text
🤥 ReadmeTruth — X contradictions
🚨 X bloquantes
⚠️ X trompeuses
🧹 X à nettoyer
```

Puis pour chaque problème :

```text
README :
"npm run dev"

Réalité :
package.json ne contient aucun script "dev"

Action :
remplacer par "npm run start"
```

Termine par :

- **Ce qui bloque un nouveau clone**
- **Ce qui doit être mis à jour**
- **Verdict** : `✅ README cohérent` ou `❌ README à corriger`

## Correction optionnelle

Si l'utilisateur demande de corriger :

1. modifie uniquement les passages prouvés comme faux ou incomplets ;
2. conserve le ton et la structure du README ;
3. ne réécris pas toute la documentation sans raison ;
4. vérifie une seconde fois les commandes et chemins après modification.
