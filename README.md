# Personalized Workout Plan Generator (PWPG)

**A Java 17 desktop project based on the supplied AAT report**  
Student: KISHOR PANDIYAN J · Register No.: 711525BCS077 · KIT-CBE

## Features in this repository
- Swing desktop interface for entering a profile and fitness goal.
- BMI calculation and basic profile validation.
- Rule-based weekly plan generation using goal, fitness level, available days, equipment and limitations.
- Six-exercise catalogue: squat, push-up, bicep curl, lunge, plank and jumping jack.
- Workout session logging (repetitions/hold seconds, duration and form score).
- SQLite persistence through JDBC for profile and workout sessions.
- CSV export of workout history.
- Simple progression suggestion based on completion and form score.
- Clear separation of profile, plan, database and UI logic.

## Important implementation note
This is a runnable, student-project foundation implementing the profile, plan-generation, session-log, database and export parts of the report. **Live MoveNet pose inference, webcam skeleton overlay, and automatic camera-based rep counting are not implemented in this starter build.** The report describes those as target features. The current session form lets a user enter observed reps and form score manually. Add a MoveNet ONNX model and OpenCV/ONNX Runtime camera pipeline to complete those modules; do not report camera accuracy/FPS until you measure them.

## Requirements
- JDK 17+
- Maven 3.9+
- Internet on first build so Maven can download dependencies

## Run
From this folder:

```bash
mvn clean test
mvn exec:java
```

The SQLite database is created locally as `pwpg.db` in the working directory. It is ignored by Git.

## Export
Use **Export CSV** in the app to write `pwpg-session-history.csv`.

## GitHub
```bash
git init
git add .
git commit -m "Add PWPG personalized workout plan generator"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```
Create an empty GitHub repository first, then replace the remote URL above with your repository URL.

## Project structure
```text
src/main/java/in/kitcbe/pwpg/
  Main.java
  model/UserProfile.java
  model/Exercise.java
  model/WorkoutSession.java
  plan/PlanGenerator.java
  db/Database.java
  service/ProgressionEngine.java
  service/CsvExporter.java
  ui/MainFrame.java
src/test/java/in/kitcbe/pwpg/plan/PlanGeneratorTest.java
```

## Safety and privacy
This app provides general educational fitness suggestions and is not a medical device. Stop if you feel pain or dizziness. If you have an injury or medical condition, consult a qualified health professional. Keep the camera pose-processing extension local and avoid saving raw video unless there is a clear need and informed consent.
