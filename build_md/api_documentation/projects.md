# Projects

## Get, find and validation functions

#### NOTE
Values are validated against the DRS name of the terms of the projects whereas find functions are based on the id of the terms.

<a id="module-esgvoc.api.projects"></a>

### esgvoc.api.projects.find_collections_in_project(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)]]

Find collections in the given project based on a full text search defined by the given expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of collection ids and contexts, sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
This function performs an exact match on the project_id,
and does not search for similar or related projects.
If the provided expression does not hit any collection or the given project_id does not
match exactly to an id of a project, the function returns an empty list.
The function searches for the expression in the collection specifications.
However, if only_id is True (default is False), the search is restricted to the id of the
collections. **At the moment, \`only_id\` is set to \`True\` as the collections
haven’t got any description.**

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
* **Returns:**
  A list of collection ids and contexts. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)]]
* **Raises:**
  [**EsgvocValueError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.projects.find_items_in_project(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[Item](../source/api_documentation/miscellaneous.md#esgvoc.api.search.Item)]

Find items, at the moment terms and collections, in the given project based on a full-text
search defined by the given expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of item instances sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
This function performs an exact match on the project_id,
and does not search for similar or related projects.
If the provided expression does not hit any item, or the provided project_id is not found,
the function returns an empty list.
The function searches for the expression in the term and collection specifications.
However, if only_id is True (default is False), the search is restricted to the id of the
terms and collections. **At the moment, \`only_id\` is set to \`True\` for the collections because
they haven’t got any description.**

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
* **Returns:**
  A list of item instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[Item](../source/api_documentation/miscellaneous.md#esgvoc.api.search.Item)]
* **Raises:**
  [**EsgvocValueError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.projects.find_terms_in_all_projects(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]]]

Find terms in all projects based on a full text search defined by the given expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of project ids and term instances, sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
If the provided expression does not hit any term, the function returns an empty list.
The function searches for the expression in the term specifications.
However, if only_id is True (default is False), the search is restricted to the id of the
terms.

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of project ids and term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]]]
* **Raises:**
  [**EsgvocValueError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.projects.find_terms_in_collection(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), collection_id: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Find terms in the given project and collection based on a full text search defined by the given
expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of term instances, sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
This function performs an exact match on the project_id and collection_id,
and does not search for similar or related projects and collections.
If the provided expression does not hit any term or if any of the provided ids
(project_id or collection_id) is not found, the function returns an empty list.
The function searches for the expression in the term specifications.
However, if only_id is True (default is False), the search is restricted to the id of the
terms.

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **collection_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given collection.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]
* **Raises:**
  [**EsgvocValueError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.projects.find_terms_in_project(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Find terms in the given project based on a full text search defined by the given expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of term instances, sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
This function performs an exact match on the project_id,
and does not search for similar or related projects.
If the provided expression does not hit any term or if any of the provided project_id is
not found, the function returns an empty list.
The function searches for the expression in the term specifications.
However, if only_id is True (default is False), the search is restricted to the id of the
terms.

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]
* **Raises:**
  [**EsgvocValueError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.projects.get_all_collections_in_project(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]

Gets all collections of the given project.
This function performs an exact match on the project_id and
does not search for similar or related projects.
If the provided project_id is not found, the function returns an empty list.

* **Parameters:**
  **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A project id
* **Returns:**
  A list of collection ids. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]

### esgvoc.api.projects.get_all_projects() → [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]

Gets all projects.

* **Returns:**
  A list of project ids.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]

### esgvoc.api.projects.get_all_terms_in_all_projects(selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]]]

Gets all terms of all projects.

* **Parameters:**
  **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of tuple project_id and term instances of that project.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]]]

### esgvoc.api.projects.get_all_terms_in_collection(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), collection_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Gets all terms of the given collection of a project.
This function performs an exact match on the project_id and collection_id,
and does not search for similar or related projects and collections.
If any of the provided ids (project_id or collection_id) is not found, the function
returns an empty list.

* **Parameters:**
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A project id
  * **collection_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A collection id
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  a list of term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

### esgvoc.api.projects.get_all_terms_in_project(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Gets all terms of the given project.
This function performs an exact match on the project_id and
does not search for similar or related projects.
Terms are unique within a collection but may have some synonyms in a project.
If the provided project_id is not found, the function returns an empty list.

* **Parameters:**
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A project id
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

### esgvoc.api.projects.get_collection_from_data_descriptor_in_all_projects(data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)]]

Returns the collections, in all projects, that correspond to the given data descriptor
in the universe.
This function performs an exact match on data_descriptor_id,
and does not search for similar or related data descriptors.
If the provided data_descriptor_id is not found, or if
there is no collection corresponding to the given data descriptor, the function returns
an empty list.

* **Parameters:**
  **data_descriptor_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given data descriptor.
* **Returns:**
  A list of collection ids, their project_ids and contexts.     Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)]]

### esgvoc.api.projects.get_collection_from_data_descriptor_in_project(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)] | [None](https://docs.python.org/3/library/constants.html#None)

Returns the collection, in the given project, that corresponds to the given data descriptor
in the universe.
This function performs an exact match on the project_id and data_descriptor_id,
and does not search for similar or related projects and data descriptors.
If any of the provided ids (project_id or data_descriptor_id) is not found, or if
there is no collection corresponding to the given data descriptor, the function returns None.

* **Parameters:**
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **data_descriptor_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given data descriptor.
* **Returns:**
  A collection id and context. Returns None if no matches are found.
* **Return type:**
  [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)] | None

### esgvoc.api.projects.get_collection_in_project(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), collection_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)] | [None](https://docs.python.org/3/library/constants.html#None)

Returns the collection, in the given project, whose id corresponds exactly to
the given collection id.
This function performs an exact match on the project_id and collection_id, and does not search
for similar or related projects and collections.
If any of the provided ids (project_id or collection_id) is not found,
the function returns None.

* **Parameters:**
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **collection_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of a collection to be found.
* **Returns:**
  A collection id and context. Returns None if no match is found.
* **Return type:**
  [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)] | None

### esgvoc.api.projects.get_project(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [ProjectSpecs](../source/api_documentation/project_specs.md#esgvoc.api.project_specs.ProjectSpecs) | [None](https://docs.python.org/3/library/constants.html#None)

Get a project and returns its specifications.
This function performs an exact match on the project_id and
does not search for similar or related projects.
If the provided project_id is not found, the function returns None.

* **Parameters:**
  **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A project id to be found
* **Returns:**
  The specs of the project found. Returns None if no matches are found.
* **Return type:**
  [ProjectSpecs](../source/api_documentation/project_specs.md#esgvoc.api.project_specs.ProjectSpecs) | None

### esgvoc.api.projects.get_term_from_universe_term_id_in_all_projects(data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str), universe_term_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str), [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]]

Returns the terms, in all projects, that correspond to the given term in the universe.
This function performs an exact match on the data_descriptor_id
and universe_term_id, and does not search for similar or related data descriptors
and terms. If any of the provided ids (data_descriptor_id or universe_term_id)
is not found, or if there is no project term corresponding to the given universe term
the function returns an empty list.

* **Parameters:**
  * **data_descriptor_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the data descriptor that contains the given universe term.
  * **universe_term_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given universe term.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A project_id, collection id and the project term instance.     Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str), [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]]

### esgvoc.api.projects.get_term_from_universe_term_id_in_project(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str), universe_term_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)] | [None](https://docs.python.org/3/library/constants.html#None)

Returns the term, in the given project, that corresponds to the given term in the universe.
This function performs an exact match on the project_id, data_descriptor_id
and universe_term_id, and does not search for similar or related projects, data descriptors
and terms. If any of the provided ids (project_id, data_descriptor_id or universe_term_id)
is not found, or if there is no project term corresponding to the given universe term
the function returns None.

* **Parameters:**
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **data_descriptor_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the data descriptor that contains the given universe term.
  * **universe_term_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given universe term.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A collection id and the project term instance. Returns None if no matches are found.
* **Return type:**
  [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)] | None

### esgvoc.api.projects.get_term_in_collection(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), collection_id: [str](https://docs.python.org/3/library/stdtypes.html#str), term_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | [None](https://docs.python.org/3/library/constants.html#None)

Returns the term, in the given project and collection,
whose id corresponds exactly to the given term id.
This function performs an exact match on the project_id, collection_id and term_id,
and does not search for similar or related projects, collections and terms.
If any of the provided ids (project_id, collection_id or term_id) is not found,
the function returns None.

* **Parameters:**
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **collection_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given collection.
  * **term_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of a term to be found.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A term instance. Returns None if no match is found.
* **Return type:**
  [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | None

### esgvoc.api.projects.get_term_in_project(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), term_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | [None](https://docs.python.org/3/library/constants.html#None)

Returns the first occurrence of the terms, in the given project, whose id corresponds exactly to
the given term id.
Terms are unique within a collection but may have some synonyms in a project.
This function performs an exact match on the project_id and term_id, and does not search
for similar or related projects and terms.
If any of the provided ids (project_id or term_id) is not found,
the function returns None.

* **Parameters:**
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
  * **term_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of a term to be found.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A term instance. Returns None if no match is found.
* **Return type:**
  [DataDescriptor](../source/api_documentation/data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | None

### esgvoc.api.projects.valid_term(value: [str](https://docs.python.org/3/library/stdtypes.html#str), project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), collection_id: [str](https://docs.python.org/3/library/stdtypes.html#str), term_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [ValidationReport](../source/api_documentation/projects.md#esgvoc.api.report.ValidationReport)

Check if the given value may or may not represent the given term. The functions returns
a report that contains the possible errors.

Behavior based on the nature of the term:
: - plain term: the function try to match the value on the drs_name field.
  - pattern term: the function try to match the value on the pattern field (regex).
  - composite term:
    : - if the composite has got a separator, the function splits the value according to the              separator of the term then it try to match every part of the composite              with every split of the value.
      - if the composite hasn’t got a separator, the function aggregates the parts of the               composite so as to compare it as a regex to the value.

If any of the provided ids (project_id, collection_id or term_id) is not found,
the function raises a EsgvocNotFoundError.

* **Parameters:**
  * **value** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A value to be validated
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A project id
  * **collection_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A collection id
  * **term_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A term id
* **Returns:**
  A validation report that contains the possible errors
* **Return type:**
  [ValidationReport](../source/api_documentation/projects.md#esgvoc.api.report.ValidationReport)
* **Raises:**
  [**EsgvocNotFoundError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocNotFoundError) – If any of the provided ids is not found

### esgvoc.api.projects.valid_term_in_all_projects(value: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[MatchingTerm](../source/api_documentation/miscellaneous.md#esgvoc.api.search.MatchingTerm)]

Check if the given value may or may not represent a term in all projects. The function
returns the terms that the value matches.

Behavior based on the nature of the term:
: - plain term: the function try to match the value on the drs_name field.
  - pattern term: the function try to match the value on the pattern field (regex).
  - composite term:
    : - if the composite has got a separator, the function splits the value according to the               separator of the term then it try to match every part of the composite               with every split of the value.
      - if the composite hasn’t got a separator, the function aggregates the parts of the               composite so as to compare it as a regex to the value.

* **Parameters:**
  **value** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A value to be validated
* **Returns:**
  The list of terms that the value matches.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[MatchingTerm](../source/api_documentation/miscellaneous.md#esgvoc.api.search.MatchingTerm)]

### esgvoc.api.projects.valid_term_in_collection(value: [str](https://docs.python.org/3/library/stdtypes.html#str), project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), collection_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[MatchingTerm](../source/api_documentation/miscellaneous.md#esgvoc.api.search.MatchingTerm)]

Check if the given value may or may not represent a term in the given collection. The function
returns the terms that the value matches.

Behavior based on the nature of the term:
: - plain term: the function try to match the value on the drs_name field.
  - pattern term: the function try to match the value on the pattern field (regex).
  - composite term:
    : - if the composite has got a separator, the function splits the value according to the               separator of the term then it try to match every part of the composite               with every split of the value.
      - if the composite hasn’t got a separator, the function aggregates the parts of the               composite so as to compare it as a regex to the value.

If any of the provided ids (project_id or collection_id) is not found,
the function raises a EsgvocNotFoundError.

* **Parameters:**
  * **value** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A value to be validated
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A project id
  * **collection_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A collection id
* **Returns:**
  The list of terms that the value matches.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[MatchingTerm](../source/api_documentation/miscellaneous.md#esgvoc.api.search.MatchingTerm)]
* **Raises:**
  [**EsgvocNotFoundError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocNotFoundError) – If any of the provided ids is not found

### esgvoc.api.projects.valid_term_in_project(value: [str](https://docs.python.org/3/library/stdtypes.html#str), project_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[MatchingTerm](../source/api_documentation/miscellaneous.md#esgvoc.api.search.MatchingTerm)]

Check if the given value may or may not represent a term in the given project. The function
returns the terms that the value matches.

Behavior based on the nature of the term:
: - plain term: the function try to match the value on the drs_name field.
  - pattern term: the function try to match the value on the pattern field (regex).
  - composite term:
    : - if the composite has got a separator, the function splits the value according to the               separator of the term then it try to match every part of the composite               with every split of the value.
      - if the composite hasn’t got a separator, the function aggregates the parts of the               composite so as to compare it as a regex to the value.

If the project_id is not found, the function raises a EsgvocNotFoundError.

* **Parameters:**
  * **value** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A value to be validated
  * **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A project id
* **Returns:**
  The list of terms that the value matches.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[MatchingTerm](../source/api_documentation/miscellaneous.md#esgvoc.api.search.MatchingTerm)]
* **Raises:**
  [**EsgvocNotFoundError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocNotFoundError) – If the project_id is not found

## Validation reporting

### *Pydantic model* esgvoc.api.report.ProjectTermError

Bases: [`ValidationError`](../source/api_documentation/projects.md#esgvoc.api.report.ValidationError)

A validation error on a term from a project.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ProjectTermError",
   "description": "A validation error on a term from a project.",
   "type": "object",
   "properties": {
      "value": {
         "title": "Value",
         "type": "string"
      },
      "term": {
         "additionalProperties": true,
         "title": "Term",
         "type": "object"
      },
      "term_kind": {
         "$ref": "#/$defs/TermKind"
      },
      "collection_id": {
         "title": "Collection Id",
         "type": "string"
      }
   },
   "$defs": {
      "TermKind": {
         "description": "The kinds of term.",
         "enum": [
            "plain",
            "pattern",
            "composite",
            "mixed"
         ],
         "title": "TermKind",
         "type": "string"
      }
   },
   "required": [
      "value",
      "term",
      "term_kind",
      "collection_id"
   ]
}
```

