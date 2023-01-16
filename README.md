# wd-nano-serveur-http
mini serveur http pour intégration dans une application WinDev

exemple de code
```ruby
mon_serveur est un NanoServeurHttp
mon_serveur.ajoute_traitement_uri("/",  ( requete , réponse ) => {	
	réponse.envoie_chaine("<html><body>voici la page <b>racine</b> du site <hr>en construction... </body></html>") 
})
mon_serveur.démarreServeur(8080)

```
