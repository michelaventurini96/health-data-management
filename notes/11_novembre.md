# HL7

HL7 is a clinical document architecture (CDA). Inside HL7, free text still remain a gold standard, in certain portions of it. A structured document converts the plain text in a tree-organized data structure with many fields (patient history, etc.) with some subsection (presenting complains, significant diseases, traumatic injuries) leading to a serie of coded concept ([C1384666] Hearing impairment, etc). The [C1384666] is a SNOMED(?) code, standardized.  Document can become **structured and standardized**.

A serie of techniques of NLP has beed deployed to automatically structure text. [Example](http://linguistic-annotation-tool.italianlp.it/).  Few basics of NLP were given.  In some case studies, NLP algorithms performed much better to extract information from unstructured EHR compared from querying structured EHR. NLP Techniques can cross the **semantic barrier**, that limits information extraction because of any lack of coding.

# dictionaries

Organized collection of terms, such as two persons can associated the same meaning at the same term. In an informatic system, it becomes a **database of terminology**, or a **medical dictionary** in medical settings. NLP can be ambiguous, while a dictionary is more regularly stochastic. DRG's are dictionaries. Lab results can be given a code, associated with results and date, to be able to search for past exams. They can be used to **support decisions**, for example giving alerts if a medic prescribe an incompatible drug (e.g. nefrotoxic drugs for kidney-deficient patients). A system can guess if the patient is kidney-deficient, and eventually alert the medic. Unstructured data, NLP processed, can have false positive or negatives (irrelevant data mistaken for relevant, or viceversa).

To build a dictionary we need 1) a shared denomination, 2) a definition and 3) a code. 

* there can be a LOT of terms, changing often;
* different **granularity** levels must be managed
* terms needs to be **organized**;
  * a possible way to organize them could be **nested tree structures** (taxonomical / systematical organization)
* terms must be combined among each other following **certain rules**
* each term can have some related **attributes*
* term can vary in different **context**
* they are part of a various and complex **knowledge domain**
* so most terms are **domain-specific**

### concepts

a dictionary is a list of **concepts**. They can have a **descriptive definition** and a **computable definition** (as list of attributes). A term can be a single (heart, diabetes,...) or aggregated concept (familiy history of heart attack, circulation, degenerative extrapiramidal disease...).

In dictionaries can be pre-coordinated or post-coordinated. Pre-coordinated has complete non-ambiguity. It eliminates every nonsense combination of atomic concepts, but it can be redundant and requires to be domain-savvy, requiring a sistematic approach to the WHOLE domain. Usually employed in administrative tasks. Post coordinated are flexible, non redundant, but the information is not univoc anymore. Preferrable in clinical and diagnostic tasks, where a single task is described by many and many different terms("test a/a + liquor + one sampling + flocculation" = an antigen/antibody test made on a cerebrospinal sample taken in a single sample and analized by flocculation).

# SNOMED CT vs ICD9/10

ICD: International Code of Diseases. Nested tree of diseases, that cathegorizes all diseases. Precoordinated.  482.1 : Psudomonas pneumonia.

* ICD9-CM

  * 01--05 Nervous System surgeries

    * 01 Incision and ablation of pathology of the cranium, brain and meningi

      * 01.0 - transcranic puncture

        * 01.01 ...of cisternae
        * 01.02 ...of ventricula
        * 01.09 ... other.

        http://salute.gov.it/portale/temi/ric_codice/default.jps

SNOMED: postcoordinated: pneumococcal pneumonia = T-28000 (lung) + M-40000 (inflammation) + L-25116 (pneumococcus)

Identificators are:

* Hiearchical: tree index
* Context-free: no meaning, the next free is given.

both pre and post coordinated can be both hierarchical or context-free.

There are a lot of them:

* diagnostics and findings : **ICD9/10**, ICPC, ICF, **SNOMED CT**, Read Codes, MedDRA, CTCAE....
* procedures, CPT, CDT
* nursing
* ...

ICD version 9 or 10 (soon 11) and SNOMED CT are competing standards. They are similar in their aims, but...

## SNOMED CT

born in US College of American Pathologists, an clinical analysis laboratory for pathologic anatomy, then expanded. CT = Clinical Terms, when it implemented NHS Read Codes, in 2002. It was acquired in 2007 by IHTDO, and became SNOMED International. It's a no-profit company, owned and funded by its members (free for low income countries). Italy is not among them. It is very flexible, and it has been recomended to be used in : problems, procedures, smoking status, lab test results, family health history, oncology registry, under "Meaningful Use" in Obamacare.

## ICD

