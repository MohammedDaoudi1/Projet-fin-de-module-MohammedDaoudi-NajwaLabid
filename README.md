# CAHIER DES CHARGES

## Agent architecte logiciel intelligent

### Conception avancée d'architectures logicielles à partir d'un cahier des charges

| Élément | Description |
|---|---|
| **Type de projet** | Application intelligente d'aide à la conception et à la documentation d'architectures logicielles |
| **Version du document** | 1.0 |
| **Date** | Novembre 2026 |
| **Statut** | Proposition initiale — à valider avec le commanditaire |
| **Public cible** | Étudiants, architectes logiciels, développeurs, chefs de projet et équipes techniques |

*Document de cadrage fonctionnel et technique*

---

## 1. Présentation générale du projet

### 1.1 Contexte

La conception d'une architecture logicielle nécessite l'analyse approfondie des besoins métier, des contraintes techniques et des objectifs de qualité. Cette activité demande de l'expérience, du temps et une bonne maîtrise des styles architecturaux ainsi que des langages de modélisation.

Le projet consiste à développer un agent intelligent capable d'assister cette démarche à partir d'un cahier des charges fourni par l'utilisateur.

### 1.2 Problématique

Comment transformer automatiquement un cahier des charges, parfois rédigé en langage naturel, en propositions d'architectures logicielles cohérentes, comparables et justifiées, accompagnées de diagrammes techniques exploitables ?

### 1.3 Vision de la solution

L'**Agent Architecte Logiciel** est une application conversationnelle et documentaire. Il :

- extrait les exigences fonctionnelles et non fonctionnelles ;
- identifie les contraintes ;
- propose une ou plusieurs architectures candidates ;
- compare leurs avantages et limites ;
- recommande une solution ;
- génère des diagrammes visuels ou du code de diagrammes (C4, UML et Mermaid).

L'utilisateur peut ensuite demander des modifications et exporter les livrables.

---

## 2. Objectifs du projet

- Automatiser l'analyse initiale d'un cahier des charges rédigé en français ou en anglais.
- Identifier et structurer les exigences fonctionnelles, non fonctionnelles et les contraintes.
- Proposer plusieurs styles d'architecture pertinents : monolithe modulaire, microservices, architecture en couches, événementielle, serverless ou hybride.
- Comparer les propositions selon des critères explicites et pondérables : coût, complexité, scalabilité, maintenabilité, sécurité et disponibilité.
- Justifier les choix techniques en reliant chaque décision aux exigences du projet.
- Produire des diagrammes techniques cohérents : C4, UML et Mermaid.
- Permettre l'itération, la correction et l'export des résultats.
- Réduire le temps de préparation d'une première conception sans remplacer la validation d'un architecte ou d'une équipe technique.

---

## 3. Périmètre du projet

### 3.1 Fonctionnalités incluses

- Création d'un projet et saisie ou importation du cahier des charges (texte, PDF ou DOCX).
- Analyse automatique et extraction des exigences, contraintes, acteurs et règles métier.
- Détection des informations manquantes, ambiguïtés et contradictions, avec questions de clarification.
- Génération d'au moins deux architectures candidates lorsque le contexte le justifie.
- Comparaison multicritère, notation explicable et recommandation argumentée.
- Génération et visualisation de diagrammes C4, UML et Mermaid.
- Modification des hypothèses et régénération ciblée des propositions.
- Export des résultats en PDF/DOCX et des diagrammes en PNG/SVG ou code source.
- Conservation de l'historique des analyses d'un projet.

### 3.2 Hors périmètre de la première version

- Génération complète et garantie du code source de l'application cible.

---

## 4. Parties prenantes et utilisateurs

| Acteur | Responsabilités / besoins |
|---|---|
| **Utilisateur / porteur du projet** | Fournit le cahier des charges, répond aux questions, consulte et exporte les propositions. |
| **Architecte logiciel** | Vérifie les exigences, ajuste les critères, examine les diagrammes et valide les décisions. |
| **Administrateur** | Gère les comptes, les paramètres globaux, les modèles d'IA et les journaux techniques. |
| **Agent intelligent** | Analyse, questionne, propose, compare, justifie et génère les livrables. |

