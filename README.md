# Atra AntiCheat - Build Guide

## Requirements

- **Java Development Kit (JDK)**: 17 or newer
- **Gradle**: 8.8 or newer (included via Gradle Wrapper)
- **Git**: For cloning the source code

## Downloading Source Code

```bash
git clone https://github.com/yourusername/atra-anticheat.git
cd atra-anticheat
```

## Build Process

### Windows

```cmd
gradlew.bat clean build
```

### Linux/Mac

```bash
./gradlew clean build
```

## Build Commands

### Full build (with tests and JAR creation)
```bash
./gradlew build
```

### Compile only (skip tests)
```bash
./gradlew build -x test
```

### Create JAR file
```bash
./gradlew jar
```

### Clean project
```bash
./gradlew clean
```

### Refresh dependencies
```bash
./gradlew build --refresh-dependencies
```

## Build Output

After a successful build, the JAR file can be found at:
```
build/libs/Atra-1.0.0.jar
```

## Setting Up Development Environment

### IntelliJ IDEA

1. Open IntelliJ IDEA
2. File → Open → Select the project folder
3. IntelliJ will automatically recognize the Gradle project
4. Wait for indexing and dependency downloads to complete

### Eclipse

1. Open Eclipse
2. File → Import → Gradle → Existing Gradle Project
3. Select the project folder
4. Finish

### Visual Studio Code

1. Install the "Java Extension Pack"
2. Open the project folder
3. VS Code will automatically recognize the Gradle project

## Dependencies

The project uses the following main dependencies:

- **Spigot API**: 1.21.3-R0.1-SNAPSHOT
- **ProtocolLib**: 5.3.0
- **Adventure API**: 4.17.0
- **HikariCP**: 5.1.0 (database connection pooling)
- **H2 Database**: 2.2.224

All dependencies are automatically downloaded during the build process.

## Common Issues

### "Permission denied" error on Linux/Mac

```bash
chmod +x gradlew
./gradlew build
```

### Gradle Daemon issues

```bash
./gradlew --stop
./gradlew clean build --no-daemon
```

### Memory issues

Edit the `gradle.properties` file:
```properties
org.gradle.jvmargs=-Xmx2048m -XX:MaxMetaspaceSize=512m
```

### Dependency download issues

```bash
./gradlew build --refresh-dependencies --no-daemon
```

## Testing

### Run all tests
```bash
./gradlew test
```

### View test report
Test report can be found at: `build/reports/tests/test/index.html`

## Changing Version

You can modify the version number in the `build.gradle` file:

```gradle
version = '1.0.0'
```

## Testing on Spigot Server

1. Build the project
2. Copy the JAR file to your server's `plugins` folder
3. Start the server
4. Check the console to verify the plugin loaded successfully

## Contributing to the Project

1. Fork the repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Support

If you have issues with building:
- Open an Issue on GitHub
- Check the [Wiki](https://github.com/yourusername/atra-anticheat/wiki) page
- Join our Discord server

## Useful Commands

```bash
# Project information
./gradlew projects

# List available tasks
./gradlew tasks

# List dependencies
./gradlew dependencies

# Clean build cache
./gradlew clean cleanBuildCache
```
