# mediatheque-raspberry-Deploy Project

Ce projet a pour objectif de mettre en place une **chaîne complète d’automatisation** pour le déploiement d’applications sur un **Raspberry Pi**.

### 🔄 Cycle de vie

1. **Dev + Build stage (Localhost)**
   - Compilation et préparation des artefacts.  
   - Génération des fichiers nécessaires au déploiement.  

2. **Check Raspberry Pi version**
   - Vérification de la version actuellement déployée.  
   - Si la Raspberry dispose déjà de la dernière version, aucune mise à jour n’est effectuée.  

3. **System Install (Raspberry Pi)**
   - Installation ou mise à jour des dépendances système.  
   - Configuration de l’environnement nécessaire à l’application.  

4. **Deploy (Raspberry Pi)**
   - Déploiement automatique de l’application.  
   - Mise en production avec la version la plus récente.  

---

 L’objectif principal est de **sécuriser et automatiser le  déploiement** afin d’éviter les réinstallations inutiles et de garantir que la Raspberry Pi exécute toujours la **dernière version stable**.


# Global artchitecture


                                   ┌───────────────────────┐
                                   │    Dev + Build stage  │
                                   │       (Localhost)     │
                                   └───────────┬───────────┘
                                               │
                                               ▼
                                   ┌───────────────────────┐
                                   │   Check Raspberry Pi  │
                                   │     current version   │
                                   └───────┬───────┬───────┘
                                           │       │
                                Outdate ───┘       └─── Latest
                                           │
                                           ▼
                               ┌───────────────────────┐
                               │     Systems Install   │
                               │    (Raspberry Pi)     │
                               └───────────┬───────────┘
                                           │
                                           ▼
                               ┌───────────────────────┐
                               │        Deploy         │
                               │    (Raspberry Pi)     │
                               └───────────────────────┘
