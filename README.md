# **Process Mining Project Report**

- **Introduction**

  The main objective of the project was to show and analyse how two different algorithms works using the same tool.

- **Log Description**

  For the project I chose a log from the web page “processmining.org”, that contains several community datasets.
  In particular, I used an event log of a Loan Application Process dated 23.04.2012, which came from Eindhoven University of   Technology.
  The format of the log is XES (eXtensible Event Stream), that is the standard format for process mining supported by the      majority of process mining tools.
  It contains 13087 traces.

- **Implementation**

  - *Algorithms Description*

    Alpha Algotithm -> 
    The α-algorithm focus on control flow such as the ordering of the activities, it’s one of the first algorithm suitable to     discovery model.
    It scans the event log for particular patterns.
    It considers the footprint, based on direct successions, causality successions, parallel successions, choice successions.
    From this footprint, it applies a set of 8 rules useful to extract a Petri Net from your log.

    Heuristic Miner -> 
    We consider the frequency of the traces, we count the cardinality of the direct successions on the traces, and we     calculate the dependency measure. 
    This provides the basis for identifying the dependencies and to build the dependency graph.
    Eventually, there are tools that can convert this dependency graph into a Petri Net.

  - *Tool Description*

    The choosen tool is Pm4Py, that is the leading open-source process mining platform written in Python.
    It is extendable, easily integrable with other application and fully documented on their documentation pages ([Pm4Py Documentation](https://pm4py.fit.fraunhofer.de/docs)).

  - *Results*
  
    All the final Nets are the result of function provided by the tool Pm4Py, that provides a lot of functionalities about Process Mining.
    This Heuristic graphical result is really clear and the dependencies inside the graph itself are well showed, thanks to a function of Pm4Py the resulting Dependency graph has been converted into a Petri Net.
    Both the Petri Nets and the Heuristic Net, coming from Heuristic Miner and from Alpha Algorithm, will appear as images when you run the filter.py, thanks to the functionalties of the graphical tool **GraphViz**.
    The two Petri Nets can also be found in the two files with the extension ".pnml", that can be exported in any other Process Mining tool that supports that format.

- **Conclusion**

  The final results are satisfactory, I created a program in Python using the library Pm4Py and I have been able to configure it and to try two different algorithms, the Alpha Algorithm and the Heuristic Miner, both with the same log.
The log was pretty big, so the result should be correct (usually if the datasets are correct, more data you have, more precise is the model).
