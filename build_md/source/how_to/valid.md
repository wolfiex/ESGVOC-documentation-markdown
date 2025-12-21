# Valid

The command valid check if a string input correspond to a term drs_name attribute or not. This feature can be use in CLI and API.

## Knowing the term id:

Command line interface

```bash
esgvoc valid IPSL cmip6:institution_id:ipsl
```

![image](source/_static/CLI_Valid_term.png)

#### NOTE
IPSL is the drs_name of the term with id ipsl therefore the valid command return “True”.

API as python lib

```python
import esgvoc.api as ev

ev.valid_term("IPSL","cmip6","institution_id","ipsl")
```

![image](source/_static/API_Valid_Term.png)

#### NOTE
The API returns a DrsValidationReport Object. The \_\_str_\_ dunder function reports errors if any. The \_\_bool_\_ dunder function permits to use result in if statement.

## Knowing the only the collection id:

Command line interface

```bash
esgvoc valid IPSL cmip6:institution_id:
```

![image](source/_static/CLI_Valid_collection.png)

#### NOTE
This command looks for the drs_name in every term in the specified collection.

API as python lib

```python
import esgvoc.api as ev

ev.valid_term_collection("IPSL","cmip6","institution_id")
```

![image](source/_static/API_Valid_collection.png)

#### NOTE
The function ev.valid_term_collection returns a list of MatchingTerm.

## Knowing the only the project id:

Command line interface

```bash
esgvoc valid IPSL cmip6::
```

![image](source/_static/CLI_Valid_project.png)

#### NOTE
This command looks for the drs_name in every term in the specified project. Therefore, it could be pretty long compared to the above functions.

API as python lib

```python
import esgvoc.api as ev

ev.valid_term_project("IPSL","cmip6")
```

![image](source/_static/API_Valid_project.png)

#### NOTE
The function ev.valid_term_project returns a list of MatchingTerm.

## Find it in all known projects

Command line interface

```bash
esgvoc valid IPSL ::
```

![image](source/_static/CLI_Valid_all_project.png)

#### NOTE
This command looks for the drs_name in every project. Therefore, it could be pretty long compared to the above functions.

API as python lib

```python
import esgvoc.api as ev

ev.valid_term_in_all_projects("IPSL")
```

![image](source/_static/API_Valid_all_project.png)

#### NOTE
The function ev.valid_term_in_all_projects returns a list of MatchingTerm.
