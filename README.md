# BD
SET FOREIGN_KEY_CHECKS = 0;

DROP TABLE IF EXISTS Manufacturer;

DROP TABLE IF EXISTS Category;

DROP TABLE IF EXISTS Technic;

DROP TABLE IF EXISTS Flooring;

DROP TABLE IF EXISTS Practicality;

DROP TABLE IF EXISTS Waterresistance;

DROP TABLE IF EXISTS Wearresistance;

DROP TABLE IF EXISTS Price;

DROP TABLE IF EXISTS Premises;

DROP TABLE IF EXISTS Hotels;

DROP TABLE IF EXISTS OptYesNo;

DROP TABLE IF EXISTS Login;

DROP TABLE IF EXISTS Mail;

DROP TABLE IF EXISTS Passwd;

DROP TABLE IF EXISTS Roly;

DROP TABLE IF EXISTS Сustomers;

SET FOREIGN_KEY_CHECKS = 1;



CREATE TABLE Manufacturer (

Manufacturer_id INT(5),

Manufacturer_name VARCHAR(20),

Icon MEDIUMBLOB,

PRIMARY KEY (Manufacturer_id)

);

CREATE TABLE Category (

Category_id INT(5),

Category_name VARCHAR(100),

Icon MEDIUMBLOB,

PRIMARY KEY (Category_id)

);



CREATE TABLE Technic (

name VARCHAR(100),

manufacturer_id INT(5),

category_id INT(5),

INDEX(name),

icon MEDIUMBLOB,

PRIMARY KEY (name),

FOREIGN KEY (manufacturer_id) REFERENCES Manufacturer (Manufacturer_id),

FOREIGN KEY (category_id) REFERENCES Category (Category_id)

);





CREATE TABLE Flooring (

Flooring_id INT(5),

Flooring_name VARCHAR(100),

Icon MEDIUMBLOB,

PRIMARY KEY (Flooring_id)

);



CREATE TABLE Practicality (

Practicality_id INT(5),

Practicality_parameter VARCHAR(100),

PRIMARY KEY(Practicality_id)

);



CREATE TABLE Waterresistance (

Waterresistance_id INT(5),

Waterresistance_parameter VARCHAR(100),

PRIMARY KEY(Waterresistance_id)

);



CREATE TABLE Wearresistance (

Wearresistance_id INT (5),

Wearresistance_parameter VARCHAR(100),

PRIMARY KEY(Wearresistance_id)

);



CREATE TABLE Price (

Price_id INT(5),

Price_parameter VARCHAR(100),

PRIMARY KEY(Price_id)

);



CREATE TABLE Premises (

Premises_id INT(5),

Premises_name VARCHAR(100),

PRIMARY KEY(Premises_id)

);



CREATE TABLE OptYesNo (

Opt_id INT(5),

Opt_name VARCHAR(100),

PRIMARY KEY(Opt_id)

);



CREATE TABLE Hotels (

id INT,

name VARCHAR(100),

Decor_id INT(5),

Food_id INT(5),

Swim_id INT(5),

Pets_id INT(5),

INDEX(name),

PRIMARY KEY (name),

FOREIGN KEY (Decor_id) REFERENCES OptYesNo(Opt_id),

FOREIGN KEY (Food_id) REFERENCES OptYesNo (Opt_id),

FOREIGN KEY (Swim_id) REFERENCES OptYesNo (Opt_id),

FOREIGN KEY (Pets_id) REFERENCES OptYesNo (Opt_id)

);



CREATE TABLE Login (

Login_id INT(5),

login_name VARCHAR(100),

PRIMARY KEY(Login_id)

);



CREATE TABLE Mail (

Mail_id INT(5),

Mail_name VARCHAR(100),

PRIMARY KEY(Mail_id)

);



CREATE TABLE Passwd (

Passwd_id INT(5),

Passwd_name VARCHAR(100),

PRIMARY KEY(Passwd_id)

);



CREATE TABLE Roly (

Roly_id INT(5),

Roly_name VARCHAR(100),

PRIMARY KEY(Roly_id)

);



CREATE TABLE Сustomers (

id INT,

name VARCHAR(100),

login_id INT(5),

mail_id INT(5),

passwd_id INT(5),

roly_id INT(5),

INDEX(name),

PRIMARY KEY (name),

FOREIGN KEY (Login_id) REFERENCES Login (Login_id),

FOREIGN KEY (Mail_id) REFERENCES Mail (Mail_id),

FOREIGN KEY (Passwd_id) REFERENCES Passwd (Passwd_id),

FOREIGN KEY (Roly_id) REFERENCES Roly (Roly_id)

);





INSERT INTO Manufacturer (Manufacturer_id, Manufacturer_name, icon)

VALUES (0, 'Швейцария', NULL ),

(1, 'Германия', NULL ),

(2, 'Италия', NULL ),

(3, 'Турция', NULL ),

(4, 'Китай', NULL),

(5, 'Россия', NULL),

(6, 'Дания', NULL),

(7, 'Великобритания', NULL),

