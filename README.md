# Blur on Control Center (No Root)
#### Redmi Note 13 Pro 4G / Poco M6 Pro

If you want to enable the blur effect on the Control Center of your Redmi /  Poco device, here's a detailed guide on how to do it without root. Keep in mind that this method may cause minor bugs, such as issues with status bar icons and animations. Proceed with caution!

## Prerequisites
- Shizuku app
- Canta app
- USB cable for connecting your phone to a PC
- A custom theme that modifies the status bar
  
## Steps

### 1. **Uninstall the "DevicesOverlay" System App**
   - Install and open [**Shizuku**](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) and [**Canta**](https://github.com/samolego/Canta) apps on your device.
   - Use them to uninstall the system app `DevicesOverlay` (`com.miui.systemui.devices.overlay`).
   - Once the app is uninstalled, restart your phone.

### 2. **Blur will appear, but with bugs**
   - You should now see the blur effect in the Control Center, but the status bar clock and battery icons margins might look a bit off.
   - The animations for the fingerprint and charging may not work properly.

### 3. **Fix the Status Bar bug**
   - Apply a **custom theme** that alters the status bar (any theme that changes the status bar should work).
   - You can find a reference theme in the video below (optional):  
     [Watch Tutorial](https://www.youtube.com/watch?v=xFFApwR-AZ8)

### 4. **Remove other Themes**
   - Delete any other themes on your device but save them as favorites to avoid losing them.

### 5. **Connect your Phone to your PC**
   - Plug your phone into a PC using a USB cable.
   - Set the phone to **File Transfer mode**.

### 6. **Navigate to the Theme Files**
   - On your PC, go to the following directory:
     ```
     Internal storage > Android > data > com.android.thememanager > files > MIUI > theme > .data > content > statusbar
     ```
   - You should see a `.mrc` file in that folder. **Copy** this file to your PC.

### 7. **Extract and Edit the Theme**
   - Change the file extension of the `.mrc` file to `.zip`.
   - Extract the contents of the `.zip` file.
   - Open the `themevalues.xml` file inside the extracted folder.
   - Find the `<MIUI_Theme_Values>` tag and copy the following lines into the file below the tag:
     ```xml
     <dimen name="statusbar_padding_start">19.4dip</dimen>
     <dimen name="statusbar_padding_end">16.8dip</dimen>
     <dimen name="statusbar_padding_top">5.0dip</dimen>
     <dimen name="status_bar_padding_start">19.4dip</dimen>
     <dimen name="status_bar_padding_end">16.8dip</dimen>
     <dimen name="status_bar_padding_top">5.0dip</dimen>
     <dimen name="status_bar_clock_size">13.5dp</dimen>
     ```

   - If there's a **nightmode** folder, repeat the process for its `themevalues.xml` file.

### 8. **Recompress the Files**
   - After editing the files, compress the extracted files (excluding the parent folder).
   - Name the zip file the same as the parent folder, and change the extension back to `.mrc`.

### 9. **Replace the Original .mrc File**
   - Copy the newly created `.mrc` file back to the original folder on your phone:
     ```
     Internal storage > Android > data > com.android.thememanager > files > MIUI > theme > .data > content > statusbar
     ```

### 10. **Apply the Theme**
   - Open the **Themes** app on your device.
   - Apply the newly edited theme.
   - If there are any issues with the status bar or theme, restart your phone to apply the changes.

## Important Notes
- This method was tested on **Redmi Note 13 Pro 4G** (version 2.0.2.0.VNFMIXM).
- This is a manual workaround, and bugs may occur, especially with the status bar and animations.
- Proceed carefully, as this may cause minor glitches. I am not responsible for any issues like bricking or voiding warranties.

## Undoing the Changes
If you want to revert to the original settings:
1. Delete the custom theme from the **Themes** app.
2. Reinstall the `DevicesOverlay` app using Shizuku and Canta.

By following these steps, you should now have the blur effect in your Control Center without rooting your device!
