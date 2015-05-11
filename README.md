# plex-channel-updater
Universal plugin updater module for Plex Server Channels that implement automatic plugins updates from remote config.
Support Github API by default.

Usage
-------

```python
from updater import Updater

@handler(PREFIX, TITLE, thumb=ICON)
def MainMenu():

    oc = ObjectContainer(title2=TITLE)
    Updater(PREFIX+'/updater', oc)
```

Configuration Info.plist
-------

```XML
  <!-- Current bundle version -->
  <key>CFBundleVersion</key>
  <string>1.7</string>
  <!-- Path to your latest bundle info -->
  <key>PlexPluginVersionUrl</key>
  <string>https://api.github.com/repos/:owner/:repo/releases/latest</string>
  <!-- Required for updater -->
  <key>PlexPluginCodePolicy</key>
  <string>Elevated</string>
```

Constants
-------
```python
# Version key
KEY_DATA_VERSION = 'tag_name'
# Release info key
KEY_DATA_DESC = 'body'
# ZIP URL
KEY_DATA_ZIPBALL = 'zipball_url'
```

Localization strings
-------

```JSON
"Success": "Success",
"Error": "Error",
"Update available: %s": "Update available: %s",
"Install latest version of the channel.": "Install latest version of the channel.",
"Channel updated to version %s": "Channel updated to version %s"
```