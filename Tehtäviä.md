# OSIO 1: Relaatiotietokannan peruskäsitteiden harjoitukset

### Tehtävä 1

vastaus: 5

### Tehtävä 2

vastaus: 5

### Tehtävä 3

vastaus: ident

### Tehtävä 4

vastaus: varchar

### Tehtävä 5

vastaus: iso_country

### Tehtävä 6

vastaus: country

### Tehtävä 7

vastaus: iso_country

### Tehtävä 8

vastaus: varchar

### Tehtävä 9

vastaus: 70942

### Tehtävä 10

vastaus: iso_country

### Tehtävä 11

vastaus: varchar

### Tehtävä 12

vastaus: 248

### Tehtävä 13

vastaus: goal

### Tehtävä 14

vastaus: 0DEG

### Tehtävä 15

vastaus: id

### Tehtävä 16

vastaus: Epätosi

### Tehtävä 17

vastaus: game

### Tehtävä 18

vastaus: game

### Tehtävä 19

vastaus: game

### Tehtävä 20

vastaus: game

### Tehtävä 21

vastaus: id

### Tehtävä 22

vastaus: location

### Tehtävä 23

vastaus: goal_reached

### Tehtävä 24

vastaus: goal_id, game_id

### Tehtävä 25

vastaus: 2

# OSIO 2: Yhteen tauluun kohdistuvien kyselyiden harjoitukset

### Tehtävä 1

select * from goal;