International Code of Diseases, born in 1850 to classify death causes. Developed and maintained by World Health Organization. It included sickness causes in 1909, then diseases and injuries in 1948 (after the last war) and mental/behavioural disorders in 1975. A version of ICD is a pile of 3 paper books, with an index, an instruction manual, and the alphabetical list of terms. From version 11, it won't be paper-based anymore. It's made of 5 groups (epidemics, general disease, local diseases by site, development disease, and injuries). ICD10 is made of 21 chapters. There is a chapters for every part of the body, plus extras like "Every sympton, abnormal clinical sign and lab finding, not elsewhere classified", "external causes of morbidity and mortality", "factors influencing health status and contact with health services".

Codes are made of 1 letter + 2 digits, mandatory, plus an optional "." and another single digit for subcategories. 

Codes U00-U49 are to be used by WHO for the provisional assignment of new diseases of uncertain etiology. Codes U50-U99 may be used in research, i.e. then testing an alternative sub-classification for a special project.

Codes can have symbols: cross or star. Cross can identify the primary cause, star is used for the secondary cause. E.g.: `"A06.6+ (Amoebic brain abscess(G07* ))"` that sends to `"A06 Intracranial & intraspinal abscess (G07* )"` that includes `"Amoebic brain abscess (A06.6+)"`.

[Browser for ICD codes.](icd.who.int) A code can have additional desciptive codes.  Multiple inheritance is forbidden (unlike in SNOMED), but a single inheritance is forced. There are `NOS` terms (Not Otherwise Specified) and `NEC` (Not Elsewhere Classified), that means ", other". (E.g. "Viral pneumonia, NEC"). This code reduces over time, when new codes are created.

## SNOMED

The heart of SNOMED is the Concept. It has an unique *ID*, a *Description* (with exactly one **Fully Specified Name (FSN)** and N **Synonims**, one or more of which is marked as "**Preferred**", and zero or more may be marked as "**Acceptable**") and *Relations* (Each Concept has an ID at least one "is a" relationship, and N "attribute" relationships), *Hierachies*.

[SNOMED browser](browser.ihtsdotools.org)

Multiple inheritance can be implemented (polyhierarchy through inheritance many-to-many relationships).

![1573557027563](/home/andrea/.config/Typora/typora-user-images/1573557027563.png)

![1573557138636](/home/andrea/.config/Typora/typora-user-images/1573557138636.png)

![1573557179253](/home/andrea/.config/Typora/typora-user-images/1573557179253.png)

Post-coordination can be implemented dinamically. New codes can be invented by appending existing codes (pattern: concept:relation=concept):

`"Laparoscopic removal of device from abdomen" `
`= 68526066 "removal of device from abdomen": 425391005 "using access = 6174004"laparoscope"`

## contents

SNOMED has 100k terms. ICT9 14k but ICD10 68k!! (That means a bloodbath for version updating). SNOMED is not necessarily more specific. ICD has excessive details on something like V30.2xxD: "*Person on outside of three-wheeled motor vehicle injuried in collision with pedestrian or animal in nontraffic accident, subsequent encounter*", or burning water-skis, or turtle bite.

There is a contrast between public health perspective vs. patient perspective.

## mapping between them

It's very hard. (NLP embedding?) 

# UMLS

Unified Medical Language Systems. Born in 1986, at the National Library of Medicine. Classified as a "*long term R&D project*", it's complementary to IAIMS (Integrated Academic Information Management Systems).

It's a relational database (despite being an ontology). It has many interfaces (web interface, Java API, web API) and some applications (lvg: lexical programs, MetamorphoSYS...)

Let's make an example: Addison's disease (hypocortisolism, chronic adrenal insufficiency). It can be primary or secondary, acute or chronic, isolated or in a polyendocrine deficiency syndrome. It has many names (bronzed skin, measma addisonii, addisonian syndrome, asthenia pigmentosa, ... ).
UMLS lookup for Addison's disease in all his dictionaries (let's say MeSH, MedDRA, ICD10 and SNOMED-CT) and cluster them under a concept code (**CUI, code unique identifier**): C0001403, and label it with a string, like "Addison's disease". After, it compares the hierarchies of our term in all hierarchical or polyhierarchical dictionaries.

From all these trees, it tries to organize concept in a graph, that summarise them all. Then some experts integrate the tree with additional children/branches. 

UMLS labels the concet, finally, with semantic cathegories (disease, body part, etc.). Entries are manually annotated. The results are a **metathesaurus** with concepts and relations, and a **semantic network**, with semantic types and network relationships. Plus some lexical resources (SPECIALIST Lexicon and lexical tools).

### metathesaurus

