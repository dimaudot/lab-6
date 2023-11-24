# lab-6  
![msedge_AOOcuENVef](https://github.com/dimaudot/lab-6/assets/150914730/890363b5-caa8-4994-ab25-6c03050ce0b7)
1<?php
2$host = 'localhost';
3$dbname = 'mults';
4$username = 'root';
5$password = ''


1<?php
2
3include 'config.php';
4
5try {
6 $pdo = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
7 $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
8 } catch (PDOException $e) {
9 die("Помилка підключення до бази даних: " . $e->getMessage());
10 }
11
12?>





1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22<!DOCTYPE html>
    
     
     1<html lang="en">
2<head>
3 <meta charset="UTF-8">
    4 <meta name="viewport" content="width=device-width, initial-scale=1.0">
    5 <title>Лабораторна робота №6</title>
    6 <link rel="stylesheet" href="style.css">
 7 </head>
8 <body>
   9  <h1>База даних "mutls"</h1>
    <img src="photos/msedge_AOOcuENVef.png" alt="">

    <ul>
        <li><a href="showMults.php">Таблиця Mutls</a></li>
        <li><a href="showCountry.php">Таблиця Country</a></li>
        <li><a href="showName.php">Таблиця Name</a></li>
    </ul>

    <h2>Лабораторна зроблена на швидку руку</h2>
</body>
</html>
 2
 3
 4
 5
 6
 7
 8
 9
 10
 11
 12
 13
 14
 15
 16
 17
 18
 19
 20
 <html>
<head>
    <meta charset="utf-8">
    <meta name="keywords" content="Лабораторна робота, MySQL, робота з базою даних">
    <meta name="description" content="Лабораторна робота. Робота з базою даних">
    <title>Таблиця Country</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Таблиця Country</h1>


    <?php

    include "databaseConnect.php";

    try {
        $stmt = $pdo->query("SELECT * FROM mults");
        // Виконання запиту і отримання результатів
        printf("<h3>Список мультів:</h3>");
        printf("<table><tr><th>ID</th><th>Назва мультиків</th></tr>");
        while ($row = $stmt->fetch(PDO::FETCH_ASSOC)) {
            printf("<tr><td>%s</td><td>%s</td></tr>", $row['id'], $row['name']);
        };
        printf("</table>");
    } catch (PDOException $e) {
        die("Помилка запиту: " . $e->getMessage());
    }

    ?>

    <br><br><br>

    <ul>
        <li><a href="#">Звіт Кількість мультиків</a><br></li>
        <li><a href="index.html">На головну</a><br></li>
    </ul>
    
</body>
</html>
