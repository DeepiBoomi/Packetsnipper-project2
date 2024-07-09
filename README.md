This project consists of a packet statistics application implemented in C. The application captures and analyzes packet statistics, storing the data in shared memory. The statistics are displayed in either tabular or graphical format, and the user can specify which protocols to display (TCP, UDP, ICMP, or all).

Features
  1.Captures and analyzes packet statistics.
  2.Stores packet statistics in shared memory.
  3.Displays statistics in tabular or graphical format.
  4.Allows filtering of displayed protocols (TCP, UDP, ICMP).
Prerequisites
  1.GCC (GNU Compiler Collection)
  2.POSIX thread library
  3.Shared memory and semaphore libraries
  4.Linux-based operating system (recommended)
Files
   main.c: Contains the main code for capturing, analyzing, and displaying packet statistics.
Compilation
   To compile the application, use the following command:
      gcc -o packet_stats main.c -lpthread -lrt

Usage
     Running the Application
          1.Start the application by executing the following command:
                 ./packet_stats [tabular|graph] [tcp|udp|icmp|all]
                 [tabular|graph]: Optional argument to specify the display format (default is tabular).
                [tcp|udp|icmp|all]: Optional argument to specify which protocols to display (default is all).
         2.The application will start capturing and analyzing packet statistics, displaying them in the specified format and for the specified protocols.

Examples
    1.To display statistics in tabular format for all protocols:
            ./packet_stats tabular all
    2.To display statistics in graphical format for TCP only:
            ./packet_stats graph tcp

Display Formats
       Tabular Format: Displays the packet statistics in a table.
       Graphical Format: Displays the packet statistics using a simple text-based bar graph.

Notes
      The application simulates packet capture by generating random data.
       The shared memory segment is created with a key of 3427 and a size of 1024 bytes.
Cleanup
     To remove the shared memory segment after running the application, ensure the application is stopped and then manually remove the shared memory segment using the following command:
            ipcrm -M 3427

Troubleshooting
          shmget failed: Ensure your system supports shared memory and that the key 3427 is not already in use by another application.
          shmat failed: Ensure you have the necessary permissions to attach to the shared memory segment.
