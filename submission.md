# Description de la remise

### Nom complet: Mohamed Lamine Niang,Tasnim Khalil  
### NIP: 537 281 079, 537 404 354

---

## Liste des codes et descriptions des fonctionnalités sélectionnées

- **(FA1)** Sécurisation de l'application via HTTPS / TLS  
  *(Ingress NGINX avec certificat TLS auto-signé)*

- **(FA31)** Gestion centralisée des logs via **Loki + Promtail**  
  *(collecte des logs de tous les pods Kubernetes)*

- **(FA32)** Monitoring des ressources via **Prometheus + Node Exporter**

- **(FA34)** Visualisation du monitoring et des logs via **Grafana**  
  *(datasources Prometheus et Loki configurées, accès anonyme)*

---

## Directives nécessaires à la correction

### 1. Création du cluster et prérequis
Créer le cluster **Kind** à l’aide du fichier fourni, puis installer un contrôleur **Ingress NGINX** si celui-ci n’est pas déjà présent dans l’environnement.

---

### 2. Déploiement des manifests
Déployer l’ensemble des ressources Kubernetes en une seule commande :

```bash
kubectl apply -f ./submission

```

## Accès aux services (HTTPS)

> ⚠️ Le certificat TLS est **auto-signé** ; un avertissement du navigateur est attendu.

### Accès à l'application

| Composant | URL |
|----------|-----|
| UI (Frontend) | https://127.0.0.1/ |
| Admin | https://127.0.0.1/admin/feedback |

---

### Accès aux outils de monitoring

| Outil | URL |
|------|-----|
| Grafana (UI) | https://127.0.0.1/grafana |
| Prometheus (UI) | https://127.0.0.1/prometheus/ |
| Loki (API – readiness) | https://127.0.0.1/loki/ready |

> **Note** : Loki ne fournit pas d’interface web.  
> Les logs sont consultables via **Grafana → Explore → Logs**.
> Utilisation de Flask==2.0.3 et Werkzeug==2.0.3 dans requirements.txt de logic-api pour éviter des problèmes de compatibilité.
> Utilisation de **eclipse-temurin:8-jre-alpine** pour les images de feedback-api.
---
