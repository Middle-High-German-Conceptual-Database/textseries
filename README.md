mhdbdb text series - Textreihentypologie (v. 0.1, 05/2023)
=====================================================================================

mhdbdb text series is an application-oriented thesaurus that can be used to classify and annotate resources in order to derive various benefits from them: For example, the indexing of sources, consideration in web user interfaces, the enrichment of bibliographic metadata/norm data and, last but not least, an expansion of the method inventory and improved contextualisation overall.


Repository content
------------------

* `skos`: machine-readable version in SKOS
* See also the project website at [http://www.mhdbdb.sbg.ac.at/textreihen](http://www.marketext.at/Textreihentypologie)

How To
-----------------------
1. 
Each data entry has an ID that can be uniquely referenced in the Semantic Web, for example:
| SKOS label | ID |
|----------|----------|
| Dietrichsepik    | c_f3e5cee1   |
| Marienleich    | c_dacec895   | 
| Losbuch    | c_d21adda7   | 

2.
If required, each work which is annotated with the SKOS vocabulary can also be assigned more than one text series entry, for example:
| Work | SKOS / exact classification 1 (*genreForm*) | SKOS / exact classification 2 (*genreForm*) |
|----------|----------|----------|
| Stricker: Die Gäuhühner    | Bîspel (c_8bb910cf)   | Allegorie (c_dd3320dc)   |
| Sebastian Brant: Das Narrenschiff    | Schwankroman (c_535c3395)   | Großdidaxe (c_60bae378)   |
| Honorius Augustodunensis: Elucidarium, dt. (Auswahlübersetzung)   | Enzyklopädie (c_6e09fcd0)   | Pastorales Handbuch (c_d11208c0)   |

3.
For data entries that have several origins, no generally valid decision has to be made in this way. For example, "Calendars" can be accessed via "Astronomy and Astrology" as well as via "Special Medial Forms".
What sounds simple in the theory of text series systematics, however, turns out to be a challenge in the practical annotation application. The following approach offers a solution:
Each work needs (at least) one main form and one associated distinct origin in the tree, for example:
| Work | SKOS / exact classification 1 (*genreForm*) | SKOS / distinct origin of 1 (*genreFormMainparent*) | SKOS / exact classification 2 (*genreForm*) | SKOS / distinct origin of 2 (*genreFormMainparent*) |
|----------|----------|----------|----------|----------|
| Stricker: Vaterunser    | Vaterunser (c_707350eb)   | Dialogische Kurzform (c_01bf2b8b)   |
| Wach uff myn hort (Rostocker Liederbuch)    | Tagelied (c_2e829572)   | Liederbuchlyrik (c_76c0e2b7)   |
| Hans Folz: Bäderbüchlein   | Bäderschrift (c_6a30d34d)   | Texte zur Behandlung von Krankheiten (c_97d95287)   | Bäderschrift (c_6a30d34d) | Reiseliteratur (c_90d500db) |

We recommend using the already existing BIBFRAME (Bibliographic Framework) property "genre" and the attribute "genreForm" for ontologies in the sense of better machine readability and interoperability in the Semantic Web - although strictly speaking we are not talking about genres, but about text series. However, this is not problematic in this case, a machine does not discuss what the difference between genre and text series is, but only reads out identifiers.
Works (in the Semantic Web mostly classes) therefore always get two new properties, for example:
- *genreForm* (exact assignment 1-n)
- *genreFormMainparent* (distinct origin of 1-n)

For example, the triples are formed as follows:
| <!-- -->      | <!-- -->        | <!-- -->      |
|:-------------:|:---------------:|:-------------:|
| [Stricker: Vaterunser]    | [is genreForm]   | [Vaterunser (c_707350eb)]   |
| [Stricker: Vaterunser]    | [has genreFormMainparent]   | [Dialogische Kurzform (c_01bf2b8b)]   |

Coordinators
------------
* Katharina Zeppezauer-Wachauer, Salzburg, Austria
* Marco Heiles, Hamburg, Germany

Contributors
------------
* Peter Färberböck, Salzburg, Austria
* Julia Höpfner, Darmstadt, Germany
* Leonie Weiss, Darmstadt, Germany

Projects using mhdbdb text series
-------------------------
* [Mittelhochdeutsche Begriffsdatenbank](http://www.mhdbdb.sbg.ac.at)
* … more in preparation

Reference publication (please cite when using mhdbdb text series!)
-----------------------------------------
* [Mittelalterblog](https://mittelalter.hypotheses.org/)

Good to know
------------
Let us make one thing clear: Nothing we publish here is set in stone. Everything is negotiable. More specifically, we explicitly ask the research community to collectively improve the beta version of our model. We appeal to demystify the development process of such a project and to make it collaborative, transparent and with the courage to use swarm intelligence and heuristics. Experts in the respective fields may contribute their knowledge to make this typology better for all. In this sense, we also ask - rather untypically for the current professional discourse - that criticism be packaged in constructive suggestions: What concrete changes would help to improve it?
Please use the issue tracker here on GitHub or write us an email: katharina.wachauer@plus.ac.at or marco.heiles@uni-hamburg.de.
