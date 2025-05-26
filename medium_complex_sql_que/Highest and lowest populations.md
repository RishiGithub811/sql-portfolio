-- Display highest and lowest populations corresponding to each states. 
CREATE TABLE Cities (
    id INT AUTO_INCREMENT PRIMARY KEY,
    state_name VARCHAR(100),
    city_name VARCHAR(100),
    population INT
);

INSERT INTO Cities (state_name, city_name, population) VALUES

('Maharashtra', 'Mumbai', 12442373),
('Maharashtra', 'Pune', 3124458),
('Maharashtra', 'Nagpur', 2405665),
('Uttar Pradesh', 'Lucknow', 2815601),
('Uttar Pradesh', 'Kanpur', 2737190),
('Uttar Pradesh', 'Varanasi', 1198491),
('Tamil Nadu', 'Chennai', 7090000),
('Tamil Nadu', 'Coimbatore', 1704694),
('Karnataka', 'Bengaluru', 8443675),
('Karnataka', 'Mysuru', 1014227);



select * from Cities; 
-- Solution

SELECT *,
       MAX(population) OVER (PARTITION BY state_name) AS maximum_population,
       MIN(population) OVER (PARTITION BY state_name) AS minimum_population
FROM Cities;
