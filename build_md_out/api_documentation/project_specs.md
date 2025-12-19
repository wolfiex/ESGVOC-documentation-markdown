# Project specs

### *Pydantic model* esgvoc.api.project_specs.AttributeProperty

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

A NetCDF global attribute property specification.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "AttributeProperty",
   "description": "A NetCDF global attribute property specification.",
   "type": "object",
   "properties": {
      "source_collection": {
         "title": "Source Collection",
         "type": "string"
      },
      "is_required": {
         "title": "Is Required",
         "type": "boolean"
      },
      "value_type": {
         "title": "Value Type",
         "type": "string"
      },
      "specific_key": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Specific Key"
      },
      "field_name": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Field Name"
      },
      "default_value": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Default Value"
      }
   },
   "required": [
      "source_collection",
      "is_required",
      "value_type"
   ]
}
```

</details></p>

#### *field* default_value *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The default value for the attribute.

#### *field* field_name *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The name of the attribute field.

#### *field* is_required *: [bool](https://docs.python.org/3/library/functions.html#bool)* *[Required]*

Specifies if the attribute must be present in the NetCDF file.

#### *field* source_collection *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The project collection that originated the property.

#### *field* specific_key *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

Specifies a specific key in the collection.

#### *field* value_type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The type of the attribute value.

### *Pydantic model* esgvoc.api.project_specs.CatalogExtension

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CatalogExtension",
   "type": "object",
   "properties": {
      "name": {
         "title": "Name",
         "type": "string"
      },
      "version": {
         "title": "Version",
         "type": "string"
      }
   },
   "required": [
      "name",
      "version"
   ]
}
```

</details></p>

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The name of the extension

#### *field* version *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The version of the extension

### *Pydantic model* esgvoc.api.project_specs.CatalogProperties

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CatalogProperties",
   "type": "object",
   "properties": {
      "name": {
         "title": "Name",
         "type": "string"
      },
      "url_template": {
         "title": "Url Template",
         "type": "string"
      },
      "extensions": {
         "items": {
            "$ref": "#/$defs/CatalogExtension"
         },
         "title": "Extensions",
         "type": "array"
      }
   },
   "$defs": {
      "CatalogExtension": {
         "properties": {
            "name": {
               "title": "Name",
               "type": "string"
            },
            "version": {
               "title": "Version",
               "type": "string"
            }
         },
         "required": [
            "name",
            "version"
         ],
         "title": "CatalogExtension",
         "type": "object"
      }
   },
   "required": [
      "name",
      "url_template",
      "extensions"
   ]
}
```

</details></p>

#### *field* extensions *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[CatalogExtension](#esgvoc.api.project_specs.CatalogExtension)]* *[Required]*

The extensions of the catalog.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The name of the catalog system.

#### *field* url_template *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The URI template of the catalog system.

### *Pydantic model* esgvoc.api.project_specs.CatalogProperty

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

A dataset property described in a catalog.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CatalogProperty",
   "description": "A dataset property described in a catalog.",
   "type": "object",
   "properties": {
      "source_collection": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Source Collection"
      },
      "catalog_field_value_type": {
         "title": "Catalog Field Value Type",
         "type": "string"
      },
      "is_required": {
         "title": "Is Required",
         "type": "boolean"
      },
      "source_collection_term": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Source Collection Term"
      },
      "catalog_field_name": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Catalog Field Name"
      },
      "source_collection_key": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Source Collection Key"
      }
   },
   "required": [
      "source_collection",
      "catalog_field_value_type",
      "is_required"
   ]
}
```

</details></p>

#### *field* catalog_field_name *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The name of the collection referenced in the catalog.

#### *field* catalog_field_value_type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The type of the field value.

#### *field* is_required *: [bool](https://docs.python.org/3/library/functions.html#bool)* *[Required]*

Specifies if the property must be present in the dataset properties.

#### *field* source_collection *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