---

## 5. Parcours nominal

1. L'utilisateur crée un nouveau projet et fournit son cahier des charges.
2. Le système extrait le texte et vérifie que le document est exploitable.
3. L'agent identifie les exigences fonctionnelles, non fonctionnelles, acteurs, données, intégrations et contraintes.
4. L'agent présente une synthèse structurée à l'utilisateur pour validation.
5. Si des informations importantes manquent, l'agent pose des questions ciblées et met à jour l'analyse après les réponses.
6. L'agent génère plusieurs architectures candidates adaptées au contexte.
7. Le moteur de comparaison évalue les candidats selon les critères et pondérations retenus.
8. L'agent explique les compromis et formule une recommandation.
9. Le système génère les diagrammes et vérifie leur cohérence syntaxique.
10. L'utilisateur ajuste les exigences ou les critères, puis relance tout ou partie de l'analyse.
11. L'utilisateur exporte le dossier final et retrouve l'analyse dans l'historique du projet.

---

## 6. Exigences fonctionnelles

| ID | Exigence | Priorité | Critère d'acceptation |
|---|---|---|---|
| **EF-01** | Créer, nommer, consulter et archiver un projet. | Haute | Un projet peut être créé et retrouvé dans la liste de l'utilisateur. |
| **EF-02** | Importer un fichier PDF/DOCX ou coller du texte. | Haute | Le contenu est extrait ou une erreur lisible est affichée. |
| **EF-03** | Extraire et classer les exigences fonctionnelles et non fonctionnelles. | Haute | La sortie distingue les deux catégories et conserve les éléments sources. |
| **EF-04** | Identifier les contraintes, acteurs, systèmes externes et données principales. | Haute | Les éléments extraits sont affichés dans une synthèse structurée. |
| **EF-05** | Détecter les ambiguïtés et demander des clarifications. | Haute | L'agent pose des questions pertinentes et intègre les réponses. |
| **EF-06** | Générer plusieurs architectures candidates. | Haute | Au moins deux candidats sont proposés lorsque cela est pertinent, avec hypothèses explicites. |
| **EF-07** | Comparer les architectures selon des critères pondérés. | Haute | Un tableau comparatif et les justifications des notes sont disponibles. |
| **EF-08** | Recommander une architecture. | Haute | La recommandation cite les exigences qui motivent le choix et ses compromis. |
| **EF-09** | Générer des diagrammes C4, UML et Mermaid. | Haute | Les diagrammes sont rendus ou le code source valide est exportable. |
| **EF-10** | Permettre la régénération après modification. | Moyenne | Une modification d'exigence met à jour les éléments concernés. |
| **EF-11** | Exporter le rapport et les diagrammes. | Haute | Les formats PDF/DOCX et PNG/SVG ou Mermaid sont téléchargeables. |
| **EF-12** | Consulter l'historique et les versions d'analyse. | Moyenne | Les versions sont datées et consultables. |
| **EF-13** | Administrer les utilisateurs et les paramètres IA. | Moyenne | L'administrateur peut gérer les accès et paramètres autorisés. |

---

## 7. Exigences non fonctionnelles

| ID | Exigence | Cible / vérification |
|---|---|---|
| **ENF-01** | Sécurité et confidentialité | Authentification, contrôle d'accès, chiffrement en transit, secrets hors du code. |
| **ENF-02** | Performance | Pour un document standard, retour de la première synthèse en moins de 60 secondes dans l'environnement de référence (à mesurer). |
| **ENF-03** | Disponibilité | Gestion propre des indisponibilités du fournisseur IA et possibilité de relancer une tâche. |
| **ENF-04** | Scalabilité | Composants séparables et traitement asynchrone possible pour les documents volumineux. |
| **ENF-05** | Maintenabilité | Code modulaire, documentation API, tests automatisés et configuration par environnement. |
| **ENF-06** | Traçabilité | Journaliser les étapes, versions de prompts/modèles et décisions sans exposer de secrets. |
| **ENF-07** | Fiabilité | Validation des sorties structurées et contrôle syntaxique des diagrammes. |
| **ENF-08** | Ergonomie | Interface claire, responsive, messages d'erreur compréhensibles et possibilité de reprise. |

