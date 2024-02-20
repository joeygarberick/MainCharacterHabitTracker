# Development 
## Code
In the command line navigate to the place in which you would like to initialize the repository. Then run the following command:

> git clone https://github.com/joeygarberick/main_character_habit_tracker.git


## Firebase emulator Setup
1. Create or sign into a [firebase account](https://firebase.google.com/).
2.  Create project called ''main-char-habit-tracker''.
3. Get the firebase CLI through npm.

        $ npm install firebase

4. navigate to the project directory.
5. initialize firebase emulators.

        $ firebase init emulators bundle install

    - select firestore, authentication, and database.
    - make sure selected ports are:
        - 3000 for auth 
        - 8080 for firestore
        - 9000 for database.
6.  Start emulators 

        $ firebase emulators:start
7. Verify using the local UI givin

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
