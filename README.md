# Ghidra
![immagine](https://user-images.githubusercontent.com/56889513/117017483-ea211880-acf3-11eb-96c7-a573d0985302.png)

Ghidra Script Development.
In order to write a script:
Ghidra script must be written in Java.
Your script class must extend ghidra.app.script.GhidraScript.
You must implement the run() method. This is where you insert your script-specific code.
You should create a description comment at the top of the file. Each description line should start with "//".


When you create a new script using the script manager, you will automatically receive a source code stub (as shown below).
  //TODO write a description for this script

        public class NewScript extends GhidraScript {

                public void run() throws Exception {
                        //TODO Add User Code Here
                }
        }
 
Ghidra Script State
All scripts, when run, will be handed the current state in the form of class instance variable. These variables are:

currentProgram: the active program
currentAddress: the address of the current cursor location in the tool
currentLocation: the program location of the current cursor location in the tool, or null if no program location exists
currentSelection: the current selection in the tool, or null if no selection exists
currentHighlight: the current highlight in the tool, or null if no highlight exists
Hello World Example
This example, when run, will simply print "Hello World" into the Ghidra console.
        public class HelloWorldScript extends GhidraScript {
                public void run() throws Exception {
                        println("Hello World!");
                }
        }
 
All scripts, when run, will be handed the current state and are automatically run in a separate thread.
