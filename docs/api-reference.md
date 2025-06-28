# EnneadTab API Reference

This document provides a comprehensive reference for the EnneadTab API.

## Table of Contents

1. [Core API](#core-api)
2. [Revit API](#revit-api)
3. [Rhino API](#rhino-api)
4. [AutoCAD API](#autocad-api)
5. [InDesign API](#indesign-api)
6. [Utilities](#utilities)

## Core API

### EnneadTabManager

The main entry point for EnneadTab functionality.

```csharp
namespace EnneadTab.Core
{
    public class EnneadTabManager
    {
        // Properties
        public static bool IsInitialized { get; }
        public static string Version { get; }
        public static string ApplicationPath { get; }
        
        // Methods
        public static void Initialize();
        public static void Shutdown();
        public static void Reload();
        public static bool IsSoftwareSupported(string softwareName);
    }
}
```

### Configuration

Manages EnneadTab configuration settings.

```csharp
namespace EnneadTab.Core
{
    public class Configuration
    {
        // Properties
        public static string ConfigPath { get; }
        public static bool DebugMode { get; set; }
        public static bool LoggingEnabled { get; set; }
        
        // Methods
        public static T GetSetting<T>(string key, T defaultValue = default(T));
        public static void SetSetting<T>(string key, T value);
        public static void SaveConfiguration();
        public static void LoadConfiguration();
    }
}
```

### Logger

Provides logging functionality.

```csharp
namespace EnneadTab.Core
{
    public class Logger
    {
        // Methods
        public static void Log(string message, LogLevel level = LogLevel.Info);
        public static void LogError(string message, Exception ex = null);
        public static void LogWarning(string message);
        public static void LogInfo(string message);
        public static void LogDebug(string message);
    }
    
    public enum LogLevel
    {
        Debug,
        Info,
        Warning,
        Error
    }
}
```

## Revit API

### RevitManager

Main interface for Revit operations.

```csharp
namespace EnneadTab.Revit
{
    public class RevitManager
    {
        // Properties
        public static Document ActiveDocument { get; }
        public static Application Application { get; }
        public static bool IsRevitRunning { get; }
        
        // Methods
        public static void ExecuteCommand(string commandName);
        public static Element GetElement(ElementId elementId);
        public static List<Element> GetElementsOfType<T>() where T : Element;
        public static void RefreshView();
    }
}
```

### FamilyManager

Manages Revit family operations.

```csharp
namespace EnneadTab.Revit
{
    public class FamilyManager
    {
        // Methods
        public static Family CreateFamily(string templatePath, string familyPath);
        public static void LoadFamily(string familyPath);
        public static void SaveFamily(Family family, string path);
        public static List<Family> GetLoadedFamilies();
        public static void EditFamily(Family family);
    }
}
```

### ProjectManager

Manages Revit project operations.

```csharp
namespace EnneadTab.Revit
{
    public class ProjectManager
    {
        // Methods
        public static void CreateView(ViewType viewType, string viewName);
        public static void CreateSheet(string sheetName, string titleBlockName);
        public static void ExportToDWG(string filePath);
        public static void ExportToPDF(string filePath);
        public static List<Element> GetProjectInfo();
    }
}
```

## Rhino API

### RhinoManager

Main interface for Rhino operations.

```python
import rhinoscriptsyntax as rs
import EnneadTab.Rhino as et

class RhinoManager:
    """Main interface for Rhino operations"""
    
    @staticmethod
    def get_active_document():
        """Get the active Rhino document"""
        return rs.doc
    
    @staticmethod
    def execute_command(command_name):
        """Execute a Rhino command"""
        rs.Command(command_name)
    
    @staticmethod
    def get_objects_by_type(object_type):
        """Get objects of a specific type"""
        return rs.GetObjects("Select objects", object_type)
```

### BlockManager

Manages Rhino block operations.

```python
class BlockManager:
    """Manages Rhino block operations"""
    
    @staticmethod
    def create_block(geometry, name, insertion_point):
        """Create a block from geometry"""
        return rs.AddBlock(geometry, insertion_point, name)
    
    @staticmethod
    def insert_block(block_name, insertion_point):
        """Insert a block instance"""
        return rs.InsertBlock(block_name, insertion_point)
    
    @staticmethod
    def explode_block(block_instance):
        """Explode a block instance"""
        return rs.ExplodeBlockInstance(block_instance)
```

### SurfaceManager

Manages Rhino surface operations.

```python
class SurfaceManager:
    """Manages Rhino surface operations"""
    
    @staticmethod
    def create_surface_from_curves(curves):
        """Create a surface from curves"""
        return rs.AddSrfPt(curves)
    
    @staticmethod
    def offset_surface(surface, distance):
        """Offset a surface"""
        return rs.OffsetSurface(surface, distance)
    
    @staticmethod
    def join_surfaces(surfaces):
        """Join multiple surfaces"""
        return rs.JoinSurfaces(surfaces)
```

## AutoCAD API

### AutoCADManager

Main interface for AutoCAD operations.

```csharp
namespace EnneadTab.AutoCAD
{
    public class AutoCADManager
    {
        // Properties
        public static Document ActiveDocument { get; }
        public static Database Database { get; }
        public static bool IsAutoCADRunning { get; }
        
        // Methods
        public static void ExecuteCommand(string command);
        public static ObjectId CreateLine(Point3d start, Point3d end);
        public static ObjectId CreateCircle(Point3d center, double radius);
        public static void SetLayer(string layerName);
    }
}
```

### LayerManager

Manages AutoCAD layer operations.

```csharp
namespace EnneadTab.AutoCAD
{
    public class LayerManager
    {
        // Methods
        public static void CreateLayer(string layerName, short colorIndex = 7);
        public static void DeleteLayer(string layerName);
        public static void SetLayerColor(string layerName, short colorIndex);
        public static void SetLayerLinetype(string layerName, string linetypeName);
        public static List<string> GetLayerNames();
    }
}
```

### DrawingManager

Manages AutoCAD drawing operations.

```csharp
namespace EnneadTab.AutoCAD
{
    public class DrawingManager
    {
        // Methods
        public static void SaveDrawing(string filePath);
        public static void OpenDrawing(string filePath);
        public static void ExportToPDF(string filePath);
        public static void PlotDrawing(string plotterName, string paperSize);
    }
}
```

## InDesign API

### InDesignManager

Main interface for InDesign operations.

```javascript
class InDesignManager {
    /**
     * Get the active InDesign document
     */
    static getActiveDocument() {
        return app.activeDocument;
    }
    
    /**
     * Create a new document
     */
    static createDocument(width, height) {
        return app.documents.add(false, width, height);
    }
    
    /**
     * Execute a script
     */
    static executeScript(scriptPath) {
        return app.doScript(scriptPath);
    }
}
```

### DocumentManager

Manages InDesign document operations.

```javascript
class DocumentManager {
    /**
     * Create a new page
     */
    static createPage(document, pageWidth, pageHeight) {
        return document.pages.add();
    }
    
    /**
     * Add text frame
     */
    static addTextFrame(document, bounds, contents) {
        var textFrame = document.textFrames.add();
        textFrame.geometricBounds = bounds;
        textFrame.contents = contents;
        return textFrame;
    }
    
    /**
     * Export to PDF
     */
    static exportToPDF(document, filePath) {
        document.exportFile(ExportFormat.PDF_TYPE, new File(filePath));
    }
}
```

## Utilities

### FileUtils

File system utilities.

```csharp
namespace EnneadTab.Utilities
{
    public class FileUtils
    {
        // Methods
        public static string GetApplicationPath();
        public static bool FileExists(string path);
        public static void CreateDirectory(string path);
        public static void CopyFile(string source, string destination);
        public static void DeleteFile(string path);
        public static List<string> GetFiles(string directory, string pattern = "*.*");
        public static string GetFileName(string path);
        public static string GetDirectoryName(string path);
        public static string GetExtension(string path);
    }
}
```

### StringUtils

String manipulation utilities.

```csharp
namespace EnneadTab.Utilities
{
    public class StringUtils
    {
        // Methods
        public static bool IsNullOrEmpty(string value);
        public static string ToTitleCase(string value);
        public static string RemoveSpecialCharacters(string value);
        public static string GenerateUniqueName(string baseName);
        public static List<string> SplitAndClean(string value, char separator);
    }
}
```

### MathUtils

Mathematical utilities.

```csharp
namespace EnneadTab.Utilities
{
    public class MathUtils
    {
        // Methods
        public static double ConvertToRadians(double degrees);
        public static double ConvertToDegrees(double radians);
        public static double RoundToPrecision(double value, int precision);
        public static bool IsWithinTolerance(double value1, double value2, double tolerance);
        public static double GetDistance(Point3d point1, Point3d point2);
    }
}
```

### ValidationUtils

Input validation utilities.

```csharp
namespace EnneadTab.Utilities
{
    public class ValidationUtils
    {
        // Methods
        public static bool IsValidFilePath(string path);
        public static bool IsValidEmail(string email);
        public static bool IsValidNumber(string value);
        public static bool IsValidDate(string date);
        public static string SanitizeFileName(string fileName);
    }
}
```

## Error Handling

### EnneadTabException

Base exception class for EnneadTab.

```csharp
namespace EnneadTab.Core
{
    public class EnneadTabException : Exception
    {
        public string ErrorCode { get; }
        public string SoftwareContext { get; }
        
        public EnneadTabException(string message, string errorCode = null, string softwareContext = null);
        public EnneadTabException(string message, Exception innerException, string errorCode = null, string softwareContext = null);
    }
}
```

### ErrorCodes

Common error codes used throughout EnneadTab.

```csharp
namespace EnneadTab.Core
{
    public static class ErrorCodes
    {
        public const string SOFTWARE_NOT_FOUND = "SOFTWARE_NOT_FOUND";
        public const string INVALID_INPUT = "INVALID_INPUT";
        public const string FILE_NOT_FOUND = "FILE_NOT_FOUND";
        public const string PERMISSION_DENIED = "PERMISSION_DENIED";
        public const string OPERATION_FAILED = "OPERATION_FAILED";
    }
}
```

## Events

### EnneadTabEvents

Events that can be subscribed to.

```csharp
namespace EnneadTab.Core
{
    public static class EnneadTabEvents
    {
        public static event EventHandler<EnneadTabEventArgs> Initialized;
        public static event EventHandler<EnneadTabEventArgs> Shutdown;
        public static event EventHandler<ErrorEventArgs> ErrorOccurred;
        public static event EventHandler<ProgressEventArgs> ProgressChanged;
    }
    
    public class EnneadTabEventArgs : EventArgs
    {
        public string Message { get; set; }
        public DateTime Timestamp { get; set; }
    }
    
    public class ProgressEventArgs : EventArgs
    {
        public int Progress { get; set; }
        public string Status { get; set; }
    }
}
```

---

For more detailed information about specific features, see the [Developer Guide](developer-guide.md) and [User Guide](user-guide.md). 