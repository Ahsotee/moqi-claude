---
name: moqi-clips
description: Découper une vidéo YouTube ou Twitch en clips verticaux avec Moqi, suivre le découpage, programmer ou publier les clips sur TikTok et lire leurs chiffres. À utiliser quand la personne parle de clips, de TikTok, de Shorts, de Reels, de découper une vidéo ou de programmer des sorties.
---

# Travailler avec Moqi

Moqi transforme une vidéo longue en clips verticaux sous-titrés, recadrés sur la personne qui parle. Les outils `moqi_*` viennent du serveur MCP de Moqi (`https://moqi.fr/api/mcp`). Tant que le compte n'est pas connecté, Claude Code indique que Moqi demande une connexion : lancer `/mcp` et choisir Moqi ouvre la page d'autorisation de Moqi.

## Ce qui coûte, et comment ne pas payer deux fois

- Tout se paie en Moqi, sur le solde du compte. Lire `moqi_solde` avant un découpage, et dire le prix à la personne avant de lancer.
- **Un découpage de plusieurs clips est UN seul appel** : pour 5 clips d'une vidéo, `moqi_decouper` une fois avec `clipCount: 5`. Cinq appels feraient cinq découpages facturés.
- Rien n'est instantané. Après `moqi_decouper`, relire l'état avec `moqi_decoupage` en respectant `sonder_dans_s`, jusqu'à `fini` ou `echoue`.

## Les refus

Chaque erreur porte `reessayable` :

- `oui` : un nouvel essai peut passer ;
- `jamais` : recommencer donnera le même refus ;
- `apres-action` : la personne doit agir (recharger des Moqi, régler une facture). Le lui dire, et ne pas boucler.

## Programmer et publier

- `moqi_programmer` pose une sortie dans l'agenda : le clip se désigne par son découpage et sa position, jamais par un identifiant de clip.
- `moqi_publier` ne publie pas sur le champ : il pose une sortie armée, et il exige que la personne ait déjà réglé ses paramètres TikTok sur moqi.fr. Ne jamais remplir ces réglages à sa place.
- Pour relier un compte TikTok, `moqi_relier_un_compte` rend un lien que la personne ouvre elle-même.

## Les chiffres

`moqi_videos` rend les vues, likes, commentaires et partages des vidéos du compte TikTok relié. Moqi ne relie pas de façon fiable un clip fabriqué à la vidéo TikTok correspondante : ne pas déduire ce lien.
