![1571740457241](/home/andrea/.config/Typora/typora-user-images/1571740457241.png)



ER Diagram of an hospital.



# Software engineering principles

A software comprehends any system to elaborate informations, and its documentation. Any program, procedure and doc implements calculations. Software engineering is :

* the application of scientific and technological knowledge, methods and experience to design, implement, test and document a software.
* the application of a systematic, disciplinated, quantificable approach to develop, operate and maintain a software (IEEE standards, 1990)

Software engineering was born after software ('60s). SE differs from programming: projects are complex, multi-programmer, require management, main activity is programming activities and not coding anymore, requires extra skills: project management, process management, definition of specifications, communication/interaction among user/client/coders).

It is immaterial (not tangible), human intensive (requires a lot of human time), elastic (easiliy modifiable), complex (a lot of interacting instructions), and non linear (a slight modification can require a huge chance of all the system).

Many key figures are identified: coders, producers, clients and users.

Additional components: theoretical informatics, AI, Operative Systems, system engineering, process engineering. quality management.

Software quality is described by internal qualities (code, perceived by coders) and external qualities (UX, experienced by users).

### correctness

if the input is correct, the output should be what expected. Depends from specifications, and *preconditions*. Can be evaluated in testing phase. Testing must be able to be specified.

### reliability

A superset of correctness. It's the probability that the software is correct in a certain time interval. It's a relative quality: if the error is not severe, it could be fine too. A correct software is reliable. A reliable software does not need to be correct (a good error management, i.e.)

### robustness

The capacity of being able to manage anomalous or wrong inputs. 

* Not robust (level 0): it just ignores it or crash. 
* More robust (level 1): quits, manages the **exception**.
* Robust (level 2): reacts to the anomaly, fix it, asks for more input, present a diagnostic.

### performance

Speed, simultaneous accesses, cooperation with other applications, etc. Usually, requisites.

### efficiency

Rational use of hardware and software resources. *Computational complexity*, worst case and average case, $$\Omega$$ and $$\Theta$$ numbers. Logging. Simulation and berchmarking.

### scalability

How the software can grow or shrink following more or less requests.

### usability

Easiness of use and learning from the user. Optimizes user interfaces, easy configuration, adaptability to running environment. It's a subjective measure. The final user must be known and defined.

### verificability

Software use monitoring. User logging, accesses, etc.

### maintainability

* upgradability with new features (perfective maintenance), 
* debuggability (corrective maintenance) 
* evolution to new environments (OSs, drivers, hardware) (adaptive maintenance).

It must be **evolvable**: software must be elastic, diagnostics must be functional, error reporting works. Features are well isolated/encapsulated: modulare design.

It must be **repairable**: errors must be corrected with a reasonable work. Standard parts are used.