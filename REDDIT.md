I do a thing that is a little bit unorthodox. I have a suite of libraries which allow me to easily and reliably manage a Firefox process and a Firefox profile, with fixed parameters for what should be accomplished by that Firefox/Profile pair. So if I want to pre-install addons, I can do it. If I want to change settings, I can do it. If I want to edit `userChrome.css`, I can do that too. I use these libraries to make Firefox act the way I need it to, and one of the ways I need it to be is to hide the navigation bar and compact the tab bar and webExtension `browserAction`'s onto a single line. Like a PWA, but without the support.

I've **almost** had it perfect for weeks, but I just can't seem to figure out this one(probably tiny) remaining tweak, I want to go from:

- ![before:](https://eyedeekay.github.io/userChrome.app.css/before.png)

to something more like:

- ![after:](https://eyedeekay.github.io/userChrome.app.css/after.png)

Since this appears to be the place where the `userChrome.css` experts hang out, I thought this would be the place to ask for advice. How do I manage this? Here is my existing CSS:

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
