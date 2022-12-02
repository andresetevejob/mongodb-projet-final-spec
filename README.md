# mongodb-projet-final-spec


NB: Les valeurs des objets json contenues dans les requêtes sont à titre d'exemple.
## Description des api

1 - creation d'un article

````
url :  /api/article/
method: POST
requête : 
{ 
    
    "title": "monarticle",
    "description": "madescription",
    "date": "12/12/2022",
    "categorieId":"034447bfcg5353",
    "auteurId":"948848fge56777",
    "tags":["sports","football","coupe du monde"]
 
}
réponse succès: 
{ 
    "message": "Article crée",
    "id": "035454646dfc",
}
réponse error: 
{ 
    "message": "Article non crée, une erreur est survenue lors de la création",
}
`````
2 - modification d'un article

````
 url :  /api/article/035454646dfc
 method: PUT
requête : 
{ 
    
    "title": "monarticle",
    "description": "madescription",
    "date": "12/12/2022",
    "categorieId":"034447bfcg5353",
    "auteurId":"948848fge56777",
    "tags":["sports","football","coupe du monde"]
 
}
réponse succès: 
{ 
    "message": "Article modifié",
    "id": "035454646dfc",
}
réponse error: 
{ 
    "message": "Article non modifié, une erreur est survenue lors de la création",
}
`````
3 - détails d'un article

````
 url :  /api/article/035454646dfc
 method: GET

réponse succès: 
{ 
     "_id":"035454646dfc",
    "title": "monarticle",
    "description": "madescription",
    "date": "12/12/2022",
    "categorie":{"libelle":"ma categorie"},
    "auteur":{"nom": "Jules", "prenoms": "Ilé"},
    "tags":["sports","football","coupe du monde"],
    "commentaires":[
        {"description":"xxxx",date:"12/12/2022"},
    ]
 
}
réponse error: 
{ 
    "message": "L'article n'a pu être recupéré",
}


```````
 4 - suppression d'un article

````
 url :  /api/article/035454646dfc
 method: DELETE

réponse succès: 
{ 
    "message": "L'article 035454646dfc a été supprimé",
}
réponse error: 
{ 
    "message": "L'article n'a pu être supprimé",
}
`````

 5 - ajout de commentaire

````
 url :  /api/article/035454646dfc/comment
 method: POST
requête : 
{ 
    "description": "mon commentaire",
    "date": "12/12/2022",
}
réponse succès: 
{ 
    "message": "Votre commentaire a été ajouté",
}
réponse error: 
{ 
    "message": "Votre commentaire n'a pu être ajouté,une erreur est survenue",
}
`````

 5 - Liste des articles

````
 url :  /api/articles/
 method: GET
réponse succès: 
[
    { 
     "_id":"766777fcdg",
     "title": "monarticle",
     "description": "madescription",
     "date": "12/12/2022",
     "categorie":{"libelle":"ma categorie"},
     "auteur":{"nom": "Jules", "prenoms": "Ilé"},
     "tags":["sports","football","coupe du monde"],
    },
    { 
      "_id":"766777fcdi",
     "title": "monarticle 1",
     "description": "madescription essai",
     "date": "12/12/2022",
     "categorie":{"libelle":"ma categorie"},
     "auteur":{"nom": "Jules", "prenoms": "Ilé"},
     "tags":["sports","football","coupe du monde"],
    }
]
réponse error: 
{ 
    "message": "La liste des articles n'a pu être recupérée",
}
`````


5 - Liste des categories

````
url :  /api/categories/
method: GET
réponse succès: 
[
    { 
     "_id":"766777sdfcdg",
     "title": "monarticle",
    },
    { 
      "_id":"7667dd77fcdi",
     "title": "monarticle 1",
    }
]
réponse error: 
{ 
    "message": "La liste des categories n'a pu être recupérée",
}
`````


6 - Liste des auteurs

````
 url :  /api/auteurs/
 method: GET
réponse succès: 
[
    { 
      "_id":"766777sdfcdga",
      "nom": "monnom",
      "prenom": "monprenom",
    },
    { 
      "_id":"7667dd77fcdio",
      "nom": "monnom1",
      "prenom": "monprenom1",
    }
]
réponse error: 
{ 
    "message": "La liste des auteurs n'a pu être recupérée",
}
`````