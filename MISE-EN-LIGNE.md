# Mise en ligne de l'invitation

## 1. Les réponses dans une feuille Google Sheets (5 minutes)

Le script crée lui-même la feuille sur votre Drive (« Réponses mariage – Lowell & Stephanie ») : inutile d'en créer une.

1. Allez sur script.google.com → **Nouveau projet**.
2. Effacez le contenu de l'éditeur, collez tout le fichier `archives/Code.gs`, enregistrez (icône disquette).
3. Dans la liste des fonctions en haut, choisissez **creerLaFeuille** puis **Exécuter** : autorisez l'accès quand Google le
   demande (Paramètres avancés → Accéder à …). Le journal affiche le lien de la feuille créée.
4. **Déployer → Nouveau déploiement** → engrenage → **Application Web**.
   - Exécuter en tant que : **Moi**.
   - Qui a accès : **Tout le monde**.
   - **Déployer**, puis copiez l'**URL de l'application Web** (elle se termine par `/exec`).
5. Collez cette URL dans `index.html`, ligne `const RSVP_ENDPOINT = "";`, entre les guillemets. Sans cette étape, le site
   n'envoie rien à Google.

Vérification : ouvrez l'URL `/exec` dans un navigateur, elle affiche `"ok":true` et le lien de la feuille.
Chaque réponse envoyée depuis le site s'ajoute alors dans l'onglet « Réponses » : date, nom, nombre de personnes, mairie,
église, réception, message. La feuille est consultable depuis l'application Google Sheets sur téléphone.

Si vous aviez déjà déployé une ancienne version du script, ou si vous modifiez le script plus tard :
**Déployer → Gérer les déploiements → crayon → Version : Nouvelle version → Déployer** (l'URL ne change pas), puis
réexécutez `creerLaFeuille` une fois pour accorder les nouvelles autorisations.

## 2. Vos photos et votre musique

- Déposez vos fichiers dans le dossier `photos/` avec les noms indiqués dans `photos/LISEZ-MOI.txt` :
  `photomaton-1.jpg` à `photomaton-3.jpg` (la bande photomaton), `histoire-1.jpg` à `histoire-3.jpg` (les polaroïds de « Notre histoire »),
  `galerie-1.jpg` à `galerie-14.jpg` (la galerie 3D « Nos souvenirs », à déposer avant la mise en ligne : sans elles, des photos de démonstration s'affichent),
  `coeur.jpg` (le cœur en dentelle) et `musique.mp3`. Les textes de « Notre histoire » se modifient dans `index.html`
  (cherchez « Chapitre I », « Chapitre II », « Chapitre III »).
- Déroulé de l'invitation : on appuie sur le bouton du cadre doré, les prénoms apparaissent et la bande photomaton
  sort de la fente ; « Ouvrir l'invitation » affiche le collage, le compte à rebours, l'histoire, la galerie, les détails et le formulaire.
- Tant qu'une photo manque, son emplacement reste décoré.

## 3. Héberger le site sur Vercel

Le site tient dans `index.html` (illustrations incluses) plus le dossier `photos/`.

1. Créez un compte sur vercel.com.
2. **Add New → Project**, puis déposez le dossier contenant `index.html` et `photos/` (ou reliez un dépôt GitHub qui les contient).
3. Aucune configuration : laissez « Framework Preset » sur *Other* et déployez.
4. Vercel donne une adresse du type `https://nom-du-projet.vercel.app`. Vous pouvez y ajouter votre propre nom de domaine dans
   **Settings → Domains**.

Pour mettre le site à jour (textes, photos), redéployez le dossier de la même façon.

## 4. Solution de secours

Tant que l'URL du script n'est pas renseignée (ou si Google ne répond pas), le formulaire affiche un récapitulatif que
l'invité peut copier, ou envoyer par WhatsApp / e-mail si vous renseignez `RSVP_WHATSAPP` et `RSVP_EMAIL` en haut du
script de `index.html`.

## Dossier `archives/`

Photos d'origine, maquette, anciennes versions de la page (`version-serrure-index.html` = la version précédente) et script PHP (utile seulement sur un hébergement PHP, pas sur
Vercel). Le site n'en a pas besoin : vous pouvez supprimer ce dossier.
