---
# This is the icon of the page
icon: iconfont icon-chrome
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

# Global settings

### **Hide files**

Files to hide by matching regular expressions (with c`javascript`). Do not edit this field if you do not understand. Invalid/Incorrect regular expressions will cause the front-end to crash. One regex per line. There is an example expression that hides `README.md` from all directories.

Note that hidden files still exists in the list returned by the API, they only does not show up in the front-end. To completely hide files, use [meta](../guide/advanced/meta.md) records instead.

### **Package download**

Whether to enable package downloading. Defaults to `true`.

### **Customize head**

Placed in the beginning of the webpage.

### **Customize body**

Placed at the end of the body of the webpage.

### **Link expiration**

The expiration time of direct links, in hours. Set to `0` to disble expiration. Defaults to 0.
::: warning
Only direct links encrypted with passwords expire, since the expiration time is added to the sign query parameter, and this parameter is not checked for unencrypted paths.
:::

### **Privacy regex**

Content to hide in error messages by matching regular expressions (with `Golang`). One regex per line. The matched content will be replaced with `*`s of the corresponding length.

### **Ocr API**

Used to identify verification codes. Deploy yourself at `https://hub.docker.com/r/xhofe/ddddocr_server` or use the default API on [koyeb](https://app.koyeb.com/) (no availability guaranteed), which is not recommended to use in production environment.


### **Sign all**

Add signatures to direct links (no matter if is encrypted), which is `https://xxxx.com/d/xx?sign=vUQ5KFXnwMseKnIUXGRcfoG3cEHzKFBiPGp1NriMDXA=:0**`

Pay attention to security issues when this option is disabled: when this option is disabled, passwords of private files may be bypassed if AList is exposed to the public Internet.

## **Forward direct link params**

Please refer to **https://github.com/alist-org/alist/issues/3123**

### **Filename char mapping**

Special characters to replace to avoid Alist from breaking.

For example, the `/` symbol is the path symbol in Alist. Files containing `/` symbols cause the file to be discontinued halfway and break. So to fix this problem by replacing `/` with `|`, use:

```json
{"/": "|"}
```

Continue adding more replacement rules by doing:

```json
{"/": "|", "xx1":"xx2", "xx3":"xx3"}
```

## **Webauthn login enabled**

If you do not know what is **Webauthn**, STFW.

How to use:

Admin panel -> `Settings` -> `Global`-> enable `Webauthn login enabled`; Admin panel -> `Profile` -> Bind `Add a Webauthn credential`

- available Webauthn credential options: complementary devices (such as bracelets, watches), Windows Hello and security keys
- Just like using Single Sign-On, we can use **`Webauthn`** to log in after binding

  - Login page -> login button on the far right -> enter username -> Login -> configure required `Webauthn` verification method
- Using `Webauthn` requires a secure origin so can only be used on `HTTPS` or `localhost`
  - Unsafe sources such as `HTTP`, `192.168.x.x`, `127.0.0.1` or IP addresses cannot be used