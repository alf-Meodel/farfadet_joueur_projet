
# 3. Organisation et Étude du Projet
![border](../../assets/line/border_deco_rt.png)

## Contexte du Projet

- Le Farfadet Joueur cherche à moderniser sa présence en ligne
- Abandon d'une ancienne solution de vitrine mutualisée trop coûteuse
- Besoin d'une solution sur mesure pour gérer leur visibilité et leurs événements
- Manque d'espace physique nécessitant une extension virtuelle


## Enjeux

- Améliorer la visibilité en ligne de l'entreprise
- Faciliter la gestion des événements et des réservations
- Optimiser le temps de gestion du contenu promotionnel
- Renforcer la relation client et la communication des actualités
- Valoriser les produits phares sans passer par l'e-commerce

## Problématiques

- Comment permettre une gestion simple du contenu promotionnel ?
- Comment optimiser la gestion des événements et des réservations ?
- Comment automatiser la mise en avant des produits sans créer une boutique en ligne ?
- Comment intégrer une solution qui reste facile à maintenir pour les gérants ?

## Exigences Fonctionnelles

### Interface d'administration
- Gestion des produits mis en avant
- Gestion des événements
- Gestion des réservations

### Interface publique
- Vitrine des produits phares
- Calendrier des événements
- Système de réservation
- Présentation de l'entreprise

## Règles de Gestion

- Validation des réservations par les administrateurs
- Limitation du nombre de participants par événement
- Gestion des délais d'annulation
- Contrôle des contenus publiés
- Gestion des droits d'accès

## Composition des Équipes

- Product Owner : Client (Léa et Mathieu)
- Développeur(s)
- Designer UI/UX
- Chef de projet
- Justin (nouveau membre mentionné dans les documents)

## Personas

### Administrateurs (Léa et Mathieu)
- Gérants de la boutique
- Peu de temps disponible
- Besoin d'une interface simple
### Clients types
- Familles cherchant des activités
- Joueurs réguliers
Organisateurs d'événements

## Méthodologie Utilisée

Approche Agile
Cycles courts de développement
Points réguliers avec le client
Méthode itérative avec présentations de prototypes

## Dictionnaire de Données

*Présentation du dictionnaire de données*

## Sécurité

### Défense en Profondeur

La stratégie de défense en profondeur s'articule autour de plusieurs couches de sécurité :

1. **Niveau Infrastructure**
   - Hébergement sécurisé (VPS/Heroku)
   - Pare-feu configuré pour n'autoriser que les ports nécessaires (80, 443, SSH)
   - Mise à jour régulière du système d'exploitation
   - Configuration HTTPS avec certificat SSL/TLS

2. **Niveau Application**
   - Fastify configuré avec helmet pour les en-têtes de sécurité
   - Validation des données entrantes avec JSON Schema
   - Rate limiting pour prévenir les attaques par force brute
   - Gestion des sessions avec des JWT sécurisés

3. **Niveau Base de Données**
   - PostgreSQL configuré avec accès restreint
   - Chiffrement des données sensibles
   - Sauvegardes automatiques chiffrées

### Réduction de la Surface d'Attaque


1. **Frontend (React.js)**
   - Utilisation de dependencies sécurisées et à jour
   - Sanitization des données affichées
   - Protection contre les attaques XSS
   - Implementation du CSP (Content Security Policy)

2. **Backend (Fastify)**
   - Désactivation des en-têtes sensibles
   - Validation stricte des entrées utilisateur
   - Gestion des erreurs sans divulgation d'informations sensibles
   - API documentation limitée en production

3. **Base de Données**
   - Accès uniquement depuis le backend
   - Ports non exposés publiquement
   - Requêtes paramétrées pour prévenir les injections SQL

### Politique de Moindre Privilège


1. **Authentification**
   - JWT avec expiration courte
   - Refresh tokens sécurisés
   - Validation des sessions côté serveur

2. **Autorisation**
   - Rôles utilisateur clairement définis (admin, utilisateur)
   - Vérification des permissions à chaque requête API
   - Isolation des ressources par utilisateur

3. **Base de Données**
   - Utilisateur PostgreSQL dédié avec permissions minimales
   - Schémas séparés pour différentes parties de l'application
   - Audit des accès importants

### Conformité RGPD


1. **Gestion des Données Personnelles**
   - Collecte minimale des données nécessaires
   - Chiffrement des données sensibles dans PostgreSQL
   - Durée de conservation définie et respectée

2. **Droits des Utilisateurs**
   - Interface de téléchargement des données personnelles
   - Possibilité de suppression du compte
   - Système de consentement explicite

3. **Documentation et Processus**
   - Politique de confidentialité claire
   - Registre des traitements
   - Procédure en cas de violation de données

4. **Mesures Techniques**
   - Logs d'audit des accès aux données personnelles
   - Chiffrement en transit (HTTPS)
   - Chiffrement au repos des données sensibles

---

<a href="../../README.md">
<img src="../../assets/button/back_to_top.png" alt="Retour au sommaire" style="width: 150px; height: auto;">
</a>

![border](../../assets/line/line-pink-point_l.png) 