</details></p>

#### *field* collection_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The collection id that the term belongs

#### *field* term *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)* *[Required]*

JSON specification of the term.

#### *field* term_kind *: [TermKind](../source/api_documentation/miscellaneous.md#esgvoc.core.db.models.mixins.TermKind)* *[Required]*

The kind of term.

#### *field* value *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The given value that is invalid.

#### accept(visitor: [ValidationErrorVisitor](../source/api_documentation/projects.md#esgvoc.api.report.ValidationErrorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept a validation error visitor.

* **Parameters:**
  **visitor** ([*ValidationErrorVisitor*](../source/api_documentation/projects.md#esgvoc.api.report.ValidationErrorVisitor)) – The validation error visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* class_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)*

The class name of the issue for JSON serialization.

### *Pydantic model* esgvoc.api.report.UniverseTermError

Bases: [`ValidationError`](../source/api_documentation/projects.md#esgvoc.api.report.ValidationError)

A validation error on a term from the universe.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "UniverseTermError",
   "description": "A validation error on a term from the universe.",
   "type": "object",
   "properties": {
      "value": {
         "title": "Value",
         "type": "string"
      },
      "term": {
         "additionalProperties": true,
         "title": "Term",
         "type": "object"
      },
      "term_kind": {
         "$ref": "#/$defs/TermKind"
      },
      "data_descriptor_id": {
         "title": "Data Descriptor Id",
         "type": "string"
      }
   },
   "$defs": {
      "TermKind": {
         "description": "The kinds of term.",
         "enum": [
            "plain",
            "pattern",
            "composite",
            "mixed"
         ],
         "title": "TermKind",
         "type": "string"
      }
   },
   "required": [
      "value",
      "term",
      "term_kind",
      "data_descriptor_id"
   ]
}
```

</details></p>

#### *field* data_descriptor_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor that the term belongs.

#### *field* term *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)* *[Required]*

JSON specification of the term.

#### *field* term_kind *: [TermKind](../source/api_documentation/miscellaneous.md#esgvoc.core.db.models.mixins.TermKind)* *[Required]*

The kind of term.

#### *field* value *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The given value that is invalid.

#### accept(visitor: [ValidationErrorVisitor](../source/api_documentation/projects.md#esgvoc.api.report.ValidationErrorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept a validation error visitor.

* **Parameters:**
  **visitor** ([*ValidationErrorVisitor*](../source/api_documentation/projects.md#esgvoc.api.report.ValidationErrorVisitor)) – The validation error visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* class_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)*

The class name of the issue for JSON serialization.

### *Pydantic model* esgvoc.api.report.ValidationError

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel), [`ABC`](https://docs.python.org/3/library/abc.html#abc.ABC)

Generic class for the term validation error.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ValidationError",
   "description": "Generic class for the term validation error.",
   "type": "object",
   "properties": {
      "value": {
         "title": "Value",
         "type": "string"
      },
      "term": {
         "additionalProperties": true,
         "title": "Term",
         "type": "object"
      },
      "term_kind": {
         "$ref": "#/$defs/TermKind"
      }
   },
   "$defs": {
      "TermKind": {
         "description": "The kinds of term.",
         "enum": [
            "plain",
            "pattern",
            "composite",
            "mixed"
         ],
         "title": "TermKind",
         "type": "string"
      }
   },
   "required": [
      "value",
      "term",
      "term_kind"
   ]
}
```

</details></p>

#### *field* term *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)* *[Required]*

JSON specification of the term.

#### *field* term_kind *: [TermKind](../source/api_documentation/miscellaneous.md#esgvoc.core.db.models.mixins.TermKind)* *[Required]*

The kind of term.

#### *field* value *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The given value that is invalid.

#### *abstractmethod* accept(visitor: [ValidationErrorVisitor](../source/api_documentation/projects.md#esgvoc.api.report.ValidationErrorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept a validation error visitor.

* **Parameters:**
  **visitor** ([*ValidationErrorVisitor*](../source/api_documentation/projects.md#esgvoc.api.report.ValidationErrorVisitor)) – The validation error visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* class_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)*

The class name of the issue for JSON serialization.

### *class* esgvoc.api.report.ValidationErrorVisitor(\*args, \*\*kwargs)

Bases: [`Protocol`](https://docs.python.org/3/library/typing.html#typing.Protocol)

Specifications for a term validation error visitor.

#### visit_project_term_error(error: [ProjectTermError](../source/api_documentation/projects.md#esgvoc.api.report.ProjectTermError)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a project term error.

#### visit_universe_term_error(error: [UniverseTermError](../source/api_documentation/projects.md#esgvoc.api.report.UniverseTermError)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a universe term error.

### *Pydantic model* esgvoc.api.report.ValidationReport

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

Term validation report.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ValidationReport",
   "description": "Term validation report.",
   "type": "object",
   "properties": {
      "expression": {
         "title": "Expression",
         "type": "string"
      },
      "errors": {
         "items": {
            "anyOf": [
               {
                  "$ref": "#/$defs/UniverseTermError"
               },
               {
                  "$ref": "#/$defs/ProjectTermError"
               }
            ]
         },
         "title": "Errors",
         "type": "array"
      }
   },
   "$defs": {
      "ProjectTermError": {
         "description": "A validation error on a term from a project.",
         "properties": {
            "value": {
               "title": "Value",
               "type": "string"
            },
            "term": {
               "additionalProperties": true,
               "title": "Term",
               "type": "object"
            },
            "term_kind": {
               "$ref": "#/$defs/TermKind"
            },
            "collection_id": {
               "title": "Collection Id",
               "type": "string"
            }
         },
         "required": [
            "value",
            "term",
            "term_kind",
            "collection_id"
         ],
         "title": "ProjectTermError",
         "type": "object"
      },
      "TermKind": {
         "description": "The kinds of term.",
         "enum": [
            "plain",
            "pattern",
            "composite",
            "mixed"
         ],
         "title": "TermKind",
         "type": "string"
      },
      "UniverseTermError": {
         "description": "A validation error on a term from the universe.",
         "properties": {
            "value": {
               "title": "Value",
               "type": "string"
            },
            "term": {
               "additionalProperties": true,
               "title": "Term",
               "type": "object"
            },
            "term_kind": {
               "$ref": "#/$defs/TermKind"
            },
            "data_descriptor_id": {
               "title": "Data Descriptor Id",
               "type": "string"
            }
         },
         "required": [
            "value",
            "term",
            "term_kind",
            "data_descriptor_id"
         ],
         "title": "UniverseTermError",
         "type": "object"
      }
   },
   "required": [
      "expression",
      "errors"
   ]
}
```

</details></p>

#### *field* errors *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[UniverseTermError](../source/api_documentation/projects.md#esgvoc.api.report.UniverseTermError) | [ProjectTermError](../source/api_documentation/projects.md#esgvoc.api.report.ProjectTermError)]* *[Required]*

The validation errors.

#### *field* expression *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The given expression.

#### *property* nb_errors *: [int](https://docs.python.org/3/library/functions.html#int)*

The number of validation errors.

#### *property* validated *: [bool](https://docs.python.org/3/library/functions.html#bool)*

The expression is validated or not.
