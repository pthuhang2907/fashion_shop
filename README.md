# fashion_shop
demo
#code#
CREATE DATABASE Final_Prj_Gr6

USE Final_Prj_Gr6

CREATE TABLE MANUFACTURER (
    Manufacturer_Name VARCHAR(500) PRIMARY KEY,
    Manufacturer_Address VARCHAR(500)
);

CREATE TABLE SUPPLIERS (
    Supplier_Number INT PRIMARY KEY,
    Supplier_Phone_Number INT,
    Supplier_Name VARCHAR (500),
    Manufacturer_Name VARCHAR(500),
    FOREIGN KEY (Manufacturer_Name)
        REFERENCES MANUFACTURER (Manufacturer_Name)
);

CREATE TABLE ITEMS (
    Item_Code INT PRIMARY KEY,
    Item_Name VARCHAR (500),
    Origin VARCHAR(500)
);

CREATE TABLE SHOP (
    Shop_Name VARCHAR(500),
    Supplier_Number INT,
    FOREIGN KEY (Supplier_Number)
        REFERENCES SUPPLIERS (Supplier_Number),
    Item_Code INT,
    FOREIGN KEY (Item_Code)
        REFERENCES ITEMS (Item_Code)
);

CREATE TABLE SHIPPING_COMPANY (
    Shipping_Code INT PRIMARY KEY,
    Company_Name VARCHAR (500)
);

CREATE TABLE DELIVER (
    Date VARCHAR(500),
    Shipping_Code INT,
    FOREIGN KEY (Shipping_Code)
        REFERENCES SHIPPING_COMPANY (Shipping_Code),
     Item_Code INT,
    FOREIGN KEY (Item_Code)
        REFERENCES ITEMS (Item_Code)
);

CREATE TABLE CUSTOMER (
    Customer_Name VARCHAR(20) PRIMARY KEY,
    Customer_Address VARCHAR(500),
    Customer_Phone_Number INT
);

CREATE TABLE SHIPPER (
    Shipper_Code INT,
    Shipping_Code INT,
    Customer_Name VARCHAR(20) PRIMARY KEY,
);

CREATE TABLE SECOND_CUSTOMER (
    Second_Customer_Name VARCHAR(500) PRIMARY KEY,
    Second_Customer_Address VARCHAR(500),
    Second_Customer_Phone_Number VARCHAR(20)
);

CREATE TABLE TRADING (
    Price INT,
    Second_Customer_Name VARCHAR(500) PRIMARY KEY,
    Customer_Name VARCHAR(500),
); 

alter table SECOND_CUSTOMER add foreign key (Second_Customer_Name) references TRADING
alter table SHIPPER add foreign key (Shipping_Code) references SHIPPING_COMPANY
alter table SHIPPER add foreign key (Customer_Name) references CUSTOMER

INSERT INTO MANUFACTURER VALUES ('Nhà máy dệt Phương Đông','Số 21 Bùi Thị Xuân TP. Hồ Chí Minh');

