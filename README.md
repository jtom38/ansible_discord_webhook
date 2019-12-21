# discord_webhook

## About

This is a ansible role that lets you send messages to Discord Webhooks easly.  I made this for quick reuse so I can monitor when I have ansible jobs running.

## Variables

## Example Playbook

``` yaml
- include_role:
    name: luther38.discord_webhook
  vars:
    discord_webhook: ''
    discord_username: 'Ansible Monitor'
    discord_message: "This sends basic messages over to discord.  You can have multiple lines by using \n see?"
```

## Requirements.yml

``` yaml
roles:
  - src: https://github.com/luther38/ansible_discord_webhook
    name: luther38.discord_webhook
```