---

## 8. Règles métier et logique de décision

- Aucune architecture ne doit être recommandée sans présenter les exigences et contraintes qui la motivent.
- Les exigences extraites doivent pouvoir être corrigées ou confirmées par l'utilisateur.
- Une information absente ne doit pas être inventée : elle est signalée comme inconnue ou transformée en question.
- Les notes de comparaison doivent être accompagnées d'une justification et d'un niveau de confiance qualitatif.
- Les pondérations des critères doivent être visibles et leur somme normalisée à 100 %.
- Une architecture microservices ne doit pas être favorisée automatiquement : la complexité opérationnelle et le coût doivent être pris en compte.
- Les diagrammes doivent correspondre à l'architecture retenue et utiliser une nomenclature cohérente.
- Toute recommandation est une aide à la décision et nécessite une validation humaine avant mise en œuvre.

---

## 9. Critères de comparaison des architectures

Le système doit permettre de modifier les pondérations. Les valeurs ci-dessous constituent une configuration initiale indicative et non une règle universelle.

| Critère | Pondération initiale | Éléments évalués |
|---|---|---|
| **Coût** | 20 % | Infrastructure, licences, exploitation, observabilité et maintenance. |
| **Complexité** | 15 % | Nombre de composants, compétences requises, orchestration et diagnostic. |
| **Scalabilité** | 20 % | Montée en charge, indépendance des composants et évolutivité. |
| **Maintenabilité** | 15 % | Modularité, testabilité, couplage et facilité d'évolution. |
| **Sécurité** | 15 % | Contrôle d'accès, isolation, gestion des secrets et surface d'attaque. |
| **Disponibilité / résilience** | 15 % | Tolérance aux pannes, redondance, reprise et dégradation contrôlée. |

Chaque critère peut être noté de 1 à 5. Le système calcule un score pondéré, mais doit également présenter les limites de cette notation et éviter de donner une précision artificielle aux estimations.

---

## 10. Architecture fonctionnelle cible de l'agent

L'application peut être organisée autour des modules logiques suivants :

| Module | Responsabilité |
|---|---|
| **Interface utilisateur** | Gestion des projets, dépôt de documents, conversation, résultats et exports. |
| **API / gestion des projets** | Authentification, projets, versions, historique et orchestration des requêtes. |
| **Ingestion documentaire** | Lecture PDF/DOCX, extraction de texte, nettoyage et découpage. |
| **Analyse des exigences** | Extraction structurée, classification, détection des manques et validation utilisateur. |
| **Orchestrateur IA** | Coordination des étapes, gestion du contexte, appels aux modèles et reprise sur erreur. |
| **Moteur de conception** | Production des architectures candidates et de leurs composants/flux. |
| **Moteur de comparaison** | Évaluation pondérée, justification et recommandation. |
| **Générateur de diagrammes** | Production du code C4/UML/Mermaid, validation et rendu. |
| **Persistance** | Stockage des utilisateurs, projets, exigences, analyses, versions et livrables. |
| **Export et reporting** | Génération du rapport final et téléchargement des diagrammes. |

### 10.1 Principes techniques

- Séparer l'orchestration de l'agent, les fournisseurs de modèles IA et les règles métier.
- Utiliser des schémas de données structurés (par exemple JSON validé) entre les étapes.
- Conserver les prompts et paramètres de génération sous version.
- Prévoir une couche d'abstraction pour remplacer un fournisseur de modèle sans réécrire le cœur applicatif.
- Ne pas confier au modèle seul le calcul des scores : effectuer les calculs pondérés dans un module déterministe.
- Valider le code Mermaid et les diagrammes avant de les présenter comme livrables.

---

## 11. Données principales

