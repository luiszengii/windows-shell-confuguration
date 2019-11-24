# windows-terminal-confuguration
configurations for windows configuration

## Configuration Examples:

### Add a custom background to the WSL Debian terminal profile

1. Download the Debian JPG logo https://www.debian.org/logos/openlogo-100.jpg
2. Put the image in the
 `$env:LocalAppData\Packages\Microsoft.WindowsTerminal_<randomString>\LocalState\`
 directory (same directory as your `profiles.json` file).

    __NOTE__:  You can put the image anywhere you like, the above suggestion happens to be convenient.
3. Open your WT json properties file.
4. Under the Debian Linux profile, add the following fields:
```json
    "backgroundImage": "ms-appdata:///Local/openlogo-100.jpg",
    "backgroundImageOpacity": 1,
    "backgroundImageStretchMode" : "none",
    "backgroundImageAlignment" : "topRight",
```
5. Make sure that `useAcrylic` is `false`.
6. Save the file.
7. Jump over to WT and verify your changes.

Notes:
1. You will need to experiment with different color settings
and schemes to make your terminal text visible on top of your image
2. If you store the image in the UWP directory (the same directory as your profiles.json file),
then you should use the URI style path name given in the above example.
More information about UWP URI schemes [here](https://docs.microsoft.com/en-us/windows/uwp/app-resources/uri-schemes).
3. Instead of using a UWP URI you can use a:
    1. URL such as
`http://open.esa.int/files/2017/03/Mayer_and_Bond_craters_seen_by_SMART-1-350x346.jpg`
    2. Local file location such as `C:\Users\Public\Pictures\openlogo.jpg`
