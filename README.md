# Moqi pour Claude Code

Découpe tes vidéos YouTube et Twitch en clips verticaux sous-titrés, génère des vidéos et des images par IA, programme leurs sorties TikTok et lis leurs chiffres, sans quitter Claude Code.

## Installer

```bash
claude plugin marketplace add Ahsotee/moqi-claude
```

```bash
claude plugin install moqi@moqi
```

Puis, dans Claude Code, lance `/mcp`, choisis **moqi** et connecte ton compte Moqi : une page moqi.fr s'ouvre, tu autorises, c'est fait. Aucune clé à copier.

Pas de compte ? Il se crée sur https://moqi.fr.

## Ce que tu peux demander

- « Découpe cette vidéo en 5 clips : https://www.youtube.com/watch?v=… »
- « Où en est mon découpage ? »
- « Programme le clip 2 pour mardi 18 h. »
- « Combien de vues ont fait mes dernières vidéos TikTok ? »
- « Pourquoi ce clip a 62 ? Il y avait d'autres bons moments ? »
- « Qu'est-ce que mon coach me fait poster cette semaine ? Passe mon rythme à trois vidéos. »
- « Combien j'ai gagné avec Moqi ? Donne-moi mon lien d'affiliation. »
- « Supprime le clip 4, il est raté. » (Claude te demande d'abord ton accord.)
- « Combien me coûterait une vidéo IA par jour pendant un mois ? Quelle formule me couvre ? »
- « Fais-moi une série de 4 épisodes avec le même personnage, et dis-moi le prix avant. »
- « Quatre visuels de mon produit pour ma boutique et Instagram. »

## Ce que ça coûte

Chaque découpage et chaque création se paient en Moqi, la monnaie du site, sur ton solde, au même prix que depuis moqi.fr. Claude te dit le prix exact avant de lancer. Claude te demande ton accord avant chaque action qui coûte ou qui publie. La connexion apparaît sur ta page API (https://moqi.fr/compte/api), avec un plafond de dépense par jour que tu règles, et elle se coupe d'un clic.

## Le plugin contient

- le serveur MCP de Moqi (`https://moqi.fr/api/mcp`) ;
- une compétence, `moqi-clips`, qui apprend à Claude à lire les conseils et les prix de Moqi avant de proposer, à ne pas payer deux fois, et à lire les refus de Moqi.

## Confidentialité

Le plugin ne collecte rien lui-même. Ce que Moqi traite quand tu t'en sers est décrit sur https://moqi.fr/confidentialite.

Support : contact@moqi.fr
