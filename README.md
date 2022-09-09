# cassandra

### To create CASSANDRA service for Networking Portion ####

#kubectl apply -f service.yaml

### To create CASSANDRA statefulset deployment with 3 nodes replication ####

#kubectl apply -f deploy.yaml


### Cassendra Cluster Info ###

#nodetool status 

Note: Where nodetool gives many info with different parrameters about your cluster info/healthy/etc..,

					                    ################### Validation ####################
                              
### Login cassandra No-SQL console ###

#cqlsh

### Create keyspace(Database) with Specified your Cluster Name ####

CREATE KEYSPACE test_keyspace1
WITH replication = {'class':'NetworkTopologyStrategy', 'DC1' : 3};


### Create table ###

CREATE TABLE emp(
   emp_id int PRIMARY KEY,
   emp_name text,
   emp_city text,
   emp_sal varint,
   emp_phone varint
   emp_role text
   );
   
##### Insert Query ###

INSERT INTO emp (emp_id, emp_name, emp_city,
   emp_phone, emp_sal) VALUES(1,'Dinesh', 'Coimbatore', 12345, 45000);
   
INSERT INTO emp (emp_id, emp_name, emp_city,
   emp_phone, emp_sal) VALUES(2,'Sabari', 'Singapore', 678910, 50000);
 



### Select entry on other pod ### 

SELECT * FROM emp;

