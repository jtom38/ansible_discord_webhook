# discord_webhook

## About

This is a ansible role that lets you send messages to Discord Webhooks easily.  I made this for quick reuse so I can monitor when I have ansible jobs running.  
  
Currently, this will only send out basic messages.  Plans are to add embed message support to this role but not at this time.

## Variables

``` yaml

# Use a valted uri to keep your webhook secret.
discord_webhook: string

#Note: Use " if you want multi line support"
discord_message: string

# You can change the name with this flag
discord_name: string

# This defaults to the ansible logo found [here](https://github.com/luther38/ansible_discord_webhook/blob/master/files/ansible_logo.png)
discord_avatar: string

```

## Example Playbook

``` yaml
- include_role:
    name: luther38.discord_webhook
  vars:
    discord_webhook: ''
    discord_name: 'Ansible Monitor'
    discord_message: "This sends basic messages over to discord.  You can have multiple lines by using \n see?"
```

## Requirements.yml

This repo is not published in galaxy and might never be.  To use this role you will need to either clone or add these lines to your requirements.yml file.

``` yaml
roles:
  - src: https://github.com/luther38/ansible_discord_webhook
    name: luther38.discord_webhook
```
