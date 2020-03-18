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

```
interface Storage {
  getter any getItem(in DOMString key);
  setter creator void setItem(in DOMString key, in any data);
};
```

### TRACKING CHANGES TO THE HTML5 STORAGE AREA

```
if (window.addEventListener) {
  window.addEventListener("storage", handle_storage, false);
} else {
  window.attachEvent("onstorage", handle_storage);
};
```
**STORAGEEVENT OBJECT**
  - key (string) the named key that was added, removed, or modified
  - oldValue (any) the previous value (now overwritten), or null if a new item was added
  - newValue (any) the new value, or null if an item was removed
  - url (string) the page which called a method that triggered this change

  ### HTML5 STORAGE IN ACTION

  ```
  function saveGameState() {
    if (!supportsLocalStorage()) { return false; }
    localStorage["halma.game.in.progress"] = gGameInProgress;
    for (var i = 0; i < kNumPieces; i++) {
	localStorage["halma.piece." + i + ".row"] = gPieces[i].row;
	localStorage["halma.piece." + i + ".column"] = gPieces[i].column;
    }
    localStorage["halma.selectedpiece"] = gSelectedPieceIndex;
    localStorage["halma.selectedpiecehasmoved"] = gSelectedPieceHasMoved;
    localStorage["halma.movecount"] = gMoveCount;
    return true;
}
```

