# 🏋️ Cross Training EPS — Carnet d'Entraînement Numérique

**Application pédagogique numérique pour l'enseignement du Cross Training en EPS — Terminale Baccalauréat**

> Lycée Charlotte DELBO — Dammartin-en-Goële — Académie de Créteil  
> Champ d'Apprentissage n°5 · « Réaliser une activité physique pour développer ses ressources et s'entretenir »

---

## 📋 Présentation

Cette application web est un **carnet d'entraînement numérique** conçu pour accompagner les élèves de Terminale tout au long du cycle Cross Training. Elle fonctionne entièrement dans le navigateur (smartphone, tablette, ordinateur), sans installation, avec synchronisation Firebase en temps réel.

### Objectifs pédagogiques

- Expérimenter et évaluer les skills (mouvements) Cross Training
- Construire un WOD cohérent adapté à son mobile d'entraînement
- Analyser ses performances et réguler son intensité via la fréquence cardiaque
- Préparer l'épreuve du Baccalauréat EPS (AFL1, AFL2, AFL3)

---

## 🚀 Démarrage rapide

### Pour l'enseignant

1. Ouvrir le fichier `CrossTraining_EPS_v9.html` dans un navigateur
2. Sur l'écran de code session, cliquer **🔐 Espace enseignant** (bouton discret en bas)
3. Entrer le mot de passe : `epscrosstraining`
4. Aller dans l'onglet **🔑 Code** pour générer ou définir le code de session du jour
5. Écrire le code au tableau — les élèves l'entrent pour accéder à l'application

### Pour les élèves

1. Ouvrir le même fichier HTML dans le navigateur (ou via lien partagé)
2. Entrer le **code de session** donné par le professeur (4 à 6 caractères)
3. Le profil est mémorisé : pas besoin de le ressaisir à chaque séance avec le même code
4. Naviguer avec les 6 onglets du bas

---

## 📱 Interface — Les 6 onglets

### 👤 Profil
- Nom, Prénom, Classe, Âge (pour calcul FCmax)
- Genre (♂️ Homme / ♀️ Femme / ⚧️ Autre) — adapte les niveaux des exercices
- Mobile d'entraînement (optionnel — peut être choisi plus tard)
- Répartition des points AFL pour le Bac (4-4 / 6-2 / 2-6)
- Bouton **📤 Sync** pour envoyer les données au professeur via Firebase

### 📚 Skills (Bibliothèque)
- 13 mouvements classés en 4 familles : Force · Explosivité · Cardio · Résistance
- Pour chaque skill : description, muscles sollicités, niveaux (1 à 4) adaptés au genre
- **Mode Juge intégré** : boutons ✅ VALIDE et ❌ NO REP pour comptabiliser les répétitions
- Enregistrement du test : niveau, intensité ressentie (1-5), validité, commentaire

### 🏗️ Mon WOD
- Choix du mobile pour ce WOD (peut différer du profil — mode découverte possible)
- 5 types de WOD : **AMRAP · TABATA · EMOM · E2MOM · FOR TIME**
- Sélection des exercices en 2 étapes : choix du skill → choix du niveau avec descriptif complet
- Paramètres dynamiques selon le type (temps effort/repos pour TABATA, durée cycle pour EMOM/E2MOM)
- **Aperçu temps réel** : calcul automatique de la durée totale TABATA, repos prévu EMOM
- Validation automatique des critères Bac (min. 4 exercices, haut/bas corps, abdo, cardio)

### ⏱️ Séances
**Avant la séance :**
- Modal de pré-lancement avec identification du juge (obligatoire) et confirmation du mobile

**Pendant la séance :**
- Chrono global toujours visible (durée totale)
- **Chrono intelligent selon le type de WOD :**
  - 🔴 TABATA : alternance rouge (EFFORT) / bleu (REPOS) avec barre de progression + vibration
  - 🔵 EMOM : compte à rebours 60s, change de couleur au passage effort→repos
  - 🟣 E2MOM : idem sur 120s
- Changement de niveau en cours de séance (▼ / ▲ par exercice)
- Boutons **✅ VALIDE** / **❌ NO REP** par exercice — % de validité en temps réel
- Analyseur FC : entrer sa fréquence cardiaque pour voir dans quelle zone on se trouve

**Fin de séance :**
- Modal de ressenti WOD : 🔥 Top / 👍 Bien / 😅 Difficile / 😰 Trop dur (conseil contextuel)
- Enregistrement : score, FC moyenne, sensations musculaires, commentaire

### 📊 Analyse & Annotations
- Analyseur FC : visualisation de la zone d'intensité (Mobile 1 ou 2) avec jauge colorée
- Muscles les plus sollicités (graphique à barres)
- Répartition par famille de mouvements
- Validation WOD pour le Bac (6 critères)
- **Zone d'annotations** : notes libres par exercice + note générale, sans modifier le WOD Bac
  - Affiche les données juge de la dernière séance (valides / no rep)
  - Pré-rempli avec le ressenti global (🔥 Top, etc.)

### 🎓 Bilan & Bac
- Fiche récapitulative complète : profil, stats, WOD construit, zones FC
- Barème Bac complet : AFL1 (12pts), AFL2 et AFL3 (8pts au choix)
- Progression graphique des dernières séances
- Zones FC personnalisées selon l'âge (FCmax = 220 − âge)

---

## 🔒 Sécurité & RGPD

| Élément | Traitement |
|---|---|
| Identification élève | Format **Prénom.N** (ex: Maxime.M) dans Firebase |
| Nom complet | Stocké uniquement sur l'appareil de l'élève (localStorage) |
| Clés Firebase | Encodées en base64 dans le code — jamais affichées |
| Mot de passe enseignant | Encodé (base64) — non lisible dans le code source |
| Données de session | Expiration automatique à 12h |
| Présence élève | Enregistrée sous forme anonymisée (Prénom.N + classe) |

