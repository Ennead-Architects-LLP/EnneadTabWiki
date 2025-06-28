# EnneadTab User Guide

Welcome to the EnneadTab User Guide! This comprehensive guide will help you get started with EnneadTab and make the most of its powerful features.

## Table of Contents

1. [Installation](#installation)
2. [Getting Started](#getting-started)
3. [Revit Integration](#revit-integration)
4. [Rhino Integration](#rhino-integration)
5. [AutoCAD Integration](#autocad-integration)
6. [InDesign Integration](#indesign-integration)
7. [Troubleshooting](#troubleshooting)

## Installation

### Prerequisites

Before installing EnneadTab, ensure you have:

- Windows 10/11 (64-bit)
- .NET Framework 4.7.2 or later
- One or more of the following software:
  - Autodesk Revit 2020 or later
  - Rhino 7 or later
  - AutoCAD 2020 or later
  - Adobe InDesign CC 2020 or later

### Installing for Revit

1. **Download the Installer**
   - Go to the [releases page](https://github.com/enneadtab/EnneadTab-OS/releases)
   - Download the latest `EnneadTab_For_Revit_Installer.exe`

2. **Run the Installer**
   - Close all instances of Revit
   - Run the installer as Administrator
   - Follow the installation wizard

3. **Verify Installation**
   - Open Revit
   - Look for the "EnneadTab" ribbon tab
   - Check that all tools are available

### Installing for Rhino

1. **Package Manager Method (Recommended)**
   - Open Rhino Package Manager
   - Search for "EnneadTab"
   - Click Install

2. **Manual Installation**
   - Download the `.rui` file from releases
   - Place it in your Rhino UI folder
   - Restart Rhino

### Installing for AutoCAD

1. **Load LISP Files**
   - Download the LISP files from releases
   - In AutoCAD, type `APPLOAD`
   - Browse and load the `.lsp` files

2. **Set Up Commands**
   - Add custom commands to your AutoCAD profile
   - Create custom toolbars if needed

### Installing for InDesign

1. **Script Installation**
   - Download the InDesign scripts
   - Place them in your InDesign Scripts folder
   - Restart InDesign

## Getting Started

### First Launch

After installation, you'll see new tabs and tools in your software:

- **Revit**: New ribbon tab with EnneadTab tools
- **Rhino**: New toolbar with EnneadTab commands
- **AutoCAD**: New commands available via command line
- **InDesign**: New scripts in the Scripts menu

### Basic Workflow

1. **Open your project** in the respective software
2. **Navigate to EnneadTab tools** in the interface
3. **Select the tool** you want to use
4. **Follow the prompts** and complete the operation
5. **Save your work** as usual

## Revit Integration

### Available Tools

#### Family Management
- **Family Creator**: Create parametric families quickly
- **Family Editor**: Enhanced editing tools
- **Family Browser**: Improved family browsing

#### Project Tools
- **Project Setup**: Automated project initialization
- **View Management**: Batch view creation and management
- **Sheet Management**: Automated sheet creation

#### Automation
- **Batch Operations**: Process multiple elements
- **Data Extraction**: Export project data
- **Quality Control**: Check project standards

### Common Workflows

#### Creating a New Family
1. Open Family Editor
2. Use EnneadTab Family Creator
3. Select family template
4. Add parameters and geometry
5. Test family behavior
6. Save and load into project

#### Setting Up a New Project
1. Use Project Setup tool
2. Configure project settings
3. Create standard views
4. Set up sheets
5. Apply project templates

## Rhino Integration

### Available Tools

#### Block Management
- **Block Creator**: Create blocks from geometry
- **Block Editor**: Edit existing blocks
- **Block Browser**: Browse and manage blocks

#### Modeling Tools
- **Surface Tools**: Advanced surface operations
- **Curve Tools**: Enhanced curve manipulation
- **Geometry Tools**: Specialized geometry operations

#### Visualization
- **Render Tools**: Quick rendering setup
- **Material Tools**: Material management
- **Lighting Tools**: Lighting setup automation

### Common Workflows

#### Working with Blocks
1. Select geometry to block
2. Use Block Creator tool
3. Define block properties
4. Insert blocks as needed
5. Edit blocks with Block Editor

#### Surface Modeling
1. Create base geometry
2. Use Surface Tools for refinement
3. Apply materials and textures
4. Set up lighting and rendering
5. Export or present results

## AutoCAD Integration

### Available Commands

#### Drawing Tools
- `ENNEAD-LINE`: Enhanced line creation
- `ENNEAD-CIRCLE`: Advanced circle tools
- `ENNEAD-TEXT`: Improved text handling

#### Management Tools
- `ENNEAD-LAYER`: Layer management
- `ENNEAD-STYLE`: Style management
- `ENNEAD-BLOCK`: Block operations

#### Automation
- `ENNEAD-BATCH`: Batch processing
- `ENNEAD-EXPORT`: Data export
- `ENNEAD-IMPORT`: Data import

### Common Workflows

#### Layer Management
1. Use `ENNEAD-LAYER` command
2. Select layer operations
3. Apply to selected objects
4. Save layer states

#### Batch Processing
1. Use `ENNEAD-BATCH` command
2. Select files to process
3. Choose operations
4. Monitor progress
5. Review results

## InDesign Integration

### Available Scripts

#### Document Management
- **Document Setup**: Automated document creation
- **Page Management**: Batch page operations
- **Master Page Tools**: Master page management

#### Content Tools
- **Text Processing**: Advanced text operations
- **Image Tools**: Image handling and optimization
- **Layout Tools**: Layout automation

#### Export Tools
- **PDF Export**: Automated PDF creation
- **Print Preparation**: Print-ready setup
- **Digital Publishing**: Digital output preparation

### Common Workflows

#### Document Setup
1. Run Document Setup script
2. Configure document settings
3. Create master pages
4. Set up styles and templates
5. Begin content creation

#### PDF Export
1. Prepare document for export
2. Run PDF Export script
3. Configure export settings
4. Monitor export progress
5. Verify output quality

## Troubleshooting

### Common Issues

#### Installation Problems
- **Permission Errors**: Run installer as Administrator
- **Missing Dependencies**: Install required .NET Framework
- **Software Not Detected**: Ensure software is properly installed

#### Runtime Issues
- **Tools Not Appearing**: Restart the application
- **Commands Not Working**: Check command line for errors
- **Performance Issues**: Close other applications

#### Compatibility Issues
- **Version Mismatch**: Update to latest EnneadTab version
- **Software Updates**: Check compatibility with new software versions
- **OS Updates**: Ensure OS compatibility

### Getting Help

1. **Check Documentation**: Review this guide and other docs
2. **Search Issues**: Look for similar issues on GitHub
3. **Report Bugs**: Create a new issue with detailed information
4. **Community Support**: Ask questions in discussions

### Support Information

- **GitHub Issues**: [Report bugs here](https://github.com/enneadtab/EnneadTab-OS/issues)
- **Discussions**: [Community support](https://github.com/enneadtab/EnneadTab-OS/discussions)
- **Documentation**: [Full documentation](https://enneadtab.github.io/EnneadTabWiki/)

---

For more detailed information about specific features, please refer to the [API Reference](api-reference.md) and [FAQ](faq.md). 