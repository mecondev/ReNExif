# Project Structure with Docstring Snippets

**Docstring Coverage:** 23 / 30 files documented (76.7%)

📄 README.md
📁 assets/
    📄 favicon.ico
    📄 oncut-logo-2024-CIRCLE-(1100X1100)-dark-w-white-BG.png
    📄 oncut-logo-2024-CIRCLE-(1100X1100)-white-dark-BG.png
📄 config.py — *Module: config.py  Author: Michael Economou Date: 2025-05-01  This module defines global configuration constants and settings used throughout the oncutf application. It centralizes UI defaults, file filters, path definitions, and other shared parameters.  Intended to be imported wherever consistent application-wide settings are required.  Contains: - Default UI settings - File extension filters - Paths to resources and stylesheets*
📁 docs/
    📄 oncutf_module_docstrings.md
📄 logger_helper.py — *Returns a logger with the given name, or the module name if None.  Args: name (str): Optional name for the logger (defaults to caller's module)  Returns: logging.Logger: Configured logger instance*
📄 logger_setup.py — *logger_setup.py  This module provides the ConfigureLogger class for setting up logging in the application. It allows for flexible configuration of logging settings, including log levels, output destinations, and formatting. The logger is configured to log INFO and higher levels to the console, and ERROR and higher levels to a rotating file.  Classes: ConfigureLogger: Configures application-wide logging with console and file handlers.  Author: Michael Economou Date: 2025-05-01*
📁 logs/
    📄 oncutf.log
📄 main.py — *Module: main.py  Author: Michael Economou Date: 2025-05-01  This module serves as the entry point for the oncutf application. It sets up logging, initializes the Qt application with a stylesheet, creates and displays the main window, and starts the application's main event loop.  Functions: main: Initializes and runs the Batch File Renamer application.*
📄 main_window.py — *Module: main_window.py  Author: Michael Economou Date: 2025-05-01  This module defines the MainWindow class, which implements the primary user interface for the oncutf application. The MainWindow provides a comprehensive interface for browsing folders, selecting files, configuring rename operations through modular components, previewing name changes, and executing batch file renaming.  The interface is divided into several key areas: - A folder tree view for navigating the file system - A file table for selecting and displaying files to be renamed - An information panel showing metadata for selected files - A module area where rename operations can be configured - A preview area showing original and new filenames with validation indicators - Controls for executing rename operations  Classes: MainWindow: The main application window and interface controller.  Usage: from main_window import MainWindow*
📁 models/
    📄 __init__.py
    📄 file_item.py — *file_item.py  This module defines the FileItem class, which represents a single file entry with attributes such as filename, filetype, last modification date, and a checked state indicating whether the file is selected for renaming. The class is used within the FileTableModel to manage file entries in a table view.  Classes: FileItem: Represents a single file item in the table.  Author: Michael Economou Date: 2025-05-01*
    📄 file_table_model.py — *file_table_model.py  This module defines the FileTableModel class, which is a PyQt5 QAbstractTableModel for managing and displaying a list of FileItem objects in a QTableView. The model supports functionalities such as checkboxes for selection, sorting by different columns, and updating previews based on user interactions. It emits signals to notify changes in sorting and interacts with a parent window for UI updates.  Classes: FileTableModel: A table model for displaying and managing file entries.  Author: Michael Economou Date: 2025-05-01*
📁 modules/
    📄 __init__.py
    📄 counter_module.py — *Module: counter_module.py  Author: Michael Economou Date: 2025-05-02  This module defines a rename module that inserts an incrementing counter into filenames. It is used within the oncutf application to generate sequential file names based on configurable start value, step, and padding.*
    📄 metadata_module.py — *Module: metadata_module.py  Author: Michael Economou Date: 2025-05-04  This module provides a widget-based rename module that allows selecting a metadata field (such as creation date, modification date, or EXIF tag) to include in the renamed filename.  It is used in the oncutf tool to dynamically extract and apply file metadata during batch renaming.*
    📄 specified_text_module.py — *Module: specified_text_module.py  Author: Michael Economou Date: 2025-05-02  This module defines a rename module that inserts user-specified text into filenames. It allows users to prepend, append, or inject static text at a defined position within the filename.  Used in the oncutf application as one of the modular renaming components.*
📁 reports/
    📄 structure.md
📄 requirements.txt
📁 resources/
    📁 icons/
        📄 duplicate.png
        📄 invalid.png
        📄 unchanged.png
        📄 valid.png
📁 tests/
    📄 __init__.py
    📄 conftest.py
    📄 test_custom_msgdialog.py — *Module: test_custom_msgdialog.py Author: Michael Economou Date: 2025-05-09  This module contains unit tests for the CustomMessageDialog class used in the oncutf application.  CustomMessageDialog is a styled and flexible alternative to the standard QMessageBox, supporting: - Modal and non-modal dialogs - Progress bar display for long-running operations - Cancel via Escape key - Custom question and conflict dialogs  Tests in this module cover: - Dialog creation and visibility - Escape key cancellation behavior - Progress bar value updates - Static dialogs for questions and information - File conflict resolution options - Application modality settings - Callback triggering (e.g., accept on cancel)  These tests ensure consistent and reliable user interaction in dialog-based flows within the application.*
    📄 test_loading_dialog.py — *Module: test_loading_dialog.py Author: Michael Economou Date: 2025-05-09  This module contains tests for the loading dialog behavior used in the oncutf application, specifically for the non-blocking progress dialog implemented via CustomMessageDialog.show_waiting().  The tests validate: - Correct initialization and visibility of the dialog - Dynamic updates of progress bar values and ranges - Signal-based integration with background workers (e.g., FakeWorker) - Proper closure of the dialog upon completion - Modal behavior and safe event handling  These tests ensure that the loading dialog provides responsive and reliable user feedback during asynchronous operations like metadata scanning.*
📁 utils/
    📄 __init__.py
    📄 dark_theme.qss
    📄 file_loader.py — *Module: file_loader.py  Author: Michael Economou Date: 2025-05-01  This utility module handles the logic for selecting and loading files from one or more folders into the application's data model.  It supports recursive directory scanning, file type filtering, and preparation of file data for use in the oncutf renaming system.*
    📄 filename_validator.py — *Module: filename_validator.py  Author: Michael Economou Date: 2025-05-01  This utility module provides logic for validating filenames across different operating systems. It checks for invalid characters, reserved names, and other constraints to ensure safe and portable file naming.  Used by oncutf to prevent errors during batch renaming.*
    📄 icon_cache.py — *Module: icon_cache.py  Author: Michael Economou Date: 2025-05-01  This utility module provides functions for caching QIcons or other visual assets to avoid redundant loading and improve GUI performance.  Used by oncutf to store and reuse icons across different widgets without unnecessary overhead.  Supports: - Icon retrieval by file type or status - In-memory caching of icons - Integration with GUI elements via shared cache*
    📄 icons.py — *Module: icons.py  Author: Michael Economou Date: 2025-05-01  This utility module provides functions for creating and preparing icons, typically using QIcon or related PyQt components. It may also include logic for assigning icons based on file status or other contextual rules.  Used by oncutf to generate or modify visual indicators in the user interface.  Supports: - Dynamic icon generation based on input conditions - Theming or state-aware icon selection - Compatibility with oncutf UI components*
    📄 metadata_reader.py — *Module: metadata_reader.py  Author: Michael Economou Date: 2025-05-01  This utility module defines a class responsible for extracting file metadata using exiftool. It serves as an interface between the oncutf application and the underlying metadata extraction process.  Supports reading creation date, modification date, camera info, and other EXIF tags from image and video files.*
    📄 preview_generator.py — *Module: preview_generator.py  Author: Michael Economou Date: 2025-05-02  This module implements the core logic for generating preview filenames based on the active rename modules. It orchestrates the execution of each module in sequence and validates the resulting names.  Used by oncutf to display accurate previews before performing batch renaming operations.  Supports: - Modular rename pipeline execution - Duplicate and invalid filename detection - Conflict resolution and visual feedback*
    📄 theme.py — *Module: theme.py  Author: Michael Economou Date: 2025-05-01  This utility module is responsible for loading the application's stylesheet from external `.qss` files. It provides helper functions to apply consistent theming across all UI components of oncutf.  Typically used during application startup to apply a dark or light theme.  Supports: - Loading QSS from file path or resource - Applying styles to QApplication instance*
📁 widgets/
    📄 __init__.py
    📄 checkbox_header.py — *Module: checkbox_header.py  Author: Michael Economou Date: 2025-05-01  This module defines a custom QHeaderView subclass that adds a checkbox to the first column header of a QTableView. The checkbox allows users to select or deselect all rows in the table with a single click.  Used in the oncutf UI to streamline batch actions and improve usability when working with large file lists.  Features: - Syncs header checkbox state with row checkboxes - Emits signals when selection state changes - Visually updates based on user interaction*
    📄 custom_msgdialog.py — *custom_msgdialog.py  Author: Michael Economou Date: 2025-05-01  This module defines the CustomMessageDialog class, a flexible and styled alternative to QMessageBox for use in the oncutf application.  It provides support for various types of dialogs including: - Question dialogs with custom button labels - Informational dialogs with an OK button - Non-blocking waiting dialogs with optional progress bar - Conflict resolution dialogs for rename operations (e.g., Skip, Overwrite)  This dialog is intended for consistent and modern user feedback across the application, and is used instead of standard QMessageBox to allow greater control over layout, behavior, and styling.*
    📄 rename_module_widget.py — *Module: rename_module_widget.py  Author: Michael Economou Date: 2025-05-01  This module defines a custom widget for managing rename modules within the oncutf application. It allows users to add, configure, remove, and reorder individual rename modules that collectively define the batch renaming logic.  The widget provides a visual, modular interface for customizing the renaming workflow interactively.  Features: - Dynamic UI creation for each module type - Dropdown-based module type selection - Add/Remove buttons and layout management*
📁 workers/
    📄 __init__.py
    📄 metadata_worker.py — *Module: metadata_worker.py  Author: Michael Economou Date: 2025-05-01  This module defines a worker thread or task responsible for retrieving metadata from files asynchronously. It decouples metadata extraction from the UI thread to keep the application responsive.  Typically used in the oncutf application to run exiftool or similar metadata extractors in the background and emit signals when data is ready.  Features: - Threaded metadata reading - Signal-based communication with UI - Error handling and progress updates*

---

## ⚠️ Files Missing Module-Level Docstrings

- __init__.py
- __init__.py
- __init__.py
- conftest.py
- __init__.py
- __init__.py
- __init__.py
