# userChrome.app.css
userChrome.css file which hides many normal interface features in order to provide the **base** for an app-like(not browser-like) use of Firefox. PWA-adjacent.

```css
@namespace url("http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul");

/* only needed once */

@namespace html url("http://www.w3.org/1999/xhtml");
#PersonalToolbar,
#PanelUI-Button,
#PanelUI-menu-button,
#star-button,
#forward-button,
#home-button,
#bookmarks-toolbar-button,
#library-button,
#sidebar-button,
#pocket-button,
#fxa-toolbar-menu-button,
#reader-mode-button,
#identity-icon {
    visibility: collapse;
}

#urlbar-background {
    background-color: black !important;
}


/* Remove back button circle */

#back-button:not(:hover),
#back-button:not(:hover)>.toolbarbutton-icon {
    background: transparent !important;
    border: none !important;
    box-shadow: none !important;
}

#back-button:hover,
#back-button:hover>.toolbarbutton-icon {
    border: none !important;
    border-radius: 2px !important;
}

#urlbar-container {
    visibility: collapse !important
}

#TabsToolbar-customization-target {
    min-width: 50vw;
    max-width: 50vw;
    width: 50vw;
}
```