INSERT INTO SUPPLIERS VALUES (01, 0123456789, 'Anh Tiến','Nhà máy dệt Phương Đông');
ERS VALUES (13, 0943216581, 'Em Lan','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (14, 0956562403, 'Em Luyến','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VINSERT INTO SUPPLIERS VALUES (02, 0798451358, 'Chị Giang','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (03, 0256648715, 'Anh Mạnh','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (04, 0325678954, 'Chú Hải','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (05, 0315884478, 'Bác Lành','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (06, 0215475145, 'Em Duyên','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (07, 0956231467, 'Em Hà', 'Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (08, 0956478125, 'Em Hải','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (09, 0956453288, 'Em Hằng','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (10, 0963256644, 'Em Huy','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (11, 0954486223, 'Em Hương','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (12, 0965583211, 'Em Linh','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIALUES (15, 0987874541, 'Em Đức','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (16, 0962457861, 'Em Đăng','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (17, 0979783678, 'Cô Nhài','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (18, 0937357950, 'Anh Mạng','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (19, 0975567117, 'Chị Thảo','Nhà máy dệt Phương Đông');
INSERT INTO SUPPLIERS VALUES (20, 0908874849, 'Anh Mạnh','Nhà máy dệt Phương Đông');

INSERT INTO ITEMS  VALUES (01, 'blue dress', 'China');
INSERT INTO ITEMS  VALUES (02, 'pink shirt', 'China');
INSERT INTO ITEMS  VALUES (03, 'mini skirt', 'China');
INSERT INTO ITEMS  VALUES (04, 'nice vest', 'China');
INSERT INTO ITEMS  VALUES (05, 'elegant pants', 'China');
INSERT INTO ITEMS  VALUES (06, 'a pair of glasses', 'China');
INSERT INTO ITEMS  VALUES (07, 'blue pink dress', 'China');
INSERT INTO ITEMS  VALUES (08, 'pink blue shirt', 'China');
INSERT INTO ITEMS  VALUES (09, 'mini short skirt', 'China');
INSERT INTO ITEMS  VALUES (10, 'blue vest', 'China');
INSERT INTO ITEMS  VALUES (11, 'elegant dark pants', 'China');
INSERT INTO ITEMS  VALUES (12, 'a pair of sunglasses','China');
INSERT INTO ITEMS  VALUES (13, 'blue red dress', 'China');
INSERT INTO ITEMS  VALUES (14, 'pink shirt', 'China');
INSERT INTO ITEMS  VALUES (15, 'dress shirt', 'China');
INSERT INTO ITEMS  VALUES (16, 'suitable vest', 'China');
INSERT INTO ITEMS  VALUES (17, 'elegant hat', 'China');
INSERT INTO ITEMS  VALUES (18, 'a pair of golden glasses','China');
INSERT INTO ITEMS  VALUES (19, 'high priestess dress', 'China');
INSERT INTO ITEMS  VALUES (20, 'pink blouse', 'China');
INSERT INTO ITEMS  VALUES (21, 'mini sweatpants', 'China');
INSERT INTO ITEMS  VALUES (22, 'good looking watch', 'China');
INSERT INTO ITEMS  VALUES (23, 'elegant boxer', 'China');
INSERT INTO ITEMS  VALUES (24, 'a pair of golden chopsticks','China');

INSERT INTO SHOP VALUES ('TruongHaFashion', 01 , 01); 
INSERT INTO SHOP VALUES ('TruongHaFashion', 02 , 02) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 03 , 03) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 04 , 04) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 05 , 05) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 06 , 06) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 01 , 07) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 02 , 08) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 03 , 09) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 04 , 10) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 05 , 11) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 06 , 12) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 01 , 13) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 02 , 14) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 03 , 15) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 01 , 16) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 02 , 17) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 03 , 18) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 04 , 19) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 05 , 20) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 06 , 21) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 01 , 22) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 02 , 23) ;
INSERT INTO SHOP VALUES ('TruongHaFashion', 03 , 24) ;

INSERT INTO SHIPPING_COMPANY VALUES (1, 'Extra Shipping');
INSERT INTO SHIPPING_COMPANY VALUES (2, 'Shopee Ship');
INSERT INTO SHIPPING_COMPANY VALUES (3, 'GHTK');
INSERT INTO SHIPPING_COMPANY VALUES (4, 'Be');
INSERT INTO SHIPPING_COMPANY VALUES (5, 'Grab');
INSERT INTO SHIPPING_COMPANY VALUES (6, 'Aha Ship');
INSERT INTO SHIPPING_COMPANY VALUES (7, 'Alo Ship');
INSERT INTO SHIPPING_COMPANY VALUES (8, 'Shipping');
INSERT INTO SHIPPING_COMPANY VALUES (9, 'Long Luong Ship');
INSERT INTO SHIPPING_COMPANY VALUES (10, 'SSS Ship');
INSERT INTO SHIPPING_COMPANY VALUES (11, 'Aladin Ship');
INSERT INTO SHIPPING_COMPANY VALUES (12, 'Express Ship');
INSERT INTO SHIPPING_COMPANY VALUES (13, 'ADC Ship');
INSERT INTO SHIPPING_COMPANY VALUES (14, 'CherryLove Ship');
INSERT INTO SHIPPING_COMPANY VALUES (15, 'GDC');
INSERT INTO SHIPPING_COMPANY VALUES (16, 'TombowArt');
INSERT INTO SHIPPING_COMPANY VALUES (17, 'FlowerKnows');
INSERT INTO SHIPPING_COMPANY VALUES (18, 'RtopR');
INSERT INTO SHIPPING_COMPANY VALUES (19, 'Marvy');
INSERT INTO SHIPPING_COMPANY VALUES (20, 'Holicshipping');

