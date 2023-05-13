# Discord Bot Template


## What is this?

Just my way to structure Discord Bot applications, making this document just to remember how to do it next time.
This is for Python only, as I haven't used other languages to build Discord Bots.

## Folder structure

```
Discord Bot/
|-- bot/
|   |-- __init__.py
|   |-- commands/
|   |   |-- __init__.py
|
|
|-- db/
|   |-- ddl/
|   |   |-- creates.sql
|   |   |-- drops.sql
|   |   
|   |-- dml/
|   |   |-- inserts.sql
|
|-- tests/
|   |-- __init__.py
|
|-- requirements.txt
|-- main.py
|-- README.md
|-- Dockerfile
|-- .env
|-- cacert.pem
|-- .gitattributes
|-- .gitignore
```

## Database
I use MySQL database to deploy them on Planetscale

## Installation
(WIP)

### Libraries
1. [Hikari](https://github.com/hikari-py/hikari)
2. [Lightbulb](https://github.com/tandemdude/hikari-lightbulb)
