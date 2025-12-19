# Get

## One term

Command line interface

```bash
esgvoc get universe:institution:ipsl
```

![image](_static/one_term.png)

#### NOTE
It is possible to submit multiple requests with the same command:

esgvoc get universe:institution:ipsl universe:institution:llnl

API as python lib

```python
import esgvoc.api as ev

ev.get_term_in_data_descriptor(data_descriptor_id="institution", term_id="ipsl")
ev.get_term_in_universe(term_id="ipsl") # same result but slower but still fast
```

![image](_static/Jup_one_term.png)

## All terms from one data descriptor or collection

Command line interface

```bash
esgvoc get universe:institution:
```

![image](_static/all_term_from_one_collection.png)

#### NOTE
It is possible to submit multiple requests with the same command:

esgvoc get universe:institution: cmip6:institution_id: cmip6:grid_label:

API as python lib

```python
import esgvoc.api as ev

ev.get_all_terms_in_data_descriptor("institution")
ev.get_all_terms_in_collection("cmip6","institution_id")
```

![image](_static/Jup_terms_from_one_dd.png)![image](_static/Jup_terms_from_one_collection.png)

#### NOTE
In the universe, a data descriptor is the equivalent to a collection in a project.

The final information are contained in data descriptors, terms in collections are references to their opposites in data descriptors with optional and/or additional information.

## A term from a CV

Command line interface

```bash
esgvoc get universe::ipsl
esgvoc get cmip6::ipsl
```

![image](_static/one_term_from_one_cv.png)

#### NOTE
The term ipsl is the same in cmip6 (institution_id) and in universe (institution) since the cmip6 one refers to the universe one:

Try the one from cmip6plus: esgvoc get cmip6plus::ipsl. To showcase the possibility to add information in project CV term. We added a ‘myprop’ attribute in this term in cmip6plus CV.

API as python lib

```python
import esgvoc.api as ev

ev.get_term_in_universe("ipsl")
ev.get_term_in_project("cmip6", "ipsl")
ev.get_term_in_project("cmip6plus", "ipsl")
```

![image](_static/Jup_one_term_from_one_CV.png)

#### NOTE
The term ipsl is the same in cmip6 (institution_id) and in universe (institution) since the cmip6 one refers to the universe one:

Try the one from cmip6plus: esgvoc get cmip6plus::ipsl. To showcase the possibility to add information in project CV term. We added a ‘myprop’ attribute in this term in cmip6plus CV.
