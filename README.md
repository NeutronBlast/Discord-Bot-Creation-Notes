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
|   |   |-- help/
|   |   |   |-- __init__.py
|   |   |   |-- help.py
|   
|   
|   |-- embeds/
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

## IDEs
I use Pycharm to develop in Python so all the instructions will be based on Pycharm

## Installation
1. Press Ctrl+Shift+S and select `Project -> Python Interpreter`, then press the `+` icon and install the libraries in the list that will be specified after
2. In `main.py` copy the following code
```
import os

import hikari
import lightbulb
from dotenv import load_dotenv

# Load environment file
load_dotenv()

bot = lightbulb.BotApp(
    token=os.getenv('BOT_TOKEN'),
    default_enabled_guilds=[]
)

# Add commands
bot.load_extensions_from('./bot/commands/help')
bot.run(status=hikari.Status.DO_NOT_DISTURB, activity=hikari.Activity(name=""))
```
3. In `help.py` copy the following code
```
import lightbulb

plugin = lightbulb.Plugin('help')


def load(bot):
    bot.add_plugin(plugin)


@plugin.command
@lightbulb.option('command', 'The command you want info from', required=False, choices=[])
@lightbulb.command('help', 'Shows information about all commands or about a specific group of commands')
@lightbulb.implements(lightbulb.SlashCommand)
async def help_command(ctx):
    """
    Shows a guide of syntax and usage from each command

    :param ctx:
    :return: None
    """
    if ctx.options.command is None:
        await ctx.respond("")
```

We can import embeds or other stuff later.


## Libraries
1. [Hikari](https://github.com/hikari-py/hikari)
2. [Lightbulb](https://github.com/tandemdude/hikari-lightbulb)
3. [Pipreqs](https://pypi.org/project/pipreqs/)
4. [SQLalchemy](https://pypi.org/project/SQLAlchemy/)
5. [Python Dotenv](https://github.com/theskumar/python-dotenv)
