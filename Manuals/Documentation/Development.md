# Development 
## Code
In the command line navigate to the place in which you would like to initialize the repository. Then run the following command:

    $ git clone https://github.com/joeygarberick/main_character_habit_tracker.git


## Firebase emulator Setup
1. Create or sign into a [firebase account](https://firebase.google.com/).
2.  Create project called ''main-char-habit-tracker''.
3.  On the Firebase Console, select to add a new Android app to this Firebase project.
4.  The "Android Package Name" should match com.example.main_character_habit_tracker

        $ The debug signing certificate SHA-1 is not needed here

5. Once registered in the firebase console, you will need to download the configuration file from the Firebase console called google-services.json. This file will be added to your project under the android/app directory.
6. To install the configuration file to the project, add the following line of code to the android/build.gradle file to add the 'google-serivces' plugin

        $ classpath 'com.google.gms:google-services:4.3.8'

> [!NOTE]
> Multidex should be preenabled thus there will be no issues with merging dex archives



8.  Apply the plugin by adding the following underneath the line "apply plugin: 'com.android.application'

        $ apply plugin: 'com.google.gms.google-services'

> [!NOTE]
> Skip steps - if you do not have a mac to release to iOS as Xcode is required


10. On the firebase console select to add an additional iOS app to the Firebase app.
11. When prompted add your iOS bundle id to the flutter project
> [!NOTE]
> This can be found under the General tab when opening ios/Runner.xcworkspace with Xcode

12. Download teh GoogleService-Info.plst file from the Firebase console and using Xcode, open the projects ios/main-character-habit-tracker.xcworkspace file. Right click Runner from the left side nav bar within Xcode and select Add files and select the file you just downloaded to add to the project. Ensure that you have Copy Items if needed selected


13. Get the firebase CLI through npm.

        $ npm install firebase

14. navigate to the project directory.
15. initialize firebase emulators.

        $ firebase init emulators bundle install

    - select firestore, authentication, and database.
    - make sure selected ports are:
        - 3000 for auth 
        - 8080 for firestore
        - 9000 for database.
16.  Start emulators 

        $ firebase emulators:start
17. Verify using the local UI givin

    <img width="487" alt="Screenshot 2023-11-12 at 3 30 38 PM" src="https://github.com/joeygarberick/MainCharacterHabitTracker/assets/112219906/48b98a56-8dad-4443-b14d-bd5516730f10">

## Environment Setup
1. [Download Flutter](https://docs.flutter.dev/get-started/install) as this is a flutter application.

## Simulator Setup Xcode
1. Download XCode
2. Download the mobile phone simulator.
    - With ios 15 or newer 
3. Start up ios simulator
    - Link to your editor
4. Run the code

## Simulator Setup Android Studio
1. Download Android Studio
2. Download the mobile phone simulator.
4. Link to your editor
4. Run the code

## Linting
- This is a flutter project meaning we utilize Dart's built-in linter for an analysis of our Dart codebase. 

        $ dart analyze

- The rules are configured using the `analysis_options.yaml` file in our project.

- Run the `dart analyze` before  a commit. 

- If any linting issues are detected the commit is stopped.

- To view more about the dart linter visit [this link](https://dart.dev/tools/linter-rules)
