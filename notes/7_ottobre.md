# Principles of relational algebra

(tomorrow, exercises)

Definitions: in relational models: relations, tuples, attributes. In query they become tables, rows and columns.
Keys, superkeys, primary keys.

Integrity: intra- and inter-relational boundaries. Domains. Foreign keys.

NULL values can be associated to different meanings:

* not valid for current istance
* valid but not yet existing
* existing but cannot be saved
* existing but unknown
* existing but not yet saved
* stored and then deleted
* available but in an updating phase
* available but not reliable
* available but not valid
* calculated from another NULL value

Relational Algebra: SELECT, PROJECTION, CARTESIAN PRODUCT, JOIN.

Select:  $\sigma_{(field="value")} TABLE$

Projection: $\pi_{(field)} TABLE$

Union: $ R1 \cup R2$

Intersection : $ R1 \cap R2$

Difference: $ R1 - R2$

Cartesian product: $R1 \times R2$

Join : $R1 \bowtie R2$ , $R1 \bowtie_{(condition)} R2$

Rename : $R1 = \rho_{(renaming criteria)} (R2)$

