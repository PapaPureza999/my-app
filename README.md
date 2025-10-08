
# my-app

A simple Maven quickstart Java project.
Below are the exact steps I used (copy & paste commands) so anyone can reproduce the project locally.

---

## Check maven installation

```bash
mvn -v
```

Expected sample output (your environment):

```
Apache Maven 3.9.11
Maven home: C:\My Stuff\CODE MASTER\apache-maven-3.9.11
Java version: 24.0.2, vendor: Oracle Corporation
OS name: "windows 11"
```

If `mvn` is not recognized: make sure Maven's `bin` folder is added to your PATH (for example `%MAVEN_HOME%\bin`) and reopen the terminal.

---

## go into the directory where you want tot make the project

Change to the folder where you want the project to live. Example on Windows (Command Prompt or Git Bash):

```bash
cd "C:\My Stuff\CODE MASTER\CODING PROJECTS"
```

---

## (Generate the project)

Run the Maven archetype generate command to create the quickstart project:

```bash
mvn archetype:generate \
  -DgroupId=com.mycompany.app \
  -DartifactId=my-app \
  -DarchetypeArtifactId=maven-archetype-quickstart \
  -DarchetypeVersion=1.5 \
  -DinteractiveMode=false
```

This will create the folder `my-app` with the standard Maven structure (`pom.xml`, `src/main/java`, `src/test/java`, etc.).

---

## Go into the project folder

```bash
cd "my-app"
```

List files to confirm:

```bash
dir        # on Windows
# or
ls -la     # on Git Bash / Linux / macOS
```

You should see `pom.xml` and the `src` directory.

---

## Run mvn package

Build, run tests, and create the JAR:

```bash
mvn package
```

Expected outcome:

```
[INFO] BUILD SUCCESS
```

After success, the packaged JAR will be in:

```
target/my-app-1.0-SNAPSHOT.jar
```

---

## Test the compiled and packaged jar with the command

Run the compiled JAR using the fully-qualified main class:

```bash
java -cp target\my-app-1.0-SNAPSHOT.jar com.mycompany.app.App
```

Expected output:

```
Hello World!
```

---

## Notes / troubleshooting

* If `mvn archetype:generate` times out while downloading, re-run the command — Maven will resume downloads.
* If your shell shows warnings about `sun.misc.Unsafe`, those are warnings from libraries and do not block the build.
* If `java` or `mvn` commands are not found, ensure the JDK and Maven `bin` paths are in your system `PATH`.
* On Windows, paths containing spaces are fine when quoted (e.g., `cd "C:\My Stuff\CODE MASTER\..."`).

---

## Project structure

```
my-app
├── pom.xml
└── src
    ├── main
    │   └── java
    │       └── com.mycompany.app.App.java
    └── test
        └── java
            └── com.mycompany.app.AppTest.java
```

