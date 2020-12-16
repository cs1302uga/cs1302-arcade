# CSCI 1302 - Arcade App v2020.fa

![Approved for: Fall 2020](https://img.shields.io/badge/Approved%20for-Fall%202020-blueviolet)
![Team Size: 1](https://img.shields.io/badge/Team%20Size-1-informational)

<hr>

**The [final late submission deadline](#final-submission-deadline) has passed for Fall 2020.**

</hr>

This document contains the description for the `cs1302-arcade` project
that is assigned to the students in the CSCI 1302 classes
at the University of Georgia.

**Please read the entirety of this file before
beginning your project.**

## Due Dates

This project has **three due dates**, which are briefly described below
and further described later in this document. You can also reach
the requirements for each deadline by clicking it in the list below.

* [**Deadline 1**](#deadline-1) (*Required*): **TUE 2020-12-01 (Dec 01) @ 11:55 PM** 
* [**Deadline 2**](#deadline-2) (*Required*): **TUE 2020-12-08 (Dec 08) @ 11:55 PM**
* [**Deadline 3**](#deadline-3) (*Required*): **WED 2020-12-16 (Dec 16) @ 12:00 PM (NOON)**

## Table of Contents

* [Due Dates](#due-dates)
* [Academic Honesty](#academic-honesty)
* [Updates](#updates)
* [Important Final Project Policies](#important-final-project-policies)
  * [Final Submission Deadline](#final-submission-deadline)
  * [Private GitHub-hosted Git Repository](#private-github-hosted-git-repository)
  * [Working a Local Machine](#working-a-local-machine)
* [Project Description](#project-description)
* [Project Requirements & Grading](#project-requirements--grading)
  * [Functional Requirements](#functional-requirements)
  * [Non-Functional Requirements](#non-functional-requirements)
  * [Absolute Requirements](#absolute-requirements)
* [How to Download the Project](#how-to-download-the-project)
* [Submission Instructions](#submission-instructions)
* [Appendix - Useful Links](#appendix---useful-links)
* [Appendix - Starter Code](#appendix---starter-code)
* [Appendix - Workflow](#appendix---workflow)
* [Appendix - FAQ](#appendix---faq)

## Academic Honesty

You agree to the Academic Honesty policy as outlined in the course syllabus and the
University honesty website. 
Furthermore, you must adhere to the copyright notice and licensing information 
at the bottom of this document.

Additionally, we recognize that free and open-source software implementations
of the games described in this project are available. You are expected to write
your games from scratch. The only exception to this is the use of existing
art / visual assets, provided that you include proper attribution to the
author(s) of any creative works you incorporate into your submission.

## Updates

Updates will be posted here.
If there has been an update and you have already cloned the project
using the instructions in this document, then you can update your copy 
of the project by folliwing these steps: 
i) fully commit; 
ii) checkout the `master` branch; then 
iii) pull the changes using the `git pull skeleton master` command.

## Important Final Project Policies

### Final Submission Deadline

Please take care to note the date/time for **Deadline 3**, the 
**final submission deadline** for this project. For both logistical and
policy-related reasons, the usual late work policy will not apply,
and **no late submissions will be accepted after 05:00:00 PM on 
WED 2020-12-16 (Dec 16)**. Late submissions will only be accepted 
between **12:00:01 PM -- 05:00:00 PM on WED 2020-12-16 (Dec 16)**;
submissions received during that time frame will incur the standard 
penalty for one day late.

### Private GitHub-hosted Git Repository

Each student is required to setup a private GitHub-hosted Git repository 
for their project with the following users both added as collaborators:

  * [`mepcotterell`](https://github.com/mepcotterell) -- Dr. Cotterell
  * [`bjb211`](https://github.com/bjb211) -- Dr. Barnes

Your instructors will have access to your private repository's history. This
means that they can see what you did and when it was committed based on 
the log.

**To setup this repository,** students should refer to their notes for the
[required tutorial reading](https://github.com/cs1302uga/cs1302-tutorials/blob/master/github-setup.md),
which covers how to: 
i) setup SSH keys on Odin and GitHub (only need to do once);
ii) create a private repository; and
iii) add collaborators.

**Specific instructions for connecting your project on Odin with
your private repository** are provided 
[later in this document](#how-to-download-the-project).

### Working on a Local Machine

If you decide to work on part or all of the project on your local machine,
then it's your responsibility to ensure that your environment is compatible
with the versions of software on Odin. No technical assistance will be provided 
by the instructional staff to accomodate this beyond the information provided
in this policy statement. A list of the relevant software versions currently 
in use on Odin is provided below for convenience. 

* **Apache Maven 3.6.3**
* **Java 11.0.8** (vendor: Oracle Corporation; **not OpenJDK**)
* **OpenJFX 11** (note: should get handled by Maven)

Remember, **your code still needs to compile and run on Odin** per the 
"Development Environment" [absolute requirement](#absolute-requirements).
That is, if your submission does not compile on Odin, then that will result
in an immediate zero for the assignment. 

## Project Description

Your goal is to implement, from scratch, a single GUI application
in Java 11 using JavaFX 11 that provides a playable game.

You must choose one game total from either of the following groups:

* **Group 1**

  * [Asteroids](https://en.wikipedia.org/wiki/Asteroids_(video_game))

  * [Centipede](https://en.wikipedia.org/wiki/Centipede_(video_game))

  * [Tetris](https://en.wikipedia.org/wiki/Tetris)

* **Group 2**

  * [Mancala](https://en.wikipedia.org/wiki/Mancala)

  * [Reversi](https://en.wikipedia.org/wiki/Reversi)

  * [Chess](https://en.wikipedia.org/wiki/Chess)

You have a lot of flexibility with regard to the visuals of your games.
As long as the functional requirements are met and the game mechanics are easily
recognizable, you are free to make each game look and feel however you want
(please keep it appropriate). The general functional requirements for each game
group are provided later in this document.

Part of software development is being given a goal but not necessarily being
given instruction on all of the details needed to accomplish that goal. For example,
even though working with things like keyboard and mouse-related events
haven't been explicitly covered in class, you are going to need to look up how to do
these things in order to complete this project. **Some [starter code](#appendix---starter-code)
and a generously helpful [FAQ](#appendix---faq) are provided.**

This project is also designed to help you better understand the usefulness of good
class design. While you can technically write your entire JavaFX-based
GUI application entirely in the `start` method, this will make your code messy,
hard to read, possibly redundant, and likely more prone to errors.
Before you write any code, you should plan out your application's scene graph
(i.e., the containment hierarchy), and design custom components as needed.
If you find that you are writing a lot of code related to a specific component
(e.g., setting styling, adding event handlers, etc.), then it's probably
a good idea to make a custom version of that component in order to reduce
clutter. **You are strongly encouraged to consider swapping out multiple scenes
for this project.**

### Learning Outcomes

* Plan, design, implement, test, debug, and deploy a complete object-oriented
  software solution in Linux/Unix environment (1302-LO1)
* Utilize inheritance and polymorphism in a software project (1302-LO3-LO4).
* Develop a GUI for a software project (1302-LO7).
* Implement exception-handling in a software project (1302-LO8).
* Understand and apply language basics using an OOP language (1302-LO11).

### Functional Requirements

* **Main Application Requirements (10 points):** The main part of your
  application needs to fulfill the following functional requirements:

  * *Initial Title Window** (5 points):* Your application should present
    the user with a visual / graphical title screen for your game. Starting a game should
    either swap the scene in the current stage or create a new application modal stage
    on which to display the game's scene graph.

  * *Multiple Games per Execution (5 points):* After the application is started and
    and the title screen/window is displayed, your application should allow a user
    to start and end an instance of the game without exiting the entire application.
    Furthermore, after a game instance has ended, it should be possible for the user to 
    start and end another instance of the game. There is no limit to how many times
    the user may do this.

* **Game Requirements (90 points):**

   * **Group 1 Game Requirements:** If you choose a Group 1 game, your implementation
     needs to fulfill the following functional requirements:

     * *UI, Mechanics, and Scoring (80 points):* The user interface and game mechanics
       must be easily recognizable and consistent with traditional implementations of
       the game you chose (see the Wikipedia links for more information). Your game
       must provide a consistent scoring mechanism and display the score(s) to
       the user somewhere in the user interface. Additionally, games in this group
       must provide a leveling mechanism by which the game's level of difficulty
       increases over time as the "level" increases. A minimum of three levels is
       required, however, there is no maximum level requirement. The first level
       should be easy enough for most players familiar with the game to complete.

     * *Controls (10 points):* You are required to provide keyboard controls
       for a game in this group. If anything is not intuitive, then you need to let
       the user know before the game starts.

   * **Group 2 Game Requirements:** If you choose a Group 2 game, your implementation
     needs to fulfill the following functional requirements:

     * *UI, Mechanics, and Scoring (80 points):* The user interface and game mechanics
       must be easily recognizable and consistent with traditional implementations of
       the game you chose (see the Wikipedia link for more information). Your game
       must provide a consistent scoring mechanism and display the score or scores to
       the users somewhere in the user interface.

     * *Controls (10 points):* You are required to provide intuitive mouse or
       keyboard controls for a game in this group. If anything is not intuitive,
       then you need to let the user know before the game starts.

     * *Note:* You are only required to provide a
       human player vs. human player mode for for a multiplayer game in this category.
       Feel free to add support for computer players, however, such support will not
       contribute to your grade.

* **Extra Credit 1 (5 points):** Add some kind of animated intro to your application.
  One potential way to accomplish this is by using a separate scene for your intro.
  This intro should include, in addition to some kind of animated element, the
  application title (i.e., `cs1302-arcade`) and your name. An animated GIF, by itself, 
  does not meet this requirement. We
  want one or more nodes in the scene to move around. **If you want the grader to
  check for this requirement, then you must make sure it is included in your
  last update to `REFLECTION.md`.**

* **Extra Credit 2 (5 points):** Add a [high score table](https://en.wikipedia.org/wiki/Score_(game)#High_score)
  to your application's initial title window.
  The table needs to actually keep track of the high scores for each game and include
  player initials. This may involve modifications in other areas of your application to
  accommodate this. In order to receive full credit for this extra credit functional
  requirement, the high score table must persist over time and over separate executions
  of your application. This will involve reading and writing to a file.
  **If you want the grader to check for this requirement, then you must
  make sure it is included in your last update to `REFLECTION.md`.**

### Non-Functional Requirements

A non-functional requirement is *subtracted* from your point total if
not satisfied. In order to emphasize the importance of these requirements,
non-compliance results in the full point amount being subtracted from your
point total. That is, they are all or nothing.

* **User-Friendly Experience (10 points):** The windows of your application
  should not exceed a pixel dimension of `1280` (width) by `720` (height). 
  Additionally, except for reasonable delays resulting from X forwarding, your 
  application should not hang/freeze or crash during execution. If a grader 
  encounters lag, then they will try to run your application locally using Oracle
  Java 11.

* **Local Assets / Resources (10 points):** All assets (e.g., images) need to
  be pre-downloaded and placed under `resources`. You are not allowed
  to load assets directly from the web. This will help make your app faster.

  You should place local files under `resources` in your project directory (you may need to
  create the `resources` directory). URLs prefixed with `file:` should be relative to your
  project directory. 
   
  Example:
   
  | Resource                | URL                            |
  |-------------------------|--------------------------------|
  | `resources/icon.png`    | `"file:resources/icon.png"`    |
  | `resources/foo/img.png` | `"file:resources/foo/img.png"` |
  
* **(20 points) Code Style Guidelines:** You should be consistent with the style 
  aspect of your code in order to promote readability. Every `.java` file that
  you include as part of your submission for this project must be in valid style 
  as defined in the [CS1302 Code Style Guide](https://github.com/cs1302uga/cs1302-styleguide).
  All of the individual code style guidelines listed in that document are part 
  of this single non-functional requirement. Like the other non-functional
  requirements, this requirement is all or nothing. 
  
  **NOTE:** The [CS1302 Code Style Guide](https://github.com/cs1302uga/cs1302-styleguide)
  includes instructions on how to use the `checkstyle` program to check
  your code for compliance on Odin.

* **In-line Documentation (10 points):** Code blocks should be adequately documented
  using in-line comments. This is especially necessary when a block of code
  is not immediately understood by a reader (e.g., yourself or the grader).

* **Attribution (10 points):** Proper attribution should be given for all assets (e.g.,
  art, sound, music, etc.) that you did not author.
  You should make an `ATTRIBUTION.md` file that contains this information. For each
  asset, please provide the following information:

  * Asset Name
  * Path within your project
  * Author citation
  * URL
  * License

  Here is an example of an entry in an `ATTRIBUTION.md` file:

  ```
  ## Alien
  * `resources/alien.png`
  * Carlos Alface. "Alien" November 15, 2014
  * https://opengameart.org/content/alien-1
  * Creative Commons Attribution 3.0 Unported (CC BY 3.0)
  ```

* <a name="reflections"/>**(30 points; 10 points each) Reflections in Deadline Submissions:** 
  Each deadline submission has its own specific requirement, which are outlined in the
  [Submission Instructions](#submission-instructions). For each deadline, satisfaction 
  of this non-functional requirement will be determined based on the existence of an 
  updated `RELECTION.md` file on your `master` branch prior to the deadline, 
  the related Git tag, and germaneness of the content included in your `REFLECTION.md` file,
  and evidence of branching and merging in your Git log.

### Absolute Requirements

An absolute requirement is similar to a non-functional requirement, except that violating
it will result in an immediate zero for the assignment. In many cases, a violation
will prevent the graders from evaluating your functional requirements. No attempts will be
made to modify your submission to evaluate other requirements.

* **Project Structure:** The location of the default
  package for the source code should be a direct subdirectory called `src/main/java`.
  When the project is compiled using Maven, the the default package for compiled
  code should be `target/classes`.

  If you follow this structure, then you might type the following to clean, compile,
  and run your code using Maven, assuming you are in the top-level project directory:

  ```
  $ mvn clean
  ```

  ```
  $ mvn -e compile
  ```

  ```
  $ export MAVEN_OPTS=-Dprism.order=sw;
  $ mvn -e exec:java -Dexec.mainClass="cs1302.arcade.ArcadeDriver"
  ```
  
  The following may also work to run the program:
  ```
  $ mvn -e -Dprism.order=sw exec:java -Dexec.mainClass="cs1302.arcade.ArcadeDriver"
  ```

  Your main application class should be `cs1302.arcade.ArcadeApp`.
  The driver class should be `cs1302.arcade.ArcadeDriver`.
  Any additional `.java` files in your project are expected to fulfill all
  non-functional and absolute requirements, even if the main parts of the
  project do not use them. You should remove any `.java` files that are not required for
  your project prior to submission.

* **GitHub Collaborators:** You are required to add the following users as collaborators
  to the private GitHub-hosted Git repository that you setup for their project:

  * [`mepcotterell`](https://github.com/mepcotterell) -- Dr. Cotterell
  * [`bjb211`](https://github.com/bjb211) -- Dr. Barnes

  Your instructors will have access to your private repository's history. This
  means that they can see what you did and when based on the git log.

* **<a id="devenv"/>Development Environment:** This project must be implemented 
  in Java 11, and it *must compile and run* correctly on Odin using the specific
  version of Java 11 that is setup according to the instructions provided
  by your instructor. For this requirement, the term *compile* should be 
  interpreted as *compile with no errors or warnings*.

* **No FXML or use of Scene Builder:** FXML and SceneBuilder
  are advanced tools that are not currently covered in this course. Use of
  either for this project is prohibited. Please note that the project is
  not easier with these tools. In most cases, they actually make the
  project harder, especially since those topics have not been covered.

### Grading

The graders will compile and run your code on Odin using Maven (likely via
the provided `Makefile`). They will test each of the requirements and total up the points
earned. This project is worth 100 points. Students have an opportunity to earn
an additional 10 points via extra credit.

## How to Download the Project

These instructions assume that you have
[setup your SSH keys](https://git.io/fjLzB#setting-up-ssh-keys)
on Odin and GitHub.

1. If you have not done so already, you should create a
   free GitHub-hosted private Git repository for your project under your GitHub
   account called `cs1302-arcade` and add `mepcotterell` and `bjb211`as collaborators to that private repository. 
   **In the remaining instructions,**
   **`TEAM_REPO_SSH` will refer to the SSH URL for that repository as provided by GitHub.**

1. You should clone your empty repository to your Odin account and
   setup a link to the remote skeleton repository provided by your instructor. A sequence
   of commands is provided below. You should make every effort to understand what
   each command is doing *before* you execute the command.

   ```
   $ git clone TEAM_REPO_SSH cs1302-arcade
   $ cd cs1302-arcade
   $ git remote add skeleton https://github.com/cs1302uga/cs1302-arcade.git
   $ git pull skeleton master
   $ git push origin master
   ```

   If you followed these instructions correctly, then the steps above should have
   created a directory called `cs1302-arcade` in your present working directory that
   contains the project files as well as a local copy of the repository.
   If you have any problems with any of these procedures, then please
   ask about them on Piazza.

## Submission Instructions

### Deadline 1

For this deadline, you're required to include the **starter code** and an **initial update 
to your `REFLECTION.md` file.** You are not expected to have made any changes to the 
starter code at this time, but it's perfectly okay if you have. The `REFLECTION.md` is 
just a text file that you will update prior to this and subsequent deadlines to reflect 
on the work that you have done and the work that you have remaining. 

* Update your project's `REFLECTION.md` and tag your `master` branch (details below) prior to
  this deadline. Your reflection update should include the following:

  1. Work that has been done since you started the project, if any.
  2. The work you plan to complete before the next deadline (except for the last submission); and
  3. Based on your plan, what features do you anticipate making branches for to 
     satisfy the "demonstrate branching and merging" requirement for Deadline 2?
  
  **These changes, including your work in progress, must be committed and tagged in the `master` branch of your repository.** 
  
  1. Ensure that whatever branch you are on is **fully committed** (i.e., `git status` says there is nothing to commit); 
  2. Checkout the `master` branch;
  3. If needed, merge in changes from the branch you were working on; then
     execute the commands below:

     ```
     $ git tag -am "Deadline 1" deadline1
     $ git push --all origin
     $ git push origin --tags
     ```
  
  After pushing, all commits that you've made so far should be visible in your private repository
  on GitHub. Under the green "Code" button on your repository's GitHub page, you should see a link
  that says something like, "XYZ commits." If you click it, it will show you log for your `master`
  branch -- compare it with `git log` or `git adog` to make sure it's actually up to date.
  If you need to make more commits and retag, then use an `a`, `b`, `c`, ... suffix in
  the tag names (e.g., `deadline1a`).

* Evidence of branching and merging is not required for this deadline, but it is for future 
  deadlines. **Please take some time now to read those requirements** so that you're not
  thrown off guard and try to do them at the last minute.

### Deadline 2

For this deadline, you're required to include your **updated project code** and an 
**update to your `REFLECTION.md` file.** You **are expected** to have made some
progress based on your Deadline 1 reflection; however, it's okay if the work you
did differed from your original plan. You are **also expected** to demonstrate
the use of branching and merging. Here are the specific requirements:

* Update your project's `REFLECTION.md` and tag your `master` branch (details below) prior to
  this deadline. Your reflection update should include the following:

  1. Work that has been done since you started the project and how it
     differs from the plan you presented in your Deadline 1 reflection; 
     if it helps, you may summarize your Git log for part of this description;
  2. The work you plan to complete before the next deadline; and
  3. What issues have you encountered while working on this project?
     
  **These changes, including your work in progress, must be committed and tagged in the `master` branch of your repository.** 
  
  1. Ensure that whatever branch you are on is **fully committed** (i.e., `git status` says there is nothing to commit); 
  2. Checkout the `master` branch;
  3. If needed, merge in changes from the branch you were working on; then
     execute the commands below:

     ```
     $ git tag -am "Deadline 2" deadline2
     $ git push --all origin
     $ git push origin --tags
     ```
     
  After pushing, all commits that you've made so far should be visible in your private repository
  on GitHub. Under the green "Code" button on your repository's GitHub page, you should see a link
  that says something like, "XYZ commits." If you click it, it will show you log for your `master`
  branch -- compare it with `git log` or `git adog` to make sure it's actually up to date.
  If you need to make more commits and retag, then use an `a`, `b`, `c`, ... suffix in
  the tag names (e.g., `deadline2a`).

* Evidence of branching and merging **is required** for this deadline. When inspecting your
  Git log, the graders would like to see that you made proper use of `branch`, `checkout`,
  and `merge` to work on portions of your project prior to including those changes in
  your `master` branch.

### Deadline 3

For this deadline, you're required to include your **final project code** and an 
**update to your `REFLECTION.md` file.** You **are expected** to have made
progress based on your Deadline 2 reflection; however, it's okay if the work you
did differed from your earlier plan. You are **also expected** to demonstrate
the use of branching and merging. Here are the specific requirements: 

* Update your project's `REFLECTION.md` and tag your `master` branch (details below) prior to
  this deadline. Your reflection update should include the following:

  1. Work that has been done since Deadline 2 and how it
     differs from the plan you presented in your Deadline 2 reflection; 
     if it helps, you may summarize your Git log for part of this description;
  2. What steps have taken to try to resolve the issue(s) you mentioned in your
     last reflection update? Have you encountered any new issues?
  3. **What extra credit opportunities should the graders check for in your submission?**
     If you don't include this, then the graders will not check for any
     extra credit, even if it's obvious that it's present in your
     final program.

 **These changes, including your completed work, must be committed and tagged in the `master` branch of your repository.** 
  
  1. Ensure that whatever branch you are on is **fully committed** (i.e., `git status` says there is nothing to commit); 
  2. Checkout the `master` branch;
  3. If needed, merge in changes from the branch you were working on; then
     execute the commands below:

     ```
     $ git tag -am "Deadline 3" deadline3
     $ git push --all origin
     $ git push origin --tags
     ```
     
* Evidence of branching and merging **is required** for this deadline. When inspecting your
  Git log, the graders would like to see that you made proper use of `branch`, `checkout`,
  and `merge` to work on portions of your project prior to including those changes in
  your `master` branch.
  
* Take special care to ensure that your fully-committed `master` branch reflects the project
  you wish to submit. Compare your log to the log on GitHub. If your GitHub repository does not have
  the most recent version of your project, then you may need to do a
  `git push origin master` while on your `master` branch. Finally, using `git status` should not indicate 
  any untracked files. If you need to make more commits and retag, then use an `a`, `b`, `c`, ... suffix in
  the tag names (e.g., `deadline3a`).

**CRITICAL:** For this deadline, you also need to submit on Odin! 
Change into the parent directory of your local copy of the repository and
submit it using the `submit` command:

   ```
   $ submit cs1302-arcade csci-1302
   ```

If you have any problems submitting your project, then please contact the CSCI
1302 Support Team by sending a private post to "Instructors" via the course
Piazza as soon as possible.

# Appendix - Useful Links

## JavaFX 11

* [JavaFX 11 API Documentation](https://openjfx.io/javadoc/11/)
* [JavaFX 11 Bookmarks](https://github.com/cs1302uga/cs1302-tutorials/blob/master/javafx/javafx-bookmarks.md)
* [CSCI 1302 JavaFX Tutorial](https://github.com/cs1302uga/cs1302-tutorials/blob/master/javafx/javafx.md)

## Resources

* [Reference Manual](https://git-scm.com/docs) - alternative to the manual pages for `git`
* [Pro Git (Book)](https://git-scm.com/book/en/v2) - contains a lot of good examples
* [Version Control by Example (Book)](https://ericsink.com/vcbe/index.html) - excellent introduction to version control by Eric Sink

# Appendix - Starter Code

While you may be comfortable creating a standard desktop application using JavaFX, you
may be less familiar with how to put together a game. To illustrate some of the graphical
capabilities of JavaFX, including event handlers for mouse and keyboard input, some
starter code has been provided. **Please read, compile, and execute the starter code.**
You are not required to use the starter code as a foundation for your program; however,
you are required to meet the Project Structure absolute requirement. 

Here is a video that demonstrates the execution of the starter code 
(click [here](https://www.youtube.com/watch?v=mwdF5eZoCHc) or the image below):

[![ArcadeApp Starter Code](starter-code.png)](https://www.youtube.com/watch?v=mwdF5eZoCHc)

Here are some links to the API documentation for some of the keyboard-related and
mouse-related classes used in the starter code:

* [`javafx.scene.input.KeyEvent`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/scene/input/KeyEvent.html):
  used as the input parameter type for the `handle` method in a keyboard-related event handler.
  
* [`javafx.scene.input.KeyCode`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/scene/input/KeyCode.html):
  an enumeration that describes the possible outputs of calling `getCode()` on a `KeyEvent` object.
  
* [`javafx.scene.input.MouseEvent`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/scene/input/MouseEvent.html):
  used as the input parameter type for the `handle` method in a mouse-related event handler.
  
Please note that the datatype for a keyboard-related event handler needs to be `EventHandler<? super KeyEvent>` and
not merely `EventHandler<KeyEvent>`. Likewise, the the datatype for a mouse-related event handler needs to be 
`EventHandler<? super MouseEvent>` and not `EventHandler<MouseEvent>`.

# Appendix - FAQ

Below are some frequently asked questions related to this project.
You may also find the [`cs1302-gallery` FAQ](https://github.com/cs1302uga/cs1302-gallery#appendix---faq)
a useful resource as well.

1. **How do I make my game run at *x* frames per second (e.g., 60 FPS)?**

   If you are using a single `Timeline` object for your main game loop, then duration of all
   key frames in the main game loop should sum to exactly `1000 / x` ms (e.g.,
   `Duration.millis(1000.0 / 60.0)`).
   The easiest way to ensure this is to have only one key frame with that duration.

1. **What is a good GUI container for games?**

   You already know that you can setup your scene graph however you want by using and nesting
   different types of layout panes. If you need explicit control over the `x` and `y` positions
   of some nodes, then I recommend using the
   [`Group`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/scene/Group.html) class.
   Since `Group` is a sub-class of `Node`, you should be able to add a `Group` object anywhere in
   your scene graph just like any other node.

1. **How do I setup event handlers related to mouse and keyboard events?**

   Look at the Javadoc documentation for the
   [`Node`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/scene/Node.html) class,
   specifically the methods that start with `setOnMouse` and `setOnKey`, to see the
   different types of mouse and keyboard events you can handle. Here is a simple example
   that prints the current time (using
   [`LocalTime`](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/time/LocalTime.html)) to
   standard output when a user clicks on an `ImageView` object (referenced by `iv`) that
   is assumed to be visible within the current scene graph:
   ```java
   iv.setOnMouseClicked(event -> System.out.println(LocalTime.now()));
   ```
   Remember, you can setup these event handlers for any node in the scene graph, including
   the containers.

1. **How can I detect if two nodes in my scene collide?**

   Look at the "Bounding Rectangles" section in the Javadoc documentation for the
   [`Node`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/scene/Node.html) class.
   The getter methods described in that section return references to
   [`Bounds`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/geometry/Bounds.html)
   objects, which likely contain useful information regarding the whereabouts of
   node. I would recommend taking a very close look at the methods in that class.

1. **How do I add sound?**

   While JavaFX does support audio playback of various formats, this feature is not
   currently available over X11 forwarding from Odin. **If you incorporate audio into**
   **your application, then take measures to properly deal with the unchecked exceptions**
   **that might get thrown if audio playback is not available.**

1. **How do I make basic shapes appear?**

   Look at the classes in the
   [`javafx.scene.shape`](https://openjfx.io/javadoc/11/javafx.graphics/javafx/scene/shape/package-summary.html)
   package.

Have a question? Please post it on the course Piazza.

<hr/>

[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by-nc-nd/4.0/)

<small>
Copyright &copy; Michael E. Cotterell and the University of Georgia.
This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a> to students and the public.
The content and opinions expressed on this Web page do not necessarily reflect the views of nor are they endorsed by the University of Georgia or the University System of Georgia.
</small>