129 families of source vocabularies (not counting translations), 21 languages. Broad coverage on biomedicine (8.6M names, normalized), ~3M concepts, >10M relations. It can be used to translate between different dictionaries (ex. medical dictionary SNOMED <-> UMLS <-> GO <-> genome annotation) or MeSH for biomedical literature. An entry is  nested tree of term codes: a Concept (C code, 2.9M) includes many Term (L code, 8.6M), that include many Strings (S term, 9.7M) that include many Atoms with different codes from different sources (A code 11.6M)

Relations are semantic, between a couple of Atoms, with single or complex mapping. "...is a...", "...is part of..."

### semantic network

Different semantic types can create **semantic networks** of terms linked by semantic similarity between the categories. After UMLS thesaurus relations, a Term inherits the semantic relations from its semantic categories. In this way UMLS becomes an **ontology**.

e.g. "..is used to cure.."





# Health Informatics Standards

It's not just about trading information, but about working together in synergy. It's a historical reason: structures were built without any coordinative effort.  Interoperability means having standards, mostly. You will need:

* Tecnological standards
* Communication standards (structural standards)
* Common terminologies and ontologies (semantic standards: medical dictionaries)
* Processes  (organizational standards)
* Frameworks and agreements (governance standards)
* International legislation

We'll new see the first two levels. 

## Health Information Exchange (HIE)

According to healthit.gov: "[*HIE allows doctors, nurses, pharmacists and other health care providers and patients to appropriately access and securely share a patient's vital medical information electronically - improving the speed, quality, safety and cost of patient care*](https://www.healthit.gov/sites/default/files/ONC10yearInteroperabilityConceptPaper.pdf)".

![1575304661828](/home/andrea/.config/Typora/typora-user-images/1575304661828.png)

Apple and other portable device producers adhere to this kind of standards. How is a standard made? 

