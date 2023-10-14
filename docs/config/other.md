---
# This is the icon of the page
icon: iconfont icon-snow
# This control sidebar order
order: 9
# A page can have multiple categories
category:
  - Config
# A page can have multiple tags
tag:
  - Config
  - Settings
# this page is sticky in article list
sticky: true
# this page will appear in starred articles
star: true
---

# Other settings

### **Aria2**

Aria2 URI for offline downloading. Aria2 needs to be installed on the same server (same container if use Docker) as AList.



## **Qbittorrent url**

Webpage used to configure **Qbittorrent** parameters for the client to use.

Defaults to `http://admin:adminadmin@localhost:8080/`; modify by referring to [specific instructions](../guide/advanced/offline-download.md#_2-qbittorrent).



### **Token**

Token that can access all APIs.



### **other**

1. [**Differences between 2 Aria2.**](../faq/why.md#what-is-the-difference-between-the-two-aria2)
2. Support using Aria2 to download folders at the same time and save the folder directory structure style

   - Opening method, `Toggle Checkbox` in the lower right corner--> select list file/folder--> `Download` at the bottom--> `send to Aria2`

   - But it is recommended not to download too much at one time. For example, downloading thousands of folders and tens of thousands of files at one time may cause AList to crash