# 🧱 Pattern Builder III — Les Mécanismes du Comportement

**Mini-guide d’utilisation et d’animation pédagogique**  
**Public :** étudiants intermédiaires en développement logiciel ayant déjà vu la matière  
**Durée cible :** 30 minutes  
**Contenu de référence :** *Les patrons de conception (4).pdf*, 19 pages, catégorie **Comportement**.

---

## 1. Démarrage en 20 secondes

1. Décompresser `PatternBuilder_III_Comportements.zip` dans un dossier local.
2. Garder **`index.html`**, **`style.css`** et **`script.js`** côte à côte.
3. Double-cliquer sur **`index.html`** et l'ouvrir avec **Google Chrome** ou **Microsoft Edge**.
4. Cliquer sur **« Commencer l’aventure »** puis entrer dans le premier monde.

**Connexion Internet non requise.** Le jeu fonctionne sans serveur, sans compte, sans installation et sans bibliothèque externe. Les illustrations sont des **SVG vectoriels intégrés au JavaScript** : aucun fichier image supplémentaire n’est nécessaire.

> **Attention :** la progression n'est pas enregistrée. Recharger la page, fermer l'onglet ou cliquer sur « Nouvelle partie » remet le jeu à zéro.

## 2. Les trois royaumes

| Royaume | Patron | Exemple directement tiré du PDF | Compétence exercée |
|---|---|---|---|
| ⚔️ La Forge des Tactiques | **Strategy** | IronMan, `IAttaque`, `AttaqueLaser`, `AttaqueMissile`, `AttaqueCorpsACorps` | Échanger un algorithme à l’exécution en utilisant une interface commune |
| 🔗 Le Relais des Héros | **Chain of Responsibility** | Impa, Navi et Link ; `SetProchain()`, `TraiterQuete()` | Organiser le passage d’une requête entre gestionnaires |
| 🧭 Le Labyrinthe de l’Inventaire | **Iterator** | Mario et ses objets ; `GetIterator()`, `HasNext()`, `Next()` | Parcourir une collection sans exposer sa structure interne |

Chaque royaume contient **4 défis**, soit **12 défis au total**. Un **Grand Atelier final** propose **3 réparations** qui demandent de sélectionner le bon patron et de justifier l’architecture appropriée.

## 3. Détail des défis

### ⚔️ Monde 1 — Strategy (environ 7 minutes)

- **Les trois cibles :** choisir l’algorithme correspondant à chaque situation. Examiner visuellement le remplacement de l’objet `IAttaque`.
- **Le carrousel des attaques :** former et exécuter la séquence Laser → Missile → Corps à corps à l’aide de `SetStrategie()` et `Attaquer()`.
- **L’atelier des choix :** observer les trois variantes et expliquer la différence entre stratégie remplaçable et gros bloc conditionnel.
- **Le plan UML :** placer `IAttaque`, `IronMan` et les trois classes d’attaque, puis identifier leurs relations.

**Message à retenir :** Strategy permet de **remplacer** une variante de comportement. Il ne sert pas à empiler simultanément des fonctionnalités comme Decorator.

### 🔗 Monde 2 — Chain of Responsibility (environ 7 minutes)

- **Le sentier brisé :** reconstruire par glisser-déposer la chaîne **Impa → Navi → Link** de l’exemple du cours.
- **Les quêtes d’Hyrule :** simuler la circulation de trois requêtes jusqu’au bon gestionnaire.
- **La requête impossible :** vérifier qu'une chaîne peut arriver à son terme sans qu'aucun objet traite la requête.
- **Le schéma des gardiens :** construire le diagramme UML autour de `IQueteHandler`, `QueteHandler` et des trois héros.

**Message à retenir :** les gestionnaires traitent ou transmettent la requête. Une demande **n'est pas forcément prise en charge** : la fin de chaîne doit être pensée explicitement.

### 🧭 Monde 3 — Iterator (environ 7 minutes)

- **La sacoche secrète :** appeler `HasNext()` avant chaque `Next()` pour lire **Champignon → Étoile → Carapace**.
- **Deux aventuriers, une sacoche :** faire évoluer deux itérateurs indépendants sur une même collection.
- **Le rituel du parcours :** placer les trois opérations dans l'ordre correct, puis simuler la boucle.
- **La carte UML :** reconstruire `IInventaire`, `IIterator`, `Inventaire` et `InventaireIterator`.

