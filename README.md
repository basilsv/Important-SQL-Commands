# Important-SQL-Commands
Just a repo to keep important SQL commands to refer easily. Can be used on db-fiddle.com

## Schema SQL Commands
### These are commands to creat the schema

create table tutorials_tbl(
   tutorial_id INT NOT NULL AUTO_INCREMENT,
   tutorial_title VARCHAR(100) NOT NULL,
   tutorial_author VARCHAR(40) NOT NULL,
   submission_date DATE,
   PRIMARY KEY ( tutorial_id )
);

INSERT INTO tutorials_tbl (tutorial_title, tutorial_author, submission_date) 
VALUES ("Learn MySQL", "Abdul S", NOW());

INSERT INTO tutorials_tbl 
(tutorial_title, tutorial_author, submission_date)
VALUES
("Learn PHP", "John Poul", NOW());

INSERT INTO tutorials_tbl
(tutorial_title, tutorial_author, submission_date)
VALUES
("JAVA Tutorial", "Sanjay", '2007-05-06');

create table tcount_tbl
(
tutorial_author varchar(40) NOT NULL,
tutorial_count  INT
 );
 
 INSERT INTO tcount_tbl
(tutorial_author, tutorial_count) values ('mahran', 20);

INSERT INTO tcount_tbl
(tutorial_author, tutorial_count) values ('mahnaz', NULL);

INSERT INTO tcount_tbl
(tutorial_author, tutorial_count) values ('Jen', NULL);

INSERT INTO tcount_tbl
(tutorial_author, tutorial_count) values ('Gill', 20);
INSERT INTO tcount_tbl
(tutorial_author, tutorial_count) values ('John Poul', 1);

INSERT INTO tcount_tbl
(tutorial_author, tutorial_count) values ('Sanjay', 1);


## Query SQL Commands
Select * from tutorials_tbl; 

UPDATE tutorials_tbl SET tutorial_title = "Learn Java" where tutorial_id=3;

Select * from tutorials_tbl;

select * from tutorials_tbl WHERE tutorial_author = "Sanjay";

Select * from tutorials_tbl where tutorial_author LIKE "%jay";

select * from tutorials_tbl;

select * from tcount_tbl;

select * from tcount_tbl ORDER BY tutorial_author DESC;

SELECT a.tutorial_id, a.tutorial_author, b.tutorial_count
 FROM tutorials_tbl a, tcount_tbl b
WHERE a.tutorial_author = b.tutorial_author;

Delete from tutorials_tbl where tutorial_id=3;

SELECT tutorial_author,tutorial_count FROM tcount_tbl WHERE tutorial_author REGEXP '^S';
SHOW CREATE TABLE tutorials_tbl;
