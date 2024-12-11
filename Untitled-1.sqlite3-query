-- database: ./Edusign.db
INSERT INTO users (firstname, surname, email) 
SELECT 'Ada', 'Lovelace', 'ada@test.fr'
UNION SELECT 'Beatrice', 'Worsley', 'bea@test.fr'
UNION SELECT 'Bella', 'Guerin', 'bella@test.fr'
UNION SELECT 'Barbara', 'Chase', 'barbara@test.fr';

UPDATE edusign
SET user_id = (
    SELECT users.user_id
    FROM users
    WHERE edusign.user_id = users.user_id
)
WHERE EXISTS (
    SELECT 1
    FROM users
    WHERE edusign.user_id = users.user_id
);

SELECT * FROM users;

SELECT * 
FROM users
WHERE firstname = 'Ada';

SELECT * 
FROM users
WHERE firstname LIKE 'B%';

SELECT COUNT(*) 
FROM users;

SELECT COUNT(*) 
FROM users
WHERE firstname LIKE 'B%';

SELECT firstname
FROM users;

INSERT INTO edusign (user_id, created_at) 
VALUES (1, '2024-05-30 09:30:00');

INSERT INTO edusign (user_id, created_at)
VALUES (4, '2024-05-30 09:30:00');

INSERT INTO edusign (user_id, created_at) 
SELECT 2, '2024-09-01 09:30:00'
UNION SELECT 3, '2024-09-01 09:30:00';

SELECT * FROM edusign
ORDER BY created_at ASC, user_id ASC;

SELECT * FROM edusign
ORDER BY user_id ASC;

SELECT * FROM edusign
ORDER BY created_at ASC;

SELECT * FROM edusign
WHERE created_at = '2024-05-30 09:30:00';

SELECT created_at, COUNT(*) AS total
FROM edusign
GROUP BY created_at
ORDER BY total DESC;

SELECT COUNT(*) AS volume
FROM edusign
JOIN users ON edusign.user_id = users.user_id
WHERE users.firstname = 'Bella';