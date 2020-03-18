## Local Storage

### DIVING IN

Cookies can be used for persistent local storage of small amounts of data. Dealbreaking downsides:

- Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
- Cookies are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)
- Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful

What we really want is

- a lot of storage space
- on the client
- that persists beyond a page refresh
- and isn’t transmitted to the server

### INTRODUCING HTML5 STORAGE

**HTML5 Storage** s a way for web pages to store named key/value pairs locally, within the client web browser. 

check for HTML5 Storage:

```
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}
```

### USING HTML5 STORAGE

