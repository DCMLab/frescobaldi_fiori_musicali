![Version](https://img.shields.io/github/v/release/DCMLab/frescobaldi_fiori_musicali?display_name=tag)
[![DOI](https://zenodo.org/badge/{{ zenodo_badge_id }}.svg)](https://doi.org/{{ concept_doi }})
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/frescobaldi_fiori_musicali)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/frescobaldi_fiori_musicali](https://github.com/DCMLab/frescobaldi_fiori_musicali) and the corresponding
* documentation page [https://dcmlab.github.io/frescobaldi_fiori_musicali](https://dcmlab.github.io/frescobaldi_fiori_musicali)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/frescobaldi_fiori_musicali/introduction).

# Girolamo Frescobaldi (1583-1643) – Fiori Musicali, op. 12 (1635)

Frescobaldi, sometimes organist at St. Peter's Basilica in Rome, composed Fiori Musicali near the beginning of the last
of these appointments, under the patronage of Pope Urban VIII. These three organ masses, using borrowed chant melodies
in the Renaissance practice, are fairly early examples of a genre that would become much more common in the Baroque, and
were regarded for centuries afterward as examples of technical perfection in composition. Johann Joseph Fux incorporated
portions of this work into his Gradus ad Parnassum as examples of supreme contrapuntal perfection. Our annotations show
the intricacy of harmonic successions created by Frescobaldi's elegant modal counterpoint.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/frescobaldi_fiori_musicali/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [frescobaldi_fiori_musicali.zip](https://github.com/DCMLab/frescobaldi_fiori_musicali/releases/latest/download/frescobaldi_fiori_musicali.zip)
  * [frescobaldi_fiori_musicali.datapackage.json](https://github.com/DCMLab/frescobaldi_fiori_musicali/releases/latest/download/frescobaldi_fiori_musicali.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/frescobaldi_fiori_musicali.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first piece, *Toccata avanti la Messa della Domenica* has the following files:

* `MS3/12.01_Toccata_avanti_la_Messa_della_Domenica.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/12.01_Toccata_avanti_la_Messa_della_Domenica.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/12.01_Toccata_avanti_la_Messa_della_Domenica.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/12.01_Toccata_avanti_la_Messa_della_Domenica.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/12.01_Toccata_avanti_la_Messa_della_Domenica.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/12.01_Toccata_avanti_la_Messa_della_Domenica.harmonies.tsv")
notes = ms3.load_tsv("notes/12.01_Toccata_avanti_la_Messa_della_Domenica.notes.tsv"")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/frescobaldi_fiori_musicali/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/frescobaldi_fiori_musicali/issues) and/or feel free to fork and submit pull requests.

## Cite as

_Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Girolamo Frescobaldi (1583-1643) – Fiori Musicali, op. 12 (1635) [Data set]. Zenodo. https://doi.org/{{ concept_doi }}_

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Scores

This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards). It represents the three organ masses and
two capriccios of Fiori musicali, the composer Frescobaldi's magnum opus and only principally liturgical work, written
during his tenure as the organist of St. Peter's Basilica. These pieces use Gregorian chants and folk melodies as the
basis for complex contrapuntal settings. The annotation standard produced distinctive results when applied to this
late-Renaissance/early-Baroque material, as the pieces in this set make extensive use of modal minor (lacking a #7
leading tone) and generally lack functional cadences. Several movements, such as `12.31_Toccata_per_l'Elevatione`,
employ an experimental variation of the standard to accommodate the Phrygian mode.

These organ scores were created by MuseScore engraver [Gil Martinez](https://musescore.com/user/11977961) and correspond
most closely to the 1955 Bärenreiter editions. Small instrumentation edits included in the scores to optimize playback
were removed for purposes of this corpus.


### Messa della Domenica

| title                                                             | catalogue_no | filename                                          |
|-------------------------------------------------------------------|--------------|---------------------------------------------------|
| 01. Toccata avanti la Messa della Domenica                        | F 12.01      | 12.01_Toccata_avanti_la_Messa_della_Domenica.mscx |
| 02. Kyrie della domenica                                          | F 12.02      | 12.02_Kyrie_della_domenica.mscx                   |
| 03. Kyrie                                                         | F 12.03      | 12.03_Kyrie,_Tema_A.mscx                          |
| 04. Christe                                                       | F 12.04      | 12.04_Christe,_Tema_B.mscx                        |
| 05. Christe alio modo                                             | F 12.05      | 12.05_Christe,_Tema_B,_alio_modo.mscx             |
| 06. Christe alio modo                                             | F 12.06      | 12.06_Christe,_Tema_B,_alio_modo_II.mscx          |
| 07. Christe alio modo                                             | F 12.07      | 12.07_Christe,_Tema_B,_alio_modo_III.mscx         |
| 08. Kyrie                                                         | F 12.08      | 12.08_Kyrie,_Tema_C.mscx                          |
| 09. Kyrie alio modo                                               | F 12.09      | 12.09_Kyrie,_Tema_D,_alio_modo_I.mscx             |
| 10. Kyrie alio modo                                               | F 12.10      | 12.10_Kyrie,_Tema_D,_alio_modo_II.mscx            |
| 11. Kyrie ultimo                                                  | F 12.11      | 12.11_Kyrie_ultimo.mscx                           |
| 12. Kyrie alio modo                                               | F 12.12      | 12.12_Kyrie,_Tema_D,_alio_modo_III.mscx           |
| 13. Kyrie alio modo                                               | F 12.13      | 12.13_Kyrie,_Tema_D,_alio_modo_IV.mscx            |
| 14. Canzon dopo l’Epistola                                        | F 12.14      | 12.14_Canzon_dopo_l’Epistola.mscx                 |
| 15. Recercar dopo il Credo                                        | F 12.15      | 12.15_Recercar_dopo_il_Credo.mscx                 |
| 16. Toccata cromaticha per l’elevatione                           | F 12.16      | 12.16_Toccata_cromaticha_per_l’elevatione.mscx    |
| 17. Canzon post il Comune                                         | F 12.17      | 12.17_Canzon_post_il_Comune.mscx                  |

### Messa delli Apostoli

| title                                        | catalogue_no | filename                                        |
|----------------------------------------------|--------------|-------------------------------------------------|
| 18. Toccata avanti la Messa delli Apostoli   | F 12.18      | 12.18_Toccata_avanti_la_Messa_delli_Apostoli    |
| 19. Kyrie delli Apostoli                     | F 12.19      | 12.19_Kyrie,_Tema_E_1                           |
| 20. Kyrie                                    | F 12.20      | 12.20_Kyrie,_Tema_E_2                           |
| 21. Kyrie                                    | F 12.21      | 12.21_Kyrie,_Tema_E_3                           |
| 22. Christe                                  | F 12.22      | 12.22_Christe,_Tema_F_1                         |
| 23. Christe                                  | F 12.23      | 12.23_Christe,_Tema_F_2                         |
| 24. Kyrie                                    | F 12.24      | 12.24_Kyrie,_Tema_G_1                           |
| 25. Kyrie                                    | F 12.25      | 12.25_Kyrie,_Tema_G_2                           |
| 26. Kyrie                                    | F 12.26      | 12.26_Kyrie,_Tema_H                             |
| 27. Canzon dopo l'Epistola                   | F 12.27      | 12.27_Canzon_dopo_l'Epistola                    |
| 28. Toccata avanti il Recercar               | F 12.28      | 12.28_Toccata_avanti_il_Recercar                |
| 29. Recercar cromaticho post il Credo        | F 12.29      | 12.29_Recercar_cromaticho_post_il_Credo         |
| 30. Altro Recercar                           | F 12.30      | 12.30_Alto_recercar                             |
| 31. Toccata per l'elevatione                 | F 12.31      | 12.31_Toccata_per_l'Elevatione                  |
| 32. Recercar con obligo del basso come apare | F 12.32      | 12.32_Recercar_con_obligo_del_Basso_come_appare |
| 33. Canzon quarti toni dopo il post Comune   | F 12.33      | 12.33_Canzon_quarti_toni_dopo_il_post_Comune    |
| 34. Toccata avanti la Messa della Madonna    | F 12.34      | 12.34_Toccata_avanti_la_Messa_della_Madonna     |

### Messa della Madonna

| title                                                             | catalogue_no | filename                                                                |
|-------------------------------------------------------------------|--------------|-------------------------------------------------------------------------|
| 35. Kyrie della Madonna                                           | F 12.35      | 12.35_Kyrie,_Tema_I                                                     |
| 36. Kyrie                                                         | F 12.36      | 12.36_Kyrie,_Tema_K                                                     |
| 37. Christe                                                       | F 12.37      | 12.37_Christe,_Tema_L                                                   |
| 38. Christe                                                       | F 12.38      | 12.38_Christe,_Tema_M                                                   |
| 39. Kyrie                                                         | F 12.39      | 12.39_Kyrie,_Tema_N                                                     |
| 40. Kyrie                                                         | F 12.40      | 12.40_Kyrie,_Tema_O                                                     |
| 41. Canzon dopo l’Epistola                                        | F 12.41      | 12.41_Canzon_dopo_l'Epistola                                            |
| 42. Recercar dopo il Credo                                        | F 12.42      | 12.42_Recercar_dopo_il_Credo                                            |
| 43. Toccata avanti il Recercar                                    | F 12.43      | 12.43_Toccata_avanti_il_Recercar                                        |
| 44. Recercar con obligo di cantare la quinta parte senza toccarla | F 12.44      | 12.44_Recercar_con_obligo_di_cantare_la_quinta_parte_non_senza_toccarla |
| 45. Toccata per l’elevatione                                      | F 12.45      | 12.45_Toccata_per_l'Elevatione                                          |
| 46. Bergamasca                                                    | F 12.46      | 12.46_Bergamasca                                                        |
| 47. Capriccio sopra la Girolmeta                                  | F 12.47      | 12.47_Capriccio_sopra_la_Girolmeta                                      |

## Source

Transcribed by musescore.com user [SpaceGuru5](https://musescore.com/user/11977961).

Source files as of 2020-12-21:

| URL                                                | filename                           | license |
|----------------------------------------------------|------------------------------------|---------|
| https://musescore.com/user/11977961/scores/5563581 | 12.34-47_Messa_della_Madonna.mscx  | None    |
| https://musescore.com/user/11977961/scores/5552416 | 12.18-33_Messa_delli_Apostoli.mscx | CC0     |
| https://musescore.com/user/11977961/scores/5317011 | 12.01-17_Messa_della_Domenica.mscx | CC0     |

## Alternative annotations

Adrian Nagel has created an alternative version of the annotations for `12.16_Toccata_cromaticha_per_l’elevatione`
which considers the key to be E (phrygian). This was achieved in an additional copy of the score which is present in 
the Git history as `12.16_Toccata_cromaticha_per_l’elevatione_phrygian` up until commit 0f4bdb9a. The annotation 
file is still present as `harmonies/12.16_Toccata_cromaticha_per_l’elevatione_phrygian.harmonies.tsv`.
However, the columns related to chord tones have been manually removed because the ms3 parser currently supports 
creating them only for major and minor keys (that is, everything related to scale degree 2 would be incorrect).


## Overview
|                               file_name                               |measures|labels|
|-----------------------------------------------------------------------|-------:|-----:|
|12.01_Toccata_avanti_la_Messa_della_Domenica                           |       8|    57|
|12.02_Kyrie_della_domenica                                             |      13|    60|
|12.03_Kyrie,_Tema_A                                                    |      17|    66|
|12.04_Christe,_Tema_B                                                  |      15|    47|
|12.05_Christe,_Tema_B,_alio_modo                                       |       8|    47|
|12.06_Christe,_Tema_B,_alio_modo_II                                    |      21|    46|
|12.07_Christe,_Tema_B,_alio_modo_III                                   |      14|    35|
|12.08_Kyrie,_Tema_C                                                    |      13|    54|
|12.09_Kyrie,_Tema_D,_alio_modo_I                                       |      21|    63|
|12.10_Kyrie,_Tema_D,_alio_modo_II                                      |      18|    52|
|12.11_Kyrie_ultimo                                                     |      19|    65|
|12.12_Kyrie,_Tema_D,_alio_modo_III                                     |      12|    84|
|12.13_Kyrie,_Tema_D,_alio_modo_IV                                      |      21|    48|
|12.14_Canzon_dopo_l’Epistola                                           |      59|   211|
|12.15_Recercar_dopo_il_Credo                                           |      47|   162|
|12.16_Toccata_cromaticha_per_l’elevatione                              |      53|   199|
|12.17_Canzon_post_il_Comune                                            |      80|   213|
|12.18_Toccata_avanti_la_Messa_delli_Apostoli                           |      21|    74|
|12.19_Kyrie,_Tema_E_1                                                  |      16|    46|
|12.20_Kyrie,_Tema_E_2                                                  |      17|    64|
|12.21_Kyrie,_Tema_E_3                                                  |      10|    45|
|12.22_Christe,_Tema_F_1                                                |      13|    43|
|12.23_Christe,_Tema_F_2                                                |      14|    52|
|12.24_Kyrie,_Tema_G_1                                                  |      27|    51|
|12.25_Kyrie,_Tema_G_2                                                  |      20|    65|
|12.26_Kyrie,_Tema_H                                                    |      20|    63|
|12.27_Canzon_dopo_l'Epistola                                           |      68|   210|
|12.28_Toccata_avanti_il_Recercar                                       |      13|    60|
|12.29_Recercar_cromaticho_post_il_Credo                                |      70|   248|
|12.30_Alto_recercar                                                    |      81|   319|
|12.31_Toccata_per_l'Elevatione                                         |      33|   132|
|12.32_Recercar_con_obligo_del_Basso_come_appare                        |      64|   219|
|12.33_Canzon_quarti_toni_dopo_il_post_Comune                           |      58|   207|
|12.34_Toccata_avanti_la_Messa_della_Madonna                            |      12|    38|
|12.35_Kyrie,_Tema_I                                                    |      12|    42|
|12.36_Kyrie,_Tema_K                                                    |      13|    46|
|12.37_Christe,_Tema_L                                                  |      14|    61|
|12.38_Christe,_Tema_M                                                  |      12|    40|
|12.39_Kyrie,_Tema_N                                                    |      12|    34|
|12.40_Kyrie,_Tema_O                                                    |       9|    53|
|12.41_Canzon_dopo_l'Epistola                                           |      49|   126|
|12.42_Recercar_dopo_il_Credo                                           |      46|   156|
|12.43_Toccata_avanti_il_Recercar                                       |      14|    38|
|12.44_Recercar_con_obligo_di_cantare_la_quinta_parte_non_senza_toccarla|      59|   202|
|12.45_Toccata_per_l'Elevatione                                         |      24|    86|
|12.46_Bergamasca                                                       |     124|   415|
|12.47_Capriccio_sopra_la_Girolmeta                                     |     102|   375|


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