The project collection that originated the property. None value means that the property

#### *field* source_collection_key *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

Specifies a key other than drs_name in the collection.

#### *field* source_collection_term *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

Specifies a specific term in the collection.

### *Pydantic model* esgvoc.api.project_specs.CatalogSpecification

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

A catalog specifications.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CatalogSpecification",
   "description": "A catalog specifications.",
   "type": "object",
   "properties": {
      "version": {
         "title": "Version",
         "type": "string"
      },
      "catalog_properties": {
         "$ref": "#/$defs/CatalogProperties"
      },
      "dataset_properties": {
         "items": {
            "$ref": "#/$defs/CatalogProperty"
         },
         "title": "Dataset Properties",
         "type": "array"
      },
      "file_properties": {
         "items": {
            "$ref": "#/$defs/CatalogProperty"
         },
         "title": "File Properties",
         "type": "array"
      }
   },
   "$defs": {
      "CatalogExtension": {
         "properties": {
            "name": {
               "title": "Name",
               "type": "string"
            },
            "version": {
               "title": "Version",
               "type": "string"
            }
         },
         "required": [
            "name",
            "version"
         ],
         "title": "CatalogExtension",
         "type": "object"
      },
      "CatalogProperties": {
         "properties": {
            "name": {
               "title": "Name",
               "type": "string"
            },
            "url_template": {
               "title": "Url Template",
               "type": "string"
            },
            "extensions": {
               "items": {
                  "$ref": "#/$defs/CatalogExtension"
               },
               "title": "Extensions",
               "type": "array"
            }
         },
         "required": [
            "name",
            "url_template",
            "extensions"
         ],
         "title": "CatalogProperties",
         "type": "object"
      },
      "CatalogProperty": {
         "description": "A dataset property described in a catalog.",
         "properties": {
            "source_collection": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "title": "Source Collection"
            },
            "catalog_field_value_type": {
               "title": "Catalog Field Value Type",
               "type": "string"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            },
            "source_collection_term": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Source Collection Term"
            },
            "catalog_field_name": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Catalog Field Name"
            },
            "source_collection_key": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Source Collection Key"
            }
         },
         "required": [
            "source_collection",
            "catalog_field_value_type",
            "is_required"
         ],
         "title": "CatalogProperty",
         "type": "object"
      }
   },
   "required": [
      "version",
      "catalog_properties",
      "dataset_properties",
      "file_properties"
   ]
}
```

</details></p>

#### *field* catalog_properties *: [CatalogProperties](#esgvoc.api.project_specs.CatalogProperties)* *[Required]*

The properties of the catalog.

#### *field* dataset_properties *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[CatalogProperty](#esgvoc.api.project_specs.CatalogProperty)]* *[Required]*

The properties of the dataset described in a catalog.

#### *field* file_properties *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[CatalogProperty](#esgvoc.api.project_specs.CatalogProperty)]* *[Required]*

The properties of the files described in a catalog.

#### *field* version *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The version of the catalog.

### *Pydantic model* esgvoc.api.project_specs.DrsPart

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

A fragment of a DRS specification

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DrsPart",
   "description": "A fragment of a DRS specification",
   "type": "object",
   "properties": {
      "source_collection": {
         "title": "Source Collection",
         "type": "string"
      },
      "source_collection_term": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Source Collection Term"
      },
      "is_required": {
         "title": "Is Required",
         "type": "boolean"
      }
   },
   "required": [
      "source_collection",
      "is_required"
   ]
}
```

</details></p>

#### *field* is_required *: [bool](https://docs.python.org/3/library/functions.html#bool)* *[Required]*

Whether the collection is required for the DRS specification or not.

#### *field* source_collection *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The collection id.

#### *field* source_collection_term *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

Specifies a specific term in the collection.

### *Pydantic model* esgvoc.api.project_specs.DrsSpecification

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

