# 🚀 SecureLink : Détection Intelligente de Phishing
> **Projet de Fin d'Études (PFE) | ECE Paris**

SecureLink est une plateforme web conçue pour protéger le grand public contre le phishing. Elle utilise un moteur de **scoring hybride à 12 couches** combinant Machine Learning, analyses réseau et inspection de contenu pour fournir un verdict clair (feu tricolore).

---

## 🏗️ Architecture du Système
SecureLink repose sur une architecture moderne et asynchrone :
*   **Frontend** : React 19, Tailwind CSS, shadcn/ui.
*   **Backend** : FastAPI (Python 3.12) pour l'orchestration haute performance.
*   **Base de données** : MongoDB (Stockage flexible des résultats d'analyse).
*   **Intelligence Artificielle** : Modèle RandomForest (scikit-learn) avec 98,8% d'accuracy.
*   **Automation** : Playwright pour la capture d'écran automatisée des sites suspects.

## 🛡️ Expertise Technique (Le Pipeline d'Analyse)
L'URL soumise traverse simultanément 12 couches d'inspection :
1.  **Machine Learning** : Analyse de 20 features structurelles de l'URL.
2.  **Règles Déterministes** : Heuristiques sur les TLD suspects et l'entropie.
3.  **Vérifications Réseau** : DNS, certificats SSL/TLS (validité et émetteur), WHOIS.
4.  **Inspection de Contenu** : Détection de formulaires de login, usurpation de marque et typosquatting.
5.  **Intelligence Externe** : Intégration de l'API Google Safe Browsing.
6.  **Signature de Kits** : Fingerprinting regex pour identifier les kits de phishing connus.

## ✅ Performance & Validation
*   **Benchmark** : Validé sur un dataset réel de 74 URLs.
*   **Fiabilité** : F1-Score de 100% lors des tests finaux.
*   **Sécurité** : Protection native contre les attaques SSRF et Rate Limiting intégré.

---
📬 **Contact** : [LinkedIn](https://www.linkedin.com/in/franck-deffo)
