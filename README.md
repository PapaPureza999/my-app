

# my-app

A simple **Maven Quickstart Java Project**, created and built entirely from the command line.

This guide explains step-by-step how this project was made, what each command does, and how to verify your setup.

---

## ✅ Check Maven Installation

Before creating the project, ensure Maven is properly installed and added to your system’s `PATH`.

```bash
mvn -v
```

**Example Output:**

```
Apache Maven 3.9.11
Maven home: C:\My Stuff\CODE MASTER\apache-maven-3.9.11
Java version: 24.0.2, vendor: Oracle Corporation
OS name: "windows 11"
```

If `mvn` is not recognized, ensure that the Maven `bin` folder is correctly added to your environment variables.

---

## 📁 Go into the Directory Where You Want to Make the Project

Navigate to the folder where you want to create your new project:

```bash
cd "C:\My Stuff\CODE MASTER\CODING PROJECTS"
```

---

## 🚀 Creating a Project

You need somewhere for your project to reside. Create a directory somewhere and start a shell in that directory.
On your command line, execute the following Maven goal:

```bash
mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.5 -DinteractiveMode=false
```

If you have just installed Maven, **it may take a while on the first run** because Maven is downloading the most recent artifacts (plugin jars and other files) into your local repository (`~/.m2/repository`).

You may also need to execute the command a couple of times before it succeeds.
This is because the remote server may time out before your downloads are complete.

---

### 📖 What These Parameters Mean

| Parameter                                          | Description                                                                                                                                                    |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-DgroupId=com.mycompany.app`                      | Defines the unique base name of the company or organization that created the project. Usually follows reverse domain convention (e.g., `com.example.project`). |
| `-DartifactId=my-app`                              | Defines the name of your project folder and generated artifact (the JAR file).                                                                                 |
| `-DarchetypeArtifactId=maven-archetype-quickstart` | Tells Maven to use the “Quickstart” archetype, which provides a simple structure for Java applications.                                                        |
| `-DarchetypeVersion=1.5`                           | Specifies the archetype version to use.                                                                                                                        |
| `-DinteractiveMode=false`                          | Prevents Maven from asking questions interactively — it will use your provided values automatically.                                                           |

---

## 📂 Go into the Project Folder

Once the command completes successfully, you’ll have a new folder named after your `artifactId`.

```bash
cd my-app
```

---

## 📁 Standard Project Structure

Your project will look like this:

```
my-app
|-- pom.xml
`-- src
    |-- main
    |   `-- java
    |       `-- com
    |           `-- mycompany
    |               `-- app
    |                   `-- App.java
    `-- test
        `-- java
            `-- com
                `-- mycompany
                    `-- app
                        `-- AppTest.java
```

* **`src/main/java`** — contains your main application source code
* **`src/test/java`** — contains your unit tests
* **`pom.xml`** — the **Project Object Model (POM)** file — Maven’s main configuration file

---

## 🧩 Understanding the POM File

The `pom.xml` file is the heart of every Maven project.
It contains all the configuration needed to build, package, and manage dependencies for your project.

You don’t need to know every detail yet, but in short:

* It defines your project’s metadata (`groupId`, `artifactId`, `version`)
* Lists all your dependencies (e.g., JUnit for testing)
* Controls your build lifecycle phases and plugins

---

## 🛠️ Build the Project

Now, build and package your Java application using:

```bash
mvn package
```

This command performs several steps automatically — Maven’s **build lifecycle phases**.
It validates your code, compiles it, runs tests, and finally packages it into a `.jar` file.

---

### 🔍 What Happens When You Run `mvn package`

When you run this command, Maven executes these phases (in order):

```
validate
generate-sources
process-sources
generate-resources
process-resources
compile
process-classes
test
package
```

After the build completes, you’ll see:

```
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```

The packaged `.jar` file will be created here:

```
target/my-app-1.0-SNAPSHOT.jar
```

---

## ▶️ Test the Compiled and Packaged JAR

Now test your compiled Java program by running the jar with:

```bash
java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App
```

**Expected Output:**

```
Hello World!
```

This confirms that your Maven project was created, built, and executed successfully.

---

## 💡 Notes & Tips

* If you see warnings about `sun.misc.Unsafe`, they can be safely ignored — they come from third-party dependencies.
* If Maven fails on the first run, re-run the command. It caches downloaded files, so it will be faster next time.
* Maven creates a `.m2/repository` folder in your user directory where all dependencies are stored.

---

## 🧠 Summary

| Step                          | Command                                                         | Purpose                                  |
| ----------------------------- | --------------------------------------------------------------- | ---------------------------------------- |
| 1️⃣ Check Maven version       | `mvn -v`                                                        | Verify Maven is installed and in PATH    |
| 2️⃣ Go to your working folder | `cd "C:\My Stuff\CODE MASTER\CODING PROJECTS"`                  | Choose where to create the project       |
| 3️⃣ Create the project        | `mvn archetype:generate ...`                                    | Generate standard Java project structure |
| 4️⃣ Go inside project folder  | `cd my-app`                                                     | Move into your new project directory     |
| 5️⃣ Build it                  | `mvn package`                                                   | Compile, test, and package the app       |
| 6️⃣ Run it                    | `java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App` | Run your program                         |

---

**Created by:** Pranjal
**GitHub:** [PapaPureza999](https://github.com/PapaPureza999)
**Tools used:** Java 24, Apache Maven 3.9.11, Windows 11

