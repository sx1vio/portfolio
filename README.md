# Portfolio — Ayélérun Marc-Sylvio CHALLA

Développeur full-stack & systèmes embarqués · Abomey-Calavi, Bénin
challasylvio@gmail.com · +229 01 59 19 65 75

Deux éléments : `index.html` et le dossier `assets/` (logos et photo). Aucun backend,
aucun build, aucune dépendance à installer. Double-cliquez sur `index.html`, il s'ouvre.
Gardez `assets/` à côté du fichier.

Ressources réseau : les polices Google (Onest + JetBrains Mono) et, uniquement à
l'envoi d'un message, l'API FormSubmit. Tout le reste — les logos de technologies, la
photo — est servi en local, donc le site s'affiche entièrement hors ligne.

---

## 1. Le formulaire de contact — une activation à faire

Le formulaire envoie les messages à **challasylvio@gmail.com** via
[FormSubmit](https://formsubmit.co) : pas de compte, pas de serveur à héberger.

**Deux choses à savoir :**

1. **Un e-mail d'activation vous a déjà été envoyé** à challasylvio@gmail.com
   (objet : « Activate Form » / « Test du formulaire de votre portfolio »).
   **Cliquez sur le lien « Activate Form » qu'il contient** — sans ça, aucun message
   n'arrivera. C'est à faire une seule fois, pour toujours.

2. **FormSubmit refuse les pages ouvertes en local** (`file:///...`). Le formulaire ne
   fonctionne donc que sur le **site mis en ligne** (Netlify, Vercel, GitHub Pages…) ou
   derrière un petit serveur local :

   ```bash
   python3 -m http.server 8080   # puis http://localhost:8080
   ```

   En local sans serveur, le formulaire affiche poliment l'adresse e-mail et le numéro
   de téléphone plutôt que d'échouer en silence — rien n'est jamais perdu.

Le code de l'envoi se trouve en bas de `index.html`, cherchez `ENDPOINT`.
Pour changer l'adresse de réception, remplacez `challasylvio@gmail.com` partout dans le
fichier (attribut `action` du formulaire, constante `ENDPOINT`, liens `mailto:`).

---

## 2. Ce qu'il reste à compléter

| À faire | Où |
|---|---|
| **Activer le formulaire** (voir §1) | boîte mail challasylvio@gmail.com |
| **Logo GAPOB** — leur site `gapob.bj` est injoignable, GAPOB s'affiche donc en toutes lettres. Envoyez-moi le fichier et je le pose. | `assets/firm-gapob.svg` à créer, puis section « marquee » |
| **Année du baccalauréat** — j'ai mis 2024, à confirmer | 4<sup>e</sup> diapositive de « Formation & expérience » |
| **Dates et intitulé exact de l'alternance GAPOB** | 2<sup>e</sup> diapositive de « Formation & expérience » |

---

## 3. Contenu du site

**Ordre des sections** : hero → formation & expériences → projets → motion design →
profil → services → chiffres → parcours → tarifs → intérêts → pied de page. Les projets
passent avant le profil : c'est la preuve du travail qui doit arriver en premier.

**Les cinq projets présentés** — chaque carte porte une **capture réelle** du projet
(`assets/projets/`). Les cartes OPUS CORP, BelÔ et Baker Tilly pointent vers le produit
en ligne (flèche en haut à droite de la carte, ouvre un nouvel onglet).

| # | Projet | Visuel | Pile | Lien |
|---|---|---|---|---|
| 01 | **OPUS CORP** — site de l'agence BTL (Cotonou) | capture réelle du site en ligne | Next.js, React, Framer Motion, SEO | opuscrp.com |
| 02 | **BelÔ** — marketplace de services beauté | captures réelles de la fiche App Store | Flutter, Supabase, Firebase, React | apps.apple.com (App Store, pas encore sur Play Store) |
| 03 | **Baker Tilly Bénin** — site institutionnel | capture réelle du site en ligne | HTML, CSS, JS, SEO | bakertilly.bj |
| 04 | **Boby** — assistant dev, hackathon IBM | graphe de dépendances généré par l'app | React, FastAPI, IBM watsonx | — |
| 05 | **HUZZ** — boutique streetwear | accueil de la boutique | Node.js, Express, FedaPay | huzz-me.shop (hors ligne) |

**Motion design & design graphique** (`#motion`) — deux vidéos lues sur le site, dans
`assets/motion/` : la pub **Winix** (16:9, 37 s) et **GozemCar** (9:16, 19 s). Ce sont des
versions web recompressées (H.264 CRF 24, `faststart`) des rendus Remotion de
`~/Projets-perso/motion-graph/` (`winix-motion/out/winix-pub-horizontal.mp4`,
`gozem-motion-2/out/gozemcar.mp4`). Elles démarrent en muet quand elles arrivent à l'écran
et se mettent en pause quand on les quitte (rien d'automatique en « reduced motion ») ; le
son s'active avec les contrôles. Pour en ajouter une, recompressez-la avec :

```bash
ffmpeg -i source.mp4 -vf scale=1280:-2 -c:v libx264 -crf 24 -preset slow -pix_fmt yuv420p \
  -c:a aac -b:a 128k -movflags +faststart assets/motion/nom.mp4
```

Bailo et Sèmè City Open Park restent des projets réels (retirés de `#projets` à la
demande de Marc-Sylvio, gardés comme preuves dans certaines pages `services/`), mais ne
sont plus mis en avant sur la page d'accueil.

**Les pages de service** — chaque flèche de la section « Services » ouvre une page
dédiée dans `services/` : ce que le service couvre, les projets déjà livrés dessus, la
méthode de travail, et un appel à l'action e-mail + téléphone. Quatre pages partagent la
feuille de style `assets/page.css`.

**Les chiffres affichés** : 12+ projets livrés, 15+ technologies, 15+ prototypes
électroniques, 24 h de délai de réponse. Ajustez-les dans la section « En chiffres »
(attributs `data-count`) si vous préférez d'autres valeurs.

**La section Tarifs ne contient aucun montant** : tout est « sur devis ». Si vous ajoutez
des prix, vérifiez qu'ils correspondent à une réalité commerciale.

---

## 4. Direction artistique

Palette **greyscale, du blanc cassé au noir pur**, avec le vert réduit au rôle de
ponctuation — jamais en aplat.

| | |
|---|---|
| Fonds clairs | `#FAFAFA` (page) et `#FFFFFF` (cartes) |
| Fonds sombres | `#000000` → `#050505` → `#0B0B0B` |
| Texte sur clair | `#1C1C1C`, secondaire `#545454` |
| Texte sur sombre | `#FFFFFF`, secondaire blanc à 62 % |
| Accent | `#3DDC84` sur sombre, `#12784A` sur clair, pastille `#22C55E` |
| Filets | `#DEDEDE` |
| Titres | Onest 700, tracking négatif qui s'accentue avec la taille |
| Labels / chiffres | JetBrains Mono, majuscules, interlettrage large |
| Rayons | 24 / 16 / 12 px, pilules à 999 px |

Le **hero est clair** : lignes de repère verticales, deux lavis verts très dilués, et un
CTA noir dont le pictogramme est vert. Le rythme alterne ensuite clair et noir profond,
chaque bascule marquée par des coins arrondis qui font glisser une section sur l'autre.

Le **header est fait de pilules flottantes** — marque, navigation avec indicateur à trois
points, bouton de contact, bouton menu. Aucun texte nu : le header passe au-dessus de
sections claires comme sombres.

---

## 5. Les animations

L'animation signature est **l'empilement des cartes projets au scroll** : chaque carte se
fige à l'écran, la suivante glisse par-dessus et repousse la précédente. C'est du
`position: sticky` piloté par une seule boucle `requestAnimationFrame`.

Le reste :

- **Orbite des technologies** — dans la section Profil, 9 technos gravitent autour de la
  photo, chacune avec son vrai logo, chaque pastille contre-tournant pour rester lisible.
- **Bandeau de formation** défilant en boucle CSS à vitesse fixe.
- **Verre liquide** — la bulle d'action flottante est un vrai matériau translucide.
- **Titre ligne par ligne** — chaque ligne remonte depuis sa boîte de clipping.
- **Texte révélé mot à mot** dans la section Profil, au fil du scroll.
- **Compteurs** liés à la progression du scroll, monotones.
- **Bouton magnétique** sur le CTA principal, desktop uniquement.
- **Le personnage qui découvre les tarifs** : `assets/walk.mp4` n'est jamais lu — il est
  **déplacé dans le temps** au rythme du scroll. Une variable `--p` pilote le
  `currentTime` de la vidéo, le `clip-path` de la carte et le `translateX` du personnage.
  Le fond blanc de la vidéo disparaît par `mix-blend-mode: multiply`, posé sur le
  conteneur et non sur la vidéo.
- **Parcours en diapositives** bord à bord (`scroll-snap` natif), flèches, points et
  navigation au clavier.
- **Menu en feuille** sous le header ; le bouton se transforme en croix.
- **Bulle « Contacter »** permanente : elle apparaît une fois le hero passé et s'efface
  quand le CTA du pied de page arrive à l'écran.

Toutes les transitions n'animent que `transform` et `opacity`. Les effets de survol sont
conditionnés à `@media (hover: hover) and (pointer: fine)` : sur tactile, un tap ne
déclenche pas de faux survol.

---

## 6. Accessibilité

- Contrastes vérifiés **AA** sur toutes les paires texte/fond.
- `prefers-reduced-motion` : l'intro est sautée, l'épinglage des cartes est désactivé,
  tout reste lisible — aucun élément ne demeure invisible.
- `prefers-reduced-transparency` et `prefers-contrast: more` également pris en charge.
- Cibles tactiles ≥ 44 px, lien d'évitement, focus visible, `Échap` ferme menu et modale.
- Aucun débordement horizontal de 320 px à 2560 px.

---

## 7. Les images

| Fichier | Source |
|---|---|
| `assets/marc-sylvio.jpg` | Votre portrait, recadré en carré 800 × 800. Il alimente **4 emplacements** (en-tête, chargement, cœur de l'orbite, pied de page) : remplacez ce seul fichier pour les mettre tous à jour. |
| `assets/projets/*.jpg` | Captures réelles de vos projets, prises en lançant chacun d'eux (serveur Next.js, front buildé, pages statiques). Pour en refaire une, relancez le projet et remplacez le fichier en gardant le même nom. |
| `assets/*.svg` (technos) | [Simple Icons](https://simpleicons.org), CC0 |
| `assets/firm-epitech.svg`, `firm-ibm.svg` | Wikimedia Commons |
| `assets/firm-semecity.svg` | Logo officiel, `semecity.bj` |
| `assets/walk.mp4` | Clip généré (Kling). Il porte un filigrane en bas à droite, sorti du cadre par `transform: scale(1.26)` — si vous changez le cadrage, il peut réapparaître. |

Les icônes Simple Icons sont sous CC0, mais **les marques restent la propriété de leurs
détenteurs** : les afficher pour dire « je travaille avec » ou « je me suis formé là »
est un usage nominatif admis.

---

## 8. Mettre le site en ligne

C'est un fichier statique : n'importe quel hébergeur gratuit convient.

- **Netlify / Vercel** — glissez-déposez le dossier, c'est en ligne en une minute.
- **GitHub Pages** — poussez le dossier, activez Pages sur la branche `main`.
- **Un nom de domaine** (`marcsylviochalla.com` par exemple) rend le tout nettement plus
  crédible auprès d'un recruteur ou d'un client.

Pensez à remplacer `assets/marc-sylvio.jpg` dans la balise `og:image` par une **URL
absolue** une fois le domaine connu, sinon l'aperçu sur WhatsApp et LinkedIn sera vide.
