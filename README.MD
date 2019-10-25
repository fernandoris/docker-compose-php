# DOCKER-COMPOSE-PHP

docker-compose-php Is a docker configuration that automatically configures an environment to start developing in PHP.

It starts the following containers:

- php 7.2
- nginx 1.13
- mysql 8.0.18
- redispatch 4.0.8

## Installation

Clone the repository

```git
git clone https://github.com/fernandoris/docker-compose-php.git
```
Accessing the repository folder
```bash
cd docker-compose-php
```
Runs
```bash
docker-compose up -d
```

## Usage

You will be able to access nginx in the url:
```
http://localhost:9000
```
And you'll be able to access PhpMyAdmin in the url:
```
http://localhost:8080
SERVER : [YOUR_PROJECT_FOLDER]_mysql_1
USER : root
PASSWORD : root
```
You can change the mysql configuration in the file:
```
mysql.env
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)