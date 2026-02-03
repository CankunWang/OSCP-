# 目标已开启PDO，允许PHP请求database

	<?php try { 
			$conn = new PDO('mysql:host=db;dbname=web', 'robots', 'q4qCz10flKvKwK4S');
			$conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
			$result = $conn->query('SHOW TABLES'); 
			while ($row = $result->fetch(PDO::FETCH_NUM)) { 
			echo "- " . $row[0] . "\n"; } } 
			catch (PDOException $e) { 
			echo "Error: " . $e->getMessage(); 
			} ?>