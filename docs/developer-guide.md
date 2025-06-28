# EnneadTab Developer Guide

Welcome to the EnneadTab Developer Guide! This guide is for developers who want to contribute to the EnneadTab project.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Project Structure](#project-structure)
3. [Development Environment](#development-environment)
4. [Contributing Guidelines](#contributing-guidelines)
5. [API Documentation](#api-documentation)
6. [Testing](#testing)
7. [Building and Deployment](#building-and-deployment)

## Getting Started

### Prerequisites

To contribute to EnneadTab, you'll need:

- **Visual Studio 2019/2022** or **Visual Studio Code**
- **.NET Framework 4.7.2** or later
- **Git** for version control
- **One or more supported software**:
  - Autodesk Revit 2020+ (with SDK)
  - Rhino 7+ (with SDK)
  - AutoCAD 2020+ (with ObjectARX)
  - Adobe InDesign CC 2020+ (with SDK)

### Setting Up Your Development Environment

1. **Clone the Repository**
   ```bash
   git clone https://github.com/enneadtab/EnneadTab-OS.git
   cd EnneadTab-OS
   ```

2. **Install Dependencies**
   - Install required NuGet packages
   - Set up software SDKs
   - Configure development tools

3. **Build the Project**
   ```bash
   dotnet build
   ```

## Project Structure

```
EnneadTab-OS/
├── Apps/                    # Application-specific code
│   ├── _revit/             # Revit integration
│   ├── _rhino/             # Rhino integration
│   ├── _cad/               # AutoCAD integration
│   └── _indesign/          # InDesign integration
├── lib/                     # Shared libraries
│   └── EnneadTab/          # Core EnneadTab library
├── back_end/               # Backend services
├── DarkSide/               # Build and deployment tools
└── docs/                   # Documentation
```

### Key Components

#### Core Library (`lib/EnneadTab/`)
- **Base Classes**: Common functionality shared across all applications
- **Utilities**: Helper functions and tools
- **Interfaces**: Contracts for different software integrations

#### Application-Specific Code
- **Revit**: C# add-ins and external commands
- **Rhino**: Python scripts and C# plugins
- **AutoCAD**: LISP routines and .NET add-ins
- **InDesign**: JavaScript and AppleScript automation

## Development Environment

### Visual Studio Setup

1. **Open the Solution**
   - Open `EnneadTab-OS.sln` in Visual Studio
   - Restore NuGet packages
   - Set startup project

2. **Configure Debugging**
   - Set debug target to appropriate software
   - Configure debug parameters
   - Set up breakpoints

### Visual Studio Code Setup

1. **Install Extensions**
   - C# extension
   - Python extension (for Rhino scripts)
   - Git integration

2. **Configure Tasks**
   - Build tasks
   - Debug configurations
   - Test runners

### Software SDK Setup

#### Revit SDK
1. Download Revit SDK from Autodesk
2. Add SDK references to project
3. Configure build paths

#### Rhino SDK
1. Install Rhino SDK
2. Add SDK references
3. Configure Python environment

#### AutoCAD ObjectARX
1. Download ObjectARX SDK
2. Add SDK references
3. Configure build settings

## Contributing Guidelines

### Code Style

- **C#**: Follow Microsoft C# coding conventions
- **Python**: Follow PEP 8 style guide
- **JavaScript**: Use ES6+ features and consistent formatting
- **LISP**: Follow AutoCAD LISP conventions

### Commit Guidelines

Use conventional commit messages:

```
type(scope): description

[optional body]

[optional footer]
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes
- `refactor`: Code refactoring
- `test`: Test additions/changes
- `chore`: Build/tooling changes

### Pull Request Process

1. **Create Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make Changes**
   - Write code following style guidelines
   - Add tests for new functionality
   - Update documentation

3. **Test Your Changes**
   - Run unit tests
   - Test in target software
   - Verify no regressions

4. **Submit Pull Request**
   - Provide clear description
   - Include screenshots if UI changes
   - Reference related issues

### Code Review Process

- All PRs require review
- Address review comments
- Ensure CI/CD passes
- Update documentation as needed

## API Documentation

### Core API

#### EnneadTab.Core
```csharp
namespace EnneadTab.Core
{
    public class EnneadTabManager
    {
        public static void Initialize();
        public static void Shutdown();
        public static bool IsInitialized { get; }
    }
}
```

#### EnneadTab.Utilities
```csharp
namespace EnneadTab.Utilities
{
    public class FileUtils
    {
        public static string GetApplicationPath();
        public static bool FileExists(string path);
        public static void CreateDirectory(string path);
    }
}
```

### Software-Specific APIs

#### Revit API
```csharp
namespace EnneadTab.Revit
{
    public class RevitManager
    {
        public static Document ActiveDocument { get; }
        public static void ExecuteCommand(string commandName);
    }
}
```

#### Rhino API
```python
import rhinoscriptsyntax as rs
import EnneadTab.Rhino as et

def main():
    # Your Rhino script code here
    pass
```

## Testing

### Unit Tests

- Use MSTest or NUnit for C# tests
- Use pytest for Python tests
- Maintain good test coverage

### Integration Tests

- Test with actual software installations
- Verify functionality across different versions
- Test error conditions and edge cases

### Manual Testing

- Test in target software environments
- Verify UI/UX behavior
- Check performance impact

### Test Structure

```
Tests/
├── Unit/              # Unit tests
├── Integration/       # Integration tests
├── Performance/       # Performance tests
└── Manual/           # Manual test scripts
```

## Building and Deployment

### Build Process

1. **Clean Build**
   ```bash
   dotnet clean
   dotnet build --configuration Release
   ```

2. **Run Tests**
   ```bash
   dotnet test
   ```

3. **Create Installer**
   ```bash
   # Use DarkSide build tools
   python DarkSide/exes/ExeMaker.py
   ```

### Deployment

1. **Create Release**
   - Tag the release
   - Generate release notes
   - Upload installers

2. **Update Documentation**
   - Update version numbers
   - Add release notes
   - Update download links

### Continuous Integration

- GitHub Actions for automated builds
- Automated testing on multiple platforms
- Code quality checks
- Security scanning

## Debugging

### Common Issues

1. **Build Errors**
   - Check SDK installations
   - Verify NuGet packages
   - Check target framework

2. **Runtime Errors**
   - Check software versions
   - Verify file paths
   - Check permissions

3. **Performance Issues**
   - Profile code execution
   - Check memory usage
   - Optimize algorithms

### Debug Tools

- Visual Studio debugger
- Rhino Python debugger
- AutoCAD command line debugging
- Logging and tracing

## Performance Guidelines

### Best Practices

1. **Memory Management**
   - Dispose of objects properly
   - Avoid memory leaks
   - Use appropriate data structures

2. **Algorithm Optimization**
   - Use efficient algorithms
   - Minimize computational complexity
   - Cache results when appropriate

3. **UI Responsiveness**
   - Use async/await for long operations
   - Show progress indicators
   - Don't block the UI thread

## Security Considerations

### Code Security

1. **Input Validation**
   - Validate all user inputs
   - Sanitize file paths
   - Check file permissions

2. **Error Handling**
   - Don't expose sensitive information
   - Log errors appropriately
   - Handle exceptions gracefully

3. **Dependencies**
   - Keep dependencies updated
   - Scan for vulnerabilities
   - Use trusted sources

## Documentation Standards

### Code Documentation

- Use XML documentation for C#
- Use docstrings for Python
- Include examples and usage

### API Documentation

- Document all public APIs
- Include parameter descriptions
- Provide usage examples

### User Documentation

- Keep documentation up to date
- Include screenshots and videos
- Provide troubleshooting guides

---

For more information, see the [API Reference](api-reference.md) and [User Guide](user-guide.md). 