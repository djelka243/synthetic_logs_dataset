# synthetic_logs_dataset

## Description

Ce dataset contient des journaux (logs) générés de manière synthétique pour simuler des tentatives d'accès non autorisées à un serveur via SSH. Il est conçu pour être utilisé dans des études de sécurité informatique, des analyses de détection d'intrusions, et la formation d'algorithmes d'apprentissage automatique pour la classification des menaces.

## Structure du fichier

Le fichier CSV est structuré comme suit :

| log                                                                                                   | label              |
|-------------------------------------------------------------------------------------------------------|--------------------|
| sshd[23458]: Failed password for invalid user root from 192.168.1.1 port 22 ssh2                      | Brute Force Attempt|
| sshd[54321]: Failed password for root from 172.16.0.10 port 2222 ssh2                                 | Brute Force Attempt|
| ...                                                                                                   | ...                |

### Colonnes

1. **log**: Contient le message du journal détaillant la tentative de connexion, y compris :
   - Le service (sshd)
   - L'ID du processus
   - Le type d'erreur (échec du mot de passe, utilisateur invalide, etc.)
   - L'adresse IP source
   - Le port utilisé
   - Le protocole (ssh2)

2. **label**: Indique la catégorie de l'événement enregistré. Dans ce cas, tous les enregistrements sont étiquetés comme "Brute Force Attempt", signalant qu'il s'agit de tentatives d'accès non autorisées.

## Utilisation

Ce dataset peut être utilisé pour :

- **Détection d'intrusions** : Entraîner des modèles pour identifier des comportements anormaux basés sur des logs.
- **Analyse de la sécurité** : Évaluer les méthodes de protection contre les attaques par force brute.
- **Recherche académique** : Étudier les tendances des attaques et développer des stratégies de défense.

## Pré-requis

- Logiciel de traitement de données comme Python (avec des bibliothèques telles que pandas pour le traitement de fichiers CSV).
- Environnement de développement pour le machine learning, tel que TensorFlow ou scikit-learn, si vous prévoyez d'effectuer des analyses prédictives.

## Exemple de chargement des données

Voici un exemple de code Python pour charger et afficher les données :

```python
import pandas as pd

# Chargement du dataset
df = pd.read_csv('synthetic_logs_with_normal_activities.csv')

# Affichage des premières lignes
print(df.head())