(8, 'Южная Корея', NULL),

(9, 'noname', NULL);



INSERT INTO Category (Category_id, Category_name, icon)

VALUES (0, 'Поломоечные машины', NULL),

(1, 'Подметальные машины', NULL),

(2, 'Комбинированные машины', NULL),

(3, 'Однодисковые машины(полотёры)', NULL),

(4, 'Полировочные машины(полировщики)', NULL),

(5, 'Пылесосы вертикального типа', NULL),

(6, 'Пылеводососы', NULL),

(7, 'Экстракционные машины(экстракторы)', NULL),

(8, 'Ковромоечные машины(ковромоечный комбайны)', NULL),

(9, 'Парогенераторы', NULL),

(10, 'Пароэкстракторы', NULL),

(11, 'Пеногенераторы', NULL),

(12, 'Генераторы холодного тумана(озонатары)', NULL),

(13, 'Генераторы горячего тумана(дезинфекторы)', NULL),

(14, 'Компакторы(пресс-контейнеры)', NULL);







INSERT INTO Technic (name, manufacturer_id, category_id, icon)

VALUES ('Поломоечная машина Cleanfix RA 431' , 0, 0, NULL),

('BENNETT PATROL P150-85R', 4, 0, NULL),

('Ручная подметальная машина Cleanfix Floobe' , 0, 1, NULL),

('IPC 750 М ', 2, 1, NULL ),

('Аккумуляторная подметальная машина HS MT 80 BC', 2, 1, NULL),

('Подметальная машина KARCHER KM 70/20 C 2SB серый', 1, 2, NULL),

('Однодисковая машина Baiyun BF522 ', 4, 3, NULL),

('Однодисковая (роторная) машина', 2, 3, NULL),

('SB 150 L22 - Однодисковая (роторная) машина', 2, 3, NULL),

('Cетевая полировальная машина / шлифмашина полировальная ELECTROLITE УПМ 1800Е', 4, 4, NULL),

('Полировочная машина Nilfisk BU 500', 6, 4, NULL),

( 'Tefal X-Force Flex 14.60 Animal Care TY99A8WO', 4,5, NULL),

('Вертикальный пылесос Dreame Wet and Dry Vacuum H11 Max Black', 4, 5, NULL),

('Пылеводосос Lavor Pro TAURUS IR', 2, 6, NULL),

('Пылесос Дастпром', 5, 6, NULL),

('Экстракторная машина Cleanfix TW 300 S', 0, 7, NULL),

('Ковровый экстрактор Truvox Hydromist Compact', 7,7, NULL),

( 'Santoemma Sabrina Maxi', 2,8, NULL),

( 'Ковромоечная машина Santoemma SHARON BRUSH', 2,8, NULL),

( ' Ковромоечная машина Truvox Hydromist 35', 7,8, NULL),

( 'LAVOR Professional GV Kone', 2,9, NULL),

( 'S-Team 6', 2,9, NULL),

( 'PROCAR Tornado Lt24 inox foamer, 24 л.',1,11, NULL),

( 'Генератор холодного тумана Patriot PT-12F 230 В', 4,12, NULL),

( 'Генератор холодного тумана Vectorfog Fogger C150+', 8,12, NULL),

( 'Электрический опрыскиватель PATRIOT PT-16F, 16 л', 4,12, NULL),

( 'TF W 160/150 HD Генератор горячего тумана', 1,13, NULL),

( 'SPECOS Thermal Fogger F-200', 4, 13, NULL),

( 'Моноблочный компактор EМC 20 COMPACT ', 5,14, NULL),

( 'Вертикальный пакетировочный пресс для отходов PRESSMAX™ 530L с одним цилиндром', 5,14, NULL);



INSERT INTO Flooring (Flooring_id, Flooring_name, icon)

VALUES (0, ' Ламинат', NULL),

(1, 'Линолеум' ,NULL),

(2, 'Керамическая плитка', NULL),

(3, 'Паркет', NULL),

(4, 'Пробковый пол',NULL),

(5, 'Наливной пол', NULL),

(6, 'Кварц-виниловые полы', NULL);



INSERT INTO Practicality(Practicality_id, Practicality_parameter)

VALUES (0, 'Может прослужить долго'),

(1, 'Практичный'),

(2, 'Высокий'),

(3, '20-40 лет службы');

INSERT INTO Waterresistance(Waterresistance_id, Waterresistance_parameter)

VALUES (0, 'Имеет водопоглощение в интервале 8-16%'),

(1, 'Водостойкий'),

(2, 'Не очень водостойкий'),

(3, 'Низкий'),

(4, 'Высокий');



INSERT INTO Wearresistance(Wearresistance_id, Wearresistance_parameter)

VALUES (0, 'Высокий'),

(1, 'Не очень высокий'),

(2, 'Износостойкий'),

(3, 'Низкий');



INSERT INTO Price(Price_id, Price_parameter)

VALUES (0, 'от 323 до 2990 рублей'),

(1, 'для бытового линолеума средняя стоимость – 300 руб./м2. полукоммерческий линолеум – 400 руб./м2.'),

