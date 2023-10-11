# Architecture
![Architectrue](https://github.com/joeygarberick/MainCharacterHabitTracker/assets/112030126/fa54a1c9-6201-458c-bc04-2807a6dcc4ab)
### Flutter Frontend
This is how the end user will interact with the application. It was made a module as it contains all of the front-end code and handles most of the communication with the back end server.

### Firebase
This is where all of the user data will be stored. This is a module as it contains firebaseAuth and firestore, two services employed and interacted with by the frontend.

### Communication
The frontend app handles auth by using firebaseAuth. This sends the relevant user credentials to firebase and firebase returns an auth token. After authorization, firebase sends all relevant user habit and location data in json format to flutter which flutter will display to the end user. 
