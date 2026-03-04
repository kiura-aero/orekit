# Orekit Orbit Simulation – Overview of Codes
Scroll to the bottom for Prerequisites.

## `firstprogram.java`
- Initializes **Orekit** by loading the `orekit-data` directory.
- Uses the **new DataContext API** (Orekit 11+).
- Creates an `AbsoluteDate` to confirm time system is working.
- Prints confirmation that Orekit data loaded successfully.
- Provides a basic template for all future Orekit-based simulations.

## `SimpleSimulation.java`
- Create a **Maven Java project** in Eclipse using **Orekit**.
- Add **orekit-data** and properly load it at runtime.
- Implement a **simple orbit propagator** that outputs position & velocity over time.
- Add a **minimal HTTP endpoint** that serves the satellite’s current state as JSON (for Open MCT polling).
- Include troubleshooting notes for **Hipparchus**, classpath issues, and orekit-data configuration.

## `mathu.java`
- Create a file > new > java
    - Name the project
    - Do not "create module info/java"
- Add Orekit & Hipparchus `.jar`
    - Click the new project > build project > configure Build Path
    - Libraries > Module Path > Add External jars > Add all Orekit & Hipparchus files
- Orekit data downloaded
    - remove `main` from folder name
- Create output folder
- Create package and Java class
    - Click `src` > new > package > "name"
    - Clic package "name" > new > class > "name"

> Paste the following into the dependencies section of the `pom.xml` file of the project. 
```java
<dependencies>
    <dependency>
        <groupId>org.orekit</groupId>
        <artifactId>orekit</artifactId>
        <version>12.0.2</version>
    </dependency>

    <dependency>
        <groupId>org.hipparchus</groupId>
        <artifactId>hipparchus-core</artifactId>
        <version>3.1</version>
    </dependency>

    <dependency>
        <groupId>org.hipparchus</groupId>
        <artifactId>hipparchus-geometry</artifactId>
        <version>3.1</version>
    </dependency>

    <dependency>
        <groupId>org.hipparchus</groupId>
        <artifactId>hipparchus-ode</artifactId>
        <version>3.1</version>
    </dependency>
</dependencies>
```

## Prerequisites

### Java
- **JDK 11 or 17** installed  
- `JAVA_HOME` correctly set  

### IDE
- **Eclipse** with Maven (M2E)  
- **VS Code** with Java/Maven extensions
  or
- Something similar 

### Orekit Data
- Download the official **orekit-data** bundle  
  (contains frames, Earth models, time scales, etc).  
- Unzip it somewhere accessible, for example:
  - `C:\orekit-data` (Windows)
  - `~/orekit-data` (macOS/Linux)

You will point Orekit to this directory during initialization.
***
