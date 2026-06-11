# 🏥 Bahjawa Medical Center

[![Laravel](https://img.shields.io/badge/Laravel-13.5-red.svg)](https://laravel.com/)
[![PHP](https://img.shields.io/badge/PHP-8.4-blue.svg)](https://php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-green.svg)](https://mysql.com/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4-cyan.svg)](https://tailwindcss.com/)
[![Railway](https://img.shields.io/badge/Railway-Deployed-purple.svg)](https://railway.app/)

# 🏥 Bahjawa Medical Center — Gestion de Cabinet Médical
 
> Projet universitaire réalisé dans le cadre du module **Programmation Backend (PHP) — Semestre S6**  
> Université Cadi Ayyad — Faculté des Sciences Semlalia de Marrakech  
> Année universitaire 2025/2026
 
---
 
## 👥 Équipe
 
| Nom |
|-----|
| DOUBABI Ali |
| SAMID Oussama |
| FARAH Mariam |
| ECHCHAFIAI Aicha |
 
**Encadrantes :** Pr. JABIR Somaya — Pr. BABA Naima  
**Responsable du module :** Pr. ELALAOUI Hasna
 
---
 
## 📋 Description du projet
 
**Bahjawa Medical Center** est une application web complète de gestion de cabinet médical développée avec **Laravel 13**. Elle centralise la gestion des rendez-vous, des dossiers médicaux, des ordonnances et du suivi d'activité pour les médecins, secrétaires et patients.
 
🔗 **Application en ligne :** [https://medical-center-bahjawi.up.railway.app](https://medical-center-bahjawi.up.railway.app)
 
---

## 📸 Aperçu de l'application
 <div align="center">
  <img src="images/login.png" alt="Interface de connexion" width="800" style="border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); border: 1px solid #e2e8f0;"/>
  <br/>
  <em>Figure 1 : Interface de connexion utilisateur</em>
</div>
<div align="center">
  <img src="images/Dashboard principal.png" alt="Dashboard principal Bahjawa Medical Center" width="800" style="border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); border: 1px solid #e2e8f0;"/>
  <br/>
  <em>Figure 2 : Dashboard principal - Vue d'ensemble du cabinet</em>
</div>

<br/>

<div align="center">
  <img src="images/RDV.png" alt="Gestion des rendez-vous" width="800" style="border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); border: 1px solid #e2e8f0;"/>
  <br/>
  <em>Figure 3 : Interface de gestion des rendez-vous</em>
</div>
 

---

## ✨ Fonctionnalités
 
### 👤 Authentification & Rôles
- Inscription / Connexion / Déconnexion sécurisées (Laravel Breeze)
- 4 rôles distincts : **Administrateur**, **Médecin**, **Secrétaire**, **Patient**
- Middlewares de restriction d'accès par rôle
- Vérification d'email à l'inscription
### 🧑‍⚕️ Espace Médecin
- Agenda personnel avec vue calendrier
- Consultation et gestion des dossiers patients
- Saisie des comptes-rendus de consultation
- Génération et export des ordonnances au format **PDF**
- Modification des disponibilités
### 👩‍💼 Espace Secrétaire
- Création et modification des fiches patients
- Recherche multicritère (nom, CIN)
- Planification, modification et annulation des rendez-vous
- Envoi de confirmations par email
### 🙋 Espace Patient
- Prise de rendez-vous en ligne (vérification des créneaux disponibles)
- Modification et annulation de RDV
- Consultation de l'historique médical
- Téléchargement des ordonnances PDF
- Notifications email automatiques (confirmation + rappel 24h avant)
### 🛡️ Espace Administrateur
- Gestion des utilisateurs (ajout, activation/désactivation)
- Gestion des rôles et permissions
- Tableau de bord statistique avec graphiques (Chart.js)
- Suivi de l'activité globale du cabinet
---
 
## 🛠️ Technologies utilisées
 
| Technologie | Rôle |
|---|---|
| **Laravel 13** | Framework backend (architecture MVC) |
| **PHP** | Langage backend |
| **MySQL** | Base de données relationnelle |
| **Tailwind CSS** | Interface utilisateur responsive |
| **Blade** | Moteur de templates Laravel |
| **Eloquent ORM** | Gestion des modèles et relations |
| **Chart.js** | Graphiques statistiques du tableau de bord |
| **DomPDF** | Génération des ordonnances au format PDF |
| **Laravel Mail + Mailtrap** | Envoi et simulation des emails |
| **PHPUnit** | Tests unitaires et fonctionnels |
| **Git / GitHub** | Versionnement collaboratif |
| **Railway** | Déploiement cloud (PaaS) |
 
---
 
## 🗂️ Structure du repository
 
```
cabinet-medical/
│
├── README.md
│
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── AuthController.php
│   │   │   ├── PatientController.php
│   │   │   ├── RendezvousController.php
│   │   │   ├── ConsultationController.php
│   │   │   ├── OrdonnanceController.php
│   │   │   └── AdminController.php
│   │   └── Middleware/
│   │       └── RoleMiddleware.php
│   └── Models/
│       ├── User.php
│       ├── Medecin.php
│       ├── Patient.php
│       ├── Specialite.php
│       ├── Rendezvous.php
│       ├── Consultation.php
│       └── Ordonnance.php
│
├── database/
│   ├── migrations/          # Schéma versionné de la base de données
│   └── seeders/             # Données de test
│
├── resources/
│   └── views/
│       ├── auth/            # Pages de connexion / inscription
│       ├── admin/           # Dashboard administrateur
│       ├── medecin/         # Espace médecin
│       ├── secretaire/      # Espace secrétaire
│       ├── patient/         # Espace patient
│       └── pdf/             # Templates d'ordonnances PDF
│
├── routes/
│   └── web.php              # Toutes les routes de l'application
│
├── tests/
│   └── Feature/
│       ├── AuthTest.php
│       ├── ModelTest.php
│       ├── ConsultationTest.php
│       ├── PatientTest.php
│       └── PasswordResetTest.php
│
├── docs/
│   ├── Rapport_projet.pdf
│   ├── diagramme_cas_utilisation.png
│   ├── diagramme_classes.png
│   ├── diagramme_sequence_auth.png
│   ├── diagramme_sequence_rdv.png
│   └── diagramme_sequence_consultation.png
│
├── .env.example             # Template des variables d'environnement
├── composer.json
└── package.json
```
 
---
 
## 🚀 Installation & déploiement local
 
### Prérequis
 
- PHP >= 8.2
- Composer
- Node.js & npm
- MySQL
- Git
### Étapes d'installation
 
1. **Cloner le repository**
```bash
   git clone https://github.com/<votre-username>/cabinet-medical.git
   cd cabinet-medical
```
 
2. **Installer les dépendances PHP**
```bash
   composer install
```
 
3. **Installer les dépendances frontend**
```bash
   npm install && npm run build
```
 
4. **Configurer l'environnement**
```bash
   cp .env.example .env
   php artisan key:generate
```
   Puis éditer `.env` avec vos paramètres de base de données et mail :
```env
   DB_DATABASE=cabinet_medical
   DB_USERNAME=root
   DB_PASSWORD=
 
   MAIL_MAILER=smtp
   MAIL_HOST=sandbox.smtp.mailtrap.io
   MAIL_PORT=2525
   MAIL_USERNAME=your_mailtrap_user
   MAIL_PASSWORD=your_mailtrap_password
```
 
5. **Créer la base de données et exécuter les migrations**
```bash
   php artisan migrate --seed
```
 
6. **Lancer le serveur de développement**
```bash
   php artisan serve
```
   L'application est accessible sur `http://localhost:8000`
 
---
 
## 🧪 Tests
 
Lancer tous les tests unitaires et fonctionnels :
```bash
php artisan test
```
 
| Suite de tests | Fonctionnalités couvertes |
|---|---|
| `ModelTest` | Relations Eloquent, rôles, statuts |
| `AuthTest` | Connexion, inscription, redirection par rôle |
| `PasswordResetTest` | Réinitialisation du mot de passe |
| `ConsultationTest` | Création consultation, génération PDF |
| `PatientTest` | CRUD patients, contrôle d'accès |
 
**Résultat attendu :** tous les tests passent ✅
 
---
 
## 📐 Architecture MVC
 
```
Requête HTTP
     │
     ▼
  Router (web.php)
     │
     ▼
Middleware (auth, role)
     │
     ▼
Controller  ──────►  Model (Eloquent ORM)  ──────►  MySQL
     │
     ▼
   View (Blade)
     │
     ▼
Réponse HTTP
```
 
---
 
## 🗄️ Modèle de données (principales entités)
 
```
users          ──── medecins  ──── specialites
    │               │
    │               ├──── rendezvous ──── patients
    │               │          │
    └──── patients  │          └──── consultations ──── ordonnances
                    │
                    └──── disponibilites
```
 
---
 
## 🔐 Comptes de test (après seeding)
 
| Rôle | Email | Mot de passe |
|---|---|---|
| Administrateur | admin@cabinet.ma | password |
| Médecin | medecin@cabinet.ma | password |
| Secrétaire | secretaire@cabinet.ma | password |
| Patient | patient@cabinet.ma | password |
 
---
 
## 🌐 Déploiement (Railway)
 
Le projet est déployé en continu via Railway connecté au dépôt GitHub.
 
Variables d'environnement à configurer sur Railway :
```
APP_ENV=production
APP_KEY=<générer avec php artisan key:generate>
DB_CONNECTION=mysql
DB_HOST=<host Railway MySQL>
DB_DATABASE=<nom de la base>
DB_USERNAME=<user>
DB_PASSWORD=<password>
MAIL_*=<configuration email production>
```
 
---
 
## 📚 Références
 
- [Documentation Laravel](https://laravel.com/docs)
- [Documentation Tailwind CSS](https://tailwindcss.com/docs)
- [Documentation Chart.js](https://www.chartjs.org/docs/)
- [Guide Scrum](https://scrumguides.org)
- Supports de cours S6 : Programmation Backend (PHP), Université Cadi Ayyad
---
 
## 📄 Licence
 
Projet académique — Université Cadi Ayyad, Faculté des Sciences Semlalia de Marrakech © 2025/2026
