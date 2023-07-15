# Splunk-org-chart
Build uplinks and downlinks from LDAP-like data in the form of a Dashboard
Stuidio dashboard

This is a demo of techniques to build tree-like structures from a linked list.

## The problem
Two most common questions asked about org chart are:
1. What is your report chain up to the top?
2. What are your direct reports?

A directory is a linked list.  Using associative array, or hash lookup, it is
not too difficult to translate directory data (downlinks) into uplinks and
direct report lists.  But SPL does not have functions/commands that operate on
hash.[1]

Linked list is also used to represent directory structures other than org
charts.  The ideas presented here can also apply to similar use cases.

## Install
Create a Dashboard Studio dashboard.  Then copy the content of [org-chart.json] into source.

## Use
The dashboard has three panels.  The bottom panel presents "raw" data.
Although the emulation has five fields, this demo only uses cn, displayName,
and manager.

The two drop-down input tokens`manager_tok` aka "Manager" and `displayName_tok`
aka "Employee" affect both other two panels.  Of all personnel, Bill Clinton and Tylor Swift are excluded from "Manager" selector, and Dean Martin is excluded from Employee selector.

## Search
To examine the search used to get result, first select the inputs you want.
(Default is Manager "All" and Employee "All".)  Then, use the magnifying glass
icon ("Open in search") to examine the search behind.

## References
[1] [Help needed with foreach query for LDAP user information][https://community.splunk.com/t5/Splunk-Search/Help-needed-with-foreach-query-for-LDAP-user-information/m-p/636254]
