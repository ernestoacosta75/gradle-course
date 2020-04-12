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