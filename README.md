# ProcessMonitoring
initial changes:-
ProcessMonitorDashboard is a Java-based, real-time process monitoring tool with a graphical user interface (GUI).
It displays system process information, tracks CPU usage over time, and provides functionalities to terminate or restart processes.
Built using standard Java libraries (Swing, AWT, and java.lang.management), it operates without external dependencies, ensuring portability across Windows, Linux, and macOS.
more functionalities :-
It introduces a TableRowSorter for dynamic table sorting and filtering, with new buttons to sort by CPU or memory and a search field to filter processes by name.
The table now includes additional columns for memory percentage, priority, and CPU trend, with the latter calculated by comparing current and previous CPU usage. Process data collection is improved with more detailed parsing for Windows (tasklist /FO CSV /V) and Unix (ps -eo), including priority levels and memory conversion to MB.
Error handling is enhanced with dialog messages, and the terminateProcess method now includes a confirmation dialog and success/failure feedback.
Revision 3:- The updated code retains the core functionality —real-time process monitoring with a GUI, table display, and CPU graph—while introducing refinements primarily in the CustomGraphPanel class.
The key change is in the CPU usage graph, where the paintComponent method now includes a wider graph (850 pixels), grid lines at 20% intervals, and percentage labels (0% to 100%), improving readability. Other functions, such as updateTable, terminateProcess, and restartProcess, remain unchanged, maintaining their enhanced features.
revision 4:- 
The CustomGraphPanel class adds a legend (a blue square labeled "System CPU Usage") and adjusts the graph’s scaling by using graphWidth (850 pixels) and graphHeight (200 pixels) for better proportionality, replacing the hardcoded 600 and 2x scaling.
The ProcessInfo class now explicitly includes the priority field in its constructor, aligning with its usage.
The startUpdates method removes an extra updateTable() call outside the timer, streamlining initialization.
Graph axes and labels are repositioned using leftMargin and bottomMargin variables consistently, and the CPU usage line calculation uses dynamic scaling (graphHeight / 100) instead of a fixed multiplier.
revision 5:-
Better Parsing: Strips .exe from Windows process names for cleaner display.
Windows CPU Estimation: Added a basic CPU% approximation using wmic (still limited but better than 0.0).
revision 6:-
Refined CPU Trend: Adjusted thresholds (e.g., ±2% and ±10%) and added "High" indicators for significant changes; uses "≈" for stable and "New" for new processes.
Selection Stability: Ensures single-selection mode to prevent multi-row confusion.
Revision 7:-
Termination (terminateProcess):
Detailed Confirmation: Shows process name, PID, and state in the dialog for better context.
Robust Execution: Uses command arrays for Runtime.exec() to avoid shell parsing issues; reports exit codes for precise feedback.
Restart (restartProcess):
Improved Reliability: Separates kill and restart steps with exit code checks; adds a timeout for restart attempts.
Detailed Feedback: Differentiates between termination success and restart outcome in the dialog.