---

## 🔐 Espace Enseignant

Accès via le bouton **🔐 Espace enseignant** (écran de code session) ou l'icône 🔐 dans le header.

**Mot de passe :** `epscrosstraining`

### Onglets du tableau de bord

| Onglet | Contenu |
|---|---|
| 🟢 **Live** | Présence en temps réel : statut de chaque élève (Actif / Parti / Hors ligne) |
| 👨‍🎓 **Carnets** | Carnets d'entraînement synchronisés par élève |
| 📊 **Stats** | Vue agrégée : répartition mobiles, WOD types, classes |
| 🔑 **Code** | Génération / personnalisation du code de session du jour |
| 📅 **Séance** | Filtrage des séances par date |

### Suivi de présence en temps réel

- L'enseignant voit instantanément si un élève **quitte l'application** (onglet 🟡 Parti)
- Bouton **⚠️ Alerter** : envoie un message push sur l'appareil de l'élève
- L'élève reçoit une bannière d'avertissement à son retour

---

## 🏗️ Architecture technique

```
CrossTraining_EPS_v9.html          ← Fichier unique, autonome
├── HTML                           ← Interface responsive mobile-first
├── CSS                            ← Design sombre, sportif, tactile
└── JavaScript
    ├── Firebase Firestore          ← Carnets élèves (sync données)
    ├── Firebase Realtime DB        ← Présence live + codes session + alertes
    ├── localStorage                ← Données offline + profil par session
    └── Logique pédagogique        ← WOD, chrono, FC, VALID/NO REP
```

### Firebase — Projet
| Paramètre | Valeur |
|---|---|
| Nom | Carnet d'entraînement CT |
| ID projet | `carnet-d-entrainement` |
| Firestore | Collection `crosstraining_students` |
| Realtime DB | `ct_presence/`, `ct_session_codes/`, `ct_warnings/` |
| Région RTDB | `europe-west1` |

---

## 📐 Barème Bac EPS — Cross Training

```
Total : 20 points
├── AFL1 : 12 points (évalué le jour de l'épreuve)
│   ├── PRODUIRE (8 pts) : s'engager dans l'intensité du mobile, maintenir, technique
│   └── ANALYSER (4 pts) : mettre en relation données & ressentis, réguler
└── AFL2 + AFL3 : 8 points (au choix de l'élève)
    ├── Répartition 4-4 (équilibre)
    ├── Répartition 6-2 (priorité AFL2 — entraînement)
    └── Répartition 2-6 (priorité AFL3 — coopération/juge)
```

### WOD Bac — critères
- Durée : **16 à 20 minutes**
- **Minimum 4 mouvements** enchaînés
- Obligatoirement : haut du corps + bas du corps + abdominaux + cardio
- Type au choix : AMRAP, TABATA, EMOM, E2MOM, FOR TIME

---

## 💪 Skills disponibles

| Famille | Exercices |
|---|---|
| 💪 **Force** | Pompes (H/F), Dips, Kettlebell Swing (H/F) |
| ⚡ **Explosivité** | Squats, Box Jump, Fentes |
| 🫀 **Cardio** | Jumping Jack, Corde à sauter, Mountain Climber, Burpees (H/F) |
| 🛡️ **Résistance** | Sit-up (H/F), Gainage dynamique, Russian Twist |

Chaque exercice a **3 à 4 niveaux de difficulté** (1 à 4 points Bac), adaptés au genre de l'élève.

---

## ❓ FAQ

**Q : L'application fonctionne-t-elle sans internet ?**  
R : Oui. Toutes les fonctionnalités pédagogiques fonctionnent offline. La synchronisation Firebase nécessite une connexion, mais les données sont d'abord sauvegardées localement.

**Q : Les élèves doivent-ils entrer leur code à chaque séance ?**  
R : Non. Le code est mémorisé 12 heures. Pour une nouvelle séance le lendemain, il faudra ressaisir le code. Le profil est automatiquement rechargé dès que le même code est entré.

**Q : Comment changer le code de session en cours de cours ?**  
R : Espace enseignant → onglet 🔑 Code → Générer ou personnaliser. Les élèves qui sont déjà connectés restent actifs ; les nouveaux entrants devront utiliser le nouveau code.

**Q : Les données élèves sont-elles vraiment anonymisées ?**  
R : Dans Firebase, les élèves apparaissent sous la forme `Maxime.M`. Le nom complet ne quitte jamais l'appareil de l'élève. L'enseignant peut recroiser si nécessaire (il connaît ses élèves).

**Q : L'application peut-elle s'installer sur smartphone ?**  
R : Le fichier HTML peut être ajouté en favori sur l'écran d'accueil depuis Safari (iOS) ou Chrome (Android). Il n'est pas une PWA officielle mais se comporte comme une webapp.

---

## 📁 Fichiers

| Fichier | Description |
|---|---|
| `CrossTraining_EPS_v9.html` | Application complète (fichier unique) |
| `README_CrossTraining_EPS.md` | Cette documentation |

---

## 🛠️ Déploiement recommandé

1. **Option simple** : Partager le fichier `.html` via mail, ENT, Pronote
2. **Option hébergée** : Déposer sur Firebase Hosting, GitHub Pages ou tout hébergeur statique
3. **Option locale** : Ouvrir directement dans le navigateur depuis un dossier ou clé USB

> ⚠️ Pour que la synchronisation Firebase fonctionne, une connexion internet est requise lors du Sync. L'application reste utilisable entièrement hors ligne.

---

*Application développée pour le Lycée Charlotte DELBO — Dammartin-en-Goële*  
*Référentiel national CA5 — EPS Baccalauréat Général et Technologique*