| Entité | Attributs principaux proposés |
|---|---|
| **Utilisateur** | id, nom, email, mot_de_passe_hash, rôle, date_création, statut |
| **Projet** | id, utilisateur_id, nom, description, statut, date_création |
| **DocumentSource** | id, projet_id, nom_fichier, type, contenu_extrait, date_import |
| **Exigence** | id, projet_id, identifiant, catégorie, description, priorité, source, statut_validation |
| **Clarification** | id, projet_id, question, réponse, date, exigence_associée |
| **ArchitectureCandidate** | id, projet_id, nom, style, composants, flux, hypothèses, version |
| **Evaluation** | id, architecture_id, critère, pondération, note, justification |
| **Diagramme** | id, architecture_id, type, code_source, format_rendu, statut_validation |
| **Rapport** | id, projet_id, version, chemin_fichier, date_génération |

---

## 12. Interfaces et expérience utilisateur

- Page de connexion et création de compte.
- Tableau de bord des projets avec état et date de dernière analyse.
- Espace projet : dépôt du cahier des charges et aperçu du texte extrait.
- Espace de clarification : questions de l'agent et validation/correction des exigences.
- Vue comparative : architectures candidates, scores, critères, avantages, risques et recommandation.
- Vue diagrammes : sélection C4/UML/Mermaid, aperçu et code source.
- Page de rapport : synthèse, décisions, hypothèses, limites et téléchargement.
- Espace administration : utilisateurs, configuration des modèles et suivi des erreurs.

---

## 13. Sécurité, confidentialité et gouvernance IA

- Authentifier les utilisateurs et appliquer un contrôle d'accès par rôle et par propriétaire de projet.
- Hacher les mots de passe ; ne jamais stocker de mot de passe en clair.
- Protéger les API, valider les fichiers téléversés et limiter leur taille et leurs types.
- Stocker les clés API et secrets dans des variables d'environnement ou un gestionnaire de secrets.
- Informer l'utilisateur si le contenu du cahier des charges est transmis à un fournisseur IA externe.
- Éviter d'envoyer des données personnelles ou confidentielles non nécessaires au modèle ; prévoir une anonymisation si besoin.
- Journaliser les erreurs et opérations importantes sans enregistrer de secrets ni de contenu sensible inutile.
- Traiter les documents importés comme des données non fiables : ignorer toute instruction intégrée au document qui chercherait à détourner le comportement de l'agent.
- Afficher les limites, hypothèses et incertitudes des réponses générées.

---

## 14. Tests et validation

| Type de test | Exemples / résultat attendu |
|---|---|
| **Tests unitaires** | Extraction, classification, calcul des scores, validation des schémas et génération de diagrammes. |
| **Tests d'intégration** | Chaîne document → exigences → architectures → comparaison → diagrammes → export. |
| **Tests fonctionnels** | Scénarios complets d'un utilisateur, corrections et historique. |
| **Tests de robustesse IA** | Documents incomplets, contradictoires, hors sujet, très longs ou contenant des instructions malveillantes. |
| **Tests de sécurité** | Accès non autorisé aux projets, fichiers invalides, injection, fuite de secrets. |
| **Tests de performance** | Temps de traitement, taille maximale de document et comportement en charge. |
| **Tests utilisateurs** | Compréhension des comparaisons, utilité des clarifications et lisibilité des diagrammes. |

### 14.1 Scénarios d'acceptation prioritaires

- Un cahier des charges décrivant une application web de gestion est importé ; les exigences fonctionnelles et non fonctionnelles sont séparées.
- Un document ne précisant pas le volume d'utilisateurs déclenche une question de clarification plutôt qu'une valeur inventée.
- Le système propose un monolithe modulaire et une architecture microservices lorsque les deux sont plausibles, puis explique les compromis.
- La modification de la pondération du coût change le classement selon le calcul déterministe.
- Le diagramme généré est syntaxiquement valide et représente les composants de l'architecture sélectionnée.
- Un utilisateur ne peut pas consulter les projets d'un autre utilisateur.
- En cas d'indisponibilité du fournisseur IA, l'application affiche une erreur compréhensible et permet de réessayer.

---

## 15. Livrables attendus

