# DRL-STAGE-ROBOTIQUE
Apprentissage Automatique pour l'Allocation de Tâches par des Bras Robotiques
# Apprentissage Automatique pour l'Allocation de Tâches par des Bras Robotiques

## Informations du Projet
- Étudiant : Aymane IBN EL QORCHY  
- Formation : Master Informatique – Université Sidi Mohamed Ben Abdellah (Fès)  
- Stage : Laboratoire LS2N, Nantes Université  
- Période : 2024 – 2025  

---

## Objectifs
Développement d’un système d’apprentissage par renforcement pour un robot manipulateur Kuka 7DOF, visant à :  
- Atteindre des objets avec précision  
- Apprendre de manière autonome par essai-erreur  
- Servir de base pour une coordination multi-robots  
- Préparer l’intégration dans un système MILP global  

---

## Méthodologie Technique

### Algorithme d’Apprentissage
- Méthode : PPO (Proximal Policy Optimization)  
- Raison du choix : stabilité et efficacité dans les environnements robotiques  

### Environnement de Simulation
- Moteur physique : PyBullet 3D  
- Interface RL : Gymnasium (ancien OpenAI Gym)  
- Robot : Kuka 7DOF (7 articulations)  

### Fonction de Récompense Hybride
- Signal dense : -10 × distance (guidage continu)  
- Bonus progressifs : paliers de 1.0m → 0.05m  
- Bonus temporel : incitation à l’efficacité  

### Architecture Réseau
- Structure : 20 → 64 → 64 → 7 neurones  
- Entrées : positions articulaires, vitesses, positions objet/effecteur  
- Sorties : 7 actions continues pour le contrôle articulaire  

---

## Résultats

### Performance Finale
- Taux de réussite : 85% (17/20 épisodes)  
- Distance moyenne finale : 0.163m  
- Temps de convergence : environ 50k timesteps (≈ 90 minutes)  
- Meilleure performance : 0.136m (au-delà de l’objectif)  

### Métriques d’Évaluation
- Précision : distance euclidienne finale moyenne  
- Efficacité : nombre de steps par épisode  
- Robustesse : tests sur positions aléatoires d’objets  
- Reproductibilité : 20 épisodes déterministes  

---

## Technologies et Dépendances

### Langages et Frameworks
- Python 3.8+  
- PyBullet 3.2.5  
- Stable-Baselines3 2.0.0  
- Gymnasium 0.28.1  

### Outils de Développement
- TensorBoard 2.13.0 (suivi de l’entraînement)  
- Matplotlib / Seaborn (visualisation)  
- NumPy / Pandas (analyse de données)  

---

## Structure du Projet
```bash
apprentissage-robotique-Stage-kuka/
├── README.md                        # Documentation (ce fichier)
├── requirements.txt                 # Dépendances Python
├── apprentissage_robotique_kuka.ipynb  # Notebook principal complet
├── models/                          # Modèles sauvegardés
│   └── best_model.zip               # Modèle final
└── docs/                            # Documentation
    └── rapport_stage.pdf            # Rapport de stage
