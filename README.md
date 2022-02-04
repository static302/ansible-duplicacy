# Ansible duplicacy role
Ansible role to install and configure [Duplicacy](https://github.com/gilbertchen/duplicacy).

## Requirements

Works on Linux, other platforms are easy to add if needed.<br>
Ansible target hosts require python and POSIX-compatible shell.<br>
[jq](https://stedolan.github.io/jq/) is requiered to parse JSON but you can use sed for this, it's just a handy tool to have.<br>
For monitoring and notification needs [healthchecks.io](https://healthchecks.io/) is used, you can use either cloud or standalone version or remove it from role\script or replace with your own recipe.

## Role itself

This role can be separated into 2 roles (install and configure), but in my understanding it's better to run alltogether to ensure you are using up to date version of duplicacy.

## Role Common Variables
`use_duplicacy` - Used to mark host\group as an subject to duplicacy role. Put it in you inventory host\group files.<br>
`duplicacy_storage_backend` - Define backend where duplicacy store data.<br>
`hc_API_key` - Your healthchecks.io API key goes here.<br>
`duplicacy_storage_name`/`duplicacy_storage_url`/`duplicacy_storage_password` - Selfexplanatory.<br>
`duplicacy_pretasks`/`duplicacy_posttasks` - Tasks you have to run before and\or after duplicacy jobs, depends on data you're securing.<br>
`application` - To use as a separator between applications running on target hosts to point specific pre|post tasks or filters. Also should be placed in you inventory host\group files.<br>
`duplicacy_filters` - Your set of directories to backup, in addition to /etc, which is default.
