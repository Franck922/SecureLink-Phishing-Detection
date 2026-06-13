# 🚀 SecureLink : Plateforme Intelligente de Détection de Phishing
> **Projet de Fin d'Études (PFE) | Expertise Cybersécurité & IA | ECE Paris**

SecureLink est une solution hybride conçue pour protéger les utilisateurs contre les attaques de phishing sophistiquées. Elle combine **Machine Learning**, **Analyse Heuristique** et **OSINT** pour fournir un verdict de sécurité en temps réel.

---

## 🛡️ Expertise Cyber : Le Pipeline d'Analyse (12 Couches)
Le cœur de SecureLink repose sur une analyse multicouche asynchrone orchestrée par **FastAPI** :
1.  **Moteur IA** : Modèle RandomForest entraîné pour détecter les anomalies structurelles des URLs (Précision : 98.8%).
2.  **Analyse de Typosquattage** : Détection de marques usurpées via l'algorithme de Levenshtein et la recherche d'homoglyphes.
3.  **Vérifications Réseau & Trust** : Analyse SSL/TLS, réputation DNS, WHOIS et validation des entités via l'API Pappers.
4.  **Inspection de Contenu** : Fingerprinting de kits de phishing (Office365, PayPal, etc.) et détection de formulaires de login suspects.
5.  **Protection Anti-SSRF** : Validation stricte des IPs pour empêcher l'analyse de réseaux internes privés.

## ✅ Benchmark & Performances
*   **Dataset de test** : 74 URLs réelles (Phishing & Legitimate).
*   **Précision (Accuracy)** : 100% sur le jeu de test final grâce au scoring hybride.
*   **Vitesse** : Analyse complète en moins de 3 secondes grâce à l'exécution concurrente (Python Asyncio).

---

## 🏗️ Structure du Projet

---

## 🚀 Installation & Lancement

### Prérequis
- Python 3.10+ | Node.js 18+ | MongoDB (local ou Atlas)
- Playwright : `playwright install chromium`

### Démarrage Rapide
1. **Backend** :
   ```bash
   cd backend
   cp .env.example .env # Configurer vos clés API
   pip install -r requirements-local.txt
   uvicorn server:app --host 0.0.0.0 --port 8001
cd ../frontend
yarn install
yarn start
### Cles API (dans backend/.env)

| Cle | Obligatoire | Ou l'obtenir |
|-----|-------------|-------------|
| MONGO_URL | Oui | MongoDB local ou [Atlas](https://cloud.mongodb.com) |
| GEMINI_API_KEY | Non | [Google AI Studio](https://aistudio.google.com/apikey) (pour le chatbot) |
| GOOGLE_SAFE_BROWSING_KEY | Non | [Google Cloud Console](https://console.cloud.google.com/apis/library/safebrowsing.googleapis.com) |
| PAPPERS_API_KEY | Non | [pappers.fr/api](https://www.pappers.fr/api) (verification entreprise FR) |

Les cles optionnelles activent des couches supplementaires. L'analyse fonctionne sans elles avec la degradation gracieuse.