(2, '?'),

(3, 'от 450 руб. за кв. м'),

(4, '1 кв метр от 2548'),

(5, '250-300 рублей за квадратный метр'),

(6, '1 792 руб./кор)');



INSERT INTO Premises (Premises_id, Premises_name)

VALUES (0, 'Жилые'),

(1, 'Приёмно-вестибюльные'),

(2, 'Общественного питания'),

(3, 'Бытового обслуживания и торговли'),

(4, 'Культурно-досугового назначения бизнес-центр'),

(5, 'Физкультурно- оздоровительного назначения'),

(6, 'Технического обслуживания и заправки автомобилей'),

(7, 'Служебные');





INSERT INTO OptYesNo (Opt_id, Opt_name)

VALUES(0, '+'),

(1, '-');

INSERT INTO Hotels(id, name, Decor_id, Food_id, Swim_id, Pets_id )

VALUES(0, 'Отели', 0,1,0,0 ),

(1, 'Гостиницы среднего класса',0,1,0,0),

(2, 'Курортные гостиницы', 0,0,0,0),

(3, 'Частные гостиницы',0,0,0,1),

(4, 'Гостиницы-апартамент', 1,1,1,1),

(5, 'Мотели', 0,0,0,0),

(6, 'Гостиницы эконом класса',0,0,0,0),

(7, 'Флайтели',0,0,0,1),

(8, 'Флотели',0,0,1,0),

(9, 'Бунгало',0,1,0,1),

(10, 'Гостиничные дворы',0,1,1,1),

(11, 'Кемпинг',1,0,1,1);



INSERT INTO Login(Login_id, login_name)

VALUES (0, 'Ivan'),

(1, 'Angelina'),

(2, 'Marewfa34'),

(3, 'DRAGO76q'),

(4, 'Systel2');



INSERT INTO Mail(Mail_id, Mail_name)

VALUES (0, 'kondukov.i@km-spb.com'),

(1, 'koreshkova.a@km-spb.com'),

(2, 'masfha@km-spb.com'),

(3, 'griller@yandex.ru'),

(4, 'nutre@gmail.com');

INSERT INTO Passwd(Passwd_id, Passwd_name)

VALUES (0, 'VIM@13'),

(1, 'Zercalo12'),

(2, 'AF23qer'),

(3, '123Qaslo'),

(4, 'Raketa123@class');



INSERT INTO Roly (Roly_id, Roly_name)

VALUES(0, 'Admin'),

(1, 'User'),

(2, 'Guest');



INSERT INTO Сustomers(id,name, login_id, mail_id, passwd_id, roly_id)

VALUES (0,'Пользователь 2',0,0,0,1),

(1,'Пользователь 1',1,1,1,0),

(2,'Пользователь 3',2,2,2,2),

(3,'Пользователь 4',3,3,3,2),

(4,'Пользователь 5',4,4,4,2);



SELECT * FROM Manufacturer;

SELECT * FROM Category;

SELECT * FROM Technic;

SELECT * FROM Flooring;

SELECT * FROM Practicality;

SELECT * FROM Waterresistance;

SELECT * FROM Wearresistance;

SELECT * FROM Price;

SELECT * FROM Premises;

SELECT * FROM Hotels;

SELECT * FROM OptYesNo;

SELECT * FROM Login;

SELECT * FROM Mail;

SELECT * FROM Passwd;

SELECT * FROM Roly;

SELECT * FROM Сustomers;



SELECT name AS 'Наименование'

manuf.Manufacturer_name AS 'Производитель',

categ.Category_name AS 'Категория'

FROM Technic AS tech

INNER JOIN Manufacturer AS manuf ON

manuf.Manufacturer_id = tech.manufacturer_id

INNER JOIN Category AS categ ON

categ.Category_id = tech.category_id;



SELECT name AS 'Гостиницы',

decs.Opt_name AS 'Декор',

fd.Opt_name AS 'Еда',

sw.Opt_name AS 'Бассейн',

pt.Opt_name AS 'Животные'

FROM Hotels AS hots

INNER JOIN OptYesNo AS decs ON

decs.Opt_id = hots.Decor_id

INNER JOIN OptYesNo AS fd ON

fd.Opt_id = hots.Food_id

INNER JOIN OptYesNo AS sw ON

sw.Opt_id = hots.Swim_id

INNER JOIN OptYesNo AS pt ON

pt.Opt_id = hots.Pets_id;



SELECT name 'Пользовательские данные',

log.Login_name AS 'Логин',

ml.Mail_name AS 'Почта',

ps.Passwd_name AS 'Пароль',

rl.Roly_name AS 'Роли'

FROM Сustomers AS custm

INNER JOIN Login AS log ON

log.Login_id = custm.login_id

INNER JOIN Mail AS ml ON

ml.Mail_id = custm.mail_id

INNER JOIN Passwd AS ps ON

ps.Passwd_id = custm.passwd_id

INNER JOIN Roly AS rl ON

rl.Roly_id = custm.roly_id;
