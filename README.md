# QA avec ChromaDB, LLaMa-2 et Gradio

Ce projet implémente une solution de question-réponse (QA) en utilisant **ChromaDB** comme base de données vectorielle, **LLaMa-2-7B-Chat** comme modèle de génération et **Gradio** pour l'interface utilisateur. Il inclut également la gestion des rôles et des seuils pour améliorer la pertinence des réponses.

## Fonctionnalités

- **RAG (Retrieval-Augmented Generation)** : Amélioration des réponses grâce à une récupération efficace des documents.
- **ChromaDB** : Stockage et recherche efficace des embeddings textuels.
- **LLaMa-2-7B-Chat** : Génération de réponses contextuelles et précises.
- **Gradio** : Interface utilisateur interactive et accessible via le web.
- **Gestion des rôles** : Filtrage et adaptation des réponses selon les permissions de l'utilisateur.
- **Seuil de pertinence** : Vérification de la qualité des réponses avant affichage.

## Gestion des rôles et types de questions

Dans cette tâche, j’ai développé un modèle d’intelligence artificielle capable de fournir des réponses personnalisées en fonction de trois rôles d’utilisateurs :

1. **Utilisateur Simple**
2. **Utilisateur Développeur (Dev)**
3. **Utilisateur Administrateur (Admin)**

Le modèle utilise l’approche Retrieval-Augmented Generation (RAG) pour répondre à quatre types de questions :

1. **Questions spécifiques à chaque rôle** : Le modèle génère des réponses précises adaptées aux spécificités de chaque rôle d’utilisateur.

   <img width="947" alt="RAG question par Simple utilisateur 1 PNG" src="https://github.com/user-attachments/assets/5f68d357-4d56-4452-be32-400e836b78d6" />
   <img width="938" alt="RAG question par Dev utilisateur 1 PNG" src="https://github.com/user-attachments/assets/e7cf0675-d9f9-4354-880a-4cffcacc934d" />
   
   <img width="941" alt="RAG question par Admin utilisateur 1 PNG" src="https://github.com/user-attachments/assets/15df3268-b100-4518-9c26-60f88cec2ffb" />

3. **Questions inter-rôles** : Si, par exemple, un utilisateur Dev pose une question qui appartient au rôle Admin, le système répond avec *"Cette question est associée à un autre rôle."*.

   <img width="940" alt="RAG question dans d'autre role" src="https://github.com/user-attachments/assets/afc51e43-c153-44db-819e-9f6fb4a18e57" />

5. **Questions hors contexte** : Si la question ne correspond à aucune donnée dans la base associée aux rôles définis, le modèle répond avec *"Cette question ne correspond à aucun des rôles définis."*.
   
<img width="939" alt="RAG question hors context" src="https://github.com/user-attachments/assets/e2501165-1730-4dbb-a77f-3fd3c6620c50" />

   
7. **Questions communes** : Certaines questions peuvent être posées par tous les rôles (Simple, Dev, Admin), mais le système répondra de manière différente selon le rôle, fournissant des réponses adaptées au contexte de chaque utilisateur.

<img width="927" alt="RAG question par Simple utilisateur 5 communes" src="https://github.com/user-attachments/assets/b94be92f-d7ff-475a-8ccc-edc163e07bf6" />
<img width="927" alt="RAG question par Dev utilisateur 4 communes" src="https://github.com/user-attachments/assets/87a803e4-b046-4dbc-947a-325a8c414f36" />
<img width="949" alt="RAG question par Admin utilisateur 4 communes" src="https://github.com/user-attachments/assets/49ad9b60-a5e1-4da5-86c3-524c67865529" />


## Installation

1. **Cloner le dépôt**
   ```bash
   git clone https://github.com/OussamaNaya/RAG-QA-with-ChromaDB-LlaMa-2-Gradio.git
   cd RAG-QA-with-ChromaDB-LlaMa-2-Gradio
   ```

2. **Télécharger et préparer LLaMa-2**
   - Suivre les instructions de Meta pour obtenir le modèle.
   - Charger les poids via Hugging Face.



## Usage
- Accéder à l'interface via `http://localhost:7860/`.
- Entrer une question et obtenir une réponse générée.
- Vérifier la pertinence grâce au seuil configuré.
- Tester différents rôles pour observer les variations des réponses.

## Structure du projet


## Améliorations futures
- Intégration de modèles plus légers pour réduire la latence.
- Affinement des rôles et des seuils pour une meilleure précision.
- Ajout d'une gestion utilisateur plus poussée.

## Licence
