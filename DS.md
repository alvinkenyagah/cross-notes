## DSEA 

- [x]  python3
- [x]  (To install dbt) `pip install dbt-core` if you get path warning `export PATH="$PATH:/home/<username>/.local/bin"`
- [x]   (To install airflow)  `pip install "apache-airflow[celery]==2.7.1" --constraint`
- [x]    (To install pyspark) `pip install pyspark`
- [x]    (To install snowflake) `pip install snowflake-connector-python`
- [x]     To install MySQL https://kontext.tech/article/615/install-mysql-on-wsl




## MYSQL WSL INSTALLATION
-------------------------------
- `sudo apt update`
- `sudo apt install mysql-server`
- `mysql --version` ====> Confirm mysql installation
- `sudo service mysql start` =====> Start mysql service 
- `sudo service mysql status` ====> Check the status of the service
- `sudo mysql_secure_installation` =====> Start security script prompts
- `sudo mysql` ======>Try MySQL prompt using the following command
                                     `show databases;`     => Show existing databases

  ## MYSQL BASICS ON lINUX
- `sudo service mysql start` After booting up you would like to stat mysql service 
- client by running `mysql -u username -p`, where username is your MySQL username.You'll be prompted to enter your MySQL password. 
- `CREATE DATABASE mydatabase;` replace `mydatabase` with the name you want for your database.
- `SHOW DATABASES;` This list all the available databases.
- `USE mydatabase;` If you want to work with the newly created database, you can use the USE statement.
  
