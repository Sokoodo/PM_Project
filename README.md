# **Process Mining Project Report**

## **Application of two Process Mining techniques using specific tools**

- **Introduction**

  The project is based on the application of Process Mining techniques and algorithms using particular logs, in this case an event log from a Loan Application Process.

  The main objective of the project was to analyse how two different algorithms works with the functionalities of the same tool, that is Pm4Py, and show their results.

  In the first place, the logs have been imported with a Pm4Py function from a XES file. Afterward, the Process Discovery algorithms have been applied and the resulting Nets have been extracted.

- **Log Description**

  The project uses a log that comes from 4TU.ResearchData, that is an international data repository for science, engineering and design. Its services include curation, sharing, long-term access and preservation of research datasets.

  In particular, the project uses an event log from a Loan Application Process. It is dated 23.04.2012 and comes from Eindhoven University of Technology.

  The format of the log is XES (eXtensible Event Stream), that is the standard format for process mining supported by the majority of process mining tools. 

  It contains 13087 traces.

- **Development**

  - *Process Discovery*
  
    The Process Discovery algorithms are used to find a suitable process model based on an events log, in this case the Loan Application log.
    The used process discovery algorithms are the Alpha Algorithm and the Heuristic Miner, both of them were executed using the functions provided by the tool PM4Py.

    Alpha Algotithm->
    The α-algorithm focus on control flow such as the ordering of the activities, it’s the first process discovery algorithm ever created.
    It scans the event log for particular patterns.
    The goal of the α-algorithm is to take an event log in input and convert it into a Petri Net.
    To do that, it considers the footprint of the log, that is based on direct successions, causality successions, parallel successions and choice successions.
    The algorithm has some kind of problem, for example, it cannot handle loops of lengths one and two, it cannot discover an invisible and duplicated task and it is       weak against noise.

    Heuristic Miner->
    The Heuristics Miner is an improvement of the Alpha algorithm.
    We consider the frequency of the traces, we count the cardinality of the direct successions on the traces, and we calculate the dependency measure.
    This provides the basis for identifying the dependencies and to build the resulting Heuristic Net.
    Thanks to the Heuristic net, it is possible to see the number of times each activity and path is executed.
    The algorithm also provides a way to handle noise by applying threshold values on activity and arcs to consider only the strong relations excluding the weaker.
    Eventually, there are tools that can convert this dependency graph into a Petri Net.

  - *Tools Description*
  
    The tools employed in the project execution were PM4Py and ProM.
    
    Pm4Py->
    The Loan Application events log have been analysed using the tool PM4Py, a Python library that supports Process Mining algorithms in Python itself.
    This tool is the leading open-source process mining platform that can be used in both academia and industry projects.
    It is extendable, easily integrable with other application and fully documented on their documentation pages.
    Some of its main features are the handling and filtering on event data, process discovery, Petri Net management and conformance checking.
    
    ProM->
    ProM (which is short for Process Mining framework) is an OpenSource extensible framework for process mining algorithms. 
    ProM provides a platform to users and developers of the process mining algorithms that is easy to use and easy to extend.
    It is platform independent as it is implemented in Java and can be downloaded free of charge.
    The project uses ProM just for the graphical visualization of the resulting Petri Net found with the α-algorithm.

  - *Results*
  
    All the final Nets are the result of function provided by the tool Pm4Py, that provides a lot of functionalities about Process Mining.
    This Heuristic graphical result is really clear and the dependencies inside the graph itself are well shown, thanks to a function of Pm4Py the resulting Dependency graph has been converted into a Petri Net.
    Both the Petri Nets and the Heuristic Net, coming from Heuristic Miner and from Alpha Algorithm, will appear as images when you run the filter.py, thanks to the functionalties of the graphical tool **GraphViz**.
    The two Petri Nets can also be found in the two files with the extension ".pnml", that can be exported in any other Process Mining tool that supports that format, for example I used the tool ProM to visualise it.

- **Conclusion**

  The project has been used as a test to understand the basic Process Mining algorithms and techniques in practice and to try out some Process Mining tool.

  The final results are satisfactory, the program has been written in Python using the library Pm4Py , it is well configured and it uses two different algorithms, the   Alpha Algorithm and the Heuristic Miner, both with the same log.
  
  The log was pretty big, so it’s actually not so easy to compare the 2 resulting Petri Nets.
  On the other hand, the Dependency Graph resulted really clear and readable.

