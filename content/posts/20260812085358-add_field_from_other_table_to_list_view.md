+++
title = "Add Field From other table to list"
lastmod = 2026-08-12T15:29:31+02:00
draft = false
+++

## Add Field from other table to list view {#add-field-from-other-table-to-list-view}

The other day, I was creating a module under an application menu in ServiceNow that looks at the sc_task table with a filter for specific catalog items (cat_item).
The client wanted the list to display the Requested For field (requested_item.requested_for).
However, because that field isn't directly on the sc_task table, I ran into a problem: I couldn't find it using the normal Personalize List option.

So, I did what any sane person would do and asked my best friend, Google. That didn't seem to get me very far at first—until I stumbled upon a ServiceNow Community post.

It turns out ServiceNow has another way to customize the list layout:

-   Click the three dots (column menu) on any field header in the list.

-   Select Configure &gt; List Layout.

This opens a completely different menu with a lot more fields to choose from, including dot-walked fields from related tables.


### The One Caveat {#the-one-caveat}

You need to enable a specific UI property to see fields from other tables in this menu.
You can do this in one of two ways:

-   Via System Properties UI: Search for UI Properties in the Application Navigator and look for the setting titled:

> "Allow base table list (task, cmdb_ci, etc) to include extended table fields (incident_state, os_version, etc), and allow filtering on extended table fields."

-   Set this to Yes by checking the box.

Via System Properties Table (sys_properties): Navigate to sys_properties.list, locate the property named glide.ui.list.allow_extended_fields, and set its value to true.
