# Tinyr - URL Shortener

Tinyr is a simple and efficient URL shortener that allows users to convert long URLs into shorter, more manageable links. It provides a user-friendly web interface for URL input, validation, shortening, and tracking.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

## Features

- Shortens long URLs to concise and memorable links.
- Validates entered URLs to ensure their correctness.
- Stores both the original long URLs and their shortened versions in a MySQL database.
- Displays a table showing the long URL, corresponding short URL, and the click count.
- Tracks the number of times each shortened link is accessed, providing valuable engagement metrics.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/amaan14999/tinyr.git
```

2. Install the dependencies:

```bash
npm install
```

3. Set up the MySQL database:

- Login to MySQL as root:

```bash
mysql -u root -p
Enter password: <your_password>
```

- Create the database and table:

```sql
CREATE DATABASE shorturls;

USE shorturls;

CREATE TABLE links (
    id INT(11) AUTO_INCREMENT PRIMARY KEY,
    longurl VARCHAR(255),
    shorturlid VARCHAR(255),
    count INT(11) DEFAULT 0
);
```

- It should output something like this:

```bash
+------------+--------------+------+-----+---------+----------------+
| Field      | Type         | Null | Key | Default | Extra          |
+------------+--------------+------+-----+---------+----------------+
| longurl    | varchar(255) | YES  |     | NULL    |                |
| shorturlid | varchar(255) | YES  |     | NULL    |                |
| count      | int          | YES  |     | 0       |                |
| id         | int          | NO   | PRI | NULL    | auto_increment |
+------------+--------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)
```

- Grant privileges to the root user:

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_new_password';

FLUSH PRIVILEGES;
```

4. Start the application:

```bash
node code.js
```

5. Open the application in your browser:

```bash
http://localhost:5000
```

6. Enjoy!

## Technologies Used

- Node.js
- Express.js
- MySQL
- HTML
- CSS
- JavaScript

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the [MIT](https://github.com/amaan14999/tinyr/blob/main/LICENSE) License.