- Cahier des charges validé.
- Spécifications fonctionnelles et règles métier.
- Modèle de données et documentation des API.
- Code source de l'application et instructions d'installation.
- Jeux de tests et rapport des résultats.
- Au moins un dossier d'architecture généré sur un cas d'usage représentatif.
- Diagrammes C4 (contexte, conteneurs et composants selon le besoin), UML et Mermaid.
- Rapport exportable présentant exigences, hypothèses, architectures comparées, recommandation, risques et décisions.
- Guide utilisateur et documentation technique.

---

## 16. Planning prévisionnel

| Phase | Travaux | Durée indicative |
|---|---|---|
| **1. Cadrage** | Validation du périmètre, cas d'usage, critères et exigences. | 1 semaine |
| **2. Conception** | Architecture de la plateforme, modèle de données, API et maquettes. | 1 semaine |
| **3. Socle applicatif** | Authentification, projets, import documentaire et persistance. | 1 à 2 semaines |
| **4. Agent IA** | Extraction, clarification, génération des architectures et comparaison. | 2 semaines |
| **5. Diagrammes et exports** | Génération C4/UML/Mermaid, validation et rapport. | 1 à 2 semaines |
| **6. Tests et stabilisation** | Tests fonctionnels, robustesse, sécurité et corrections. | 1 semaine |
| **7. Documentation et démonstration** | Guide, dossier technique et préparation de la présentation. | 1 semaine |

> **Durée totale indicative : 8 à 10 semaines**, à ajuster selon l'effectif, les technologies et les exigences de démonstration.

---

## 17. Risques et mesures de réduction

| Risque | Impact | Mesure préventive / corrective |
|---|---|---|
| **Hallucinations ou exigences inventées** | Élevé | Extraction structurée, références aux passages sources, validation humaine et signalement des hypothèses. |
| **Architectures trop complexes** | Élevé | Évaluation du coût opérationnel et règle de simplicité adaptée au contexte. |
| **Diagrammes incohérents ou invalides** | Moyen | Génération à partir d'un modèle structuré commun et validation syntaxique. |
| **Dépendance à un fournisseur IA** | Moyen | Couche d'abstraction et configuration interchangeable. |
| **Coût et latence des appels IA** | Moyen | Limites de taille, cache ciblé, suivi de consommation et traitement asynchrone. |
| **Fuite de données confidentielles** | Élevé | Contrôle d'accès, minimisation, anonymisation et transparence sur les fournisseurs. |
| **Document mal formé ou non exploitable** | Moyen | Contrôle du format, extraction avec messages d'erreur et saisie manuelle alternative. |

---

## 18. Hypothèses et décisions à confirmer

- Le produit est d'abord destiné à un usage académique ou à une démonstration de faisabilité ; une mise en production nécessitera une étude complémentaire.
- La langue principale de l'interface et des livrables est le français ; l'anglais pourra être ajouté.
- Les formats d'entrée prioritaires sont PDF, DOCX et texte brut.
- Le choix du fournisseur LLM, de la base de données et du framework front-end/back-end reste ouvert jusqu'à l'étude technique.
- Les pondérations initiales des critères sont configurables et devront être validées par le commanditaire.
- Le volume maximal de documents, le nombre d'utilisateurs simultanés, l'hébergement et le budget doivent être précisés.
- Le niveau de détail des diagrammes C4/UML dépendra du temps disponible et de la qualité des informations fournies.

---

## 19. Conditions de réussite du projet

Le projet sera considéré comme réussi si un utilisateur peut :

- fournir un cahier des charges ;
- obtenir une extraction d'exigences vérifiable ;
- répondre aux clarifications ;
- comparer au moins deux architectures pertinentes lorsque le cas le permet ;
- comprendre la recommandation ;
- consulter des diagrammes valides ;
- exporter un dossier cohérent.

La qualité sera évaluée sur la **traçabilité des décisions**, la **pertinence des compromis**, la **robustesse face aux documents incomplets** et la **clarté des limites de l'IA** — et non uniquement sur la fluidité des réponses.

---

## 20. Validation du cahier des charges

| Rôle | Nom | Date | Visa / signature |
|---|---|---|---|
| **Commanditaire** | | | |
| **Responsable du projet** | | | |
| **Référent technique** | | | |

---

*AGENT ARCHITECTE LOGICIEL INTELLIGENT — CAHIER DES CHARGES*