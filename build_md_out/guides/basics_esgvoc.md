```ipython3
from datetime import datetime

datetime.now()
```

# ESGVOC library tutorial

prerequesite:

```bash
pip install esgvoc  
esgvoc install # in order to get the latest CVs
```

The esgvoc library supports a wide range of use cases, including:

* Listing:<br />
  \\\\
  All data descriptors from the universe.<br />
  \\\\
  All terms of one data descriptor from the universe.<br />
  \\\\
  All available projects.<br />
  \\\\
  All collections from a project.<br />
  \\\\
  All terms from a project.<br />
  \\\\
  All terms of a collection from a project.
* Validating an input string against:<br />
  \\\\
  All terms of a project.<br />
  \\\\
  All terms of a collection from a project.<br />
  \\\\
  All terms from all projects (cross-validation).

## Universe and projects organization

The universe CV (Controlled Vocabularies) follows this organizational pattern:

```bash
<universe><DataDescriptor><Term>
```

Similarly, all CVs are organized as:

```bash
<project><collection><Term>   
```

## ESGVOC API organization

The API functions are sorted as follows:

- **get** functions return a list of something based on an id (collections from a project, terms from a collection, etc.)
- **find** functions try to find terms, data descriptors or collections corresponding to an expression.
- **valid** functions check the compliance of an input string to the DRS of terms.

```ipython3
import esgvoc.api as ev
```

## Universe

### Listing

```ipython3
ev.get_all_data_descriptors_in_universe()
```

```ipython3
ev.get_all_terms_in_data_descriptor(data_descriptor_id="activity")[:3]
# each datadescriptor from the above cell could be use as argument
# [:3] just to limit the result with the 3 first one
```

```ipython3
ev.get_term_in_data_descriptor(data_descriptor_id="activity", term_id="aerchemmip")
```

### Little detour: pydantic model instance return

The result of the previous call is a list of instances of a pydantic model of the requested data descriptor. From the above example, the result is an **Activity** object that can be query directly in Python.

```ipython3
my_activity = ev.get_term_in_data_descriptor(data_descriptor_id="activity", term_id="aerchemmip")
print(my_activity.id)
print(my_activity.drs_name)
print(my_activity.long_name)
print(my_activity)
```

```myst-ansi
aerchemmip
AerChemMIP
Aerosols and Chemistry Model Intercomparison Project
id='aerchemmip' type='activity' drs_name='AerChemMIP' name='AerChemMIP' long_name='Aerosols and Chemistry Model Intercomparison Project' url=None @context='000_context.jsonld' cmip_acronym='AerChemMIP'
```

```ipython3
ev.get_term_in_universe(term_id="aerchemmip") # give the same result as above
```

### Find terms in universe

The find functions perform full text search (FTS) over terms or data descriptor specs. They accept expressions composed not only of keywords but boolean operators that relate them together. The result is sorted according to the hit rank (bm25): the first term in the list is the better match (index zero).

```ipython3
# The headquarter of the institution IPSL and the CNES are both located in Paris.
# We want to find the term which corresponds to the IPSL institution, but not the CNES one:
ev.find_terms_in_data_descriptor(expression='pArIs NOT CNES',
                                 data_descriptor_id='institution',
                                 selected_term_fields=['location'])
```

```ipython3
# We can also search in the whole universe, but expect to find many more terms:
ev.find_terms_in_universe(expression='pArIs NOT CNES',
                          selected_term_fields=['location'])
```

### Find terms or data decriptors in universe

```ipython3
# We want to find the data descriptors time_range and its terms:
ev.find_items_in_universe(expression='time_range')
```

## Project example: CMIP6plus

The API provides the same functions for the projects (get, find) and adds the validation functions.

```ipython3
ev.get_all_projects()
```

```ipython3
ev.get_all_collections_in_project(project_id="cmip6plus")
```

```ipython3
ev.get_all_terms_in_collection(project_id="cmip6plus", collection_id="activity_id")
```

```ipython3
ev.get_term_in_collection(project_id="cmip6plus", collection_id="activity_id", term_id="cmip")
```

### Find terms in a project

```ipython3
# We want to find all the term related to miroc:
ev.find_terms_in_project(expression='mir*', project_id='cmip6plus', selected_term_fields=[])
```

### Find terms and collections

```ipython3
# We want to find the collection named 'institution_id'
items_found = ev.find_items_in_project(expression='instit*', project_id='cmip6plus')
print(f'number of items: {len(items_found)}')
for item in items_found:
    if item.kind == 'collection':
        break
print(item)
```

```myst-ansi
number of items: 41
id='institution_id' kind=<ItemKind.COLLECTION: 'collection'> parent_id='cmip6plus'
```

```ipython3
# But we probably should execute this function:
ev.find_collections_in_project(expression='instit*', project_id='cmip6plus')
```

## Validating string against the project CV

```ipython3
valid_string = "IPSL" # the standard name of the institution : "Institut Pierre Simon Laplace"
unvalid_string = "ipsl" # NOT the DRS name ! but in that case it is the 'id' of the term
```

### Queries based on the project and the collection ids

```ipython3
ev.valid_term_in_collection(value=valid_string, project_id="cmip6plus", collection_id="institution_id")
```

```ipython3
ev.valid_term_in_collection(value=unvalid_string, project_id="cmip6plus", collection_id="institution_id")
```

```ipython3
if ev.valid_term_in_collection(value=valid_string, project_id="cmip6plus", collection_id="institution_id"):
    print("Valid")
else:
    print("Unvalid")
```

```myst-ansi
Valid
```

```ipython3
if ev.valid_term_in_collection(value=unvalid_string, project_id="cmip6plus", collection_id="institution_id"):
    print("Valid")
else:
    print("Unvalid")
```

```myst-ansi
Unvalid
```

### Queries based only on the project id

```ipython3
ev.valid_term_in_project(value=valid_string, project_id="cmip6plus")
```

### Across all projects

```ipython3
print(ev.valid_term_in_all_projects(value=valid_string))
print(ev.valid_term_in_all_projects(value=unvalid_string))
```

```myst-ansi
[MatchingTerm(project_id='cmip6', collection_id='institution_id', term_id='ipsl'), MatchingTerm(project_id='cmip6plus', collection_id='institution_id', term_id='ipsl')]
[]
```
