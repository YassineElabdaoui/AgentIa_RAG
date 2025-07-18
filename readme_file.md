# RAG Juridique - Assistant IA pour Conseils Juridiques

## 📋 Description

Ce projet est un système RAG (Retrieval-Augmented Generation) conçu pour fournir des réponses juridiques précises et contextualisées selon les cas spécifiques et en se basant sur le droit du pays concerné.

Le système utilise une architecture basée sur N8N avec intégration de Pinecone pour la vectorisation des documents juridiques et OpenAI pour la génération de réponses intelligentes.

## 🎯 Fonctionnalités

- **Analyse juridique contextuelle** : Fournit des réponses basées sur la législation locale
- **Vectorisation de documents** : Stockage et recherche sémantique dans Pinecone
- **Mémoire conversationnelle** : Maintient le contexte des conversations
- **Upload de documents** : Permet l'ajout de nouveaux documents juridiques
- **Interface chat** : Interaction naturelle via webhook

## 🏗️ Architecture

### Composants principaux :

1. **Agent IA Principal** (`pincone_agent_ia.json`)
   - Agent conversationnel avec mémoire
   - Intégration OpenAI GPT-4.1-mini
   - Recherche vectorielle dans Pinecone
   - Webhook pour interactions

2. **Système d'Upload** (`upload_document_pincone.json`)
   - Upload et traitement de documents juridiques
   - Découpage intelligent du texte
   - Vectorisation et indexation automatique

## 🚀 Installation et Configuration

### Prérequis

- N8N installé et configuré
- Compte OpenAI avec API key
- Compte Pinecone avec index créé
- Node.js et npm

### Étapes d'installation

1. **Cloner le repository**
```bash
git clone https://github.com/votre-username/rag-juridique.git
cd rag-juridique
```

2. **Configurer les credentials dans N8N**
   - Créer les connexions OpenAI API
   - Configurer Pinecone API
   - Créer un index Pinecone nommé "aiagent"

3. **Importer les workflows**
   - Importer `pincone_agent_ia_clean.json` dans N8N
   - Importer `upload_document_pincone_clean.json` dans N8N

4. **Configurer les variables d'environnement**
   - Remplacer `YOUR_INSTANCE_ID` par votre ID d'instance N8N
   - Configurer les webhooks selon votre environnement

## 🔧 Configuration

### Credentials à configurer :

1. **OpenAI API** :
   - API Key de votre compte OpenAI
   - Utilisé pour l'embedding et la génération de réponses

2. **Pinecone API** :
   - API Key Pinecone
   - Environment et index configurés

### Paramètres importants :

- **Modèle** : GPT-4.1-mini (configurable)
- **Index Pinecone** : aiagent
- **Dimension des embeddings** : 1536 (OpenAI standard)

## 📖 Utilisation

### 1. Upload de documents juridiques

Utilisez le workflow `upload_document_pincone` pour ajouter des documents :
- Textes de loi
- Jurisprudences
- Codes juridiques
- Réglementations

### 2. Consultation juridique

Interagissez avec l'agent via le webhook configuré :
- Posez des questions juridiques spécifiques
- Obtenez des réponses contextualisées
- Bénéficiez de la mémoire conversationnelle

## 🌍 Adaptabilité Juridique

Le système est conçu pour s'adapter à différents systèmes juridiques :

- **Droit civil** : France, Allemagne, Italie, etc.
- **Common Law** : États-Unis, Royaume-Uni, Canada, etc.
- **Systèmes mixtes** : Écosse, Afrique du Sud, etc.

## 🔒 Sécurité et Confidentialité

- Aucune donnée sensible stockée dans le code
- Credentials gérés via N8N
- Chiffrement des communications
- Respect du RGPD

## 🤝 Contribution

Les contributions sont les bienvenues ! Veuillez :

1. Fork le projet
2. Créer une branche pour votre feature
3. Commiter vos changements
4. Pousser vers la branche
5. Ouvrir une Pull Request

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

## ⚠️ Disclaimer

Ce système est un outil d'assistance et ne remplace pas l'avis d'un avocat qualifié. Les réponses fournies sont à titre informatif uniquement.

## 📞 Support

Pour toute question ou support, veuillez ouvrir une issue dans le repository GitHub.

---

**Note** : Assurez-vous de configurer correctement tous les credentials avant d'utiliser le système en production.