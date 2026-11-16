# Creative Look — bêta privée

Creative Look est un panneau de looks cinéma pour DaVinci Resolve Studio sur Windows. En un double-clic, il pose
un look inspiré d'un film sur ta power grade. Tu règles ensuite l'intensité, l'expo et le contraste sans quitter
la page Color.

> **Bêta privée.** Merci de ne partager ni l'archive ni des captures du panneau en dehors du groupe de test.

## Ce qu'il te faut

- Windows 10 ou 11.
- DaVinci Resolve **Studio**. Les Workflow Integrations n'existent pas dans la version gratuite. Le panneau est
  testé sur Resolve Studio 21.0.
- Une power grade dont les nodes portent les noms attendus (voir plus bas).

## Installer ou mettre à jour

1. Dans la colonne de droite de cette page, ouvre **Releases**, puis télécharge le fichier
   `CreativeLook-…-beta.zip` de la dernière version.
2. Ferme DaVinci Resolve.
3. Décompresse l'archive (clic droit > Extraire tout), puis double-clique sur **Installer Creative Look.bat**.
   - Si Windows affiche « Windows a protégé votre ordinateur », clique sur **Informations complémentaires**, puis
     sur **Exécuter quand même**.
   - Si la copie échoue, fais un clic droit sur le fichier, puis **Exécuter en tant qu'administrateur**.
4. Ouvre Resolve Studio, puis **Workspace > Workflow Integrations > Creative Look**.

Pour mettre à jour, refais la même chose avec la nouvelle archive. Tes favoris, tes recettes et tes power grades
sont conservés.

## Ta power grade

Le panneau applique ta power grade, puis pose le look sur un node précis. Il reconnaît les nodes par leur nom
(clic droit sur un node > Node Label) :

| Nom du node | Ce que le panneau y met |
|---|---|
| `LUT` | le look (obligatoire) |
| `Exp` | l'exposition et l'équilibre automatique |
| `Look` | le contraste (sans ce node, il va dans `Exp`) |
| `WB` | la balance des blancs automatique |
| `Film Look` | l'émulation pellicule (power grade film : CST de sortie en Cineon Film Log) |

Pour l'utiliser :

1. Exporte ta power grade depuis la Gallery (.drx).
2. Dans le panneau, choisis « … » > **Utiliser ma power grade**.
3. Pour vérifier, choisis « … » > **Diagnostic de la power grade**. Il dit ce que le panneau trouve sur le plan
   courant.

## L'essentiel

- **Survol** d'une vignette : aperçu du look dans Resolve. **Double-clic** : appliquer.
- **Onglets du bas** : Look (intensité, densité, peau, cinémascope), Expo & contraste, Équilibre, Portée.
- **Densité film** et **Peau protégée** : chaque clic passe au niveau suivant (léger, moyen, fort, coupé).
- **A/B** : compare sur le plan le look posé (A) et celui sélectionné dans la grille (B). Appliquer garde le B.
- **Portée > Scènes** : le panneau regroupe les plans par scène, avec une couleur de clip par scène. Ensuite, un
  look appliqué sur un plan va sur toute sa scène.
- **Vue mosaïque** : l'icône en grille 3 × 3, en haut.
- **Mode Film** : seuls les looks essentiels, adaptés à l'émulation pellicule pour garder leur couleur.
- **Recettes** : « … » > Recettes, pour enregistrer tes réglages sous un nom, ou exporter et importer recettes et
  favoris.

### Raccourcis

Ils marchent aussi quand Resolve est au premier plan. Ils commencent tous par **Ctrl+Alt+Maj** :

| Touche | Action |
|---|---|
| 1 à 9 | favoris |
| ← → | look précédent / suivant |
| ↑ ↓ | intensité |
| Page haut / Page bas | expo ±0,5 |
| Début / Fin | expo ±0,1 |
| A | équilibrer |
| M | raccorder |
| B | avant / après |
| C | comparer A/B |
| Z | annuler |

## Donner un retour

Ouvre l'onglet **Issues**, clique sur **New issue**, puis choisis **Un problème** ou **Une idée**.

Pour un problème, joins le rapport de support :

1. Dans le panneau, choisis « … » > **Préparer un rapport pour le support**.
2. Un fichier texte apparaît sur ton Bureau.
3. Glisse-le dans l'issue.

Le rapport contient :

- les versions de Resolve, de Windows et du panneau ;
- les réglages du panneau ;
- les noms des nodes du plan ;
- la fin du journal.

Il ne contient aucune image. Il contient en revanche des chemins de fichiers, qui peuvent inclure ton nom
d'utilisateur Windows.

## Limites connues

- Windows uniquement pour l'instant : une version Mac est prévue.
- Les barres cinémascope recadrent le clip. L'Output Blanking prendra le relais quand Resolve 21.1 le permettra.
- La détection des scènes reste à éprouver sur de vrais projets. Dis-nous quand elle coupe trop ou pas assez.
- Le détail des versions est dans [CHANGELOG.md](CHANGELOG.md).
