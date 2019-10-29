# The Clinical Record

Before informatization, it was a physical paper folder. Modern **reference standards** derives from its informatization. See slides for 4 examples of clinical records. They were different for "Ambulatorio", "Reparto" (also among different Reparti), "Intensive Care Unit", "Medicina Interna".

Patients are different (visiting, on a bed, on recovery..), the residency has different lengths (hours/lifelong),  the reading can be manual or automatic, there could be devices, or not. and the aim can be very different (monitoring and caring a severe patient, long term risk management monitoring in "ambulatorio", diagnostics and exams archive, therapy).

Different purposes required different structures.There is also the Nurse diary. Day-to-day records, inside the clinical record.

## clinical record components

### Anagraphics in paper clinical records

Privacy issues. Marriage status entitles the partner to have informations or make decisions. There are informations about recovery dates, contacts of Medico di Base (family medic). There is a value "Bed". When hospitalized, names are taken away, for privacy, and only the bed number is used.

ADT (Ammissione, Dimissione, Trasferimento) System. Every Reparto has an admission date/time, a dimission date/time, and a transfer date/time, with the additional informations about where it was sent.

For Ambulatorio, there are no beds, so no bed number identificator. There is an extra part about recruitment (for long term monitoring) or first visit and there is no ADT. For special diseases, anagraphics can include extra infos about jobs, age (instead of birthdate), marriage status... In Internal Medicine there were still additional info (Cedola number, Ticket number, etc.)

Some data are usually **immutable**, like last name (but is it?). Most data are **dishomogeneous** and with **different granularity** (with newborns you write also the HOUR of birth, not necessary in cardiology).

Some other data are **mutable**, like phone number, job, etc. Of most mutable data, there must be a storicization (keep also past data, after change: old jobs must stay relevant for risk assessment). Traceability of the data is relevant both for **administrations** and for **diagnostics**.

So data must be recorded, but not all data is useful for all Reparti.

### Diagnosi di accettazione e di dimissione (admission and dismission diagnosis)

For acceptance the diagnosis is just one line, usually left empty. There is the signature of the Medico di Guardia. He takes the responsability of accepting the signature under that hypothesis. For dismission, Medico di Reparto, Medico Primario  AND Direttore Sanitario signs, and there is a longer text fields. In some Reparti, the diagnosis can be multi-entry (for more diagnoses), there could be localization data ("where does it hurt?"), time data ("for how long?"), and etiology. The text is not free anymore, but there is structure.

The main problem is about **information sharing**. Different medics, different words. There was no **standard terminology** (medical dictionaries). 

### Anamnesi (Patient history)

It's the big collection of history about: 

* patient family (blood family or environmental sharing): can be tabular data (diseases vs relation),
*  physiology and pathology. 