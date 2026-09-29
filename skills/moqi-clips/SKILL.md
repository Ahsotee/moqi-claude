---
name: moqi-clips
description: Piloter un compte Moqi. Découper une vidéo YouTube ou Twitch en clips verticaux, suivre le découpage, programmer ou publier les clips sur TikTok, lire leurs chiffres, et gérer le reste du compte (pilote automatique, style des clips, page de liens, suppressions, support). À utiliser quand la personne parle de clips, de TikTok, de Shorts, de Reels, de découper une vidéo, de programmer des sorties ou de son compte Moqi.
---

# Travailler avec Moqi

Moqi transforme une vidéo longue en clips verticaux sous-titrés, recadrés sur la personne qui parle. Les outils `moqi_*` viennent du serveur MCP de Moqi (`https://moqi.fr/api/mcp`). Tant que le compte n'est pas connecté, Claude Code indique que Moqi demande une connexion : lancer `/mcp` et choisir Moqi ouvre la page d'autorisation de Moqi.

## Ce qui coûte, et comment ne pas payer deux fois

- Tout se paie en Moqi, sur le solde du compte. `moqi_devis` donne le prix exact d'un découpage et ce qui manque, avec les mêmes réglages que `moqi_decouper` : le dire à la personne avant de lancer.
- **Un découpage de plusieurs clips est UN seul appel** : pour 5 clips d'une vidéo, `moqi_decouper` une fois avec `clipCount: 5`. Cinq appels feraient cinq découpages facturés.
- `sous_titres: false` retire les sous-titres (moins cher), `langue_sous_titres: "fr"` les traduit (payant).
- Rien n'est instantané. Après `moqi_decouper`, relire l'état avec `moqi_decoupage` en respectant `sonder_dans_s`, jusqu'à `fini` ou `echoue`.
- `moqi_analyse` montre les moments retenus ET écartés d'un découpage, avec la raison de chaque score. Un moment écarté se fabrique avec `moqi_moment` (payant, un à la fois).

## Ce qui ne se défait pas

Supprimer un découpage, un clip, une création ou la page de liens, couper le pilote, délier un compte TikTok : sans `confirme: true`, l'outil refuse avec `confirmation_required` et dit ce qui serait perdu. Le répéter à la personne, et ne rappeler avec `confirme: true` qu'après son oui.

## Les refus

Chaque erreur porte `reessayable` :

- `oui` : un nouvel essai peut passer ;
- `jamais` : recommencer donnera le même refus ;
- `apres-action` : la personne doit agir (recharger des Moqi, régler une facture). Le lui dire, et ne pas boucler.

## Programmer et publier

- `moqi_programmer` pose une sortie dans l'agenda, que la personne publiera elle-même : le clip se désigne par son découpage et sa position, jamais par un identifiant de clip ; une vidéo générée par `moqi_creer` se désigne par `creation`.
- `moqi_publier` fait partir un clip ou une vidéo générée, mais pas sur le champ : il pose une sortie armée que Moqi envoie dans quelques minutes (ou à l'heure donnée), et il exige que la personne ait déjà réglé ses paramètres TikTok sur moqi.fr. Ne jamais remplir ces réglages à sa place, ne publier que sur sa demande, et ne jamais dire que la vidéo est déjà en ligne.
- Une image ne part pas sur TikTok. Une vidéo qui n'est pas en 9:16 part avec des bandes : la réponse le dit dans `avertissement`, le lui répéter.
- Pour relier un compte TikTok, `moqi_relier_un_compte` rend un lien que la personne ouvre elle-même.
- `moqi_modifier_sortie` corrige le titre, la description ou les hashtags d'une sortie ; `moqi_marquer_publiee` note une sortie qu'elle a postée elle-même.

## Le pilote automatique

`moqi_regler_pilote` change son rythme (sorties par semaine, jours, moments), `moqi_pause_pilote` le met en pause. L'allumer ou le relancer reste à la personne, sur moqi.fr : aucun outil ne le fait.

## Le reste du compte

`moqi_lire_style` puis `moqi_modifier_style` pour le style des prochains clips ; `moqi_lire_page` puis `moqi_modifier_page` pour la page de liens (`liens` remplace toute la liste : renvoyer ceux à garder avec leur `id`) ; `moqi_fuseau`, `moqi_notifications`, et `moqi_support_ouvrir` pour écrire au support humain. Payer, changer de formule et les réglages de publication TikTok restent sur le site.

## Les chiffres

`moqi_videos` rend les vues, likes, commentaires et partages des vidéos du compte TikTok relié, `moqi_statistiques` les totaux du compte. Moqi ne relie pas de façon fiable un clip fabriqué à la vidéo TikTok correspondante : ne pas déduire ce lien.
