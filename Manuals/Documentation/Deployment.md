# Deployment 

## Follow Steps of [Development.md](https://github.com/joeygarberick/MainCharacterHabitTracker/blob/main/Manuals/Documentation/Development.md).

This will ensure that your project is correctly set up to release

## Android deployment
1. Sign up for a Google Play Console developer account
2. Navigate into the project directory within powershell and run the following line of code:

        $ keytool -genkey -v -keystore %userprofile%\upload-keystore.jks ^
            -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 ^
            -alias upload
3. In the android folder create a file named key.properties with the following:

        $ storePassword=<password-from-previous-step>
          keyPassword=<password-from-previous-step>
          keyAlias=upload
          storeFile=<keystore-file-location>

The keystore will be under whatever filepath you saved it to in the code in step 2

4. In the android/app/build.gradle file add the keystore information from your properties file before the android block

        $ +   def keystoreProperties = new Properties()
          +   def keystorePropertiesFile = rootProject.file('key.properties')
          +   if (keystorePropertiesFile.exists()) {
          +       keystoreProperties.load(new FileInputStream(keystorePropertiesFile))
          +   }
          +
             android {
                ...
             }


5. Add the siging configuration before the buildTypes block:

        $ +   signingConfigs {
          +       release {
          +           keyAlias keystoreProperties['keyAlias']
          +           keyPassword keystoreProperties['keyPassword']
          +           storeFile keystoreProperties['storeFile'] ? file(keystoreProperties['storeFile']) : null
          +           storePassword keystoreProperties['storePassword']
          +       }
          +   }
             buildTypes {
                release {
                   // TODO: Add your own signing config for the release build.
                   // Signing with the debug keys for now,
                   // so `flutter run --release` works.
          -           signingConfig signingConfigs.debug
          +           signingConfig signingConfigs.release
                }
             }

6. Clean the code

        $ flutter clean

7. In the AndroidMainifest.xml in android/app/src/main verify that the android:label in the application tag has the correct app name and that the android.permission.INTERNET permission is enabled
8. In the build.gradel in the android/app directory ensure that the applicationID is correct, the versionCode is correct, the versionName is correct

9. in the command line navigate to the project directory and run

        $ flutter build appbundle

10. Using the Google Play console, you can begin the process for app release to the Play Store

## iOS Deployment
