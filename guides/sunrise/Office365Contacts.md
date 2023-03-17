---
layout: page
menubar: guides_menu
title: Office365 Contacts
subtitle: Connects Central to Office365
show_sidebar: false
toc: true
---

## Office365 Contacts ##

The homepage provides functionality to synchronise Central's contacts to Office365. The homepage will either create contacts in specific Office365 contacts folder or update existing contacts in that same folder.

### Filtering ###

Only active Central contacts are processed. Any other records are excluded.

## Matching Contacts Between Central and Office365 ##

The match is done on email address. For example, if John Smith in Central has an email address of "john@outlook.com" and Patrick Parker in Office365 also uses "john@outlook.com", they will both 
be considered as a single entity and name Patrick Parker will be overriden with John Smith from Central.

### Validation ###

1. If contact has "deceased" in either first or last names, even though the record is still marked as active, the homepage will consider that record as non-actionable.
1. Any malformed email address would be considered as non-actionable record. 
1. Any records without first and last names would be non-actionable.

## Synchronisation ##

The homepage will locate all contacts in Office365 under specified contact folder (set in Settings) together with all active contacts in Central. Once matching is done and the state is determined (requires update, no updates to synchronise or contact new to Office365), the user will be able to select records to synchronise to commence the process.

### Synchronised Fields ###

1. Title.
1. First name or given name.
1. Last name or surname.
1. Mobile.
1. Email (primary email only).
1. Business telephone or telephone.
1. Website or company web page.

Home Address

1. Street (including line one, two and three of an address).
1. Town or city.
1. County or state.
1. Country or region.
1. Postal code.

Business Address
1. Street (including line one, two and three of an address).
1. Town or city.
1. County or state.
1. Country or region.
1. Postal code.

### Scopes ###

Office365 uses scopes to grant permissions to integration software. They are similar to permissions mobile apps request during installation.

We recommend approving following scopes for Office365 Contacts homepage:

```
Directory.Read.All
Directory.ReadWrite.All
Directory.AccessAsUser.All
Calendars.ReadWrite.Shared
Contacts.Read
Mail.ReadWrite
MailboxSettings.Read
MailboxSettings.ReadWrite
User.Read
User.Read.All
User.ReadBasic.All
User.ReadWrite
User.ReadWrite.All
profile
openid
email
```

### Address Street Mapping ###

Central uses address line one, two and three for street address. Office365 has a single field called "Street Address". When synchronising between systems, Central's lines of address are joined by commas.

For example, given following address in Central:
```
Line One: Flat 1
Line Two: King's Court
Line Three: 10 Long Street
```

Street in Office365 would be:
```
Flat 1, King's Court, 10 Long Street
```

### Limitations ###

* Matching can only be done on one unique email address. The same email address against several records isn't supported.
* Non email address matching isn't supported.