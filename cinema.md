### A 
```
SELECT id_film, titre, YEAR(dateSortie) AS annee, CONCAT(FLOOR(dureeMinutes / 60), ':', LPAD(dureeMinutes % 60, 2, '0')) AS duree_format, p.prenom, p.nom
FROM film f
INNER JOIN realisateur r ON f.id_film = r.id_realisateur
INNER JOIN personne p ON r.personne_id = p.id_personne
```

### B
```

```

### C
```

```

### D
```

```

### E
```

```

### F
```

```