![image](https://github.com/user-attachments/assets/e16cab4b-301e-4b88-ba21-dcfe198920ce)

### Tehtävä 2

select name from airport where iso_country = "FI";

![image](https://github.com/user-attachments/assets/e0e93c1e-1861-4bde-8d3f-baf76e0c211c)

### Tehtävä 3

select name from airport where iso_country = "FI" order by name asc;

![image](https://github.com/user-attachments/assets/e5fa289d-5325-4e8d-a9e0-53e04bb62174)

### Tehtävä 4

select name, type from airport where iso_country = "FI" order by type asc, name asc;

![image](https://github.com/user-attachments/assets/a1763a83-b15c-4734-aa5d-5642de9c4fb8)

### Tehtävä 5

select name from country where name like "f%";

![image](https://github.com/user-attachments/assets/e752f936-0b8d-424a-9c72-a15f11c79531)

### Tehtävä 6

select name from country where name like "%f%";

![image](https://github.com/user-attachments/assets/5615a8e1-1b38-470b-9e4b-4330abe55392)

### Tehtävä 7

select location from game where screen_name = "Vesa";

![image](https://github.com/user-attachments/assets/ec9ebffb-0055-4b81-b408-e463ae5a96d9)

### Tehtävä 8

select co2_consumed from game where screen_name = "Ilkka";

![image](https://github.com/user-attachments/assets/8f8590e8-9f02-4768-8374-edaa5167bbb2)

### Tehtävä 9

select distinct co2_budget from game;

![image](https://github.com/user-attachments/assets/4be1f833-afdf-43ef-ad7d-ad7106f7711d)

# OSIO 2: Where-osan liitosehto harjoitukset

### Tehtävä 1

select country.name as "country name", airport.name as "airport name" from airport, country where airport.iso_country = country.iso_country and country.name = "Iceland";

![image](https://github.com/user-attachments/assets/87f91d46-8ad5-4a45-9e31-6609ec57dc7e)

### Tehtävä 2

select airport.name as "airport name" from airport, country where airport.iso_country = country.iso_country and country.name = "France" and airport.type = "large_airport";

![image](https://github.com/user-attachments/assets/80ba5b04-7d76-4ba6-ae00-db9790eb70dd)

### Tehtävä 3

select country.name as country_name, airport.name as airport_name from airport, country where airport.iso_country = country.iso_country and country.continent = "AN";

![image](https://github.com/user-attachments/assets/552f1635-b146-4113-be3a-f6fac86265e3)

### Tehtävä 4

select elevation_ft from airport, game where location = ident and screen_name = "Heini";

![image](https://github.com/user-attachments/assets/4b5f90b1-bec4-4e7f-bed9-52248cd81390)

### Tehtävä 5

select elevation_ft * 0.3048 as elevation_m from airport, game where location = ident and screen_name = "Heini";

![image](https://github.com/user-attachments/assets/8eae1858-f8a1-4847-bbd7-58f38f37b599)

### Tehtävä 6

select name from airport, game where location = ident and screen_name = "Ilkka";

![image](https://github.com/user-attachments/assets/30af2622-a3b0-4f5a-baf2-71ad4638dc36)

### Tehtävä 7

select country.name from airport, game, country where location = ident and airport.iso_country = country.iso_country  and screen_name = "Ilkka";

![image](https://github.com/user-attachments/assets/2852d10a-8ae4-4146-a8db-536bd1bd97e2)

### Tehtävä 8

select name from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini";

![image](https://github.com/user-attachments/assets/21d0d5d8-95f1-4710-8557-e46435cf3099)

### Tehtävä 9

select airport.name from airport, game, goal, goal_reached where ident = location and game.id = game_id and goal.id = goal_id and screen_name = "Ilkka" and goal.name = "CLOUDS";

![image](https://github.com/user-attachments/assets/4a5db197-2ecb-4b76-b8b6-ff1d2246b260)

### Tehtävä 10

select country.name from country, airport, game, goal, goal_reached where airport.iso_country = country.iso_country and ident = location and game.id = game_id and goal.id = goal_id and screen_name = "Ilkka" and goal.name = "CLOUDS";

![image](https://github.com/user-attachments/assets/c8055cc0-c5bd-4cd0-bace-375610c08101)

# OSIO 3: Join harjoitukset

### Tehtävä 1

select country.name as "country name", airport.name as "airport name" from country inner join airport on airport.iso_country = country.iso_country where country.name = "Finland" and scheduled_service = "yes";

![image](https://github.com/user-attachments/assets/e40bd40f-f86d-4705-a7e2-4443330281e3)

### Tehtävä 2

select screen_name, airport.name from game inner join airport on location = ident;

![image](https://github.com/user-attachments/assets/2199cd09-52e6-4087-8016-270187df748d)

### Tehtävä 3

select screen_name, country.name from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/9c849268-9283-45b3-a4d8-636692e0c951)

### Tehtävä 4

select airport.name, screen_name from airport left join game on ident = location where name like "%Hels%";

![image](https://github.com/user-attachments/assets/67360b2e-970d-41c3-826e-662961ed05bc)

### Tehtävä 5

select name, screen_name from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;

![image](https://github.com/user-attachments/assets/0c35eb67-e555-4875-b763-0f677765f03a)

# OSIO 3: Sisäkysely harjoitukset 

### Tehtävä 1

select name from country where iso_country in(select iso_country from airport where name like "Satsuma%");

![image](https://github.com/user-attachments/assets/eeacd7a5-2b49-454d-b38a-ed88df847d8e)

### Tehtävä 2

select name from airport where iso_country in(select iso_country from country where name = "Monaco");

![image](https://github.com/user-attachments/assets/12d84bde-6ea8-4e09-bbe6-a6f5dd08bb49)

### Tehtävä 3

select screen_name from game where id in (select game_id from goal_reached where goal_id in(select id from goal where name = "CLOUDS"));

![image](https://github.com/user-attachments/assets/611a0dcb-5bd0-4ad3-ba33-9f24238f9c27)

### Tehtävä 4

select country.name from country where iso_country not in(select airport.iso_country from airport);

![image](https://github.com/user-attachments/assets/f206662f-8f86-4d63-99f2-1da845215c3d)

### Tehtävä 5

select name from goal where id not in(select goal.id from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini");

![image](https://github.com/user-attachments/assets/c0d39cff-0c57-45c7-8816-4a667d308c49)

# OSIO 4: Koostetieto kyselyt harjoitukset

### Tehtävä 1

select max(elevation_ft) from airport;

![image](https://github.com/user-attachments/assets/fe4b2f99-5475-43f3-9e63-1cb06aee2c93)

### Tehtävä 2

select continent, count(*) from country group by continent;

![image](https://github.com/user-attachments/assets/f4098822-e00f-4121-a3a3-11d7701f37d8)

### Tehtävä 3

select screen_name, count(*) from game, goal_reached where id = game_id group by screen_name;

![image](https://github.com/user-attachments/assets/9b243d61-c446-4ee0-bd59-7bbcefcc05a5)

### Tehtävä 4

select screen_name from game where co2_consumed in(select min(co2_consumed) from game);

![image](https://github.com/user-attachments/assets/711daa07-0ec2-42c5-afc5-669ad15bce39)

## Tehtävä 5

select country.name, count(*) from airport, country where airport.iso_country = country.iso_country group by country.iso_country order by count(*) desc limit 50;

![image](https://github.com/user-attachments/assets/214188e1-cd22-4cbe-902c-aa0a9ed8b6be)

### Tehtävä 6

select country.name from airport, country where airport.iso_country = country.iso_country group by country.iso_country having count(*) > 1000;

![image](https://github.com/user-attachments/assets/89b162b2-9647-484e-83d9-e9b086de835f)

### Tehtävä 7

select name from airport where elevation_ft in (select max(elevation_ft)from airport);

![image](https://github.com/user-attachments/assets/59e6e161-7ae3-49db-9878-9389fc0fd54e)

### Tehtävä 8

select name from country where iso_country in (select iso_country from airport where elevation_ft in(select max(elevation_ft)from airport));

![image](https://github.com/user-attachments/assets/6ee4bd3b-6f36-4fa9-a35b-e5041d72af55)

### Tehtävä 9

select count(*) from game, goal_reached where id = game_id and screen_name = "Vesa" group by screen_name;

![image](https://github.com/user-attachments/assets/8acfe4d8-324f-4e89-9a6f-9b0e904815a4)

### Tehtävä 10

select name from airport where latitude_deg in(select min(latitude_deg)from airport);

![image](https://github.com/user-attachments/assets/18284111-127f-426d-9bc3-7f3645fb8d7a)
