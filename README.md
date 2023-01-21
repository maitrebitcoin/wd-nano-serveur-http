# wd-nano-serveur-http
mini serveur http pour intégration dans une application WinDev

exemple de code
```javascript
mon_serveur est un NanoServeurHttp
// les fichier dans le sous répertoire "Site" seront renvoyé au navigateur
mon_serveur.ajoute_répertoire_virtuel("/Site", fRepDonnées() + "\Site")
mon_serveur.ajoute_traitement_uri("/",  ( requete , réponse ) => {	
    réponse.envoie_chaine("<html><body>voici la page <b>racine</b> du site <hr>en construction... </body></html>") 
})
// démarrage du serveur
mon_serveur.démarre_serveur(8080)

```

autre exemple, support d'une API en JSON

```javascript
// gestion de l'api http://localhost/api/date?heure=1
mon_serveur.ajoute_traitement_uri("/api/date", _api_date)	
PROCÉDURE INTERNE _api_date(req est RequêteHttp, réponse est ReponseHttp)
	ma_reponse est un JSON
	ma_reponse.date   = DateSys()
	SI req.tab_paramètre["heure"]="1"
		ma_reponse.heure  = HeureSys()
	FIN
	ma_reponse.machine = NetNomMachine()
	réponse.envoie_chaine( ma_reponse.VersChaîne() ) 
FIN
```