INSERT INTO DELIVER VALUES (26/10, 1, 20);
INSERT INTO DELIVER VALUES (26/10, 3, 20);
INSERT INTO DELIVER VALUES (26/10, 4, 24);
INSERT INTO DELIVER VALUES (27/10, 5, 16);
INSERT INTO DELIVER VALUES (27/10, 1, 06);
INSERT INTO DELIVER VALUES (28/10, 3, 03);
INSERT INTO DELIVER VALUES (29/10, 6, 15);
INSERT INTO DELIVER VALUES (30/10, 5, 09);
INSERT INTO DELIVER VALUES (31/10, 3, 13);
INSERT INTO DELIVER VALUES (1/11, 5, 22);
INSERT INTO DELIVER VALUES (2/11, 6, 22);
INSERT INTO DELIVER VALUES (2/11, 2, 19);
INSERT INTO DELIVER VALUES (2/11, 2, 21);
INSERT INTO DELIVER VALUES (2/10, 2, 18);
INSERT INTO DELIVER VALUES (2/11, 2, 04);
INSERT INTO DELIVER VALUES (2/11, 3, 09);
INSERT INTO DELIVER VALUES (2/11, 6, 18);
INSERT INTO DELIVER VALUES (3/11, 4, 05);
INSERT INTO DELIVER VALUES (3/11, 4, 17);
INSERT INTO DELIVER VALUES (3/11, 3, 14);
INSERT INTO DELIVER VALUES (3/11, 4, 02);
INSERT INTO DELIVER VALUES (4/11, 5, 01);
INSERT INTO DELIVER VALUES (5/11, 2, 01);
INSERT INTO DELIVER VALUES (6/11, 6, 04);
INSERT INTO DELIVER VALUES (7/11, 2, 09);
INSERT INTO DELIVER VALUES (8/11, 4, 12);

INSERT INTO CUSTOMER VALUES ('anh long', 'Sô 28 Hàng Bột',0959724288
);
INSERT INTO CUSTOMER VALUES ('anh hải', '65128 Thủy Tâm Garden',0324569872
);
INSERT INTO CUSTOMER VALUES ('anh thái', '4237 Nghi Minh Canyon',0956324872
);
INSERT INTO CUSTOMER VALUES ('anh hoàng', '8882 Trọng Tường Views',0973564208
);
INSERT INTO CUSTOMER VALUES ('anh hiếu', '95531 Khắc Công Track',093647258
);
INSERT INTO CUSTOMER VALUES ('anh đức', 'Bạc Liêu',0946321057
);
INSERT INTO CUSTOMER VALUES ('anh mạnh', 'Ninh Kiều',0982860341
);
INSERT INTO CUSTOMER VALUES ('anh lợi', '206 Thủy Quỳnh Hills',0972136528
);
INSERT INTO CUSTOMER VALUES ('anh cường', '67465 Bảo Thoa Pass',0962354101
);
INSERT INTO CUSTOMER VALUES ('chị hoa', '111 Hải Yến Crest',0958632482
);
INSERT INTO CUSTOMER VALUES ('chị hải', '7061 Thiên Ðức Fort',0963247852
);
INSERT INTO CUSTOMER VALUES ('chị hằng', '425 Tinh Tú Estates',0986523482
);
INSERT INTO CUSTOMER VALUES ('chị huyền', '88502 Thiên Duyên Corner',0965427362
);
INSERT INTO CUSTOMER VALUES ('chị hạnh', '0508 Cát Tường Village',09354716280
);
INSERT INTO CUSTOMER VALUES ('chị linh', '92486 Nguyệt Cát Isle',0936520820
);
INSERT INTO CUSTOMER VALUES ('chị lan', 'Tân Bình',0903846785
);
INSERT INTO CUSTOMER VALUES ('chị hiền', 'Bình Chánh',0919063460
);
INSERT INTO CUSTOMER VALUES ('chị lương', ' Hóc Môn',0913123993
);
INSERT INTO CUSTOMER VALUES ('chị liên', '121 Cô Giang',0903846785
);
INSERT INTO CUSTOMER VALUES ('chị nhàn', '529 Cộng Hòa', 0919063460
);

