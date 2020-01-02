# discord_webhook

## About

This is a ansible role that lets you send messages to Discord Webhooks easily.  I made this for quick reuse so I can monitor when I have ansible jobs running.  

## Variables

``` yaml

# Use a valted uri to keep your webhook secret.
# Required
discord_webhook: string

#Note: Use " if you want multi line support"
# Works with: basic and fancy
discord_message: string

# You can change the name with this flag
# Works with: basic and fancy
discord_name: string

# This defaults to the ansible logo found [here](https://github.com/luther38/ansible_discord_webhook/blob/master/files/ansible_logo.png)
discord_avatar: string

# This lets you flip between sending a basic or fancy message.
# Default: 'basic'
# Takes: 'basic' or 'fancy'
discord_type: string

# Defines the title card of a fancy message.  This is a good spot to write the Ansible task that is running.
# Default: null
discord_title: string

# Defines the color of a fancy message.  You can use custom colors with this but you need to get the decimal value rather then hex value. Go to https://www.spycolor.com to find your color and the decimal value.
# Red:        "16711680"
# Green:      "65314"
# Purple:     "12255487"
# Dark Blue:  "4607"
discord_color: string

```

## Example Playbook

``` yaml
- name: Send Basic Discord Message
  hosts: localhost
  vars:
    discord_webhook: "{{ discord_webhook_url_from_inventory }}"
    discord_name: 'Ansible Monitor'

  tasks:
    - include_role:
        name: luther38.discord_webhook
      vars:
        discord_message: "This sends basic messages over to discord.  You can have multiple lines by using \n see?"
```

``` yaml
- name: Send Fancy Discord Message:
  hosts: localhost
  vars:
    discord_webhook:  "{{ discord_webhook_url_from_inventory }}"
    discord_name:     'Ansible Monitor'
    discord_title:    "Cron - Service Check"
    discord_type:     "fancy"
    discord_color:    "16711680"

  tasks:
    - include_role:
        name: luther38.discord_webhook
      vars:
        discord_message: "
          This is the first line.\n
          Who wants to go hunt some monsters?
        "
```

## Requirements.yml

This repo is not published in galaxy and might never be.  To use this role you will need to either clone or add these lines to your requirements.yml file.

``` yaml
roles:
  - src: https://github.com/luther38/ansible_discord_webhook
    name: luther38.discord_webhook
```
