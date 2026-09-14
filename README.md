# Advanced Databases lab environment

You run MySQL 8.4 and phpMyAdmin in Docker for all of the labs in this module. You have full `root` access and you can create as many databases as you like.

## Start the database

Install [Docker Desktop](https://www.docker.com/products/docker-desktop/) and start it. Then run:

```
docker compose up -d
```

Open <http://localhost:8080>. There is no login page, because phpMyAdmin logs you in as `root` automatically.

Stop the database with `docker compose down`. Your databases are kept when you do, and they survive a reboot. Only `docker compose down -v` deletes them.

## Use the MySQL command line client

```
docker compose exec db mysql -uroot -proot mydatabase
```

Type `exit` to leave.

## Use VS Code

Open the folder in VS Code and accept the prompt to install [DBCode](https://marketplace.visualstudio.com/items?itemName=dbcode.dbcode). The connection is already set up, so click the DBCode icon in the sidebar and connect.

You can then run statements from any `.sql` file, browse your tables, and export results to Markdown or CSV.

## Use DataGrip

[DataGrip](https://www.jetbrains.com/datagrip/) is free for students through the [JetBrains student pack](https://www.jetbrains.com/academy/student-pack/). Choose **New Data Source, MySQL** and enter:

| Setting  | Value       |
| -------- | ----------- |
| Host     | `127.0.0.1` |
| Port     | `3306`      |
| User     | `root`      |
| Password | `root`      |

## Keep your queries in files

You can write each lab's queries in a `.sql` file here, for example `lab-02.sql`, and commit them as you work. The phpMyAdmin query box is easy to lose work in, and a file you have pushed is backed up. You can also re-run a whole lab against a fresh database in one command.