INSERT INTO SHIPPER VALUES (123569, 1, 'anh long');
INSERT INTO SHIPPER VALUES (125789, 2, 'anh hải');
INSERT INTO SHIPPER VALUES (125874, 4, 'anh thái');
INSERT INTO SHIPPER VALUES (154865, 6, 'anh hoàng');
INSERT INTO SHIPPER VALUES (120358, 2, 'anh hiếu');
INSERT INTO SHIPPER VALUES (120003, 3, 'anh đức');
INSERT INTO SHIPPER VALUES (125496, 4, 'anh mạnh');
INSERT INTO SHIPPER VALUES (120365, 4, 'anh lợi');
INSERT INTO SHIPPER VALUES (120035, 1, 'anh cường');
INSERT INTO SHIPPER VALUES (129855, 6, 'chị hoa');
INSERT INTO SHIPPER VALUES (123005, 2, 'chị hải');
INSERT INTO SHIPPER VALUES (124506, 3, 'chị hằng');
INSERT INTO SHIPPER VALUES (127895, 3, 'chị huyền');
INSERT INTO SHIPPER VALUES (126985, 3, 'chị hạnh');
INSERT INTO SHIPPER VALUES (124538, 5, 'chị linh');
INSERT INTO SHIPPER VALUES (120359, 5, 'chị lan');
INSERT INTO SHIPPER VALUES (120357, 6, 'chị hiền');
INSERT INTO SHIPPER VALUES (120365, 5, 'chị lương');
INSERT INTO SHIPPER VALUES (125869, 7, 'chị liên');
INSERT INTO SHIPPER VALUES (124475, 7, 'chị nhàn');

INSERT INTO TRADING VALUES (259876, 'Nguyễn Nguyên Hồng', 'anh long');
INSERT INTO TRADING VALUES (3248930, 'Tạ Ái Nhi', 'anh hải');
INSERT INTO TRADING VALUES (204893, 'Mạch Quế Linh', 'anh thái');
INSERT INTO TRADING VALUES (1567823, 'Trịnh Ðông Tuyền', 'anh hoàng');
INSERT INTO TRADING VALUES (122234, 'Nguyễn Ánh Lệ', 'anh hiếu');
INSERT INTO TRADING VALUES (235867, 'Trầm Thu Hường', 'anh đức');
INSERT INTO TRADING VALUES (587903, 'Phạm Xuân Lộc' , 'anh mạnh');
INSERT INTO TRADING VALUES (740000, 'Hồ Thế Vinh', 'anh lợi');
INSERT INTO TRADING VALUES (988000, 'Nguyễn Công Hoán', 'anh cường');
INSERT INTO TRADING VALUES (600000, 'Nguyễn Nhật Huy', 'chị hoa');
INSERT INTO TRADING VALUES (780000, 'Quang Ðức Khải', 'chị hải');
INSERT INTO TRADING VALUES (457712, 'Lục Xuân Bình', 'chị hằng');
INSERT INTO TRADING VALUES (655422, 'Văn Ngọc Khôi', 'chị huyền');
INSERT INTO TRADING VALUES (984453, 'Phạm Minh Khang', 'chị hạnh');
INSERT INTO TRADING VALUES (365824, 'Đinh Văn Hiển', 'chị linh');
INSERT INTO TRADING VALUES (3652887, 'Võ Thị Diễm My ', 'chị lan');
INSERT INTO TRADING VALUES (1236056, 'Lê Thị Miền ', 'chị hòa');
INSERT INTO TRADING VALUES (985314, 'Trương Bình Uyên Diễm ', 'chị lương');
INSERT INTO TRADING VALUES (628021, 'Bạch Thiện Hạnh', 'chị liên');
INSERT INTO TRADING VALUES (655154, 'Lê Ngọc Sơn ', 'chị nhàn');

