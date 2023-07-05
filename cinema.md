### A
SELECT id_film, titre, dateSortie, dureeMinutes, p.prenom, p.nom
FROM film f
INNER JOIN realisateur r ON f.id_film = r.id_realisateur
INNER JOIN personne p ON r.personne_id = p.id_personne

