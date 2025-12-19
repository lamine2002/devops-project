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
