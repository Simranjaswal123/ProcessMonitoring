# ProcessMonitoring
initial changes:-
ProcessMonitorDashboard is a Java-based, real-time process monitoring tool with a graphical user interface (GUI).
It displays system process information, tracks CPU usage over time, and provides functionalities to terminate or restart processes.
Built using standard Java libraries (Swing, AWT, and java.lang.management), it operates without external dependencies, ensuring portability across Windows, Linux, and macOS.
more functionalities :-
It introduces a TableRowSorter for dynamic table sorting and filtering, with new buttons to sort by CPU or memory and a search field to filter processes by name.
The table now includes additional columns for memory percentage, priority, and CPU trend, with the latter calculated by comparing current and previous CPU usage. Process data collection is improved with more detailed parsing for Windows (tasklist /FO CSV /V) and Unix (ps -eo), including priority levels and memory conversion to MB.
Error handling is enhanced with dialog messages, and the terminateProcess method now includes a confirmation dialog and success/failure feedback.
