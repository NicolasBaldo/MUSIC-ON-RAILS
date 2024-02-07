Réponses aux questions Exercice 2.2.3 : 

a)

° Il y a 347 albums. pour trouver cette info,j'ai Éxécuté la commande : tp Album.all et je me suis référé a la dernière ligne du tableau. 
(Note: La gem "table_print" doit être mise dans le Gemfile pour que cela fonctionne)

° L'Auteur de la chanson "White Room" n'est nul autre qu'Eric Clapton. pour trouver cette info,J'ai éxécuté la commande :
 Track.find_by(title: "White Room").artist ce qui m'as donné le nom de l'artiste.

 ° La chanson durant 188133 millisecondes est la chanson "Perfect". pour trouver cette info, J'ai éxécuté la commande: 
  title = Track.where(duration: 188133).pluck(:title).first
  (Note: La méthode pluck sers a récupérer les valeurs de la Colonne Choisie)

  ° L'album "Use Your Illusion II" a été produit par Guns N Roses. pour trouver cette info, J'ai éxécuté la commande : 
  Album.where(title: "Use Your Illusion II").pluck(:artist).first


b)

° Il y 13 Albums dont le titre contient "Great". pour trouver cette info? J'ai éxécuté la commande : 
count = Album.where("title LIKE ?", "%Great%").count 
(Note: La méthode count sert a compter le nombre d'info choisies)
(DoubleNote: Les méthodes "LIKE ?" et "% %" servent à cibler le mot en question)

° J'ai supprimé 4 albums dont le nom contenaient "music". Pour ceci J'ai éxécuté la commande : 
Album.where("title LIKE ?", "%music%").destroy_all
(Note: La méthode destroy_all supprime les fichiers ciblés)

° Il y a 2 Albums écrits par AC/DC dans la liste. Pour trouver cette info J'ai éxécuté la commande : 
count = Album.where(artist: "AC/DC").count

° Aucune Chanson dure Exactement 158589 millisecondes. Pour trouver cette info j'ai éxécuté la commande : 
count = Track.where(duration: 158589).count


c) 

° Les albums de AC/DC sont For Those About To Rock We Salute You" et "Let There Be Rock". Pour trouvé cette info j'ai éxécuté la commande: 
puts Album.where(artist: "AC/DC").pluck(:title)


° Prix total de l'album : 7.92 euros, Durée totale de l'album : 2453259 millisecondes. Pour trouver cette info j'ai éxécuté la commande : 
puts "Prix total de l'album : #{Track.where(album: 'Let There Be Rock').sum(:price)} euros, Durée totale de l'album : #{Track.where(album: 'Let There Be Rock').sum(:duration)} millisecondes"


° Coût total de la discographie de Deep Purple : 90.09 euros. Pour trouver cette info j'ai éxécuté la commande : 
puts "Coût total de la discographie de Deep Purple : #{Track.where(artist: 'Deep Purple').sum(:price)} euros"