INSERT INTO SECOND_CUSTOMER VALUES ('Nguyễn Nguyên Hồng', '123 Binh Thang village', 0923654728);
INSERT INTO SECOND_CUSTOMER VALUES ('Tạ Ái Nhi', '671 Pho Hoang Hoa Tham', 0437616458);
INSERT INTO SECOND_CUSTOMER VALUES ('Mạch Quế Linh', 'Thanh Ba Townlet', 0973885335);
INSERT INTO SECOND_CUSTOMER VALUES ('Trịnh Ðông Tuyền', '1 Nguyen Chi Thanh Street', 0932658741);
INSERT INTO SECOND_CUSTOMER VALUES ('Nguyễn Ánh Lệ', '182/2/6 Nguyen Huu Canh St', 0956478521);
INSERT INTO SECOND_CUSTOMER VALUES ('Trầm Thu Hường', '46 Bich Cau, Quoc Tu Giam Ward', 0956326581);
INSERT INTO SECOND_CUSTOMER VALUES ('Phạm Xuân Lộc', 'Quarter 4, Binh Hung Hoa Ward', 0962357841);
INSERT INTO SECOND_CUSTOMER VALUES ('Hồ Thế Vinh', ' Be Van Đan Street', 0956215877);
INSERT INTO SECOND_CUSTOMER VALUES ('Nguyễn Công Hoán', '123 Hoang Van Thu Street', 0932664588);
INSERT INTO SECOND_CUSTOMER VALUES ('Nguyễn Nhật Huy', 'Binh Thanh Dist, Ho Chi Minh', 0326547892);
INSERT INTO SECOND_CUSTOMER VALUES ('Quang Ðức Khải', '51B Tran Hung Dao Street', 0932587413);
INSERT INTO SECOND_CUSTOMER VALUES ('Lục Xuân Bình', '58 Nguyen Tri Phuong St', 0955662378);
INSERT INTO SECOND_CUSTOMER VALUES ('Văn Ngọc Khôi', '34 Ut Tich StreetWard 4', 0963652678);
INSERT INTO SECOND_CUSTOMER VALUES ('Phạm Minh Khang', '16 Ho Ba Kien street', 0965632584);
INSERT INTO SECOND_CUSTOMER VALUES ('Đinh Văn Hiển', 'Thi Xa Ha Tien,Tinh Kien Giang', 0903720805);
INSERT INTO SECOND_CUSTOMER VALUES ('Võ Thị Diễm My ', 'Xa Thong Nhat, Huyen Krongbuk, Đac Lac', 0913748604);
INSERT INTO SECOND_CUSTOMER VALUES ('Lê Thị Miền ', 'D1/2 Lac Long Quan, P.10, Q.TB', 0912243263);
INSERT INTO SECOND_CUSTOMER VALUES ('Trương Bình Uyên Diễm ', '186 Phan Rang, Ninh Thuan', 01688887788);
INSERT INTO SECOND_CUSTOMER VALUES ('Bạch Thiện Hạnh', '203 Khu I, Binh Đinh, Xuân Đinh, Xuan Loc, Đong Nai', 0909274392);
INSERT INTO SECOND_CUSTOMER VALUES ('Lê Ngọc Sơn ', '74 Nguyen Hue, Thanh pho Quy Nhon, Tinh Binh Đinh ', 0988972097); 


--1/Show item list and quantity of each item.
SELECT Item_Name, COUNT(Item_Name) AS "So luong"
FROM ITEMS
GROUP BY Item_Name;

--2/Find out the authenticity code and origin of time.
select Item_Code, Origin from items;



--3/Sort out the items by alphabet.
select * from items order by item_name;

--4/Show information of customers.
select customer_name, customer_phone_number from customer;

--5/Delete some shipper information
delete from dbo.SHIPPER where Shipper_Code = 123569

--6/Update the name of SHIPPING_COMPANY and commit to the database.
begin tran
UPDATE SHIPPING_COMPANY
SET Shipping_Code = 1, Company_Name= 'Extra Shipping'
WHERE  Shipping_Code= 1;


--7/find out which supplier provided what item
select s.shipper_code, d.item_code from shipper s inner join deliver d

on s.shipping_code = d.shipping_code;


--8/Find out which supplier provided what item
select s.supplier_name, i.item_name from suppliers s
inner join shop s1
on s.supplier_number = s1.supplier_number
inner join items i
on s1.item_code = i.item_code;


--9/Count the number of shippers of each company
select s.shipping_code, count(*) from shipper s inner join
shipping_company c
on s.shipping_code = c.shipping_code
group by s.shipping_code;
--10/Show information of 2nd customer
select Second_Customer_Name, Second_Customer_Address,
Second_Customer_Phone_Number from SECOND_CUSTOMER

