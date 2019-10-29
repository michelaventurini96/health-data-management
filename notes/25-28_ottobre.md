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

### reusability

The software should be able to be reused, even for different applications. This is accomplished by different levels of granularity, favored by the modular approach. This can be applied even at process level, by reusing requisites.

### portability

It should work on different systems.

### comprensibility/transparency

The software,the design choices and its documentation must be **readable** . 

### interoperability

The sw must coexist and cooperate with different systems. This is facilitated by using **open interfaces**. When a patient iterfaces with different istitutions, their software are often incompatible, and the information has to be duplicated. 

### productivity

Efficiency and performance of production process: correct delivery times, staying in budget. Tied to human component and group dynamics. It requires management and coordination.

### tempestivity

The product must go on market at the right time. Obsolency must be considered. A solution is *incremental delivery* or packages. Requisites evolve, too.

### transparency

All development phases must be documented and made available to the users, to developers, to the clients.

## types of systems

* Informative systems
  * data oriented
  * data and information management
* Real time systems
  * control-oriented, fast replies, scheduling and priorities. Correctness vs reply time. Safety issues: the system must not produce damages if offline.
* Distributed systems
  * partition tolerance, broken node tolerance, network tolerance
* Embedded systems
  * no issue on user interface, but must be robust and trustworthy, because no user controls.

## Software life cycle

Needs $$\rightarrow$$ Project $$\rightarrow$$ Realization (coding) $$\rightarrow$$ Maintenance $$\rightarrow$$ Retirement $$\rightarrow$$ back to Need , and we must consider Process Management and General Management

Phases:
1) Feasibility study (domain analysis)
2) Acquisition and analysis of requisites
3) Architecture planning
4) Module coding and testing
5) Integration and test of the systems
6) Release, installation and maintenance
7) Support activities

Every phase produces **an output**. 

### feasibility study

Can the product be realized? Is it convenient? What strategies could be employed? What are the resources and the costs of different alternatives?

There are 3 parts:

* Problem definition and domain analysis, as deep as possible

* Definition of different employable solutions

* Times and costs of different alternatives, with development modalities.

  ###  acquisition and analysis of requisites

What is the client requesting? What MUST be present in the final product? What is "correct"?  Its output is the **document of requisites**, and is used in testing phase, and a preliminary version of the **user manual**.  All stakeholders must be identified, and all point of views. Contradictions must be harmonized.

The Document of Requisites can be described with formal languages like **UML** (Unified Modeling Languages). It must be easily understandable, coherent (non contradictory), precise, complete, without ambiguity.

Requisites can be:

* functional: how may users, which expectations, which entities and relations, how data are checked? What will the system do?
* non functional: quality attributes (efficiency, scalability, etc.)
* development and maintenance process requisites: tests and verifications, priorities on development, possible changes of the system.

### architecture description

How is the system done? Abstract description of the model. Components, interfaces and relationships between parts are decribed. Detail granularity is nested.

### module coding and testing

Development phase. The output is code and its documentation. Transparency, readabiity and modificability are mandatory. Versioning systems.

### integration and test

Modules are put together and tested.

### release, installation and maintenance

Product delivery to few users (beta testing), then to every final user. Users must be **trained**. Runtime architecture is set up. Maintenance covers up to 60% of costs. It can be corrective, adaptive, or perfective (only the last one: 50% of maintenance resources). 

### other support activities

Documentation, verification (validation: product vs requisites (informal), and verification: product vs (formal) specifications), management (of activities, responsabilities, human resources, product, new versions, releases, etc).

## process models

Developed over years, they were implemented to follow this activities, to organize product life cycle. The older model is **waterfall model** , where activities are propedeutic to each other, in a sequence. There are also **evolutive models**, based on small prototype development, the **unified process** based on UML. There are **transformational models**, **spiral models**, etc.

Because the waterfall model sucks: problems are seen only at release (and requires restarting the whole process). This model is dangerous. Too rigid, idealistic, monolitic. Too bureaucratic. Cannot respond to anticipated change.

To improve it, it has been evolved in **waterfall with feedback**, so we can go back only to the last phase if needed, or in **V-shaped models**, where feedback can jump among different phases.

## final words



The software is made mainly by design and specifications, more than coding. Project management phases are mandatory.