# Universe

## Get and find functions

### esgvoc.api.universe.find_data_descriptors_in_universe(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)]]

Find data descriptors in the universe based on a full text search defined by the given expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of data descriptor ids and contexts, sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
If the provided expression does not hit any data descriptor, the function returns an empty list.
The function searches for the expression in the data descriptor specifications.
However, if only_id is True (default is False), the search is restricted to the id of the
data descriptors. **At the moment, \`only_id\` is set to \`True\` as the data descriptors
haven’t got any description.**

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
* **Returns:**
  A list of data descriptor ids and contexts. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)]]
* **Raises:**
  [**EsgvocValueError**](miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.universe.find_items_in_universe(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[Item](miscellaneous.md#esgvoc.api.search.Item)]

Find items, at the moment terms and data descriptors, in the universe based on a full-text
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
If the provided expression does not hit any item, the function returns an empty list.
The function searches for the expression in the term and data descriptor specifications.
However, if only_id is True (default is False), the search is restricted to the id of the
terms and data descriptors. **At the moment, \`only_id\` is set to \`True\` for the data descriptors
because they haven’t got any description.**

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
* **Returns:**
  A list of item instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[Item](miscellaneous.md#esgvoc.api.search.Item)]
* **Raises:**
  [**EsgvocValueError**](miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.universe.find_terms_in_data_descriptor(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Find terms in the given data descriptor based on a full-text search defined by the given expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of term instances sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
This function performs an exact match on the data_descriptor_id,
and does not search for similar or related data descriptor.
If the provided expression does not hit any term or the given data_descriptor_id does not
match exactly to an id of a data descriptor, the function returns an empty list.
The function searches for the expression in the term specifications.
However, if only_id is True (default is False), the search is restricted to the id of the terms.

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]
* **Raises:**
  [**EsgvocValueError**](miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.universe.find_terms_in_universe(expression: [str](https://docs.python.org/3/library/stdtypes.html#str), only_id: [bool](https://docs.python.org/3/library/functions.html#bool) = False, limit: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, offset: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None) = None, selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Find terms in the universe based on a full-text search defined by the given expression.
The expression can be composed of one or multiple keywords.
The keywords can combined with boolean operators: AND,
OR and NOT (case sensitive). The keywords are separated by whitespaces,
if no boolean operators is provided, whitespaces are handled as if there were
an implicit AND operator between each pair of keywords. Note that this
function does not provide any priority operator (parenthesis).
Keywords can define prefixes when adding a \* at the end of them.
If the expression is composed of only one keyword, the function
automatically defines it as a prefix.
The function returns a list of term instances sorted according to the
bm25 ranking metric (list index 0 has the highest rank).
If the provided expression does not hit any term, the function returns an empty list.
The function searches for the expression in the term specifications.
However, if only_id is True (default is False), the search is restricted to the id of the terms.

* **Parameters:**
  * **expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The full text search expression.
  * **only_id** ([*bool*](https://docs.python.org/3/library/functions.html#bool)) – Performs the search only on ids, otherwise on all the specifications.
  * **limit** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Limit the number of returned items found. Returns all items found the if     limit is either None, zero or negative.
  * **offset** ([*int*](https://docs.python.org/3/library/functions.html#int) *|* *None*) – Skips offset number of items found. Ignored if offset is     either None, zero or negative.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]
* **Raises:**
  [**EsgvocValueError**](miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – If the expression cannot be interpreted.

### esgvoc.api.universe.get_all_data_descriptors_in_universe() → [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]

Gets all the data descriptors of the universe.

* **Returns:**
  A list of data descriptor ids.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]

### esgvoc.api.universe.get_all_terms_in_data_descriptor(data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Gets all the terms of the given data descriptor.
This function performs an exact match on the data_descriptor_id and does not search
for similar or related descriptors.
If the provided data_descriptor_id is not found, the function returns an empty list.

* **Parameters:**
  * **data_descriptor_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A data descriptor id
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  a list of term instances. Returns an empty list if no matches are found.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

### esgvoc.api.universe.get_all_terms_in_universe(selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

Gets all the terms of the universe.
Terms are unique within a data descriptor but may have some synonyms in the universe.

* **Parameters:**
  **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A list of term instances.
* **Return type:**
  [list](https://docs.python.org/3/library/stdtypes.html#list)[[DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)]

### esgvoc.api.universe.get_data_descriptor_in_universe(data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)] | [None](https://docs.python.org/3/library/constants.html#None)

Returns the id and the context of the data descriptor, in the universe whose, id corresponds
exactly to the given data descriptor id.
This function performs an exact match on the data_descriptor_id and does not
search for similar or related data descriptors.
If the provided data_descriptor_id is not found, the function returns None.

* **Parameters:**
  **data_descriptor_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – An id of a data descriptor to be found.
* **Returns:**
  The data descriptor id and context. Returns None if no match is found.
* **Return type:**
  [tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [dict](https://docs.python.org/3/library/stdtypes.html#dict)] | None

### esgvoc.api.universe.get_term_in_data_descriptor(data_descriptor_id: [str](https://docs.python.org/3/library/stdtypes.html#str), term_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | [None](https://docs.python.org/3/library/constants.html#None)

Returns the term, in the given data descriptor, whose id corresponds exactly to the given term id.
This function performs an exact match on the term_id and the data_descriptor_id and does
not search for similar or related terms and data descriptors.
If the provided term_id is not found, the function returns None.

* **Parameters:**
  * **data_descriptor_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given data descriptor.
  * **term_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of a term to be found.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A term instance. Returns None if no match is found.
* **Return type:**
  [DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | None

### esgvoc.api.universe.get_term_in_universe(term_id: [str](https://docs.python.org/3/library/stdtypes.html#str), selected_term_fields: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None) = None) → [DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | [None](https://docs.python.org/3/library/constants.html#None)

Returns the first occurrence of the terms, in the universe, whose id corresponds exactly to
the given term id.
Terms are unique within a data descriptor but may have some synonyms in the universe.
This function performs an exact match on the term_id and does not search
for similar or related terms. If the provided term_id is not found, the function returns None.

* **Parameters:**
  * **term_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of a term to be found.
  * **selected_term_fields** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*  *|* *None*) – A list of term fields to select or None. If None, all the     fields of the terms are returned. If empty, selects the id and type fields.
* **Returns:**
  A term instance. Returns None if no match is found.
* **Return type:**
  [DataDescriptor](data_descriptors.md#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor) | None
