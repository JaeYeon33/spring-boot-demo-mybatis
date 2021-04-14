# spring-boot-demo-mybatis

### Table
- company table 생성
```sql
create table company (
		id INTEGER AUTO_INCREMENT PRIMARY KEY,
		company_name VARCHAR(128),
		company_address VARCHAR(128),
		INDEX (company_name)
)
```


```sql
+-----------------+--------------+------+-----+---------+----------------+
| Field           | Type         | Null | Key | Default | Extra          |
+-----------------+--------------+------+-----+---------+----------------+
| id              | int          | NO   | PRI | NULL    | auto_increment |
| company_name    | varchar(128) | YES  | MUL | NULL    |                |
| company_address | varchar(128) | YES  |     | NULL    |                |
+-----------------+--------------+------+-----+---------+----------------+
3 rows in set (0.08 sec)
```

- employee table 생성

```sql
CREATE TABLE employee (
		id INTEGER AUTO_INCREMENT PRIMARY KEY,
		company_id INTEGER,
		company_name VARCHAR(128),
		employee_address VARCHAR(128),
		INDEX (employee_name),
		FOREIGN KEY (company_id) REFERENCES company(id)
)
```
```sql
+------------------+--------------+------+-----+---------+----------------+
| Field            | Type         | Null | Key | Default | Extra          |
+------------------+--------------+------+-----+---------+----------------+
| id               | int          | NO   | PRI | NULL    | auto_increment |
| company_id       | int          | YES  | MUL | NULL    |                |
| employee_id      | varchar(128) | YES  |     | NULL    |                |
| employee_name    | varchar(128) | YES  | MUL | NULL    |                |
| employee_address | varchar(128) | YES  |     | NULL    |                |
+------------------+--------------+------+-----+---------+----------------+
5 rows in set (0.01 sec)
```


### Directory
```text
src
  |
  --- main
  |      |
  |      --- java
  |            |
  |            --- com.example.demomybatis
  |            |             |
  |            |             --- Company.java
  |            |             --- CompanyController.java
  |            |             --- CompanyMapper.java
  |            |             --- CompanyService.java
  |            |             --- DemoMybatisApplication.java
  |            |             --- Employee.java
  |            |             --- EmployeeController.java
  |            |             --- EmployeeMapper.java
  |            --- resources
  |                    |
  |                    --- static
  |                    --- templates
  |                    --- application.properties
  --- test
        |
        --- java
              |
              --- com.example.demomybatis
                            |
                            --- DemoMybatisApplicationTest.java
```			    

