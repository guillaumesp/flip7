# Flip 7 — LAN

PWA multijoueur du jeu de cartes **Flip 7**, jouable en temps réel sur réseau local via WebRTC (P2P).

Application non officielle, développée pour jouer entre amis. Flip 7 est une marque de The Op.

## Fonctionnement

- **Architecture étoile** : l'hôte fait autorité sur l'état du jeu ; les joueurs envoient des intentions (tirer / rester / cibler) et reçoivent l'état complet à chaque mise à jour.
- **Gameplay en P2P direct** via WebRTC (PeerJS). Seul l'échange initial de connexion (signaling) passe par le broker public PeerJS — aucune donnée de jeu n'y transite.
- Connexion par **code de partie à 5 caractères** + **QR code** (auto-remplissage).

## Règles implémentées

- Deck officiel (la valeur N apparaît N fois ; 0 une seule fois)
- Bust sur carte numérique en double
- **Flip 7** : 7 numéros différents → +15 pts, fin de manche
- Modificateurs : +2, +4, +6, +8, +10, ×2
- Cartes action : **Freeze**, **Flip 3** (chaînes gérées), **Second Chance**
- Partie à 200 points

## Utilisation

Un seul fichier autonome : `index.html`. Sert-le depuis n'importe quel hébergement statique (ou GitHub Pages).

> ⚠️ Tel quel, la **connexion** nécessite Internet (broker PeerJS public + CDN unpkg). Une fois les joueurs connectés, le flux de jeu est local. Pour un fonctionnement **100 % offline**, héberger un serveur de signaling PeerJS sur le réseau local et vendoriser les librairies.

## Développé par

[Digitalways](https://digitalways.fr) — développement web & logiciel sur mesure, Colmar.

## Licence

MIT
