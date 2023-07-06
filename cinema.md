### A 
```
SELECT id_film, titre, YEAR(dateSortie) AS annee, CONCAT(FLOOR(dureeMinutes / 60), ':', LPAD(dureeMinutes % 60, 2, '0')) AS duree_format, p.prenom, p.nom
FROM film f
INNER JOIN realisateur r ON f.id_film = r.id_realisateur
INNER JOIN personne p ON r.personne_id = p.id_personne
```

### B
```
SELECT titre, dureeMinutes
FROM film f 
WHERE dureeMinutes >= 135
ORDER BY dureeMinutes DESC
```

### C
```
SELECT titre, FLOOR(YEAR(dateSortie)) AS annee
FROM film f 
WHERE f.realisateur_id = 4
```

### D
```
SELECT nom, COUNT(genre_id) AS nbrFilm
FROM genre g
INNER JOIN posseder p ON g.id_genre = p.genre_id
GROUP BY g.id_genre
ORDER BY nbrFilm DESC
```

### E
```
SELECT nom, prenom, COUNT(f.realisateur_id) AS nbrFilm
FROM personne p
INNER JOIN realisateur r ON p.id_personne = r.personne_id
INNER JOIN film f ON r.id_realisateur = f.realisateur_id
GROUP BY p.id_personne
ORDER BY nbrFilm DESC
```

### F
```
SELECT nom, prenom, sexe
FROM personne p
INNER JOIN acteur a ON p.id_personne = a.personne_id
INNER JOIN jouer j ON a.id_acteur = j.acteur_id
WHERE film_id = 1
```

### G
```
SELECT nom, YEAR(dateSortie) AS annee
FROM role r 
INNER JOIN jouer j ON r.id_role = j.role_id
INNER JOIN film f ON j.film_id = f.id_film
WHERE acteur_id = 13
ORDER BY annee DESC
```

### H
```
SELECT nom, prenom
FROM personne p
INNER JOIN acteur a ON p.id_personne = a.personne_id
INNER JOIN realisateur r ON p.id_personne = r.personne_id
WHERE a.personne_id = r.personne_id
```

### I
Je n'ai pas pu implémenter le 'year' à l'intérieur du DATEDIFF
```
SELECT titre, YEAR(dateSortie) AS annee
FROM film f 
WHERE DATEDIFF(CURRENT_DATE, dateSortie) < 365*5 ;
```

### J
```
SELECT sexe, COUNT(sexe) as nbrTotal
FROM personne p 
INNER JOIN acteur a ON p.id_personne = a.personne_id
WHERE p.id_personne = a.personne_id
GROUP BY p.sexe
```

### K
```
SELECT nom, prenom, year(dateNaissance)
FROM personne p 
WHERE DATEDIFF(CURRENT_DATE, dateNaissance) <= 365*50 ;g
```

### L
```

```