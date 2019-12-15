# bamazon
github wont let me push my js files for some reason.

here is the mysql code:
DROP DATABASE IF EXISTS bamazonDB;

CREATE DATABASE bamazonDB;

USE bamazonDB;

CREATE TABLE inventory (
	item_id INT not null,
    product_name VARCHAR(100) not null,
    department_name VARCHAR(100) not null,
    price VARCHAR(100) not null,
    stock_quantity INT not null,
    PRIMARY KEY (item_id)
);

SELECT * FROM inventory;

INSERT INTO inventory (item_id, product_name, department_name, price, stock_quantity)
VALUES (10, "skis", "winter sports", 500, 15),
	(11, "ski boots", "winter sports", 300, 20),
    (12, "basketball", "sports", 50, 20),
    (13, "basketball hoop", "sports", 250, 15),
    (14, "snowboard", "winter sports", 300, 10),
    (15, "snowboard boots", "winter sports", 300, 10),
    (16, "macbook pro", "electronics", 1200, 8),
    (17, "gopro", "electronics", 350, 12),
    (18, "iphone", "electronics", 1000, 5),
    (19, "water bottle", "health", 30, 8)
    
    Here is the JS that I got working:
    
const mysql = require("mysql");
const inquirer = require("inquirer");

const connection = mysql.createConnection({
    host: "localhost",
    port: "3306",
    user: "root",
    password: "password",
    database: "bamazonDB"
});

connection.connect(function(err) {
    connection.query("Select * From Products ", function(err,res){
        if (err) throw (err);
    });
});
