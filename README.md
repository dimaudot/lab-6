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


