# Moqi pour Claude Code

Découpe tes vidéos YouTube et Twitch en clips verticaux sous-titrés, programme leurs sorties TikTok et lis leurs chiffres, sans quitter Claude Code.

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

## Ce que ça coûte

Chaque découpage se paie en Moqi, la monnaie du site, sur ton solde, au même prix que depuis moqi.fr. Claude te demande ton accord avant chaque action qui coûte ou qui publie. La connexion apparaît sur ta page API (https://moqi.fr/compte/api), avec un plafond de dépense par jour que tu règles, et elle se coupe d'un clic.

## Le plugin contient

- le serveur MCP de Moqi (`https://moqi.fr/api/mcp`) ;
- une compétence, `moqi-clips`, qui apprend à Claude à ne pas payer deux fois un découpage et à lire les refus de Moqi.

## Confidentialité

Le plugin ne collecte rien lui-même. Ce que Moqi traite quand tu t'en sers est décrit sur https://moqi.fr/confidentialite.

Support : contact@moqi.fr
