[See assignment in Alexa](https://alexa.bitmaker.co/cohorts/72/assignments/2247/latest)

# ----- Answers ----- #

1. Let's start by figuring out how many dinosaurs we have. Count the number of dinosaurs.

    SELECT COUNT(id) FROM dinos;
    => 331

2.  Find all the dinosaurs from the Jurassic period.

    SELECT name FROM dinos WHERE period='Jurassic';
    => returns a long list

3.  Find the total sum length of all the dinosaurs from the Cretaceous period.

    SELECT SUM(length) FROM dinos WHERE period='Cretaceous';
    => 1366.45

4.  Find all the dinosaurs from either the Jurassic OR Cretaceous periods, and order them by their species name alphabetically.

    SELECT name FROM dinos WHERE period='Jurassic' OR period='Cretaceous' ORDER BY name ASC;
    => returns a long list

5.  Find all the dinosaurs from the t_order Saurischia that are Herbivorous.

    SELECT name FROM dinos WHERE t_order='Saurischia' AND diet='Herbivorous';
    => returns a long list

6.  Find the shortest dinosaur, and rename it Shortie.

    UPDATE dinos SET name = 'Shortie' WHERE length=(SELECT MIN(length) FROM dinos);
    => one record updated

7.  Find the alphabetically first dinosaur, so we can make sure they're present for class.

    SELECT name FROM dinos ORDER BY name ASC limit 1;
    => Aardonyx

8.  Rename the five longest dinosaurs The Famous Five.

    UPDATE dinos SET name = 'The Famous Five' WHERE name in (SELECT name FROM dinos ORDER BY length DESC limit 5);