A DRS specification.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DrsSpecification",
   "description": "A DRS specification.",
   "type": "object",
   "properties": {
      "type": {
         "$ref": "#/$defs/DrsType"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      },
      "separator": {
         "title": "Separator",
         "type": "string"
      },
      "properties": {
         "anyOf": [
            {
               "additionalProperties": true,
               "type": "object"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Properties"
      },
      "parts": {
         "items": {
            "$ref": "#/$defs/DrsPart"
         },
         "title": "Parts",
         "type": "array"
      }
   },
   "$defs": {
      "DrsPart": {
         "description": "A fragment of a DRS specification",
         "properties": {
            "source_collection": {
               "title": "Source Collection",
               "type": "string"
            },
            "source_collection_term": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Source Collection Term"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            }
         },
         "required": [
            "source_collection",
            "is_required"
         ],
         "title": "DrsPart",
         "type": "object"
      },
      "DrsType": {
         "description": "The types of DRS specification (directory, file name and dataset id).",
         "enum": [
            "directory",
            "file_name",
            "dataset_id"
         ],
         "title": "DrsType",
         "type": "string"
      }
   },
   "required": [
      "type",
      "regex",
      "separator",
      "parts"
   ]
}
```

</details></p>

#### *field* parts *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[DrsPart](#esgvoc.api.project_specs.DrsPart)]* *[Required]*

The parts of the DRS specification.

#### *field* properties *: [dict](https://docs.python.org/3/library/stdtypes.html#dict) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The other specifications (e.g., file name extension for file name DRS specification).

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

General pattern for simples checks

#### *field* separator *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The textual separator string or character.

#### *field* type *: [DrsType](#esgvoc.api.project_specs.DrsType)* *[Required]*

The type of the specification.

### *class* esgvoc.api.project_specs.DrsType(\*values)

Bases: [`str`](https://docs.python.org/3/library/stdtypes.html#str), [`Enum`](https://docs.python.org/3/library/enum.html#enum.Enum)

The types of DRS specification (directory, file name and dataset id).

#### DATASET_ID *= 'dataset_id'*

The DRS dataset id specification type.

#### DIRECTORY *= 'directory'*

The DRS directory specification type.

#### FILE_NAME *= 'file_name'*

The DRS file name specification type.

### *Pydantic model* esgvoc.api.project_specs.ProjectSpecs

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

A project specifications.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ProjectSpecs",
   "description": "A project specifications.",
   "type": "object",
   "properties": {
      "project_id": {
         "title": "Project Id",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "drs_specs": {
         "additionalProperties": {
            "$ref": "#/$defs/DrsSpecification"
         },
         "propertyNames": {
            "$ref": "#/$defs/DrsType"
         },
         "title": "Drs Specs",
         "type": "object"
      },
      "catalog_specs": {
         "anyOf": [
            {
               "$ref": "#/$defs/CatalogSpecification"
            },
            {
               "type": "null"
            }
         ],
         "default": null
      },
      "attr_specs": {
         "anyOf": [
            {
               "items": {
                  "$ref": "#/$defs/AttributeProperty"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Attr Specs"
      }
   },
   "$defs": {
      "AttributeProperty": {
         "description": "A NetCDF global attribute property specification.",
         "properties": {
            "source_collection": {
               "title": "Source Collection",
               "type": "string"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            },
            "value_type": {
               "title": "Value Type",
               "type": "string"
            },
            "specific_key": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Specific Key"
            },
            "field_name": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Field Name"
            },
            "default_value": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Default Value"
            }
         },
         "required": [
            "source_collection",
            "is_required",
            "value_type"
         ],
         "title": "AttributeProperty",
         "type": "object"
      },
      "CatalogExtension": {
         "properties": {
            "name": {
               "title": "Name",
               "type": "string"
            },
            "version": {
               "title": "Version",
               "type": "string"
            }
         },
         "required": [
            "name",
            "version"
         ],
         "title": "CatalogExtension",
         "type": "object"
      },
      "CatalogProperties": {
         "properties": {
            "name": {
               "title": "Name",
               "type": "string"
            },
            "url_template": {
               "title": "Url Template",
               "type": "string"
            },
            "extensions": {
               "items": {
                  "$ref": "#/$defs/CatalogExtension"
               },
               "title": "Extensions",
               "type": "array"
            }
         },
         "required": [
            "name",
            "url_template",
            "extensions"
         ],
         "title": "CatalogProperties",
         "type": "object"
      },
      "CatalogProperty": {
         "description": "A dataset property described in a catalog.",
         "properties": {
            "source_collection": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "title": "Source Collection"
            },
            "catalog_field_value_type": {
               "title": "Catalog Field Value Type",
               "type": "string"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            },
            "source_collection_term": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Source Collection Term"
            },
            "catalog_field_name": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Catalog Field Name"
            },
            "source_collection_key": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Source Collection Key"
            }
         },
         "required": [
            "source_collection",
            "catalog_field_value_type",
            "is_required"
         ],
         "title": "CatalogProperty",
         "type": "object"
      },
      "CatalogSpecification": {
         "description": "A catalog specifications.",
         "properties": {
            "version": {
               "title": "Version",
               "type": "string"
            },
            "catalog_properties": {
               "$ref": "#/$defs/CatalogProperties"
            },
            "dataset_properties": {
               "items": {
                  "$ref": "#/$defs/CatalogProperty"
               },
               "title": "Dataset Properties",
               "type": "array"
            },
            "file_properties": {
               "items": {
                  "$ref": "#/$defs/CatalogProperty"
               },
               "title": "File Properties",
               "type": "array"
            }
         },
         "required": [
            "version",
            "catalog_properties",
            "dataset_properties",
            "file_properties"
         ],
         "title": "CatalogSpecification",
         "type": "object"
      },
      "DrsPart": {
         "description": "A fragment of a DRS specification",
         "properties": {
            "source_collection": {
               "title": "Source Collection",
               "type": "string"
            },
            "source_collection_term": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Source Collection Term"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            }
         },
         "required": [
            "source_collection",
            "is_required"
         ],
         "title": "DrsPart",
         "type": "object"
      },
      "DrsSpecification": {
         "description": "A DRS specification.",
         "properties": {
            "type": {
               "$ref": "#/$defs/DrsType"
            },
            "regex": {
               "title": "Regex",
               "type": "string"
            },
            "separator": {
               "title": "Separator",
               "type": "string"
            },
            "properties": {
               "anyOf": [
                  {
                     "additionalProperties": true,
                     "type": "object"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Properties"
            },
            "parts": {
               "items": {
                  "$ref": "#/$defs/DrsPart"
               },
               "title": "Parts",
               "type": "array"
            }
         },
         "required": [
            "type",
            "regex",
            "separator",
            "parts"
         ],
         "title": "DrsSpecification",
         "type": "object"
      },
      "DrsType": {
         "description": "The types of DRS specification (directory, file name and dataset id).",
         "enum": [
            "directory",
            "file_name",
            "dataset_id"
         ],
         "title": "DrsType",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "project_id",
      "description",
      "drs_specs"
   ]
}
```

</details></p>

#### *field* attr_specs *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[AttributeProperty](#esgvoc.api.project_specs.AttributeProperty)] | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The NetCDF global attribute specifications of the project.

#### *field* catalog_specs *: [CatalogSpecification](#esgvoc.api.project_specs.CatalogSpecification) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The catalog specifications of the project.

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The description of the project.

#### *field* drs_specs *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)[[DrsType](#esgvoc.api.project_specs.DrsType), [DrsSpecification](#esgvoc.api.project_specs.DrsSpecification)]* *[Required]*

The DRS specifications of the project (directory, file name and dataset id).

#### *field* project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The project id.
