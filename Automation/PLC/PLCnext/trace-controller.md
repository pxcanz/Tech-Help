# Trace Controller

_Tracing_ is a technique used to understand what goes on in a running software system. The piece of software used for tracing is called a tracer, which is conceptually similar to a tape recorder. When recording, specific instrumentation points placed in the software source code generate events that are saved on a giant tape: a trace file. You can record user application and operating system events at the same time, opening the possibility of resolving a wide range of problems that would otherwise be extremely challenging.

The list of recorded events inside a trace file can be read manually like a log file for the maximum level of detail, but it’s generally much more interesting to perform application-specific analyses to produce reduced statistics and graphs that are useful to resolve a given problem. Trace viewers and analyzers are specialized tools designed to do this.

For PLCnext, it can be used for diagnostics.
With this snapshot it is possible to analyze the program duration and all interruptions on Kernel level.
The interpretation of this information requires specific knowledge of LTTng. Since FW 2023.x root privileges are required.

The following is an excerpt from the Level 300 Expert PLCnext Training.

## Configuration
![image](https://github.com/user-attachments/assets/fd4f51b0-6e77-4a4e-8547-7a98132036f0)

1. The Snapshot mode can be activated by changing the configuration file /opt/plcnext/projects/Default/Services/TraceController/TraceController.config. Then restart the controller or restart PLCnext Runtime.
2. After an exception has occurred, the Trace Controller saves the snapshot into the directory /opt/plcnext/lltng_traces/ with the timestamp of the exception.

The trace controller can also configured with the RSC Service.

The trace can then be viewed with Trace Compass on a PC

## Trace Compass
![image](https://github.com/user-attachments/assets/f389ccef-356a-422e-bc51-cf946f891ce5)

With Trace Compass, you can open and run diagnostics which can be done by executing the executable. To set up the trace recording:
1. Click on the green dot to set up a new connection
2. Set up a connection to the PLC
3. Right click on the PLC and press connect
4. Right click on PLC>Sessions>plcnexttrace_snapshot and press Record Snapchot
5. To graphically display the captured image click on Import
6. Make sure that the check mark next to "Create Experiment" has been set. To see user trace points as well as kernel trace point, select "ust" and "kernel“.

## Analysis
![image](https://github.com/user-attachments/assets/8de6c236-027b-45fa-9ae8-95111690804f)

1. To facilitate the analysis of the displayed processes, they can be filtered so that only those that are of interest are displayed. Trace Compass offers a filter function that can be opened with the button shown above.
2. The process statuses are shown in different colors. For example, green indicates that the process is active and can be run, whereas a berry color (dark red) indicates that the process is currently interrupted by another process.
3. A legend, which can be called up via the menu, provides a listing of the colors and their meaning.

## Further Analysis
![image](https://github.com/user-attachments/assets/51bcc99d-7a1a-4661-b34c-89efbe5ca0dc)

1. Trace Compass offers a variety of views and perspectives for detailed analysis. On the following page, another example, the OS Tracing Overview, will be briefly presented.
2. The OS Tracing Overview shows, among other things, the CPU utilization and the proportion of individual processes at this.
