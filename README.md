# SyncMarks (Firefox)
This is a Webextension for Mozilla Firefox to share your bookmarks across WebDAV Shares. Since Version 1.x you can also the [PHP Backend](https://github.com/Offerel/SyncMarks) to sync bookmarks. You can simply install the AddOn via Mozillas [AMO](https://addons.mozilla.org/addon/davmarks/) site. Since version 1.14, the AddOn can also be used in Chromium and derivates (Google Chrome, Microsoft Edge, Chromium and others). Bookmarks can be synchronized accross this browsers. You can use this plugin to export, import and sync your bookmarks to a WebDAV share of your choice or my [PHP Backend](https://github.com/Offerel/SyncMarks).

In latest Firefox Mobile (> v79.x) the bookmark API seems to be also supported at least on Android. I didnt found a way to activate this AddOn currently, but there will be a way to get this to work in future also on Android. The AddOns can be installed in Kiwi Browser, but something prevent from using the settings. I have to investigate this issue, when i have more time, but basically the AddOn will work there.

The bookmarks can be exported manually or optionally fully automatically. There are corresponding options in the addon settings. The Export/Import process is compatible with Firefox Sync. The bookmarks are also be compatible with the corresponding [Roundcube plugin](https://github.com/Offerel/roundcube_ffbookmarks), so that they can also be used in Roundcube.

### Permissions

There are some permissions needed, so that SyncMarks can work properly.

##### access your data for all sites

The WebDAV share can theoretically be located on any website. Since I don't know beforehand which one this can be, the AddOn needs the permission to store the data on any page. However, the data is only exchanged with the server specified in the settings.

##### read and modify bookmarks

Since you export and import all your bookmarks, the AddOn needs access to them.

##### access browser tabs

This is needed since you can open the settings panel from within the AddOn

##### storage

Here all the settings you specify are saved.

##### notifications

If the AddOn finds some problems or would like to tell you how many bookmarks are imported, this is done with a notification.

##### webRequest

The bookmarks are imported and exported with a webRequest. Only https connections other http-basic-authentications are supported.

### Current open bugs
There are some open issue, where i must use currently a workaround or if no workaround is possible, we have to wait for a upstream fix in Fennec project. THis is a list of a issues im aware as of now:
* Bookmark API isn't supported on Android. There is hope, that this will be supported in the upcoming future, but currently it's unsupported at least on Android. In Kiwi Browser its working as expected. You can follow the bug at https://bugzilla.mozilla.org/show_bug.cgi?id=1625231
* Context menu isn't supported on Fennec Android. The only workaround so far is to use again the popup view. That's why this function is now re-added again.
* Notifications are completely broken in Fennec Android. As a workaround, i have added pushed urls also the logfile. You can follow the bug report at https://github.com/mozilla-mobile/fenix/issues/14993
* activeTabs permission does not include url propertie on Fennec Android. As a workaround i have re-added the tabs permission, to get the url of an active tab. You can follow this bug at https://github.com/mozilla-mobile/fenix/issues/14093
* The settings will not opened correctly in Fennec Android. So the settings page will be opened sometimes invisible in a tab in the background, some other times it will opened multiple times. You can follow the bugreport at https://github.com/mozilla-mobile/fenix/issues/15742

