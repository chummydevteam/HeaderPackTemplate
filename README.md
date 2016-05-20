# HeaderPackTemplate Readme

To use this, template, the key differences from the CyanogenMod template is two things,

## AndroidManifest.xml

Please make sure in AndroidManifest.xml (HeaderPackTemplate/theme/src/main/AndroidManifest.xml) of your theme, you REMOVE all other use-features for "cyanogenmod.theme", and replace it with this line.


    <uses-feature android:name="org.cyanogenmod.theme.extensions" android:required="true"/>

## res/values/strings.xml

Finally, please make sure that your theme's "res/values" folder (not under assets), you have added this to a strings.xml. In the sample APK above, I have named them "headers_whitelist.xml" (HeaderPackTemplate/theme/src/main/res/values/headers_whitelist.xml)

    <string-array name="theme_component_whitelist">
        <item>headers</item>
    </string-array>
    
These two changes will allow for Play Store to filter your Header APK to distribute ONLY to ROMs with these specific commits:

### ThemesProvider
https://github.com/DirtyUnicorns/android_packages_providers_ThemesProvider/commit/46cc240c06588c49d3fd9d0d835e38a0feddad8d
### FrameworksBase:
https://github.com/DirtyUnicorns/android_frameworks_base/commit/e6eadc2461c35ac26b1b80f34da74707ae366fd2
### ThemeChooser
https://github.com/DirtyUnicorns/android_packages_apps_ThemeChooser/commit/a834d60ffed1d694211a77552239f365290b8e07
### Vendor
https://github.com/DirtyUnicorns/android_vendor_du/commit/b8781a263608eb6da2950de047724f29a1898db1

Please make sure that you have these 4 commits merged in your target rom to allow it to be VISIBLE on ROMs other than DU from Play Store!
