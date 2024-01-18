# Basic Statistics

Basic Statistics is a Java-based GUI program that computes statistics on a
set of numbers.
This implementation is intended to be used in a `git bisect` exercise.

#### How to run Basic Statistics from the terminal:

Run this command from the Basic Statistics root directory, which contains the
*build.gradle* build file.

1. `./gradlew run`

The application's GUI will show up.

For Windows, use `gradlew.bat` instead of `./gradlew`.

#### How to build Basic Statistics and run its tests from the terminal:

1. Change into the Basic Statistics root directory, which contains the *build.gradle* build file.

2. Run `./gradlew compile` to compile Basic Statistics.

4. Run `./gradlew test` to run unit tests.

5. Run `./gradlew clean` whenever you want to clean up the project (i.e., delete all generated files).

#### Program features:
* Displays (at the bottom of the screen) a set of entered numbers.
* Computes the mean of the set of numbers.
* Computes the median of the set of numbers.
* Computes the mode of the set of numbers.
