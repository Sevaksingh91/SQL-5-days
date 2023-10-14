create sequence gym_members
start with 1
increment by 1;


create table gym_members_table(
id number(5) primary key,
name varchar(25) not null,
age number(3) not null check(age>0),
joining_date date not null,
expiration_date date not null,
city varchar2(35) default 'pune' not null,
height number(2) not null check(height>0),
weight number(3) not null check(weight>0),
created_at date default sysdate
);
        
insert into gym_members_table(id, name, age, joining_date, expiration_date, city, height, weight, cost) values(gym_members.nextval, 'Vaibhav', 22, '12-June-2023', '24-oct-2023', 'Mumbai', 5, 55, 25000);

insert into gym_members_table(id, name, age, joining_date, expiration_date, city, height, weight, cost) values(gym_members.nextval, 'Ram', 21, '1-June-2023', '24-oct-2023', 'Mumbai', 5, 55, 19000); 

insert into gym_members_table(id, name, age, joining_date, expiration_date, city, height, weight, cost) values(gym_members.nextval, 'Atharv', 20, '1-June-2022', '24-oct-2023', 'Mumbai', 6, 65, 30000);

insert into gym_members_table(id, name, age, joining_date, expiration_date, city, height, weight, cost) values(gym_members.nextval, 'Jay', 24, '1-Jun-2023', '24-oct-2023', 'Kolhapur', 5, 70, 18000);      

insert into gym_members_table(id, name, age, joining_date, expiration_date, city, height, weight, cost) values(gym_members.nextval, 'Shivam', 18, '1-Jan-2023', '24-June-2023', 'Satara', 4, 40, 22000);    

insert into gym_members_table(id, name, age, joining_date, expiration_date, city, height, weight, cost) values(gym_members.nextval, 'Kiran', 22, '1-Feb-2023', '28-June-2023', 'Thane', 7, 80, 33000); 

select * from gym_members_table where cost>20000;

select * from gym_members_table where city='Pune';

select * from gym_members_table where city='Mumbai' and age>24;

select * from gym_members_table where months_between(expiration_date, joining_date)=3;  

select name, (weight/height*height) as bmi from gym_members_table;   

select name, height from gym_members_table order by height desc;

select name, city, EXTRACT(YEAR FROM sysdate)-age as birth_year from gym_members_table where city='Mumbai'; 
