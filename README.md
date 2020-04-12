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
  
### Gradle Wrapper
* What is the Gradle Wrapper?
  * Is the thin "layer" around Gradle
  * Checks to see that the requested version of Gradle is installed
  * Passes the command onto the real Gradle
* How do we use the Gradle Wrapper?
  * Running the Wrapper task
    $ **gradle wrapper**
    > Task:wrapper
    BUILD SUCCESFUL in 0s
    1 actionable task: 1 executed  
 
* Use the Gradle init command to create the wrapper
  * If we don't have the **gradle** directory and the **gradlew.sh** and **gradlew.bat** files, to generate them we run the following command:
    **gradle wrapper --gradle-version** <version_number>
    #####Ej:
    ```
    gradle wrapper --gradle-version 3.5 
    ```
### Gradle Tasks
* They are functions performed by Gradle
* Consist of one or more actions
* What you can tell Gradle to do

To see which are the Gradle task availables run the following command in the terminal:
``` 
gradle tasks
```

### Gradle Vew Tool
* What is the Gradle Vew Tool?
  * Is an alternate way of running Gradle tasks
  * Has its own GUI
  * Is useful when you are first learning Gradle
  
### Create new Gradle Tasks
* Creating simple tasks using Groovy
  * In the **build.gradle** file:
    ``` 
    task showDate {
        doLast{
           println "Current Date: " + new Date() 
        }
    }
    ```
  * To run the task open the terminal and:
    ``` 
    gradle showDate
    ```  
* Assigning task dependencies
  * Let's say that the **showDate** task depends on other tasks. In that case, we us **dependsOn**:
    ``` 
    task showDate {
        dependsOn build
        doLast{
           println "Current Date: " + new Date() 
        }
    }
    ```  
    * We can assign a **group** and a **description** to our custom task:
        ``` 
        task showDate {
            dependsOn build
            group = 'my tasks'
            description = 'Show current date'
            doLast{
               println "Current Date: " + new Date() 
            }
        }
        ```    
* Integrating with the Terminal tool and Gradle View