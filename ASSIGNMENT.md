# `git bisect` exercise

## Goal
The goal of this exercise is to improve git proficiency and to learn about systematic debugging, using `git bisect`.


## Setup
1. Make sure
a **[Java 17 or 21 JDK](https://www.oracle.com/java/technologies/downloads/)**
and **[Git](https://git-scm.com/) is installed**.

2. Not required, but strongly recommended:  [practice resolving a merge conflict](https://rawgit.com/mernst/git-conflict-tutorial/master/git-conflict-resolution.html).


## Background (story time)

The command `./gradlew clean build`
builds the application from scratch and runs all tests.

The developers of this application published the first release, which they
tagged *v1.0.0*.  Unfortunately, the developers **introduced a defect** at some
point **after** the *v1.0.0* release, which **has existed in the code
since**.

The test command `./gradlew clean build` did not catch the defect.
Since the developers were so excited about coding, they never manually checked a
single test run (they trusted the test command).



## Instructions

3. **Checkout** the most recent commit on the *main* branch (`git checkout main`) and run: "`./gradlew clean build`".  Verify that the software is defective (meaning that running the tests should fail), but the command `./gradlew clean build` succeeds!

4. Figure out why the command `./gradlew clean build` succeeds, and **fix it**.  Hint: run "`./gradlew clean build; echo $?`" which prints the exit code of the *gradle* process.

5. **Check out the commit with tag *v1.0.0*** (`git checkout v1.0.0`), and compile and test the application again.  **All tests pass** on this revision.  If that is not the case, you have done something wrong.

6. **Determine** the
**number of commits between tag v1.0.0 and HEAD** (the latest revision on main).
Include v1.0.0 and HEAD when counting, and note the command(s) that you used to
**automatically** compute this number.

7. Familiarize yourself with the [git bisect](https://git-scm.com/book/en/v2/Git-Tools-Debugging-with-Git#Binary-Search) command. Use `git bisect` to identify the **commit that introduced the defect** between version **v1.0.0** and **HEAD**. Start by manually using `git bisect` to identify the **commit that introduced the defect** between version **v1.0.0** and **HEAD**. Then, automate the process using a script. Note the commit hash and log message of the defect-inducing commit. **Verify** that you **correctly identified** the defect-inducing commit.


## Questions

1. Why does the automated testing infrastructure (before your fix) not catch the test failure? How did you improve it?

2. How many commits exist between version v1.0.0 and HEAD (including v1.0.0 and HEAD)? List the command(s) that you used to **automatically** compute this number.

3. Which commit (commit hash and message) introduced the defect? How did you verify that this commit indeed introduced the defect?

4. How many commits, not including `v1.0.0` and `HEAD`, did `git bisect` analyze before finding the first failing commit? List all commands you ran; this will likely be a series of calls to `git bisect`, or a call to your script.  The course staff must be able to run these commands, by copying (once) from your document and pasting into a command shell.

5. What is the best-, worst-, and average-case run-time complexity of `git bisect` to discover the defect-inducing commit? Why?

6. Which `git` command can you use to undo an undesirable commit?  Does this command work in your case (for the commit you identified in question 3)?  Briefly explain a problem that may occur when undoing a commit and what best practices mitigate this problem. 


## Deliverables

1. A plain-text file with your answers to the questions above.
