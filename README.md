# android-restore-keystore-jks
Android restore keystore

## Sign android app with new keystore file if you missing password or lost jks file.

1. Create new keystore.jks file with comand line (not android studio build menu)

    Linux: `keytool -genkeypair -alias upload -keyalg RSA -keysize 2048 -validity 9125 -keystore keystore.jks`
    
    Windows: `"C:\Program Files\Android\Android Studio\jre\bin\keytool.exe" -genkeypair -alias upload -keyalg RSA -keysize 2048 -validity 9125 -keystore "C:\keystore_new.jks"`

2. Generate a .pem file from new keystore

    Linux: `keytool -export -rfc -alias upload -file upload_certificate.pem -keystore keystore.jks`
    
    Windows: `"C:\Program Files\Android\Android Studio\jre\bin\keytool.exe"  -export -rfc -alias upload -file  "C:\upload_cert.pem" -keystore  "C:\keystore_new.jks"`

3. Use this support form, set "keystore problem" and with attachment add .pem file: https://support.google.com/googleplay/android-developer/contact/otherbugs

4. 12-48h you new keystore is enabled. Update your app on playstore with new apk signed with new keystore :D
