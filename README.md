# Sailfish Developer Guide

## Contacts

### Read SQLite database

`/home/nemo/.local/share/system/Contacts/qtcontacts-sqlite/contacts.db`

Example: https://github.com/aebruno/whisperfish/blob/c205dacde23ed2e616082141b269e89d4ee74faa/store/contact.go

### contacts-tool

`contacts-tool` is a CLI tool to do some basic tasks:

    Usage: contacts-tool [OPTIONS] COMMAND

    where COMMAND is one of:
    list [sync-target]   - lists all contacts, optionally specified by sync-target type
    search <search-text> - searches for contacts with details containing search-text
    details <ID...>      - lists details for contacts matching the supplied ID list
    links <ID...>        - lists links for contacts matching the supplied ID list
    delete <ID...>       - removes contacts matching the supplied ID list
    dump [ID...]         - displays contact details in debug format
    help                 - show this command summary
    version              - show the application version

    OPTIONS:
    -t                   - use TAB delimiters

    Output is written to stdout.

### com.jolla.contacts.ui DBus service

Import Contacts: https://github.com/blacksailer/depecher/blob/60eea270a8bca641362232a0f3fb7c8a1218bc35/depecher/qml/pages/items/delegates/ContactDelegate.qml

## Communication History

### Read SQLite database

`/home/nemo/.local/share/commhistory/commhistory.db`

## Settings

https://github.com/blacksailer/depecher/tree/cd1ccedc44504a5251be16c86d05f9d4eb52e5b3/depecher/settings


## Notifications

### Quick notifications

Only set the preview body (no preview summary or normal body/summary) and the notification will be a small bar at the top of the screen (like when battery is low). The preview body will be shown and a icon is possible:

    Notification* notification = new Notification(this);
    notification->setIcon("image://theme/icon-lock-warning"); // optional 
    notification->setPreviewBody("this is a warning");
    notification->publish();

### Categories

https://github.com/blacksailer/depecher/tree/cd1ccedc44504a5251be16c86d05f9d4eb52e5b3/depecher/notificationcategories