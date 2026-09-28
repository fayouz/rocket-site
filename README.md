# Rocket · site vitrine

Site statique (`public/`), sans étape de construction : `public/index.html` est la page d'accueil (offres, fonctionnalités, tarifs, FAQ, inscription, démo).

## Voir en local
```bash
python3 -m http.server 8080 -d public
```
puis http://localhost:8080

## Mise en ligne (OVH)
- Le workflow `.github/workflows/deploy.yml` envoie `public/` sur l'hébergement OVH en FTPS à chaque push sur `main`.
- Secrets du dépôt à créer (GitHub › Settings › Secrets and variables › Actions) : `OVH_FTP_SERVER`, `OVH_FTP_USERNAME`, `OVH_FTP_PASSWORD`, `OVH_FTP_DIR` (souvent `www/`). Ils se trouvent dans l'espace client OVH › Hébergements › FTP-SSH.
- DNS : faire pointer `www` (et le domaine nu) vers l'hébergement OVH, puis activer le certificat SSL gratuit (Let's Encrypt) de l'hébergement.

## À savoir
- Les boutons « S'inscrire » pointent vers `https://console.rocket.app/inscription`, adresse provisoire : à remplacer par l'adresse réelle de Rocket Console.
- Le formulaire « Demander une démo » ne fait qu'afficher une confirmation : il sera branché sur Rocket Mailer ou Rocket Console.
- Règle : compléter la page à chaque nouvelle fonctionnalité livrée.
