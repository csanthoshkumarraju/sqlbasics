# sqlbasics
create  table emp2(e_id number, e_name varchar2(30),e_des varchar2(40));
insert into emp2 values(1,'mukesh','testing');
insert into emp2(e_name) values ('vikas');
select * from emp2;
insert into emp2 values(4,'abc','developer');
insert into emp2 values(2,'cde','support');
insert into emp2 values(3,'muke','testing');
insert into emp2 values(5,'mu','testing');
insert into emp2 values(6,'mukes','manager');
select * from emp2;
select distinct e_des from  emp2;
select distinct  e_name from emp2 where e_id = 1;
select distinct  e_name from emp2 where e_id = 1 or e_id =2;
select distinct  e_name from emp2 where e_des = 'developer';
select distinct  e_name from emp2 where e_id <> 1;
select distinct  e_name from emp2 order by  e_id ;
select  distinct e_name from emp2 where e_des IS NULL;
update emp2 set e_des = 'tl' where e_name = 'vikas';
select distinct * from emp2;
update emp2 set e_id=7 where e_name ='vikas';
select distinct * from emp2;
update emp2 set e_id=7 where e_name ='vikas';
select distinct * from emp2 order by e_id asc;
update emp2 set e_id=7 where e_name ='vikas';
select distinct * from emp2 order by e_id asc;
delete from emp2 where e_id =5;
select distinct * from emp2;
create table emp3(e_id number,e_name varchar2(30),e_loc varchar2(40),e_des varchar2(40),e_role varchar2(40));
insert into emp3 values(1,'reddy','hyderabad','senior aws','se');
insert into emp3 values(2,'abc','bangalore','jr aws','as');
insert into emp3 values(3,'cde','chennai','senior devops','sed');
insert into emp3 values(4,'fgd','trivandrum','senior oracle','seo');
insert into emp3 values(5,'jks','kolkata','ase','sej');
insert into emp3(e_id,e_name,e_loc) values (6,'kal','bhubaneswar');
select * from emp3;
update emp3 set e_des ='pyth', e_role = 'pyd' where e_id =6;
select * from emp3;
delete from emp3 where e_id =6;
select * from emp3;
update emp3 set e_des ='java', e_role = 'javat' where e_id =5;
select count(e_id) from emp3;
select * from emp3 where e_name like 'r%'; 
select * from emp3 where e_name like '%_k_%'; 
select * from emp3 where e_loc in ('bangalore','hyderabad')
select * from emp3 where e_des in ('jr aws','senior aws')
select * from emp3 where e_id between  1 and  3;
select  e_des as e_desi from emp3
create table emp5(e_id number,e_hr varchar2(30),e_sup varchar2(30),e_sal number)
insert into emp5 values(4,'qwwrw','oepql',41000)
select * from emp5
select * from emp3 full join emp5 on emp3.e_id=emp5.e_id
select e_loc,e_des from emp3 union select e_sup,e_hr from emp5
select e_name from emp3  group by e_name  having count(e_id)>1
create table emp7(e_id number,e_name varchar2(30),e_loc varchar2(40),e_des varchar2(40),e_role varchar2(40));
insert into  emp7 select * from emp3 
create table emp8(e_id number,e_name varchar2(30),e_loc varchar2(40),e_des varchar2(40),e_role varchar2(40));
insert into emp8 select * from emp7
create table friends(f_id number, f_name varchar2(30),f_conn varchar2(20),f_age number,f_pla varchar2(40)) 
insert into friends values (5,'mukesh','btech',19,'tpt')
insert into friends (f_id,f_name,f_conn,f_age) values (6,'reva','what',25)
select * from friends
select distinct * from friends
select * from friends where f_id >0
select * from friends where f_id <> 1 
select * from friends order by f_id desc
select * from friends where f_pla is null
update friends set f_pla = 'viz' where f_id = 6 
delete friends where f_id = 3
select min(f_id) as fid from friends
select avg(f_age) from friends
select * from friends where f_name like 'm%'
select * from friends where f_pla in ('tpt','rcty')
select distinct * from friends where f_age between 20 and 23 order by f_age asc
select f_age as f_years from friends order by f_years asc
create table friends1(fr_id number, f_job varchar2(30),f_con number,f_wpla varchar2(40)) 
insert into friends1 values (5,'hcl',16,'mum')
delete friends1 where fr_id = 5
select * from friends1
select * from friends  right join friends1 on  friends.f_id = friends1.fr_id
select f_name from friends union select f_job from friends1
select count(f_id),f_pla from friends group by f_pla
commit
drop table friends
alter table friends1 rename column f_wpla to f_wrpla

