# Social Robotics Project

![802ebe3d213260ac2e703f81092d25f4b9e42b15](https://github.com/user-attachments/assets/7c16d10c-f1aa-4b21-9266-954c2e987ef2)


Refer to the Demo video here
https://www.youtube.com/watch?v=vrSQJHgEsWs

## Getting Started: 

the program can be started using python3. You dont need to pass any parameters: 

```
python main.py
```
## Dependencies 

The following libraries are required to run the program. Sadly no requirements file is provided: 
- operator
- py_trees
- os
- openai 
- furhat_remote_api
- time
- dotenv
- datetime 
- re

# Main Program

the main programm can be found under /project/main.py. Here, the main function, classes and the tree is defined. 
In theory this could (and should) be distributed into different files, also to enhance the readability. But due to time constraints, the refactoring process was delayed. 

## Program Description

### 1. Initial Setup
- Import libraries and modules
- Load API key environment variables
- Initialize APIs (FurhatRemoteAPI, OpenAI)

### 2. Global Variables
- Current assistant
- Communication thread
- Running state

### 3. Key Classes
#### Object Classes
- `retrievedObject`: Stores game questions, expressions, status
- `GameState`: Tracks scores, interactions, history
- `furHatMediator`: Manages robot-system communication

#### Behavior Classes (py_trees.behaviour)
- `updAttendance`: Update user attendance
- `furHatSays`: Robot speech
- `furHatAsks`: Robot questioning
- `furHatListens`: Response listening
- `setupGame`: Initialize game settings
- `closeGame`: Game termination
- `isGameWonNode`: Win condition check
- `furHatExpressEmotions`: Robot emotion display
- `updateAndRetrieveAssistantsQuestion`: OpenAI question retrieval
- `sendPlayerResponseToLLM`: Player response transmission
- `triggerAssistantMessage`: Message sending/retrieval
- `updateQuestionsAsked`: Question tracking
- `finishGameIntro`: Introduction completion

### 4. Game Behaviors
- `makeLastGuess()`: Final guess attempt
- `startGuessingRound()`: Guessing round management
- `startCelebrityGuessingGame()`: Celebrity guessing game
- `startObjectDetectionGame()`: Object detection game

### 5. Tree Construction
- `create_root()`: Behavior tree organization
  - Attendance tracking
  - Welcome messages
  - Game setup
  - Game selection

### 6. Main Program Flow
1.Initialize blackboard variables

2.Create root behavior tree

3.Execute tree with continuous loop

4.Debug tree status and activity logs

5.Start main() execution