+ **ad hoc method**: a group of people choose the most used method, and elevates it as standard (e.g. DICOM) by declaring its specification. When a lot of people start using it, it becomes a standard.
+ **de facto method** : a single stakeholder controls a big enough portion of the market (e.g. Microsoft Windows)
+ **government mandate method**: a goverment agency creates a standard and legislates its use (e.g. HCFA's UB92 insurance claim form)
+ **consensus method**: a group of volunteers representing all stakeholders work in an open process to create a standard (e.g. HL7 health level 7 standard for clinical data interchange)

The development process of a standard has some phases:

Identification $$\rightarrow$$ Conceptualization $$\rightarrow$$ Discussion $$\rightarrow$$ Drafting $$ \rightarrow $$ Revision $$\rightarrow$$ Implementation

Standards are not laws!! In some cases, they can *become* laws, but most often then not they are just accepted and implemented by market selection (e.g. Bluetooth). Conformity to the standard is a simple self-declared compliance, that can be **certified** by a neutral body, with a verification stage (with an audit). Certification agencies include TUV Sud, etc. 

Standards usually guarantees :

* **agreement**: made by consensus
* **democracy**: all interested stakeholders can partecipate and make observations and suggestions
* **transparency**: the process of creation is available to the public
* **voluntary application** : norms are a reference that are voluntarily adopted

### standardization agencies

ISO (world), CEN (europe), UNI (Italy).   $$\rightarrow$$ UNI/EN/ISO , etc.
For electric area: IEC (world), CENELEC (europe), CEI (Italy).
For IT: W3C, OASIS, IETF, IEEE, OGF.... 

Adoption in single countries require translation and acceptance. They can be separated, not necessarily propedeutically.

For medical informatics, there is a special commission: CDISC, CEN Technical Commission 251, GS-1, **HL7** , etc. In Italy, there is UNINFO, member of UNI. The first US standard for transmission of medical data is from 1996 , named HIPAA (Health insurance portability and accountability act).

# HL7

Born in 1987, Health Level Seven International (HL7) is a non profit, ANSI-accreditated standards developing organization, dedicated to providing a comprehensive framework and related standards for the exchange, integration, sharing and retrieval of electronic health information.

The 7 refers to the ISO-OSI information trasmission model, it defines the 7 levels at which digital data could be traded: 

* bits
* frames (MAC address, LLC)
* packets (IP, networks)
* segments (connections, reliability)
* data (session)
* data (presentation)
* data (application)  $$\rightarrow$$  7th level, the only one ruled by HL7.

In Italy there is HL7 Italy (Uni Genova). Current version of HL7 is 3.0. This is the version implemented in all regional health data systems. Given that interoperability processes doesn't create new systems, they have to take actual implementations of IT facilities and create a common interface that allows them to talk with each other. 

There are 7 sections, 2 generals and 5 referring to particular domains (clinical and administrative domains, EHR profiles, rules and references, education and awareness).

## HL7 v. 2 

**Communication workflow: the data is exchanged between two entities as a message.** 

* It is ASCII coded, delimited by separators.
* Two actors (sender + receiver), communicate through the exchange of bi-directional messages
* The message is validated by a parser before the transmission: first, the parser adds missing parts, then the message is transmitted
* The receiver decodes the message according to the protocol rules and interpret data type, extracting all the relevant informations from the message
* Messages are independent from the system implementation $$\rightarrow$$ heterogenous systems can communicate without knowing each other
* The receiver always sends an acknowledgement (`ACK`) message to confirm the reception.

The message starts with a trigger (e.g. you change the address of a patient in your local anagraphics). An HL7 message is sent. Upon reception, an HL7-ACK message is sent back and received. A message is an ASCII string, made of **segments**. A segment is delimited by a carriage-return (`HEX 0D`), divided in **fields**, delimited by | , and inside fields data or strings can be separated by ^, subcomponents by &, etc.

Example: order places hl7 message:

`MSH|^~\6|RIS|SIEMENS|SCREENING|DEDALUS|other metadata......<cr>` this is the header line: 
`PID||59530^^^RIS|""|ROSSI^MARIA||19549191<cr>`
`PV1||O||||||||||||||||SCR20131568`
`ORC|SC|0000000000000034466^DEDALUS|434298347298374^RA2000||CM....`
`OBR|||....`

example: reply ACK

`MSH|^~\&|RIS|SIEMENS|EUROSOFT|EU|1203192830918||ACK^001|MSGID12938019283019283|P|2.3.1<cr>`  header
`MSA|AA|MSGID12938019283019283`

MSA: id of the message, and code of acceptance: AA: application accept, AE: application error, AR: application reject.

[missing part, until CDA templates]

HL7 adds a RIM (Reference Information Model), that adds interoperability trying to represent info in a common way (Entity, Role, Act). A new method to represent documents is the Clinical Document Architecture (CDA). Instead of messages, documents are passed (with signature, legal implications) in XML format. They follow the **CDA MODEL**, derived from the RIM.

CDA v2 is composed by Header and Body part, the latter divided in Structured and Unstructured parts. XML can be parsed with a CSS for a human-readable document. Different templates and/or implementations can be used to constrain the CDA specification, and to provide XML validating rules. CDA-2 relies on a SOAP architecture, for XML over HTTP.  

# FHIR

### Fast Healthcare Interoperability Resources

Always based on RIM model. It's a standard describing health data format, and an API for exchanging EHRs. It's REST-based. CDA2 creates the documents, but FHIR allows different hospitals to share data. It is similar to CDA2, but a new implementation must be done.

[FIHR structure standard example](https://www.hl7.org/fhir/condition.html)

REST: REpresentational State Transfer. It's a style to build websites (not a protocol, not an architecture). RESTful services can pass informations over different protocols (99% HTTP). It makes resources available through an URI. 

* Resources: elements containing informations
* Request verbs (POST, GET, PUT, DELETE)
* Request headers, additional instructions (type of response required, auths)
* Request body
* Response body (XML, JSON)
* Response status code (200 = OK, 404 = not found)

FHIR allows access to atomic informations to info with a RESTful API, while CDA2 is a whole document. FHIR allows interaction with data (CRUD), CDA2 is read-only. FHIR has a modular approach, without limitation on content, while CDA2 use a complex and very abstract model based on HL7 "clinical statement". Both are human readable, and based on HL7 v3.

## HAPI-FHIR

Hapi: API per FIHR data, a special kind of fileserver. [Example test server](https://fhirtest.uhn.ca/home?encoding=null&pretty=true) .  The Conformance Statement shows the available resources.  An additional layer between EHR and apps is [SMART on FHIR](smarthealthit.org), a token-based authentication framework between EHR and FHIR, and allows the app to work without knowing the FHIR server, adding a layer of security to the data. SMART is a common API for all EHRs firms and fileserver protocols and standards.



# IHE

Integrating the Healthcare Enterprises: initiative of EHR makers with the target of giving methods to implement HL7 and DICOM standards. IHE uses profiles. It's the description of a process, divided for many domains, and commissions and workgroup decide the relative profile, constituted by **actors** and **transactions** . Example: LTW (Laboratory Testing Workflow), that describes the flow of materials and information, and how information leverages HIS (Hospital Information System). In the example the Ward Information System is between the HIS and the laboratory. There is an Order Placer, an Order Filler, an Order Result Tracker, and an Automation Manager. Every communication is ruled by a transaction (LAB1, LAB2, etc.) and every transaction is an HL7 v2 message, pre-compiled by the IHE profile.

## OpenEHR

After EN 13606 and CEN14822, the model for a full EHR.

