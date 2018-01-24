The GitHub is at https://github.com/BobbyRIT/design-project-team-1

The JAR must be in the same folder as the data directory, but not inside it.
To open the GUI you can use the start-gui.sh script on macOS/Linux or start-gui.cmd on Windows.

The TUI can be launched using the start-tui.sh or start-tui.cmd scripts on macOS/Linux and Windows respectively.

This project uses Google's GSON library for JSON serialization/deserialization. In order to build this project you must
manually add the library to Intellij:
1. File > Project structure > Libraries > + button > From Maven
2. Enter com.google.code.gson:gson:2.8.2 into the dialog and click the magnifying glass
3. Choose the only option that appears in the dropdown, tick the JavaDocs box, and click ok
The project will now build.

IntelliJ inserts the wrong MANIFEST.MF into the JAR when you use it to build the JAR (it seems to use the one from gson for some reason)
As a result a JAR you built yourself will not run, however we pathced the JAR in the zip to have the correct manifest

Originally we were going to use a Maven pom.xml to hold the dependencies, however this reset the language level of the
project back to Java 1.5 every time IntelliJ reread it, and we were unable to figure out how to fix that.