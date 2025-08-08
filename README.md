# **Exercice Scrum & Git en 1h : "Le Chaos Maîtrisé"**

**Objectif** : Mettre en pratique **Git/GitHub** dans un workflow Scrum réaliste, avec des consignes fermes pour corriger les mauvaises habitudes.

---

## **Consignes Claires (à écrire au tableau)**

1. **Temps imparti** : 1h chrono.
2. **Équipes** : 2-3 personnes par groupe.
3. **Livrable** :
   - Un repository GitHub avec :
     - Une branche `main` à jour **ET PROTÉGÉE** (exigence).
     - 3 branches de fonctionnalités (`feature/*`) mergées via PR.
     - Un `README.md` avec le **Daily Scrum** fictif du jour.
4. **Règles strictes** :
   - **Interdit** de push directement sur `main`.
   - **Obligatoire** : Revue par un autre membre avant merge.
   - **Daily Scrum** : Chaque membre doit écrire ses tâches dans le README.

---

### **Étapes de l’Exercice**

#### **1. Setup (10 min)**

- **Créer un repo GitHub** (1 par équipe) avec :
  - Protection de `main` : Activer _"Require pull request before merging"_.
  - Template `.gitignore` (ex: `Node` ou `Python` selon leur stack).
- **Cloner en local** :

  ```bash
  git clone https://github.com/votre-repo.git
  cd votre-repo
  ```

#### **2. Daily Scrum (10 min)**

Chaque membre ajoute au `README.md` :

```markdown
## Daily Scrum du [date]

**Membre 1** :

- Hier : A fait X.
- Aujourd’hui : Va faire Y.
- Blocages : Z.

**Membre 2** : ...
```

→ **Commit/Push** sur une branche `docs/daily-scrum`.

#### **3. Travail en Branches (30 min)**

- **Chaque membre crée sa branche** :

  ```bash
  git checkout -b feature/nom-de-la-fonctionnalite
  ```

- **Tâches à choisir** (exemples) :
  - Ajouter un fichier `calculatrice.js` avec une fonction.
  - Corriger un bug fictif dans le README.
  - Ajouter un diagramme Scrum dans `/docs`.
- **Ouvrir une PR sur GitHub** :
  - Titre clair (ex: "FEAT: Ajout calculatrice").
  - Description : _"Reviewer : @camarade-de-groupe"_.

#### **4. Revue & Merge (10 min)**

- **Chaque PR doit être relue** par un autre membre.
- **Commenter** la PR avec :
  - "LGTM" (si tout est bon).
  - "NEEDS WORK" + explication sinon.
- **Merge** après validation.

#### **5. Mise à Jour de `main` (5 min)**

- **Tirer les changements** :

  ```bash
  git checkout main
  git pull origin main
  ```

- **Vérifier** que tout est synchronisé.

---

### **Scénario de "Chaos" (Pour les Testeurs)**

- **Si une équipe push directement sur `main`** :

  - Leur faire annuler le commit avec :

    ```bash
    git reset --hard HEAD~1
    ```

  - **Rappel** : "La branche `main` est sacrée !".

- **Si une PR est mergée sans review** :
  - Leur faire **revert** le merge via GitHub.

---

### **Critères de Validation**

- ✅ 3 PR mergées avec review.
- ✅ `main` protégée et à jour.
- ✅ Daily Scrum documenté.
- ✅ Aucun commit direct sur `main`.

---

### **Debrief (5 min)**

**Questions à poser** :

1. _"Pourquoi est-ce dangereux de push sur `main` directement ?"_
2. _"Comment GitHub vous aide-t-il à respecter Scrum ?"_

---

### **Bonus pour les Plus Rapides**

- Créer une **Issue GitHub** pour la prochaine tâche.
- Ajouter un **template de PR** dans le repo.

---

**Matériel fourni** :

- [Cheatsheet Git/GitHub](https://education.github.com/git-cheat-sheet-education.pdf).
- Exemple de [README.md](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2).
