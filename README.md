# Rebuild Everything from Scratch

  

## Copycats should Give a Credit
 Try mentioning me in your Modules 😋
### Test me on telegram (all client)

[Telegram](https://t.me/filteradderbot)

# tgbot
A modular telegram Python bot running on python3 with an sqlalchemy database.
(ഒരു മോഡുലാർ ടെലിഗ്രാം പൈത്തൺ ബോട്ട് പൈത്തൺ 3-ൽ ഒരു സ്ക്ലാൽ‌ചെമി ഡാറ്റാബേസ് ഉപയോഗിച്ച് പ്രവർത്തിക്കുന്നു.)


എന്റെ ന്യൂ ഫീച്ചേർസ് [ചാനലിൽ](https://t.me/bughunterbots) ഇടുന്നതായിരിക്കും. സംശയങ്ങൾക്ക് @bughunterbots എന്ന ഗ്രൂപ്പിൽ വരാവുന്നതാണ്.....



## You can also tap the Deploy To Heroku button below to deploy straight to Heroku!

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/nuhmanpk7/Filter-Adder)

## Starting the bot.

Once you've setup your database and your configuration (see below) is complete, simply run:

`python3 -m tg_bot`


## Setting up the bot (Read this before trying to use!):
Please make sure to use python3.6, as I cannot guarantee everything will work as expected on older python versions!
This is because markdown parsing is done by iterating through a dict, which are ordered by default in 3.6.

### Configuration

There are two possible ways of configuring your bot: a config.py file, or ENV variables.

The prefered version is to use a `config.py` file, as it makes it easier to see all your settings grouped together.
This file should be placed in your `tg_bot` folder, alongside the `__main__.py` file . 
This is where your bot token will be loaded from, as well as your database URI (if you're using a database), and most of 
your other settings.

It is recommended to import sample_config and extend the Config class, as this will ensure your config contains all 
defaults set in the sample_config, hence making it easier to upgrade.


### Creating your own modules.

Creating a module has been simplified as much as possible - but do not hesitate to suggest further simplification.

All that is needed is that your .py file be in the modules folder.

To add commands, make sure to import the dispatcher via

`from tg_bot import dispatcher`.

You can then add commands using the usual

`dispatcher.add_handler()`.

Assigning the `__help__` variable to a string describing this modules' available
commands will allow the bot to load it and add the documentation for
your module to the `/help` command. Setting the `__mod_name__` variable will also allow you to use a nicer, user
friendly name for a module.

The `__migrate__()` function is used for migrating chats - when a chat is upgraded to a supergroup, the ID changes, so 
it is necessary to migrate it in the db.

The `__stats__()` function is for retrieving module statistics, eg number of users, number of chats. This is accessed 
through the `/stats` command, which is only available to the bot owner.
