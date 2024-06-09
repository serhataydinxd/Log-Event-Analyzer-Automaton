# Log Event Analyzer with Automaton
A project made for FORMAL LANGUAGES AND AUTOMATA lecture

This C# project is an application that takes an xlsx file containing your event logs (yes the app static not real-time) and
an XML file containing:
- A DFA language which you can customize the states, number of states, production rules (which can have as much values as you want), number of production rules and terminal names that are used for state transitions.
- Start state of the DFA
- The number of critical logs each computer can send before they are banned by the systen. Any logs sent by banned computers are ignored.

# Process
The app,
- uses your XML file as a guide and the event ids of your xlsx log file to transition from one state to another which are in my case Error, Information, Warning and Critical. 
- outputs every state transition and notes the computer name when a Critical value is sent by them. I used 4625 which is the log for an incorrect password, but you can use any id or ids you want.
- bans the computer from sending any more logs if it reaches the daily critical log limit.
- writes a report of critical logs' time and from which computer they came from. The report also states when a computer gets banned and when a banned computer tries to send a log.

# Notes
Random XML's wont work, there is a DTD. There are 2 log files and an XML file present in \SIEM_PROJECT\bin\Debug if you want to test the app.
