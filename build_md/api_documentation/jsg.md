# Json schema generator

### esgvoc.apps.jsg.json_schema_generator.generate_json_schema(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [dict](https://docs.python.org/3/library/stdtypes.html#dict)

Generate json schema for the given project.

* **Parameters:**
  **project_id** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The id of the given project.
* **Returns:**
  The root node of a json schema.
* **Return type:**
  [dict](https://docs.python.org/3/library/stdtypes.html#dict)
* **Raises:**
  * [**EsgvocValueError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocValueError) – On wrong information in catalog_specs.
  * [**EsgvocNotFoundError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocNotFoundError) – On missing information in catalog_specs.
  * [**EsgvocNotImplementedError**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocNotImplementedError) – On unexpected operations resulted in wrong information in catalog_specs).
  * [**EsgvocException**](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocException) – On json compliance error.

### esgvoc.apps.jsg.json_schema_generator.pretty_print_json_node(obj: [dict](https://docs.python.org/3/library/stdtypes.html#dict)) → [str](https://docs.python.org/3/library/stdtypes.html#str)

Serialize a dictionary into json format.

* **Parameters:**
  **obj** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict)) – The dictionary.
* **Returns:**
  a string that represents the dictionary in json format.
* **Return type:**
  [str](https://docs.python.org/3/library/stdtypes.html#str)
