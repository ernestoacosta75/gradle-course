### Create a Library Modules
* Define a new module
* Code the module
* Assign the dependency for the module
* Extract the JSON display code into a separate module

### Gradle Project Structure
* Is a review of directories and files
* Identifies purpose of each file and directory
* Differentiates file and directory types (IntelliJ, Java, or Gradle)

##### settings.gradle
Its main roles is to define all included submodules and to mark the directory root of a tree of modules, so you can only have one settings. gradle file in a multi-module project.
It will be executed before any build.gradle script and even before the Project instances are created.

### Gradle Build Directory
* What is used for?
  Is the directory which all artifacts are generated into.
* How can we manipulate it directly?
* Gradle clean task
  This task is able to remove any output files or directories we have defined for our task.
  **gradle -q clean**
* Change the location of the build directory
  In the **build.gradle** file set:
  **buildDir** = "<directory_name>"