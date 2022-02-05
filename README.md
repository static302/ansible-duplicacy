# Ansible duplicacy role
Ansible role to install and configure [Duplicacy](https://github.com/gilbertchen/duplicacy).

## Requirements

Works on Linux, other platforms are easy to add if needed.<br>
Ansible target hosts require python, POSIX-compatible shell. <br>
For monitoring and notification needs [healthchecks.io](https://healthchecks.io/) is used, you can use either cloud or standalone version or remove it from role\script or replace with your own recipe. <br>
[curl](https://curl.se/) and [jq](https://stedolan.github.io/jq/) are requiered for default healthcheck implementation, you can use other methods within script if you want to.

## Role itself

This role can be separated into 2 roles (install and configure), but in my understanding it's better to run alltogether to ensure you are using up to date version of duplicacy.

## Role Common Variables
`use_duplicacy` - Used to mark host\group as an subject to duplicacy role. Put it in you inventory host\group files.<br>
`application` - Application running on target host to point specific pre|post tasks or filters. Should be placed in you inventory host\group files.<br>
`use_duplicacy_posttasks`/`use_duplicacy_pretasks` - Should role generate pre|post-backup duplicacy scripts or not. Templates for these scripts should exist.<br>
`duplicacy_storage_backend` - Define backend where duplicacy store data, onedrive and s3 available to use in the role atm.<br>
`hc_API_key` - Your healthchecks.io API key goes here.<br>
`duplicacy_storage_name`/`duplicacy_storage_url`/`duplicacy_storage_password` - Selfexplanatory.<br>
`duplicacy_s3_id`/`duplicacy_s3_secret` - s3 backend specific variables.<br>
`duplicacy_filters` - Your set of directories to backup, in addition to /etc, which is default.
