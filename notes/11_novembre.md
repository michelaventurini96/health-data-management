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

# concepts

a dictionary is a list of **concepts**. They can have a **descriptive definition** and a **computable definition** (as list of attributes). A term can be a single (heart, diabetes,...) or aggregated concept (familiy history of heart attack, circulation, degenerative extrapiramidal disease...).

In dictionaries can be pre-coordinated or post-coordinated. Pre-coordinated has complete non-ambiguity. It eliminates every nonsense combination of atomic concepts, but it can be redundant and requires to be domain-savvy, requiring a sistematic approach to the WHOLE domain. Usually employed in administrative tasks. Post coordinated are flexible, non redundant, but the information is not univoc anymore. Preferrable in clinical and diagnostic tasks, where a single task is described by many and many different terms("test a/a + liquor + one sampling + flocculation" = an antigen/antibody test made on a cerebrospinal sample taken in a single sample and analized by flocculation).

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