**Message à retenir :** Iterator sépare la collection de sa logique de parcours ; le client n’a pas besoin d’accéder au tableau ou à la liste interne.

### 🏰 Grand Atelier (environ 7 minutes)

L’étudiant résout trois pannes en choisissant **un patron** et **la façon correcte de l’appliquer** : remplacement d'attaque, transmission de requête et parcours d’inventaire. La conclusion affiche le résultat et trois jauges de maîtrise.

## 4. Commandes et interactions

| Action | Comment faire |
|---|---|
| Choisir une réponse | Cliquer sur un bouton ou une option A/B/C |
| Placer une pièce UML | **Glisser-déposer** la pièce vers sa case, ou **cliquer la pièce puis cliquer la case** |
| Modifier une pièce placée | Sélectionner une autre pièce puis cliquer la même case |
| Retirer une pièce | Cliquer une case remplie sans pièce présélectionnée |
| Déclencher une simulation | Cliquer sur le bouton d’exécution du mécanisme |
| Vérifier un défi | Cliquer sur **« Vérifier la mission »** |
| Corriger après deux erreurs | Lire le corrigé, puis **« Appliquer la correction et continuer »** |
| Rejouer un monde | Retourner à la carte et rouvrir un monde terminé |
| Recommencer à zéro | Cliquer **« Nouvelle partie »** depuis l’écran final |

Les dialogues et journaux de simulation expliquent ce qu’il se passe lors des appels et des transitions. Les exercices UML montrent les connexions au fur et à mesure du placement des objets. Les flèches en pointillés avec triangle creux représentent les réalisations/héritages selon le cas ; une autre flèche représente les associations.

## 5. Progression et XP

- **Quatre défis par monde :** maximum **40 XP par défi** = **160 XP par monde**.
- **Trois mondes :** maximum **480 XP**.
- **Grand Atelier :** maximum **40 XP par étape** = **120 XP**.
- **Total : 600 XP**.
- Une réussite du premier essai rapporte 100 % des XP. Après une première vérification erronée, le défi peut encore être réussi, mais avec une récompense réduite à 85 %.
- Après **deux vérifications erronées**, une explication détaillée est proposée ; appliquer la correction permet de poursuivre avec **55 %** des XP du défi.
- **Rejouer n’ajoute pas de nouveaux XP** : le premier résultat est conservé. Les jauges affichent le pourcentage d’XP acquis sur le maximum de chaque monde.
- **Pas de vies ni de chronomètre punitif** : l’objectif est de comprendre, pas de sanctionner la vitesse.

## 6. Pistes d’animation pour l’enseignant

Avant le jeu, poser la question : « Quelle différence existe-t-il entre un algorithme remplaçable, une demande qui circule entre objets et un parcours de collection ? »

Après chaque monde, inviter les étudiants à formuler une phrase :

- Strategy — « Je peux changer **comment** Iron Man attaque. »
- Chain of Responsibility — « Je peux transmettre une quête jusqu'au personnage **capable** de la traiter. »
- Iterator — « Je peux visiter les bonus **sans savoir comment** ils sont stockés. »

**Question de synthèse :** « Dans une même application de jeu, peut-on employer les trois patrons sans qu’ils se remplacent ? » Oui : les stratégies définissent comment attaquer, la chaîne désigne qui traite une requête et l’itérateur définit comment parcourir un inventaire.

Le document de cours présente du code C# ; le jeu est volontairement **sans saisie de code**, mais reprend les concepts, interfaces et noms de méthodes pour favoriser le transfert des connaissances vers le langage C#.

## 7. Notes techniques et limites

- Fichiers : `index.html`, `style.css`, `script.js` et ce mini-guide.
- HTML5, CSS3 et JavaScript natif, **sans dépendances externes** ni réseau.
- Les illustrations, flèches UML et animations sont produites en **SVG/CSS/JavaScript**.
- Compatible avec les versions modernes de Chrome et Edge sur ordinateur ; l’interface s’adapte aux écrans plus étroits.
- Le jeu ne compile ni n’exécute de C# : il **simule les interactions de conception**, avec des validations pédagogiques définies pour chaque mission.
- Pas de son, d’authentification, de suivi à distance, de publicité ni de stockage permanent.
- En cas d'affichage incorrect : extraire entièrement le ZIP, vérifier que les trois fichiers de code demeurent dans le même dossier, puis rouvrir `index.html`.

**Bonne aventure dans Patternia !** 🧱
