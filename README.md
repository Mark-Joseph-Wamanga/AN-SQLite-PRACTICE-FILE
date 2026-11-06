# AN SQLite PRACTICE FILE OF CREATING AND ALTERING TABLE

--CREATING A TABLE FOR THE NIGERIAN GEOPOLITICAL TERRITORIES
CREATE TABLE nigeria_geopolitical_territories(
            state VARCHAR(15),
  			state_abbreviation CHAR(3),
  			capital VARCHAR(15),
  			slogan TEXT,
  			date_created DATE,
  			geopolitical_zone VARCHAR(15),
  			number_of_local_governments INT,
  			political_party_of_the_governer VARCHAR(3)
  											);
                                            
  -- INSERTING RECORDS INTO NIGERIA STATE TABLES
  INSERT INTO nigeria_geopolitical_territories (state, state_abbreviation, capital, slogan, date_created, geopolitical_zone, number_of_local_governments, political_party_of_the_governer)
  VALUES ('Jigawa', 'JIG', 'Duste', 'Liberal State', '1991-08-27', 'North West', '27', 'APC'),
  		('Delta', 'DEL', 'Asaba', 'The Big Heart', '1991-08-27', 'South South', '25', 'APC'),
        ('Yobe', 'YOB', 'Damaturu', 'The Young Shall Grow', '1991-08-27', 'North East', '17', 'APC'),
        ('Zamfara', 'ZAM', 'Gusau', 'Home of Agricultural Products', '1976-02-03', 'North West', '14', 'APC'),
        ('Ebonyi', 'EBO', 'Abakaliki', 'Salt of the Nation', '1976-02-03', 'North West', '13', 'APC'),
        ('Gombe', 'GOM', 'Gombe', 'Land of Hope', '1976-10-01', 'North East', '11', 'APC'),
        ('Akwa-Ibom', 'AKW', 'Uyo', 'Home of All', '1987-09-23', 'South South', '31', 'APC'),
        ('Taraba', 'TAR', 'Jalingo', 'Nature`s Gift to the Nation', '1992-08-01', 'North East', '17', 'APC'); 
        
--SEEING THE RECORDS INSERTED INTO THE TABLE
SELECT *
FROM nigeria_geopolitical_territories
        
--UPDATING THE TABLE WITH SLOGANS OF SOME STATES
UPDATE nigeria_geopolitical_territories
set slogan = 'The New World'
where state = 'Jigawa';

UPDATE nigeria_geopolitical_territories
set slogan = 'Pride of the Sahel'
where state = 'Yobe';

UPDATE nigeria_geopolitical_territories
set slogan = 'Land of Promises'
where state = 'Akwa-Ibom';

UPDATE nigeria_geopolitical_territories
set slogan = 'Farming is Our Pride'
where state = 'Zamfara'

UPDATE nigeria_geopolitical_territories
set slogan = '	Jewel of Savannah'
where state = 'Gombe'

--SEEING THE UPDATED TABLE
SELECT *
FROM nigeria_geopolitical_territories

--ATERING THE TABLE AND A COLUMN WITH GOVERNOR NAMES

ALTER TABLE nigeria_geopolitical_territories
ADD COLUMN name_of_current_governor TEXT;

INSERT INTO nigeria_geopolitical_territories (state, state_abbreviation, capital, slogan, date_created, geopolitical_zone, number_of_local_governments, name_of_current_governor, political_party_of_the_governer)
VALUES('Sokoto', 'SOK', 'Sokoto', 'Seat of the Caliphate', '1976-02-03', 'North West', '23', 'Ahmed Aliyu', 'APC'),
		('Niger', 'NIG', 'Minna', 'The Power State', '1976-08-03', 'North Central', '25', 'Mohammed Umar Bago', 'APC');

--FILLING THE NAMES OF THE GOVERNORS FOR THE PREVIOUS STATES
UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Umar Namadi'
where state = 'Jigawa'

UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Sherif Oborewori'
where state = 'Delta'

UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Mai Mai Buni'
where state = 'Yobe'

UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Dauda Lawal'
where state = 'Zamfara'

UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Francis Nwifuru'
where state = 'Ebonyi'

UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Muhammad Inuwa Yahaya'
where state = 'Gombe'

UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Umo Eno'
where state = 'Akwa-Ibom'

UPDATE nigeria_geopolitical_territories
SET name_of_current_governor = 'Agbu Kefas'
where state = 'Taraba'

SELECT *
FROM nigeria_geopolitical_territories

