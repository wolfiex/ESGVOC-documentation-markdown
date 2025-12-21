# Data descriptors

## Data descriptors

<a id="module-esgvoc.api.data_descriptors"></a>

### *Pydantic model* esgvoc.api.data_descriptors.Activity

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

An ‘activity’ refers to a coordinated set of modeling experiments designed to address specific     scientific questions or objectives. Each activity is focused on different aspects of climate     science and utilizes various models to study a wide range of climate phenomena.     Activities are often organized around key research themes and may involve multiple experiments,     scenarios, and model configurations.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Activity",
   "description": "An 'activity' refers to a coordinated set of modeling experiments designed to address specific     scientific questions or objectives. Each activity is focused on different aspects of climate     science and utilizes various models to study a wide range of climate phenomena.     Activities are often organized around key research themes and may involve multiple experiments,     scenarios, and model configurations.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "name": {
         "title": "Name",
         "type": "string"
      },
      "long_name": {
         "title": "Long Name",
         "type": "string"
      },
      "url": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Url"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "name",
      "long_name",
      "url"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* long_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* url *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Archive

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Archive",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.AreaLabel

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Area sampling label.

This label provides information about the area sampling of a given dataset.
For a list of allowed values, see
[TODO think about how to cross-reference to somewhere where people can look up the allowed values,
e.g. some summary of the values in [https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/area_label](https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/area_label).]

This label is used as the area component of a branded variable’s suffix
(see [`BrandedSuffix`](#esgvoc.api.data_descriptors.BrandedSuffix)).
By definition, the area label must be consistent with the branded suffix.
area labels must not contain dashes
(as the dash is used as a separator when constructing the branded suffix).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "AreaLabel",
   "description": "Area sampling label.\n\nThis label provides information about the area sampling of a given dataset.\nFor a list of allowed values, see\n[TODO think about how to cross-reference to somewhere where people can look up the allowed values,\ne.g. some summary of the values in https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/area_label.]\n\nThis label is used as the area component of a branded variable's suffix\n(see :py:class:`BrandedSuffix`).\nBy definition, the area label must be consistent with the branded suffix.\narea labels must not contain dashes\n(as the dash is used as a separator when constructing the branded suffix).",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "label": {
         "title": "Label",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "label"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.BrandedSuffix

Bases: [`CompositeTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermDataDescriptor)

The suffix of a branded variable.

A branded variable is composed of two parts.
The first part is the root variable (see [TODO cross-ref to Variable]).
The second is the suffix, i.e. the component described here.
The suffix captures all the information
about the time sampling, horizontal sampling, vertical sampling
and area masking of the variable.

The suffix is composed of the following components:

1. [`TemporalLabel`](#esgvoc.api.data_descriptors.TemporalLabel)
2. [`VerticalLabel`](#esgvoc.api.data_descriptors.VerticalLabel)
3. [`HorizontalLabel`](#esgvoc.api.data_descriptors.HorizontalLabel)
4. [`AreaLabel`](#esgvoc.api.data_descriptors.AreaLabel)

These components are separated by a separator to create the branded suffix.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "BrandedSuffix",
   "description": "The suffix of a branded variable.\n\nA branded variable is composed of two parts.\nThe first part is the root variable (see [TODO cross-ref to Variable]).\nThe second is the suffix, i.e. the component described here.\nThe suffix captures all the information\nabout the time sampling, horizontal sampling, vertical sampling\nand area masking of the variable.\n\nThe suffix is composed of the following components:\n\n#. :py:class:`TemporalLabel`\n#. :py:class:`VerticalLabel`\n#. :py:class:`HorizontalLabel`\n#. :py:class:`AreaLabel`\n\nThese components are separated by a separator to create the branded suffix.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "separator": {
         "title": "Separator",
         "type": "string"
      },
      "parts": {
         "items": {
            "$ref": "#/$defs/CompositeTermPart"
         },
         "title": "Parts",
         "type": "array"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "$defs": {
      "CompositeTermPart": {
         "additionalProperties": true,
         "description": "A reference to a term, part of a composite term.",
         "properties": {
            "id": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "items": {
                        "type": "string"
                     },
                     "type": "array"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Id"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            }
         },
         "required": [
            "type",
            "is_required"
         ],
         "title": "CompositeTermPart",
         "type": "object"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "separator",
      "parts",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* parts *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[CompositeTermPart](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermPart)]* *[Required]*

The components.

#### *field* separator *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The components separator character.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.BrandedVariable

Bases: [`CompositeTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermDataDescriptor)

A climate-related quantity or measurement, including information about sampling.

The concept of a branded variable was introduced in CMIP7.
A branded variable is composed of two parts.
The first part is the root variable (see [`Variable`](#esgvoc.api.data_descriptors.Variable)).
The second is the suffix (see [`BrandedSuffix`](#esgvoc.api.data_descriptors.BrandedSuffix)).

For further details on the development of branded variables,
see [this paper draft]([https://docs.google.com/document/d/19jzecgymgiiEsTDzaaqeLP6pTvLT-NzCMaq-wu-QoOc/edit?pli=1&tab=t.0](https://docs.google.com/document/d/19jzecgymgiiEsTDzaaqeLP6pTvLT-NzCMaq-wu-QoOc/edit?pli=1&tab=t.0)).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "BrandedVariable",
   "description": "A climate-related quantity or measurement, including information about sampling.\n\nThe concept of a branded variable was introduced in CMIP7.\nA branded variable is composed of two parts.\nThe first part is the root variable (see :py:class:`Variable`).\nThe second is the suffix (see :py:class:`BrandedSuffix`).\n\nFor further details on the development of branded variables,\nsee [this paper draft](https://docs.google.com/document/d/19jzecgymgiiEsTDzaaqeLP6pTvLT-NzCMaq-wu-QoOc/edit?pli=1&tab=t.0).",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "separator": {
         "title": "Separator",
         "type": "string"
      },
      "parts": {
         "items": {
            "$ref": "#/$defs/CompositeTermPart"
         },
         "title": "Parts",
         "type": "array"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "$defs": {
      "CompositeTermPart": {
         "additionalProperties": true,
         "description": "A reference to a term, part of a composite term.",
         "properties": {
            "id": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "items": {
                        "type": "string"
                     },
                     "type": "array"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Id"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            }
         },
         "required": [
            "type",
            "is_required"
         ],
         "title": "CompositeTermPart",
         "type": "object"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "separator",
      "parts",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* parts *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[CompositeTermPart](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermPart)]* *[Required]*

The components.

#### *field* separator *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The components separator character.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Calendar

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Calendar",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.CitationUrl

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CitationUrl",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.ComponentType

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ComponentType",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "ui_label": {
         "title": "Ui Label",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "ui_label"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* ui_label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Consortium

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Consortium",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "validation_method": {
         "default": "list",
         "title": "Validation Method",
         "type": "string"
      },
      "name": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Name"
      },
      "status": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Status"
      },
      "changes": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Changes"
      },
      "members": {
         "items": {
            "$ref": "#/$defs/Member"
         },
         "title": "Members",
         "type": "array"
      },
      "url": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Url"
      },
      "description": {
         "default": "",
         "title": "Description",
         "type": "string"
      }
   },
   "$defs": {
      "Dates": {
         "additionalProperties": true,
         "properties": {
            "phase": {
               "title": "Phase",
               "type": "string"
            },
            "from": {
               "title": "From",
               "type": "integer"
            },
            "to": {
               "anyOf": [
                  {
                     "type": "integer"
                  },
                  {
                     "type": "string"
                  }
               ],
               "title": "To"
            }
         },
         "required": [
            "phase",
            "from",
            "to"
         ],
         "title": "Dates",
         "type": "object"
      },
      "Member": {
         "additionalProperties": true,
         "properties": {
            "type": {
               "title": "Type",
               "type": "string"
            },
            "institution": {
               "title": "Institution",
               "type": "string"
            },
            "dates": {
               "items": {
                  "$ref": "#/$defs/Dates"
               },
               "title": "Dates",
               "type": "array"
            },
            "membership_type": {
               "title": "Membership Type",
               "type": "string"
            }
         },
         "required": [
            "type",
            "institution",
            "membership_type"
         ],
         "title": "Member",
         "type": "object"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "changes",
      "url"
   ]
}
```

</details></p>

#### *field* changes *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= ''*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* members *: [list](https://docs.python.org/3/library/stdtypes.html#list)[Member]* *[Optional]*

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

#### *field* status *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* url *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* validation_method *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= 'list'*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Contact

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Contact",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Convention

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Convention",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "label": {
         "title": "Label",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "label"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Coordinate

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Native vertical grid coordinate type. The coordinate types are all CF standard names (except where indicated) with the same definitions. See section 5.2 Native vertical grid properties.
Options for the native vertical grid Coordinate property:

> • none
>   : ◦ (Not a standard name) There is no vertical dimension.
> • height
>   : ◦ Height is the vertical distance above the earth’s surface.
> • geopotential_height
>   : ◦ Geopotential height is the geopotential divided by the standard acceleration due to gravity.
> • air_pressure
>   : ◦ Air pressure is the pressure that exists in the medium of air.
> • air_potential_temperature
>   : ◦ Air potential temperature is the temperature a parcel of air would have if moved dry adiabatically to a standard pressure.
> • atmosphere_ln_pressure_coordinate
>   : ◦ Parametric atmosphere natural log pressure coordinate.
> • atmosphere_sigma_coordinate
>   : ◦ Parametric atmosphere sigma coordinate.
> • atmosphere_hybrid_sigma_pressure_coordinate
>   : ◦ Parametric atmosphere hybrid sigma pressure coordinate.
> • atmosphere_hybrid_height_coordinate
>   : ◦ Parametric atmosphere hybrid height coordinate.
> • atmosphere_sleve_coordinate
>   : ◦ Parametric atmosphere smooth vertical level coordinate.
> • depth
>   : ◦ Depth is the vertical distance below the earth’s surface.
> • sea_water_pressure
>   : ◦ Sea water pressure is the pressure that exists in the medium of sea water.
> • sea_water_potential_temperature
>   : ◦ Sea water potential temperature is the temperature a parcel of sea water would have if moved adiabatically to sea level pressure.
> • ocean_sigma_coordinate
>   : ◦ Parametric ocean sigma coordinate.
> • ocean_s_coordinate
>   : ◦ Parametric ocean s-coordinate.
> • ocean_s_coordinate_g1
>   : ◦ Parametric ocean s-coordinate, generic form 1.
> • ocean_s_coordinate_g2
>   : ◦ Parametric ocean s-coordinate, generic form 2.
> • ocean_sigma_z_coordinate
>   : ◦ Parametric ocean sigma over z coordinate.
> • ocean_double_sigma_coordinate
>   : ◦ Parametric ocean double sigma coordinate.
> • land_ice_sigma_coordinate
>   : ◦ Land ice (glaciers, ice-caps and ice-sheets resting on bedrock and also includes ice-shelves) sigma coordinate.
> • z\*
>   : ◦ (Not a standard name) The z\* coordinate of Adcroft and Campin (2004).
<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Coordinate",
   "description": "Native vertical grid coordinate type. The coordinate types are all CF standard names (except where indicated) with the same definitions. See section 5.2 Native vertical grid properties.\nOptions for the native vertical grid Coordinate property:\n    \u2022 none\n        \u25e6 (Not a standard name) There is no vertical dimension.\n    \u2022 height\n        \u25e6 Height is the vertical distance above the earth\u2019s surface.\n    \u2022 geopotential_height\n        \u25e6 Geopotential height is the geopotential divided by the standard acceleration due to gravity.\n    \u2022 air_pressure\n        \u25e6 Air pressure is the pressure that exists in the medium of air.\n    \u2022 air_potential_temperature\n        \u25e6 Air potential temperature is the temperature a parcel of air would have if moved dry adiabatically to a standard pressure.\n    \u2022 atmosphere_ln_pressure_coordinate\n        \u25e6 Parametric atmosphere natural log pressure coordinate.\n    \u2022 atmosphere_sigma_coordinate\n        \u25e6 Parametric atmosphere sigma coordinate.\n    \u2022 atmosphere_hybrid_sigma_pressure_coordinate\n        \u25e6 Parametric atmosphere hybrid sigma pressure coordinate.\n    \u2022 atmosphere_hybrid_height_coordinate\n        \u25e6 Parametric atmosphere hybrid height coordinate.\n    \u2022 atmosphere_sleve_coordinate\n        \u25e6 Parametric atmosphere smooth vertical level coordinate.\n    \u2022 depth\n        \u25e6 Depth is the vertical distance below the earth\u2019s surface.\n    \u2022 sea_water_pressure\n        \u25e6 Sea water pressure is the pressure that exists in the medium of sea water.\n    \u2022 sea_water_potential_temperature\n        \u25e6 Sea water potential temperature is the temperature a parcel of sea water would have if moved adiabatically to sea level pressure.\n    \u2022 ocean_sigma_coordinate\n        \u25e6 Parametric ocean sigma coordinate.\n    \u2022 ocean_s_coordinate\n        \u25e6 Parametric ocean s-coordinate.\n    \u2022 ocean_s_coordinate_g1\n        \u25e6 Parametric ocean s-coordinate, generic form 1.\n    \u2022 ocean_s_coordinate_g2\n        \u25e6 Parametric ocean s-coordinate, generic form 2.\n    \u2022 ocean_sigma_z_coordinate\n        \u25e6 Parametric ocean sigma over z coordinate.\n    \u2022 ocean_double_sigma_coordinate\n        \u25e6 Parametric ocean double sigma coordinate.\n    \u2022 land_ice_sigma_coordinate\n        \u25e6 Land ice (glaciers, ice-caps and ice-sheets resting on bedrock and also includes ice-shelves) sigma coordinate.\n    \u2022 z*\n        \u25e6 (Not a standard name) The z* coordinate of Adcroft and Campin (2004).",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.CreationDate

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CreationDate",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.DataSpecsVersion

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DataSpecsVersion",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Date

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Date",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.DirectoryDate

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DirectoryDate",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.EMDModelComponent

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Properties that provide a description of individual model components.
Eight model components are defined that somewhat independently account for different sets of interactive processes: aerosol, atmosphere, atmospheric chemistry, land surface, land ice, ocean, ocean biogeochemistry, and sea ice. The interactive processes covered by each  component are described in more detail in section 7.1. Model Component Type CV.
Each component is characterized as “dynamic”, “prescribed”, or “omitted” (see 2. Model properties), but only model components that dynamically simulate their processes are described in this section of the EMD. Relationships among dynamically simulated components are indicated by specifying that they are “embedded in” or “coupled with” other components (see 3.1. Embedded and Coupled components).
Note for CMIP7: The component types in the 7.1. Model Component Type CV have similar names and definitions to the CMIP “realms” given by the CMIP6_realm.json file (Durack et al., 2025), but the context in which they are used is different. An EMD component type defines a set of physical process that are simulated by one model component; whereas as one or more CMIP realms are assigned to an individual model output variable according to which sets of processes the variable is physically related to, rather than which model component created it. The CMIP realms for an output variable often include the EMD component type that created it, but this is not always the case.
In the property examples, underlined and italicised values are taken from section 7. Controlled vocabularies.
• Component

> ◦ The type of the model component.
> ◦ Taken from a standardised list: 7.1. Model Component Type CV.
> ◦ E.g. aerosol
• Name
  : ◦ The name of the model component.
    ◦ If the component is embedded in a host component and has no commonly recognised name, then a name can be constructed by combining the host component’s Name with this component’s Component type, separated by a hyphen.
    ◦ E.g. BISICLES-UKESM-ISMIP6
    ◦ E.g. MOSES2
    ◦ E.g. HadAM3-aerosol
• Family
  : ◦ The model component’s “family” name. For a component, its family members should all share much of their code bases, but the members may be configured in different ways (e.g. different resolutions, parameter choices, or the inclusion or not of particular sub-process). See Masson and Knutti (2011) for an example of how the family can be used to inform model genealogies.
    ◦ Use a value of “none” to indicate that there is no such family for the model component.
    ◦ E.g. BISICLES
    ◦ E.g. CLM
    ◦ E.g. none
• Description
  : ◦ A scientific overview of the model component.
    ◦ The description should summarise the key processes simulated by the model component.
    ◦ For CMIP7, easy-to-answer MIP-relevant questions may be posed, which should be addressed using free text. For instance “Are aerosols driven by emissions or concentration?” or “What is the aerosol activation scheme?”.
• References
  : ◦ References to published work for the model component.
    ◦ Each reference must include the properties described in section 4. References.
• Code base
  : ◦ A URL (preferably for a DOI) for the source code for the model component.
    ◦ If the source code is in a versioncontrolled repository (e.g. a git or svn repository) then the URL must identify a specific point in the repository’s history.
    ◦ Set to “private” if not publicly available.
• Embedded in
  : ◦ The host model component (identified by its Component property) in which this component is “embedded”.
    ◦ See section 3.1. Embedded and Coupled model components for a definition of an embedded component. Note that a component must be either embedded in a another component or else coupled with other components, but can not be both.
    ◦ Taken from a standardised list: 7.1. Model Component Type CV.
    ◦ Omit when this component is coupled with other components (see the Coupled with property).
    ◦ E.g. in some cases, for an aerosol model component: atmosphere
• Coupled with
  : ◦ The model components (identified by their Component properties) with which this component is “coupled”.
    ◦ See section 3.1. Embedded and Coupled model components for a definition of a coupled component. Note that a component must be either embedded in a another component or else coupled with other components, but can not be both.
    ◦ Taken from a standardised list: 7.1. Model Components Type CV.
    ◦ Omit when this component is embedded in another component (see the Embedded in property).
    ◦ E.g. In some cases for a land ice component: atmosphere, land surface, ocean
• Native horizontal grid
  : ◦ A standardised description of the model component’s horizontal grid.
    ◦ The grid is described by defining the properties listed in section 5.1. Native horizontal grid properties.
• Native vertical grid
  : ◦ A standardised description of the model component’s vertical grid.
    ◦ The grid is described by defining the properties listed in section 5.2. Native vertical grid properties.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "EMDModelComponent",
   "description": "Properties that provide a description of individual model components.\nEight model components are defined that somewhat independently account for different sets of interactive processes: aerosol, atmosphere, atmospheric chemistry, land surface, land ice, ocean, ocean biogeochemistry, and sea ice. The interactive processes covered by each  component are described in more detail in section 7.1. Model Component Type CV.\nEach component is characterized as \u201cdynamic\u201d, \u201cprescribed\u201d, or \u201comitted\u201d (see 2. Model properties), but only model components that dynamically simulate their processes are described in this section of the EMD. Relationships among dynamically simulated components are indicated by specifying that they are \u201cembedded in\u201d or \u201ccoupled with\u201d other components (see 3.1. Embedded and Coupled components).\nNote for CMIP7: The component types in the 7.1. Model Component Type CV have similar names and definitions to the CMIP \u201crealms\u201d given by the CMIP6_realm.json file (Durack et al., 2025), but the context in which they are used is different. An EMD component type defines a set of physical process that are simulated by one model component; whereas as one or more CMIP realms are assigned to an individual model output variable according to which sets of processes the variable is physically related to, rather than which model component created it. The CMIP realms for an output variable often include the EMD component type that created it, but this is not always the case.\nIn the property examples, underlined and italicised values are taken from section 7. Controlled vocabularies.\n\u2022 Component\n    \u25e6 The type of the model component.\n    \u25e6 Taken from a standardised list: 7.1. Model Component Type CV.\n    \u25e6 E.g. aerosol\n\u2022 Name\n    \u25e6 The name of the model component.\n    \u25e6 If the component is embedded in a host component and has no commonly recognised name, then a name can be constructed by combining the host component\u2019s Name with this component\u2019s Component type, separated by a hyphen.\n    \u25e6 E.g. BISICLES-UKESM-ISMIP6\n    \u25e6 E.g. MOSES2\n    \u25e6 E.g. HadAM3-aerosol\n\u2022 Family\n    \u25e6 The model component\u2019s \u201cfamily\u201d name. For a component, its family members should all share much of their code bases, but the members may be configured in different ways (e.g. different resolutions, parameter choices, or the inclusion or not of particular sub-process). See Masson and Knutti (2011) for an example of how the family can be used to inform model genealogies.\n    \u25e6 Use a value of \u201cnone\u201d to indicate that there is no such family for the model component.\n    \u25e6 E.g. BISICLES\n    \u25e6 E.g. CLM\n    \u25e6 E.g. none\n\u2022 Description\n    \u25e6 A scientific overview of the model component.\n    \u25e6 The description should summarise the key processes simulated by the model component.\n    \u25e6 For CMIP7, easy-to-answer MIP-relevant questions may be posed, which should be addressed using free text. For instance \u201cAre aerosols driven by emissions or concentration?\u201d or \u201cWhat is the aerosol activation scheme?\u201d.\n\u2022 References\n    \u25e6 References to published work for the model component.\n    \u25e6 Each reference must include the properties described in section 4. References.\n\u2022 Code base\n    \u25e6 A URL (preferably for a DOI) for the source code for the model component.\n    \u25e6 If the source code is in a versioncontrolled repository (e.g. a git or svn repository) then the URL must identify a specific point in the repository\u2019s history.\n    \u25e6 Set to \u201cprivate\u201d if not publicly available.\n\u2022 Embedded in\n    \u25e6 The host model component (identified by its Component property) in which this component is \u201cembedded\u201d.\n    \u25e6 See section 3.1. Embedded and Coupled model components for a definition of an embedded component. Note that a component must be either embedded in a another component or else coupled with other components, but can not be both.\n    \u25e6 Taken from a standardised list: 7.1. Model Component Type CV.\n    \u25e6 Omit when this component is coupled with other components (see the Coupled with property).\n    \u25e6 E.g. in some cases, for an aerosol model component: atmosphere\n\u2022 Coupled with\n    \u25e6 The model components (identified by their Component properties) with which this component is \u201ccoupled\u201d.\n    \u25e6 See section 3.1. Embedded and Coupled model components for a definition of a coupled component. Note that a component must be either embedded in a another component or else coupled with other components, but can not be both.\n    \u25e6 Taken from a standardised list: 7.1. Model Components Type CV.\n    \u25e6 Omit when this component is embedded in another component (see the Embedded in property).\n    \u25e6 E.g. In some cases for a land ice component: atmosphere, land surface, ocean\n\u2022 Native horizontal grid\n    \u25e6 A standardised description of the model component\u2019s horizontal grid.\n    \u25e6 The grid is described by defining the properties listed in section 5.1. Native horizontal grid properties.\n\u2022 Native vertical grid\n    \u25e6 A standardised description of the model component\u2019s vertical grid.\n    \u25e6 The grid is described by defining the properties listed in section 5.2. Native vertical grid properties.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "component": {
         "description": "The type of the model component. Taken from a standardised list: 7.1 component CV.",
         "title": "Component",
         "type": "string"
      },
      "name": {
         "description": "The name of the model component.",
         "minLength": 1,
         "title": "Name",
         "type": "string"
      },
      "family": {
         "description": "The model component's 'family' name. Use 'none' to indicate that there is no such family.",
         "minLength": 1,
         "title": "Family",
         "type": "string"
      },
      "description": {
         "description": "A scientific overview of the model component. The description should summarise the key processes simulated by the model component.",
         "minLength": 1,
         "title": "Description",
         "type": "string"
      },
      "references": {
         "description": "One or more references to published work for the model component.",
         "items": {
            "$ref": "#/$defs/Reference"
         },
         "minItems": 1,
         "title": "References",
         "type": "array"
      },
      "code_base": {
         "description": "A URL (preferably for a DOI) for the source code for the model component. Set to 'private' if not publicly available.",
         "minLength": 1,
         "title": "Code Base",
         "type": "string"
      },
      "embedded_in": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The host model component (identified by its component property) in which this component is 'embedded'. Taken from a standardised list: 7.1 component CV. Omit when this component is coupled with other components.",
         "title": "Embedded In"
      },
      "coupled_with": {
         "anyOf": [
            {
               "items": {
                  "type": "string"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The model components (identified by their component properties) with which this component is 'coupled'. Taken from a standardised list: 7.1 component CV. Omit when this component is embedded in another component.",
         "title": "Coupled With"
      },
      "native_horizontal_grid": {
         "$ref": "#/$defs/NativeHorizontalGrid",
         "description": "A standardised description of the model component's horizontal grid."
      },
      "native_vertical_grid": {
         "$ref": "#/$defs/NativeVerticalGrid",
         "description": "A standardised description of the model component's vertical grid."
      }
   },
   "$defs": {
      "NativeHorizontalGrid": {
         "additionalProperties": true,
         "description": "The model component\u2019s native horizontal grid is described by a subset of the following properties:\n\n\u2022 Description\n    \u25e6 A free-text description of the grid.\n    \u25e6 A description is only required if there is information that is not covered by any of the other properties.\n    \u25e6 Omit if not needed.\n\u2022 Type\n    \u25e6 The horizontal grid type, i.e. the method of distributing grid points over the sphere.\n    \u25e6 Taken from a standardised list: 7.3. Native horizontal grid Type CV.\n    \u25e6 If there is no horizontal grid, then the value \u201cnone\u201d must be selected, and no other properties should be set.\n    \u25e6 E.g. regular_latitude_longitude\n    \u25e6 E.g. tripolar\n\u2022 Grid mapping\n    \u25e6 The name of the coordinate reference system of the horizontal coordinates.\n    \u25e6 Taken from a standardised list: 7.4. Native horizontal grid Grid Mapping CV.\n    \u25e6 E.g. latitude_longitude\n\u2022 Region\n    \u25e6 The geographical region, or regions, over which the component is simulated.\n    \u25e6 A region is a contiguous part of the Earth\u2019s surface, and may include areas for which no calculations are made (such as ocean areas for a land surface component).\n    \u25e6 Taken from a standardised list: 7.5. Native horizontal grid Region CV.\n    \u25e6 E.g. global\n    \u25e6 E.g. antarctica, greenland\n\u2022 Temporal refinement\n    \u25e6 The grid temporal refinement, indicating how the distribution of grid cells varies with time.\n    \u25e6 Taken from a standardised list: 7.6. Native horizontal grid Temporal refinement CV.\n    \u25e6 E.g. static\n\u2022 Arrangement\n    \u25e6 A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields.\n    \u25e6 Taken from a standardised list: 7.7. Native horizontal grid Arrangement CV.\n    \u25e6 E.g. arakawa_B\n\u2022 Resolution X\n    \u25e6 The size of grid cells in the X direction.\n    \u25e6 The value\u2019s physical units are given by the Units property.\n    \u25e6 Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 3.75\n\u2022 Resolution Y\n    \u25e6 The size of grid cells in the Y direction.\n    \u25e6 The value\u2019s physical units are given by the Units property.\n    \u25e6 Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 2.5\n\u2022 Units\n    \u25e6 The physical units of the Resolution X and Resolution Y property values.\n    \u25e6 The only acceptable units are  \u201ckm\u201d (kilometre, unit for length) or \u201cdegree\u201d (unit for angular measure).\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. km\n    \u25e6 E.g. degree\n\u2022 N cells\n    \u25e6 The total number of cells in the horizontal grid.\n    \u25e6 If the horizontal grid is unstructured then when the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number of cells for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 265160\n\u2022 N sides\n    \u25e6 For unstructured horizontal grids only, the total number of unique cell sides.\n    \u25e6 When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number of sides for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 714274\n\u2022 N vertices\n    \u25e6 For unstructured horizontal grids only, the number of unique cell vertices.\n    \u25e6 When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 567145\n\u2022 Truncation method\n    \u25e6 The method for truncating the spherical harmonic representation of a spectral model.\n    \u25e6 Taken from a standardised list: 7.8. Native horizontal grid Truncation method CV.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. triangular\n\u2022 Truncation number\n    \u25e6 The zonal (east-west) wave number at which a spectral model is truncated.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 63\n\u2022 Resolution range km\n    \u25e6 The minimum and maximum resolution (in km) of cells of the native horizontal grid.\n    \u25e6 Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum and mean resolution.\n    \u25e6 E.g. 57.0, 290\n\u2022 Mean resolution km\n    \u25e6 The mean resolution (in km) of the native horizontal grid on which the mass-related quantities are carried by the model.\n    \u25e6 Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum, and mean resolution.\n    \u25e6 E.g. 234.8\n\u2022 Nominal resolution\n    \u25e6 The nominal resolution characterises the approximate resolution of a model\u2019s native horizontal grid.\n    \u25e6 The nominal resolution is obtained (once the Mean resolution km property is calculated) by looking it up in the table at 7.9. Native horizontal grid Nominal resolution CV.\n    \u25e6 E.g. A grid with mean resolution of 82 will have a nominal resolution of 100 km",
         "properties": {
            "id": {
               "title": "Id",
               "type": "string"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "drs_name": {
               "title": "Drs Name",
               "type": "string"
            },
            "grid": {
               "description": "The horizontal grid type, i.e. the method of distributing grid points over the sphere. Taken from a standardised list: 7.3 grid CV. If there is no horizontal grid, then the value 'none' must be selected.",
               "title": "Grid",
               "type": "string"
            },
            "description": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "A free-text description of the grid. A description is only required if there is information that is not covered by any of the other properties.",
               "title": "Description"
            },
            "grid_mapping": {
               "description": "The name of the coordinate reference system of the horizontal coordinates. Taken from a standardised list: 7.4 grid_mapping CV.",
               "title": "Grid Mapping",
               "type": "string"
            },
            "region": {
               "description": "The geographical region, or regions, over which the component is simulated. Taken from a standardised list: 7.5 region CV.",
               "title": "Region",
               "type": "string"
            },
            "temporal_refinement": {
               "description": "The grid temporal refinement, indicating how the distribution of grid cells varies with time. Taken from a standardised list: 7.6 temporal_refinement CV.",
               "title": "Temporal Refinement",
               "type": "string"
            },
            "arrangement": {
               "description": "A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields. Taken from a standardised list: 7.7 arrangement CV.",
               "title": "Arrangement",
               "type": "string"
            },
            "resolution_x": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The size of grid cells in the X direction. The value's physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.",
               "title": "Resolution X"
            },
            "resolution_y": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The size of grid cells in the Y direction. The value's physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.",
               "title": "Resolution Y"
            },
            "horizontal_units": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The physical units of the resolution_x and resolution_y property values. Taken from a standardised list: 7.8 horizontal_units CV.",
               "title": "Horizontal Units"
            },
            "n_cells": {
               "description": "The total number of cells in the horizontal grid.",
               "minimum": 1,
               "title": "N Cells",
               "type": "integer"
            },
            "n_sides": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "For unstructured horizontal grids only, the total number of unique cell sides.",
               "title": "N Sides"
            },
            "n_vertices": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "For unstructured horizontal grids only, the number of unique cell vertices.",
               "title": "N Vertices"
            },
            "truncation_method": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The method for truncating the spherical harmonic representation of a spectral model. Taken from a standardised list: 7.9 truncation_method CV.",
               "title": "Truncation Method"
            },
            "truncation_number": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The zonal (east-west) wave number at which a spectral model is truncated.",
               "title": "Truncation Number"
            },
            "resolution_range_km": {
               "description": "The minimum and maximum resolution (in km) of cells of the horizontal grid.",
               "items": {
                  "type": "number"
               },
               "maxItems": 2,
               "minItems": 2,
               "title": "Resolution Range Km",
               "type": "array"
            },
            "mean_resolution_km": {
               "description": "The mean resolution (in km) of cells of the horizontal grid.",
               "exclusiveMinimum": 0,
               "title": "Mean Resolution Km",
               "type": "number"
            },
            "nominal_resolution": {
               "description": "The nominal resolution characterises the approximate resolution of a horizontal grid. Taken from a standardised list: 7.10 nominal_resolution CV.",
               "title": "Nominal Resolution",
               "type": "string"
            }
         },
         "required": [
            "id",
            "type",
            "drs_name",
            "grid",
            "grid_mapping",
            "region",
            "temporal_refinement",
            "arrangement",
            "n_cells",
            "resolution_range_km",
            "mean_resolution_km",
            "nominal_resolution"
         ],
         "title": "NativeHorizontalGrid",
         "type": "object"
      },
      "NativeVerticalGrid": {
         "additionalProperties": true,
         "description": "4.2. Vertical grid\nThe model component's native vertical grid is described by a subset of the following properties:\n    \u2022 Description\n        \u25e6 A free-text description of the vertical grid.\n        \u25e6 A description is only required if there is information that is not covered by any of the other properties.\n        \u25e6 Omit if not needed.\n    \u2022 Coordinate\n        \u25e6 The coordinate type of the vertical grid.\n        \u25e6 Taken from a standardised list: 7.11. coordinate CV.\n        \u25e6 If there is no vertical grid, then the value \"none\" must be selected, and no other properties should be set.\n        \u25e6 E.g. height\n        \u25e6 E.g. none\n    \u2022 N z\n        \u25e6 The number of layers (i.e. grid cells) in the Z direction.\n        \u25e6 Omit when not applicable or not constant.\n        \u25e6 If the number of layers varies in time or across the horizontal grid, then the N z range property may be used instead.\n        \u25e6 E.g. 70\n    \u2022 N z range\n        \u25e6 The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers.\n        \u25e6 Omit if the N z property has been set.\n        \u25e6 E.g. 5, 15\n    \u2022 Bottom layer thickness\n        \u25e6 The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 If the value varies in time or across the horizontal grid, then provide a nominal or typical value.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. 10\n    \u2022 Top layer thickness\n        \u25e6 The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 If the value varies in time or across the horizontal grid, then provide a nominal or typical value.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. 10\n    \u2022 Top of model\n        \u25e6 The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth).\n        \u25e6 The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable or not constant.\n        \u25e6 E.g. 85003.5\n    \u2022 Vertical units\n        \u25e6 The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values.\n        \u25e6 Taken from a standardised list: 7.12. vertical_units CV.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. m",
         "properties": {
            "id": {
               "title": "Id",
               "type": "string"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "coordinate": {
               "description": "The coordinate type of the vertical grid. Taken from a standardised list: 7.11 coordinate CV. If there is no vertical grid, then the value 'none' must be selected.",
               "title": "Coordinate",
               "type": "string"
            },
            "description": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "A free-text description of the vertical grid. A description is only required if there is information that is not covered by any of the other properties.",
               "title": "Description"
            },
            "n_z": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The number of layers (i.e. grid cells) in the Z direction. Omit when not applicable or not constant. If the number of layers varies in time or across the horizontal grid, then the n_z_range property may be used instead.",
               "title": "N Z"
            },
            "n_z_range": {
               "anyOf": [
                  {
                     "items": {
                        "type": "integer"
                     },
                     "maxItems": 2,
                     "minItems": 2,
                     "type": "array"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers. Omit if the n_z property has been set.",
               "title": "N Z Range"
            },
            "bottom_layer_thickness": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value's physical units are given by the vertical_units property.",
               "title": "Bottom Layer Thickness"
            },
            "top_layer_thickness": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value's physical units are given by the vertical_units property.",
               "title": "Top Layer Thickness"
            },
            "top_of_model": {
               "anyOf": [
                  {
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth). The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level). The value's physical units are given by the vertical_units property.",
               "title": "Top Of Model"
            },
            "vertical_units": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values. Taken from a standardised list: 7.12 vertical_units CV.",
               "title": "Vertical Units"
            }
         },
         "required": [
            "id",
            "type",
            "coordinate"
         ],
         "title": "NativeVerticalGrid",
         "type": "object"
      },
      "Reference": {
         "description": "The top-level model and its model components must each have at least one reference, defined by the following properties:\n\n\u2022 Citation\n    \u25e6 A human-readable citation for the work.\n    \u25e6 E.g. Smith, R. S., Mathiot, P., Siahaan, A., Lee, V., Cornford, S. L., Gregory, J. M., et al. (2021). Coupling the U.K. Earth System model to dynamic models of the Greenland and Antarctic ice sheets. Journal of Advances in Modeling Earth Systems, 13, e2021MS002520. https://doi.org/10.1029/2021MS002520, 2023\n\u2022 DOI\n    \u25e6 The persistent identifier (DOI) used to identify the work.\n    \u25e6 A DOI is required for all references. A reference that does not already have a DOI (as could be the case for some technical reports, for instance) must be given one (e.g. with a service like Zenodo).\n    \u25e6 E.g. https://doi.org/10.1029/2021MS002520",
         "properties": {
            "citation": {
               "description": "A human-readable citation for the work.",
               "minLength": 1,
               "title": "Citation",
               "type": "string"
            },
            "doi": {
               "description": "The persistent identifier (DOI) used to identify the work. Must be a valid DOI URL.",
               "minLength": 1,
               "title": "Doi",
               "type": "string"
            }
         },
         "required": [
            "citation",
            "doi"
         ],
         "title": "Reference",
         "type": "object"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "component",
      "name",
      "family",
      "description",
      "references",
      "code_base",
      "native_horizontal_grid",
      "native_vertical_grid"
   ]
}
```

</details></p>
* **Validators:**
  - `validate_code_base_format` » `code_base`
  - `validate_coupling_exclusivity` » `coupled_with`
  - `validate_embedding_exclusivity` » `embedded_in`
  - `validate_non_empty_strings` » `code_base`
  - `validate_non_empty_strings` » `component`
  - `validate_non_empty_strings` » `description`
  - `validate_non_empty_strings` » `family`
  - `validate_non_empty_strings` » `name`

#### *field* code_base *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

A URL (preferably for a DOI) for the source code for the model component. Set to ‘private’ if not publicly available.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_code_base_format`
  - `validate_non_empty_strings`

#### *field* component *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The type of the model component. Taken from a standardised list: 7.1 component CV.

* **Validated by:**
  - `validate_non_empty_strings`

#### *field* coupled_with *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The model components (identified by their component properties) with which this component is ‘coupled’. Taken from a standardised list: 7.1 component CV. Omit when this component is embedded in another component.

* **Validated by:**
  - `validate_coupling_exclusivity`

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

A scientific overview of the model component. The description should summarise the key processes simulated by the model component.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_non_empty_strings`

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* embedded_in *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The host model component (identified by its component property) in which this component is ‘embedded’. Taken from a standardised list: 7.1 component CV. Omit when this component is coupled with other components.

* **Validated by:**
  - `validate_embedding_exclusivity`

#### *field* family *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The model component’s ‘family’ name. Use ‘none’ to indicate that there is no such family.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_non_empty_strings`

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The name of the model component.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_non_empty_strings`

#### *field* native_horizontal_grid *: [NativeHorizontalGrid](#esgvoc.api.data_descriptors.NativeHorizontalGrid)* *[Required]*

A standardised description of the model component’s horizontal grid.

#### *field* native_vertical_grid *: [NativeVerticalGrid](#esgvoc.api.data_descriptors.NativeVerticalGrid)* *[Required]*

A standardised description of the model component’s vertical grid.

#### *field* references *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[Reference](#esgvoc.api.data_descriptors.Reference)]* *[Required]*

One or more references to published work for the model component.

* **Constraints:**
  - **min_length** = 1

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *validator* validate_code_base_format  *»*  *code_base*

Validate code_base is either ‘private’ or a URL.

#### *validator* validate_coupling_exclusivity  *»*  *coupled_with*

Validate that a component cannot be both embedded and coupled.

#### *validator* validate_embedding_exclusivity  *»*  *embedded_in*

Validate that a component cannot be both embedded and coupled.

#### *validator* validate_non_empty_strings  *»*  *name* *,* *code_base* *,* *component* *,* *description* *,* *family*

Validate that string fields are not empty.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.EMDResolution

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

The nominal resolution (in km) characterises the resolution of a model’s native horizontal grid. See section 5.1 Native horizontal grid properties.
Options for the native horizontal grid nominal resolution property are defined in the following table as a function of the value of the mean resolution km property:

for mean resolution, R, in the range (km):
nominal resolution is:
0.036 ≤ R < 0.072
0.05 km
0.072 ≤ R < 0.16
0.1 km
0.16 ≤ R < 0.36
0.25 km
0.36 ≤ R < 0.72
0.5 km
0.72 ≤ R < 1.6
1 km
1.6 ≤ R < 3.6
2.5 km
3.6 ≤ R < 7.2
5 km
7.2 ≤ R < 16
10 km
16 ≤ R < 36
25 km
36 ≤ R < 72
50 km
72 ≤ R < 160
100 km
160 ≤ R < 360
250 km
360 ≤ R < 720
500 km
720 ≤ R < 1600
1000 km
1600 ≤ R < 3600
2500 km
3600 ≤ R < 7200
5000 km
7200 ≤ R < 16000
10000 km

> 7.10. Native vertical grid “Coordinate” CV
<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "EMDResolution",
   "description": "The nominal resolution (in km) characterises the resolution of a model\u2019s native horizontal grid. See section 5.1 Native horizontal grid properties.\nOptions for the native horizontal grid nominal resolution property are defined in the following table as a function of the value of the mean resolution km property:\n\nfor mean resolution, R, in the range (km):\nnominal resolution is:\n0.036 \u2264 R < 0.072\n0.05 km\n0.072 \u2264 R < 0.16\n0.1 km\n0.16 \u2264 R < 0.36\n0.25 km\n0.36 \u2264 R < 0.72\n0.5 km\n0.72 \u2264 R < 1.6\n1 km\n1.6 \u2264 R < 3.6\n2.5 km\n3.6 \u2264 R < 7.2\n5 km\n7.2 \u2264 R < 16\n10 km\n16 \u2264 R < 36\n25 km\n36 \u2264 R < 72\n50 km\n72 \u2264 R < 160\n100 km\n160 \u2264 R < 360\n250 km\n360 \u2264 R < 720\n500 km\n720 \u2264 R < 1600\n1000 km\n1600 \u2264 R < 3600\n2500 km\n3600 \u2264 R < 7200\n5000 km\n7200 \u2264 R < 16000\n10000 km\n        7.10. Native vertical grid \u201cCoordinate\u201d CV",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "mean_resolution": {
         "title": "Mean Resolution",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "mean_resolution"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* mean_resolution *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Experiment

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

An ‘experiment’ refers to a specific, controlled simulation conducted using climate models to     investigate particular aspects of the Earth’s climate system. These experiments are designed     with set parameters, such as initial conditions, external forcings (like greenhouse gas     concentrations or solar radiation), and duration, to explore and understand climate behavior     under various scenarios and conditions.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Experiment",
   "description": "An 'experiment' refers to a specific, controlled simulation conducted using climate models to     investigate particular aspects of the Earth's climate system. These experiments are designed     with set parameters, such as initial conditions, external forcings (like greenhouse gas     concentrations or solar radiation), and duration, to explore and understand climate behavior     under various scenarios and conditions.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "activity": {
         "items": {
            "type": "string"
         },
         "title": "Activity",
         "type": "array"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "tier": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "title": "Tier"
      },
      "experiment_id": {
         "title": "Experiment Id",
         "type": "string"
      },
      "sub_experiment_id": {
         "anyOf": [
            {
               "items": {
                  "type": "string"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "title": "Sub Experiment Id"
      },
      "experiment": {
         "title": "Experiment",
         "type": "string"
      },
      "required_model_components": {
         "anyOf": [
            {
               "items": {
                  "type": "string"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "title": "Required Model Components"
      },
      "additional_allowed_model_components": {
         "items": {
            "type": "string"
         },
         "title": "Additional Allowed Model Components",
         "type": "array"
      },
      "start_year": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "title": "Start Year"
      },
      "end_year": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "title": "End Year"
      },
      "min_number_yrs_per_sim": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "title": "Min Number Yrs Per Sim"
      },
      "parent_activity_id": {
         "anyOf": [
            {
               "items": {
                  "type": "string"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "title": "Parent Activity Id"
      },
      "parent_experiment_id": {
         "anyOf": [
            {
               "items": {
                  "type": "string"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "title": "Parent Experiment Id"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "tier",
      "experiment_id",
      "sub_experiment_id",
      "experiment",
      "required_model_components",
      "start_year",
      "end_year",
      "min_number_yrs_per_sim",
      "parent_activity_id",
      "parent_experiment_id"
   ]
}
```

</details></p>

#### *field* activity *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

#### *field* additional_allowed_model_components *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* end_year *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* experiment *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* experiment_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* min_number_yrs_per_sim *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* parent_activity_id *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* parent_experiment_id *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* required_model_components *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* start_year *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* sub_experiment_id *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* tier *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.ForcingIndex

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ForcingIndex",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Frequency

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Frequency",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "long_name": {
         "title": "Long Name",
         "type": "string"
      },
      "name": {
         "title": "Name",
         "type": "string"
      },
      "unit": {
         "title": "Unit",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "long_name",
      "name",
      "unit"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* long_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* unit *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.FurtherInfoUrl

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "FurtherInfoUrl",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.GridArrangement

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Native horizontal grid Arakawa arrangement types. The Arakawa grid arrangement describes how orthogonal physical quantities (especially mass-related and velocity-related quantities) are represented and computed on the grid. See, for example, Collins et al. (2013) for a description of each grid type. See section 5.1 Native horizontal grid properties.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "GridArrangement",
   "description": "Native horizontal grid Arakawa arrangement types. The Arakawa grid arrangement describes how orthogonal physical quantities (especially mass-related and velocity-related quantities) are represented and computed on the grid. See, for example, Collins et al. (2013) for a description of each grid type. See section 5.1 Native horizontal grid properties.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.GridLabel

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "GridLabel",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "short_name": {
         "title": "Short Name",
         "type": "string"
      },
      "name": {
         "title": "Name",
         "type": "string"
      },
      "region": {
         "title": "Region",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "short_name",
      "name",
      "region"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* region *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* short_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.GridMapping

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "GridMapping",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.HorizontalLabel

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Horizontal sampling label.

This label provides information about the horizontal sampling of a given dataset.
For a list of allowed values, see
[TODO think about how to cross-reference to somewhere where people can look up the allowed values,
e.g. some summary of the values in [https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/horizontal_label](https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/horizontal_label).]

This label is used as the horizontal component of a branded variable’s suffix
(see [`BrandedSuffix`](#esgvoc.api.data_descriptors.BrandedSuffix)).
By definition, the horizontal label must be consistent with the branded suffix.
Horizontal labels must not contain the separator used when constructing the branded suffix.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "HorizontalLabel",
   "description": "Horizontal sampling label.\n\nThis label provides information about the horizontal sampling of a given dataset.\nFor a list of allowed values, see\n[TODO think about how to cross-reference to somewhere where people can look up the allowed values,\ne.g. some summary of the values in https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/horizontal_label.]\n\nThis label is used as the horizontal component of a branded variable's suffix\n(see :py:class:`BrandedSuffix`).\nBy definition, the horizontal label must be consistent with the branded suffix.\nHorizontal labels must not contain the separator used when constructing the branded suffix.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "label": {
         "title": "Label",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "label"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.InitialisationIndex

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "InitialisationIndex",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Institution

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

An registered institution for WCRP modelisation MIP.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Institution",
   "description": "An registered institution for WCRP modelisation MIP.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "acronyms": {
         "description": "it is the acronym that btw doesnt belong here anymore",
         "items": {
            "type": "string"
         },
         "title": "Acronyms",
         "type": "array"
      },
      "aliases": {
         "items": {
            "type": "string"
         },
         "title": "Aliases",
         "type": "array"
      },
      "established": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "title": "Established"
      },
      "labels": {
         "items": {
            "type": "string"
         },
         "title": "Labels",
         "type": "array"
      },
      "location": {
         "additionalProperties": true,
         "title": "Location",
         "type": "object"
      },
      "name": {
         "title": "Name",
         "type": "string"
      },
      "ror": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Ror"
      },
      "url": {
         "items": {
            "type": "string"
         },
         "title": "Url",
         "type": "array"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "established",
      "name",
      "ror"
   ]
}
```

</details></p>

#### *field* acronyms *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

it is the acronym that btw doesnt belong here anymore

#### *field* aliases *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* established *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* labels *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

#### *field* location *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)* *[Optional]*

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* ror *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* url *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.KnownBrandedVariable

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

A climate-related quantity or measurement, including information about sampling.

The concept of a branded variable was introduced in CMIP7.
A branded variable is composed of two parts.
The first part is the root variable (see [`Variable`](#esgvoc.api.data_descriptors.Variable)).
The second is the suffix (see [`BrandedSuffix`](#esgvoc.api.data_descriptors.BrandedSuffix)).

For further details on the development of branded variables,
see [this paper draft]([https://docs.google.com/document/d/19jzecgymgiiEsTDzaaqeLP6pTvLT-NzCMaq-wu-QoOc/edit?pli=1&tab=t.0](https://docs.google.com/document/d/19jzecgymgiiEsTDzaaqeLP6pTvLT-NzCMaq-wu-QoOc/edit?pli=1&tab=t.0)).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "KnownBrandedVariable",
   "description": "A climate-related quantity or measurement, including information about sampling.\n\nThe concept of a branded variable was introduced in CMIP7.\nA branded variable is composed of two parts.\nThe first part is the root variable (see :py:class:`Variable`).\nThe second is the suffix (see :py:class:`BrandedSuffix`).\n\nFor further details on the development of branded variables,\nsee [this paper draft](https://docs.google.com/document/d/19jzecgymgiiEsTDzaaqeLP6pTvLT-NzCMaq-wu-QoOc/edit?pli=1&tab=t.0).",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "cf_standard_name": {
         "description": "CF standard name, e.g., 'air_temperature'",
         "title": "Cf Standard Name",
         "type": "string"
      },
      "cf_units": {
         "description": "CF standard units, e.g., 'K'",
         "title": "Cf Units",
         "type": "string"
      },
      "cf_sn_status": {
         "description": "CF standard name status, e.g., 'approved'",
         "title": "Cf Sn Status",
         "type": "string"
      },
      "variable_root_name": {
         "description": "Variable root name, e.g., 'ta'",
         "title": "Variable Root Name",
         "type": "string"
      },
      "var_def_qualifier": {
         "default": "",
         "description": "Variable definition qualifier",
         "title": "Var Def Qualifier",
         "type": "string"
      },
      "branding_suffix_name": {
         "description": "Branding suffix, e.g., 'tavg-p19-hxy-air'",
         "title": "Branding Suffix Name",
         "type": "string"
      },
      "description": {
         "description": "Human-readable description",
         "title": "Description",
         "type": "string"
      },
      "dimensions": {
         "description": "NetCDF dimensions",
         "items": {
            "type": "string"
         },
         "title": "Dimensions",
         "type": "array"
      },
      "cell_methods": {
         "default": "",
         "description": "CF cell_methods attribute",
         "title": "Cell Methods",
         "type": "string"
      },
      "cell_measures": {
         "default": "",
         "description": "CF cell_measures attribute",
         "title": "Cell Measures",
         "type": "string"
      },
      "history": {
         "default": "",
         "description": "Processing history",
         "title": "History",
         "type": "string"
      },
      "realm": {
         "description": "Earth system realm, e.g., 'atmos'",
         "title": "Realm",
         "type": "string"
      },
      "temporal_label": {
         "description": "Temporal label, e.g., 'tavg'",
         "title": "Temporal Label",
         "type": "string"
      },
      "vertical_label": {
         "description": "Vertical label, e.g., 'p19'",
         "title": "Vertical Label",
         "type": "string"
      },
      "horizontal_label": {
         "description": "Horizontal label, e.g., 'hxy'",
         "title": "Horizontal Label",
         "type": "string"
      },
      "area_label": {
         "description": "Area label, e.g., 'air'",
         "title": "Area Label",
         "type": "string"
      },
      "bn_status": {
         "description": "Branded variable status, e.g., 'accepted'",
         "title": "Bn Status",
         "type": "string"
      },
      "positive_direction": {
         "default": "",
         "description": "Positive direction for the variable",
         "title": "Positive Direction",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "cf_standard_name",
      "cf_units",
      "cf_sn_status",
      "variable_root_name",
      "branding_suffix_name",
      "description",
      "dimensions",
      "realm",
      "temporal_label",
      "vertical_label",
      "horizontal_label",
      "area_label",
      "bn_status"
   ]
}
```

</details></p>

#### *field* area_label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Area label, e.g., ‘air’

#### *field* bn_status *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Branded variable status, e.g., ‘accepted’

#### *field* branding_suffix_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Branding suffix, e.g., ‘tavg-p19-hxy-air’

#### *field* cell_measures *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= ''*

CF cell_measures attribute

#### *field* cell_methods *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= ''*

CF cell_methods attribute

#### *field* cf_sn_status *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

CF standard name status, e.g., ‘approved’

#### *field* cf_standard_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

CF standard name, e.g., ‘air_temperature’

#### *field* cf_units *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

CF standard units, e.g., ‘K’

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Human-readable description

#### *field* dimensions *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Required]*

NetCDF dimensions

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* history *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= ''*

Processing history

#### *field* horizontal_label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Horizontal label, e.g., ‘hxy’

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* positive_direction *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= ''*

Positive direction for the variable

#### *field* realm *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Earth system realm, e.g., ‘atmos’

#### *field* temporal_label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Temporal label, e.g., ‘tavg’

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* var_def_qualifier *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= ''*

Variable definition qualifier

#### *field* variable_root_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Variable root name, e.g., ‘ta’

#### *field* vertical_label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

Vertical label, e.g., ‘p19’

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.License

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "License",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "kind": {
         "title": "Kind",
         "type": "string"
      },
      "license": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "License"
      },
      "url": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Url"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "kind",
      "license",
      "url"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* kind *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* license *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* url *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.MemberId

Bases: [`CompositeTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermDataDescriptor)

The member_id uniquely identifies a specific model simulation within an experiment. It is created by combining the sub_experiment, which describes the setup or timing of the simulation (like a specific start year), and the variant_label, which details the configuration of the model (including initial conditions, physics, and forcings). Together, they form a code like s1960-r1i1p1f1. This allows users to distinguish between different ensemble members and understand how each run differs from others within the same experiment.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "MemberId",
   "description": "The member_id uniquely identifies a specific model simulation within an experiment. It is created by combining the sub_experiment, which describes the setup or timing of the simulation (like a specific start year), and the variant_label, which details the configuration of the model (including initial conditions, physics, and forcings). Together, they form a code like s1960-r1i1p1f1. This allows users to distinguish between different ensemble members and understand how each run differs from others within the same experiment.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "separator": {
         "title": "Separator",
         "type": "string"
      },
      "parts": {
         "items": {
            "$ref": "#/$defs/CompositeTermPart"
         },
         "title": "Parts",
         "type": "array"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "$defs": {
      "CompositeTermPart": {
         "additionalProperties": true,
         "description": "A reference to a term, part of a composite term.",
         "properties": {
            "id": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "items": {
                        "type": "string"
                     },
                     "type": "array"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Id"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            }
         },
         "required": [
            "type",
            "is_required"
         ],
         "title": "CompositeTermPart",
         "type": "object"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "separator",
      "parts",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* parts *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[CompositeTermPart](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermPart)]* *[Required]*

The components.

#### *field* separator *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The components separator character.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.MipEra

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "MipEra",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "start": {
         "title": "Start",
         "type": "integer"
      },
      "end": {
         "title": "End",
         "type": "integer"
      },
      "name": {
         "title": "Name",
         "type": "string"
      },
      "url": {
         "title": "Url",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "start",
      "end",
      "name",
      "url"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* end *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* start *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* url *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Model

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

The following properties provide a top-level description of the model as whole.
In the property examples, underlined and italicised values are taken from section 7. Controlled vocabularies.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Model",
   "description": "The following properties provide a top-level description of the model as whole.\nIn the property examples, underlined and italicised values are taken from section 7. Controlled vocabularies.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "name": {
         "description": "The name of the top-level model. For CMIP7, this name will be registered as the model's source_id.",
         "minLength": 1,
         "title": "Name",
         "type": "string"
      },
      "family": {
         "description": "The top-level model's 'family' name. Use 'none' to indicate that there is no such family.",
         "minLength": 1,
         "title": "Family",
         "type": "string"
      },
      "dynamic_components": {
         "description": "The model components that are dynamically simulated within the top-level model. Taken from a standardised list: 7.1 component CV.",
         "items": {
            "type": "string"
         },
         "minItems": 1,
         "title": "Dynamic Components",
         "type": "array"
      },
      "prescribed_components": {
         "description": "The components that are represented in the top-level model with prescribed values. Taken from a standardised list: 7.1 component CV.",
         "items": {
            "type": "string"
         },
         "title": "Prescribed Components",
         "type": "array"
      },
      "omitted_components": {
         "description": "The components that are wholly omitted from the top-level model. Taken from a standardised list: 7.1 component CV.",
         "items": {
            "type": "string"
         },
         "title": "Omitted Components",
         "type": "array"
      },
      "description": {
         "description": "A brief, free-text scientific overview of the top-level model.",
         "minLength": 1,
         "title": "Description",
         "type": "string"
      },
      "calendar": {
         "description": "The calendar, or calendars, that define which dates are permitted in the top-level model. Taken from a standardised list: 7.2 calendar CV.",
         "items": {
            "type": "string"
         },
         "minItems": 1,
         "title": "Calendar",
         "type": "array"
      },
      "release_year": {
         "description": "The year in which the top-level model being documented was released, or first used for published simulations.",
         "maximum": 2100,
         "minimum": 1900,
         "title": "Release Year",
         "type": "integer"
      },
      "references": {
         "description": "One or more references to published work for the top-level model as a whole.",
         "items": {
            "$ref": "#/$defs/Reference"
         },
         "minItems": 1,
         "title": "References",
         "type": "array"
      },
      "model_components": {
         "anyOf": [
            {
               "items": {
                  "$ref": "#/$defs/EMDModelComponent"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The model components that dynamically simulate processes within the model.",
         "title": "Model Components"
      }
   },
   "$defs": {
      "EMDModelComponent": {
         "additionalProperties": true,
         "description": "Properties that provide a description of individual model components.\nEight model components are defined that somewhat independently account for different sets of interactive processes: aerosol, atmosphere, atmospheric chemistry, land surface, land ice, ocean, ocean biogeochemistry, and sea ice. The interactive processes covered by each  component are described in more detail in section 7.1. Model Component Type CV.\nEach component is characterized as \u201cdynamic\u201d, \u201cprescribed\u201d, or \u201comitted\u201d (see 2. Model properties), but only model components that dynamically simulate their processes are described in this section of the EMD. Relationships among dynamically simulated components are indicated by specifying that they are \u201cembedded in\u201d or \u201ccoupled with\u201d other components (see 3.1. Embedded and Coupled components).\nNote for CMIP7: The component types in the 7.1. Model Component Type CV have similar names and definitions to the CMIP \u201crealms\u201d given by the CMIP6_realm.json file (Durack et al., 2025), but the context in which they are used is different. An EMD component type defines a set of physical process that are simulated by one model component; whereas as one or more CMIP realms are assigned to an individual model output variable according to which sets of processes the variable is physically related to, rather than which model component created it. The CMIP realms for an output variable often include the EMD component type that created it, but this is not always the case.\nIn the property examples, underlined and italicised values are taken from section 7. Controlled vocabularies.\n\u2022 Component\n    \u25e6 The type of the model component.\n    \u25e6 Taken from a standardised list: 7.1. Model Component Type CV.\n    \u25e6 E.g. aerosol\n\u2022 Name\n    \u25e6 The name of the model component.\n    \u25e6 If the component is embedded in a host component and has no commonly recognised name, then a name can be constructed by combining the host component\u2019s Name with this component\u2019s Component type, separated by a hyphen.\n    \u25e6 E.g. BISICLES-UKESM-ISMIP6\n    \u25e6 E.g. MOSES2\n    \u25e6 E.g. HadAM3-aerosol\n\u2022 Family\n    \u25e6 The model component\u2019s \u201cfamily\u201d name. For a component, its family members should all share much of their code bases, but the members may be configured in different ways (e.g. different resolutions, parameter choices, or the inclusion or not of particular sub-process). See Masson and Knutti (2011) for an example of how the family can be used to inform model genealogies.\n    \u25e6 Use a value of \u201cnone\u201d to indicate that there is no such family for the model component.\n    \u25e6 E.g. BISICLES\n    \u25e6 E.g. CLM\n    \u25e6 E.g. none\n\u2022 Description\n    \u25e6 A scientific overview of the model component.\n    \u25e6 The description should summarise the key processes simulated by the model component.\n    \u25e6 For CMIP7, easy-to-answer MIP-relevant questions may be posed, which should be addressed using free text. For instance \u201cAre aerosols driven by emissions or concentration?\u201d or \u201cWhat is the aerosol activation scheme?\u201d.\n\u2022 References\n    \u25e6 References to published work for the model component.\n    \u25e6 Each reference must include the properties described in section 4. References.\n\u2022 Code base\n    \u25e6 A URL (preferably for a DOI) for the source code for the model component.\n    \u25e6 If the source code is in a versioncontrolled repository (e.g. a git or svn repository) then the URL must identify a specific point in the repository\u2019s history.\n    \u25e6 Set to \u201cprivate\u201d if not publicly available.\n\u2022 Embedded in\n    \u25e6 The host model component (identified by its Component property) in which this component is \u201cembedded\u201d.\n    \u25e6 See section 3.1. Embedded and Coupled model components for a definition of an embedded component. Note that a component must be either embedded in a another component or else coupled with other components, but can not be both.\n    \u25e6 Taken from a standardised list: 7.1. Model Component Type CV.\n    \u25e6 Omit when this component is coupled with other components (see the Coupled with property).\n    \u25e6 E.g. in some cases, for an aerosol model component: atmosphere\n\u2022 Coupled with\n    \u25e6 The model components (identified by their Component properties) with which this component is \u201ccoupled\u201d.\n    \u25e6 See section 3.1. Embedded and Coupled model components for a definition of a coupled component. Note that a component must be either embedded in a another component or else coupled with other components, but can not be both.\n    \u25e6 Taken from a standardised list: 7.1. Model Components Type CV.\n    \u25e6 Omit when this component is embedded in another component (see the Embedded in property).\n    \u25e6 E.g. In some cases for a land ice component: atmosphere, land surface, ocean\n\u2022 Native horizontal grid\n    \u25e6 A standardised description of the model component\u2019s horizontal grid.\n    \u25e6 The grid is described by defining the properties listed in section 5.1. Native horizontal grid properties.\n\u2022 Native vertical grid\n    \u25e6 A standardised description of the model component\u2019s vertical grid.\n    \u25e6 The grid is described by defining the properties listed in section 5.2. Native vertical grid properties.",
         "properties": {
            "id": {
               "title": "Id",
               "type": "string"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "drs_name": {
               "title": "Drs Name",
               "type": "string"
            },
            "component": {
               "description": "The type of the model component. Taken from a standardised list: 7.1 component CV.",
               "title": "Component",
               "type": "string"
            },
            "name": {
               "description": "The name of the model component.",
               "minLength": 1,
               "title": "Name",
               "type": "string"
            },
            "family": {
               "description": "The model component's 'family' name. Use 'none' to indicate that there is no such family.",
               "minLength": 1,
               "title": "Family",
               "type": "string"
            },
            "description": {
               "description": "A scientific overview of the model component. The description should summarise the key processes simulated by the model component.",
               "minLength": 1,
               "title": "Description",
               "type": "string"
            },
            "references": {
               "description": "One or more references to published work for the model component.",
               "items": {
                  "$ref": "#/$defs/Reference"
               },
               "minItems": 1,
               "title": "References",
               "type": "array"
            },
            "code_base": {
               "description": "A URL (preferably for a DOI) for the source code for the model component. Set to 'private' if not publicly available.",
               "minLength": 1,
               "title": "Code Base",
               "type": "string"
            },
            "embedded_in": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The host model component (identified by its component property) in which this component is 'embedded'. Taken from a standardised list: 7.1 component CV. Omit when this component is coupled with other components.",
               "title": "Embedded In"
            },
            "coupled_with": {
               "anyOf": [
                  {
                     "items": {
                        "type": "string"
                     },
                     "type": "array"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The model components (identified by their component properties) with which this component is 'coupled'. Taken from a standardised list: 7.1 component CV. Omit when this component is embedded in another component.",
               "title": "Coupled With"
            },
            "native_horizontal_grid": {
               "$ref": "#/$defs/NativeHorizontalGrid",
               "description": "A standardised description of the model component's horizontal grid."
            },
            "native_vertical_grid": {
               "$ref": "#/$defs/NativeVerticalGrid",
               "description": "A standardised description of the model component's vertical grid."
            }
         },
         "required": [
            "id",
            "type",
            "drs_name",
            "component",
            "name",
            "family",
            "description",
            "references",
            "code_base",
            "native_horizontal_grid",
            "native_vertical_grid"
         ],
         "title": "EMDModelComponent",
         "type": "object"
      },
      "NativeHorizontalGrid": {
         "additionalProperties": true,
         "description": "The model component\u2019s native horizontal grid is described by a subset of the following properties:\n\n\u2022 Description\n    \u25e6 A free-text description of the grid.\n    \u25e6 A description is only required if there is information that is not covered by any of the other properties.\n    \u25e6 Omit if not needed.\n\u2022 Type\n    \u25e6 The horizontal grid type, i.e. the method of distributing grid points over the sphere.\n    \u25e6 Taken from a standardised list: 7.3. Native horizontal grid Type CV.\n    \u25e6 If there is no horizontal grid, then the value \u201cnone\u201d must be selected, and no other properties should be set.\n    \u25e6 E.g. regular_latitude_longitude\n    \u25e6 E.g. tripolar\n\u2022 Grid mapping\n    \u25e6 The name of the coordinate reference system of the horizontal coordinates.\n    \u25e6 Taken from a standardised list: 7.4. Native horizontal grid Grid Mapping CV.\n    \u25e6 E.g. latitude_longitude\n\u2022 Region\n    \u25e6 The geographical region, or regions, over which the component is simulated.\n    \u25e6 A region is a contiguous part of the Earth\u2019s surface, and may include areas for which no calculations are made (such as ocean areas for a land surface component).\n    \u25e6 Taken from a standardised list: 7.5. Native horizontal grid Region CV.\n    \u25e6 E.g. global\n    \u25e6 E.g. antarctica, greenland\n\u2022 Temporal refinement\n    \u25e6 The grid temporal refinement, indicating how the distribution of grid cells varies with time.\n    \u25e6 Taken from a standardised list: 7.6. Native horizontal grid Temporal refinement CV.\n    \u25e6 E.g. static\n\u2022 Arrangement\n    \u25e6 A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields.\n    \u25e6 Taken from a standardised list: 7.7. Native horizontal grid Arrangement CV.\n    \u25e6 E.g. arakawa_B\n\u2022 Resolution X\n    \u25e6 The size of grid cells in the X direction.\n    \u25e6 The value\u2019s physical units are given by the Units property.\n    \u25e6 Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 3.75\n\u2022 Resolution Y\n    \u25e6 The size of grid cells in the Y direction.\n    \u25e6 The value\u2019s physical units are given by the Units property.\n    \u25e6 Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 2.5\n\u2022 Units\n    \u25e6 The physical units of the Resolution X and Resolution Y property values.\n    \u25e6 The only acceptable units are  \u201ckm\u201d (kilometre, unit for length) or \u201cdegree\u201d (unit for angular measure).\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. km\n    \u25e6 E.g. degree\n\u2022 N cells\n    \u25e6 The total number of cells in the horizontal grid.\n    \u25e6 If the horizontal grid is unstructured then when the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number of cells for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 265160\n\u2022 N sides\n    \u25e6 For unstructured horizontal grids only, the total number of unique cell sides.\n    \u25e6 When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number of sides for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 714274\n\u2022 N vertices\n    \u25e6 For unstructured horizontal grids only, the number of unique cell vertices.\n    \u25e6 When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 567145\n\u2022 Truncation method\n    \u25e6 The method for truncating the spherical harmonic representation of a spectral model.\n    \u25e6 Taken from a standardised list: 7.8. Native horizontal grid Truncation method CV.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. triangular\n\u2022 Truncation number\n    \u25e6 The zonal (east-west) wave number at which a spectral model is truncated.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 63\n\u2022 Resolution range km\n    \u25e6 The minimum and maximum resolution (in km) of cells of the native horizontal grid.\n    \u25e6 Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum and mean resolution.\n    \u25e6 E.g. 57.0, 290\n\u2022 Mean resolution km\n    \u25e6 The mean resolution (in km) of the native horizontal grid on which the mass-related quantities are carried by the model.\n    \u25e6 Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum, and mean resolution.\n    \u25e6 E.g. 234.8\n\u2022 Nominal resolution\n    \u25e6 The nominal resolution characterises the approximate resolution of a model\u2019s native horizontal grid.\n    \u25e6 The nominal resolution is obtained (once the Mean resolution km property is calculated) by looking it up in the table at 7.9. Native horizontal grid Nominal resolution CV.\n    \u25e6 E.g. A grid with mean resolution of 82 will have a nominal resolution of 100 km",
         "properties": {
            "id": {
               "title": "Id",
               "type": "string"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "drs_name": {
               "title": "Drs Name",
               "type": "string"
            },
            "grid": {
               "description": "The horizontal grid type, i.e. the method of distributing grid points over the sphere. Taken from a standardised list: 7.3 grid CV. If there is no horizontal grid, then the value 'none' must be selected.",
               "title": "Grid",
               "type": "string"
            },
            "description": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "A free-text description of the grid. A description is only required if there is information that is not covered by any of the other properties.",
               "title": "Description"
            },
            "grid_mapping": {
               "description": "The name of the coordinate reference system of the horizontal coordinates. Taken from a standardised list: 7.4 grid_mapping CV.",
               "title": "Grid Mapping",
               "type": "string"
            },
            "region": {
               "description": "The geographical region, or regions, over which the component is simulated. Taken from a standardised list: 7.5 region CV.",
               "title": "Region",
               "type": "string"
            },
            "temporal_refinement": {
               "description": "The grid temporal refinement, indicating how the distribution of grid cells varies with time. Taken from a standardised list: 7.6 temporal_refinement CV.",
               "title": "Temporal Refinement",
               "type": "string"
            },
            "arrangement": {
               "description": "A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields. Taken from a standardised list: 7.7 arrangement CV.",
               "title": "Arrangement",
               "type": "string"
            },
            "resolution_x": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The size of grid cells in the X direction. The value's physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.",
               "title": "Resolution X"
            },
            "resolution_y": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The size of grid cells in the Y direction. The value's physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.",
               "title": "Resolution Y"
            },
            "horizontal_units": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The physical units of the resolution_x and resolution_y property values. Taken from a standardised list: 7.8 horizontal_units CV.",
               "title": "Horizontal Units"
            },
            "n_cells": {
               "description": "The total number of cells in the horizontal grid.",
               "minimum": 1,
               "title": "N Cells",
               "type": "integer"
            },
            "n_sides": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "For unstructured horizontal grids only, the total number of unique cell sides.",
               "title": "N Sides"
            },
            "n_vertices": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "For unstructured horizontal grids only, the number of unique cell vertices.",
               "title": "N Vertices"
            },
            "truncation_method": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The method for truncating the spherical harmonic representation of a spectral model. Taken from a standardised list: 7.9 truncation_method CV.",
               "title": "Truncation Method"
            },
            "truncation_number": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The zonal (east-west) wave number at which a spectral model is truncated.",
               "title": "Truncation Number"
            },
            "resolution_range_km": {
               "description": "The minimum and maximum resolution (in km) of cells of the horizontal grid.",
               "items": {
                  "type": "number"
               },
               "maxItems": 2,
               "minItems": 2,
               "title": "Resolution Range Km",
               "type": "array"
            },
            "mean_resolution_km": {
               "description": "The mean resolution (in km) of cells of the horizontal grid.",
               "exclusiveMinimum": 0,
               "title": "Mean Resolution Km",
               "type": "number"
            },
            "nominal_resolution": {
               "description": "The nominal resolution characterises the approximate resolution of a horizontal grid. Taken from a standardised list: 7.10 nominal_resolution CV.",
               "title": "Nominal Resolution",
               "type": "string"
            }
         },
         "required": [
            "id",
            "type",
            "drs_name",
            "grid",
            "grid_mapping",
            "region",
            "temporal_refinement",
            "arrangement",
            "n_cells",
            "resolution_range_km",
            "mean_resolution_km",
            "nominal_resolution"
         ],
         "title": "NativeHorizontalGrid",
         "type": "object"
      },
      "NativeVerticalGrid": {
         "additionalProperties": true,
         "description": "4.2. Vertical grid\nThe model component's native vertical grid is described by a subset of the following properties:\n    \u2022 Description\n        \u25e6 A free-text description of the vertical grid.\n        \u25e6 A description is only required if there is information that is not covered by any of the other properties.\n        \u25e6 Omit if not needed.\n    \u2022 Coordinate\n        \u25e6 The coordinate type of the vertical grid.\n        \u25e6 Taken from a standardised list: 7.11. coordinate CV.\n        \u25e6 If there is no vertical grid, then the value \"none\" must be selected, and no other properties should be set.\n        \u25e6 E.g. height\n        \u25e6 E.g. none\n    \u2022 N z\n        \u25e6 The number of layers (i.e. grid cells) in the Z direction.\n        \u25e6 Omit when not applicable or not constant.\n        \u25e6 If the number of layers varies in time or across the horizontal grid, then the N z range property may be used instead.\n        \u25e6 E.g. 70\n    \u2022 N z range\n        \u25e6 The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers.\n        \u25e6 Omit if the N z property has been set.\n        \u25e6 E.g. 5, 15\n    \u2022 Bottom layer thickness\n        \u25e6 The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 If the value varies in time or across the horizontal grid, then provide a nominal or typical value.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. 10\n    \u2022 Top layer thickness\n        \u25e6 The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 If the value varies in time or across the horizontal grid, then provide a nominal or typical value.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. 10\n    \u2022 Top of model\n        \u25e6 The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth).\n        \u25e6 The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable or not constant.\n        \u25e6 E.g. 85003.5\n    \u2022 Vertical units\n        \u25e6 The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values.\n        \u25e6 Taken from a standardised list: 7.12. vertical_units CV.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. m",
         "properties": {
            "id": {
               "title": "Id",
               "type": "string"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "coordinate": {
               "description": "The coordinate type of the vertical grid. Taken from a standardised list: 7.11 coordinate CV. If there is no vertical grid, then the value 'none' must be selected.",
               "title": "Coordinate",
               "type": "string"
            },
            "description": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "A free-text description of the vertical grid. A description is only required if there is information that is not covered by any of the other properties.",
               "title": "Description"
            },
            "n_z": {
               "anyOf": [
                  {
                     "minimum": 1,
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The number of layers (i.e. grid cells) in the Z direction. Omit when not applicable or not constant. If the number of layers varies in time or across the horizontal grid, then the n_z_range property may be used instead.",
               "title": "N Z"
            },
            "n_z_range": {
               "anyOf": [
                  {
                     "items": {
                        "type": "integer"
                     },
                     "maxItems": 2,
                     "minItems": 2,
                     "type": "array"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers. Omit if the n_z property has been set.",
               "title": "N Z Range"
            },
            "bottom_layer_thickness": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value's physical units are given by the vertical_units property.",
               "title": "Bottom Layer Thickness"
            },
            "top_layer_thickness": {
               "anyOf": [
                  {
                     "exclusiveMinimum": 0,
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value's physical units are given by the vertical_units property.",
               "title": "Top Layer Thickness"
            },
            "top_of_model": {
               "anyOf": [
                  {
                     "type": "number"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth). The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level). The value's physical units are given by the vertical_units property.",
               "title": "Top Of Model"
            },
            "vertical_units": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "description": "The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values. Taken from a standardised list: 7.12 vertical_units CV.",
               "title": "Vertical Units"
            }
         },
         "required": [
            "id",
            "type",
            "coordinate"
         ],
         "title": "NativeVerticalGrid",
         "type": "object"
      },
      "Reference": {
         "description": "The top-level model and its model components must each have at least one reference, defined by the following properties:\n\n\u2022 Citation\n    \u25e6 A human-readable citation for the work.\n    \u25e6 E.g. Smith, R. S., Mathiot, P., Siahaan, A., Lee, V., Cornford, S. L., Gregory, J. M., et al. (2021). Coupling the U.K. Earth System model to dynamic models of the Greenland and Antarctic ice sheets. Journal of Advances in Modeling Earth Systems, 13, e2021MS002520. https://doi.org/10.1029/2021MS002520, 2023\n\u2022 DOI\n    \u25e6 The persistent identifier (DOI) used to identify the work.\n    \u25e6 A DOI is required for all references. A reference that does not already have a DOI (as could be the case for some technical reports, for instance) must be given one (e.g. with a service like Zenodo).\n    \u25e6 E.g. https://doi.org/10.1029/2021MS002520",
         "properties": {
            "citation": {
               "description": "A human-readable citation for the work.",
               "minLength": 1,
               "title": "Citation",
               "type": "string"
            },
            "doi": {
               "description": "The persistent identifier (DOI) used to identify the work. Must be a valid DOI URL.",
               "minLength": 1,
               "title": "Doi",
               "type": "string"
            }
         },
         "required": [
            "citation",
            "doi"
         ],
         "title": "Reference",
         "type": "object"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "name",
      "family",
      "dynamic_components",
      "description",
      "calendar",
      "release_year",
      "references"
   ]
}
```

</details></p>
* **Validators:**
  - `validate_calendar_list` » `calendar`
  - `validate_component_lists` » `dynamic_components`
  - `validate_component_lists` » `omitted_components`
  - `validate_component_lists` » `prescribed_components`
  - `validate_non_empty_strings` » `description`
  - `validate_non_empty_strings` » `family`
  - `validate_non_empty_strings` » `name`

#### *field* calendar *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Required]*

The calendar, or calendars, that define which dates are permitted in the top-level model. Taken from a standardised list: 7.2 calendar CV.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_calendar_list`

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

A brief, free-text scientific overview of the top-level model.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_non_empty_strings`

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* dynamic_components *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Required]*

The model components that are dynamically simulated within the top-level model. Taken from a standardised list: 7.1 component CV.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_component_lists`

#### *field* family *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The top-level model’s ‘family’ name. Use ‘none’ to indicate that there is no such family.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_non_empty_strings`

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* model_components *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[EMDModelComponent](#esgvoc.api.data_descriptors.EMDModelComponent)] | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The model components that dynamically simulate processes within the model.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The name of the top-level model. For CMIP7, this name will be registered as the model’s source_id.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_non_empty_strings`

#### *field* omitted_components *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

The components that are wholly omitted from the top-level model. Taken from a standardised list: 7.1 component CV.

* **Validated by:**
  - `validate_component_lists`

#### *field* prescribed_components *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

The components that are represented in the top-level model with prescribed values. Taken from a standardised list: 7.1 component CV.

* **Validated by:**
  - `validate_component_lists`

#### *field* references *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[Reference](#esgvoc.api.data_descriptors.Reference)]* *[Required]*

One or more references to published work for the top-level model as a whole.

* **Constraints:**
  - **min_length** = 1

#### *field* release_year *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

The year in which the top-level model being documented was released, or first used for published simulations.

* **Constraints:**
  - **ge** = 1900
  - **le** = 2100

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *validator* validate_calendar_list  *»*  *calendar*

Validate calendar list contains valid strings.

#### *validator* validate_component_lists  *»*  *prescribed_components* *,* *omitted_components* *,* *dynamic_components*

Validate component lists contain valid strings.

#### *validator* validate_non_empty_strings  *»*  *family* *,* *name* *,* *description*

Validate that string fields are not empty.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.ModelComponent

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ModelComponent",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "name": {
         "title": "Name",
         "type": "string"
      },
      "realm": {
         "additionalProperties": true,
         "title": "Realm",
         "type": "object"
      },
      "nominal_resolution": {
         "additionalProperties": true,
         "title": "Nominal Resolution",
         "type": "object"
      },
      "version": {
         "title": "Version",
         "type": "integer"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "name",
      "realm",
      "nominal_resolution",
      "version"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* nominal_resolution *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)* *[Required]*

#### *field* realm *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* version *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.NativeHorizontalGrid

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

The model component’s native horizontal grid is described by a subset of the following properties:

• Description
  : ◦ A free-text description of the grid.
    ◦ A description is only required if there is information that is not covered by any of the other properties.
    ◦ Omit if not needed.
• Type
  : ◦ The horizontal grid type, i.e. the method of distributing grid points over the sphere.
    ◦ Taken from a standardised list: 7.3. Native horizontal grid Type CV.
    ◦ If there is no horizontal grid, then the value “none” must be selected, and no other properties should be set.
    ◦ E.g. regular_latitude_longitude
    ◦ E.g. tripolar
• Grid mapping
  : ◦ The name of the coordinate reference system of the horizontal coordinates.
    ◦ Taken from a standardised list: 7.4. Native horizontal grid Grid Mapping CV.
    ◦ E.g. latitude_longitude
• Region
  : ◦ The geographical region, or regions, over which the component is simulated.
    ◦ A region is a contiguous part of the Earth’s surface, and may include areas for which no calculations are made (such as ocean areas for a land surface component).
    ◦ Taken from a standardised list: 7.5. Native horizontal grid Region CV.
    ◦ E.g. global
    ◦ E.g. antarctica, greenland
• Temporal refinement
  : ◦ The grid temporal refinement, indicating how the distribution of grid cells varies with time.
    ◦ Taken from a standardised list: 7.6. Native horizontal grid Temporal refinement CV.
    ◦ E.g. static
• Arrangement
  : ◦ A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields.
    ◦ Taken from a standardised list: 7.7. Native horizontal grid Arrangement CV.
    ◦ E.g. arakawa_B
• Resolution X
  : ◦ The size of grid cells in the X direction.
    ◦ The value’s physical units are given by the Units property.
    ◦ Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.
    ◦ Omit when not applicable.
    ◦ E.g. 3.75
• Resolution Y
  : ◦ The size of grid cells in the Y direction.
    ◦ The value’s physical units are given by the Units property.
    ◦ Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.
    ◦ Omit when not applicable.
    ◦ E.g. 2.5
• Units
  : ◦ The physical units of the Resolution X and Resolution Y property values.
    ◦ The only acceptable units are  “km” (kilometre, unit for length) or “degree” (unit for angular measure).
    ◦ Omit when not applicable.
    ◦ E.g. km
    ◦ E.g. degree
• N cells
  : ◦ The total number of cells in the horizontal grid.
    ◦ If the horizontal grid is unstructured then when the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the “centre” of a dual mesh cell, and vice versa), the number of cells for the primal mesh should be provided.
    ◦ Omit when not applicable or not constant.
    ◦ E.g. 265160
• N sides
  : ◦ For unstructured horizontal grids only, the total number of unique cell sides.
    ◦ When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the “centre” of a dual mesh cell, and vice versa), the number of sides for the primal mesh should be provided.
    ◦ Omit when not applicable or not constant.
    ◦ E.g. 714274
• N vertices
  : ◦ For unstructured horizontal grids only, the number of unique cell vertices.
    ◦ When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the “centre” of a dual mesh cell, and vice versa), the number for the primal mesh should be provided.
    ◦ Omit when not applicable or not constant.
    ◦ E.g. 567145
• Truncation method
  : ◦ The method for truncating the spherical harmonic representation of a spectral model.
    ◦ Taken from a standardised list: 7.8. Native horizontal grid Truncation method CV.
    ◦ Omit when not applicable.
    ◦ E.g. triangular
• Truncation number
  : ◦ The zonal (east-west) wave number at which a spectral model is truncated.
    ◦ Omit when not applicable.
    ◦ E.g. 63
• Resolution range km
  : ◦ The minimum and maximum resolution (in km) of cells of the native horizontal grid.
    ◦ Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum and mean resolution.
    ◦ E.g. 57.0, 290
• Mean resolution km
  : ◦ The mean resolution (in km) of the native horizontal grid on which the mass-related quantities are carried by the model.
    ◦ Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum, and mean resolution.
    ◦ E.g. 234.8
• Nominal resolution
  : ◦ The nominal resolution characterises the approximate resolution of a model’s native horizontal grid.
    ◦ The nominal resolution is obtained (once the Mean resolution km property is calculated) by looking it up in the table at 7.9. Native horizontal grid Nominal resolution CV.
    ◦ E.g. A grid with mean resolution of 82 will have a nominal resolution of 100 km

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "NativeHorizontalGrid",
   "description": "The model component\u2019s native horizontal grid is described by a subset of the following properties:\n\n\u2022 Description\n    \u25e6 A free-text description of the grid.\n    \u25e6 A description is only required if there is information that is not covered by any of the other properties.\n    \u25e6 Omit if not needed.\n\u2022 Type\n    \u25e6 The horizontal grid type, i.e. the method of distributing grid points over the sphere.\n    \u25e6 Taken from a standardised list: 7.3. Native horizontal grid Type CV.\n    \u25e6 If there is no horizontal grid, then the value \u201cnone\u201d must be selected, and no other properties should be set.\n    \u25e6 E.g. regular_latitude_longitude\n    \u25e6 E.g. tripolar\n\u2022 Grid mapping\n    \u25e6 The name of the coordinate reference system of the horizontal coordinates.\n    \u25e6 Taken from a standardised list: 7.4. Native horizontal grid Grid Mapping CV.\n    \u25e6 E.g. latitude_longitude\n\u2022 Region\n    \u25e6 The geographical region, or regions, over which the component is simulated.\n    \u25e6 A region is a contiguous part of the Earth\u2019s surface, and may include areas for which no calculations are made (such as ocean areas for a land surface component).\n    \u25e6 Taken from a standardised list: 7.5. Native horizontal grid Region CV.\n    \u25e6 E.g. global\n    \u25e6 E.g. antarctica, greenland\n\u2022 Temporal refinement\n    \u25e6 The grid temporal refinement, indicating how the distribution of grid cells varies with time.\n    \u25e6 Taken from a standardised list: 7.6. Native horizontal grid Temporal refinement CV.\n    \u25e6 E.g. static\n\u2022 Arrangement\n    \u25e6 A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields.\n    \u25e6 Taken from a standardised list: 7.7. Native horizontal grid Arrangement CV.\n    \u25e6 E.g. arakawa_B\n\u2022 Resolution X\n    \u25e6 The size of grid cells in the X direction.\n    \u25e6 The value\u2019s physical units are given by the Units property.\n    \u25e6 Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 3.75\n\u2022 Resolution Y\n    \u25e6 The size of grid cells in the Y direction.\n    \u25e6 The value\u2019s physical units are given by the Units property.\n    \u25e6 Report only when cell sizes are identical or else reasonably uniform (in their given units). When cells sizes are not identical, a representative value should be provided and this fact noted in the Description property, but only if the cell sizes vary by less than 25%.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 2.5\n\u2022 Units\n    \u25e6 The physical units of the Resolution X and Resolution Y property values.\n    \u25e6 The only acceptable units are  \u201ckm\u201d (kilometre, unit for length) or \u201cdegree\u201d (unit for angular measure).\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. km\n    \u25e6 E.g. degree\n\u2022 N cells\n    \u25e6 The total number of cells in the horizontal grid.\n    \u25e6 If the horizontal grid is unstructured then when the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number of cells for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 265160\n\u2022 N sides\n    \u25e6 For unstructured horizontal grids only, the total number of unique cell sides.\n    \u25e6 When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number of sides for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 714274\n\u2022 N vertices\n    \u25e6 For unstructured horizontal grids only, the number of unique cell vertices.\n    \u25e6 When the component utilises primal and dual meshes (i.e. when each vertex of a primal mesh cell is uniquely associated with the \u201ccentre\u201d of a dual mesh cell, and vice versa), the number for the primal mesh should be provided.\n    \u25e6 Omit when not applicable or not constant.\n    \u25e6 E.g. 567145\n\u2022 Truncation method\n    \u25e6 The method for truncating the spherical harmonic representation of a spectral model.\n    \u25e6 Taken from a standardised list: 7.8. Native horizontal grid Truncation method CV.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. triangular\n\u2022 Truncation number\n    \u25e6 The zonal (east-west) wave number at which a spectral model is truncated.\n    \u25e6 Omit when not applicable.\n    \u25e6 E.g. 63\n\u2022 Resolution range km\n    \u25e6 The minimum and maximum resolution (in km) of cells of the native horizontal grid.\n    \u25e6 Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum and mean resolution.\n    \u25e6 E.g. 57.0, 290\n\u2022 Mean resolution km\n    \u25e6 The mean resolution (in km) of the native horizontal grid on which the mass-related quantities are carried by the model.\n    \u25e6 Calculate as described in this documented Python code, which can be used to obtain the maximum, minimum, and mean resolution.\n    \u25e6 E.g. 234.8\n\u2022 Nominal resolution\n    \u25e6 The nominal resolution characterises the approximate resolution of a model\u2019s native horizontal grid.\n    \u25e6 The nominal resolution is obtained (once the Mean resolution km property is calculated) by looking it up in the table at 7.9. Native horizontal grid Nominal resolution CV.\n    \u25e6 E.g. A grid with mean resolution of 82 will have a nominal resolution of 100 km",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "grid": {
         "description": "The horizontal grid type, i.e. the method of distributing grid points over the sphere. Taken from a standardised list: 7.3 grid CV. If there is no horizontal grid, then the value 'none' must be selected.",
         "title": "Grid",
         "type": "string"
      },
      "description": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "A free-text description of the grid. A description is only required if there is information that is not covered by any of the other properties.",
         "title": "Description"
      },
      "grid_mapping": {
         "description": "The name of the coordinate reference system of the horizontal coordinates. Taken from a standardised list: 7.4 grid_mapping CV.",
         "title": "Grid Mapping",
         "type": "string"
      },
      "region": {
         "description": "The geographical region, or regions, over which the component is simulated. Taken from a standardised list: 7.5 region CV.",
         "title": "Region",
         "type": "string"
      },
      "temporal_refinement": {
         "description": "The grid temporal refinement, indicating how the distribution of grid cells varies with time. Taken from a standardised list: 7.6 temporal_refinement CV.",
         "title": "Temporal Refinement",
         "type": "string"
      },
      "arrangement": {
         "description": "A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields. Taken from a standardised list: 7.7 arrangement CV.",
         "title": "Arrangement",
         "type": "string"
      },
      "resolution_x": {
         "anyOf": [
            {
               "exclusiveMinimum": 0,
               "type": "number"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The size of grid cells in the X direction. The value's physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.",
         "title": "Resolution X"
      },
      "resolution_y": {
         "anyOf": [
            {
               "exclusiveMinimum": 0,
               "type": "number"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The size of grid cells in the Y direction. The value's physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.",
         "title": "Resolution Y"
      },
      "horizontal_units": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The physical units of the resolution_x and resolution_y property values. Taken from a standardised list: 7.8 horizontal_units CV.",
         "title": "Horizontal Units"
      },
      "n_cells": {
         "description": "The total number of cells in the horizontal grid.",
         "minimum": 1,
         "title": "N Cells",
         "type": "integer"
      },
      "n_sides": {
         "anyOf": [
            {
               "minimum": 1,
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "For unstructured horizontal grids only, the total number of unique cell sides.",
         "title": "N Sides"
      },
      "n_vertices": {
         "anyOf": [
            {
               "minimum": 1,
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "For unstructured horizontal grids only, the number of unique cell vertices.",
         "title": "N Vertices"
      },
      "truncation_method": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The method for truncating the spherical harmonic representation of a spectral model. Taken from a standardised list: 7.9 truncation_method CV.",
         "title": "Truncation Method"
      },
      "truncation_number": {
         "anyOf": [
            {
               "minimum": 1,
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The zonal (east-west) wave number at which a spectral model is truncated.",
         "title": "Truncation Number"
      },
      "resolution_range_km": {
         "description": "The minimum and maximum resolution (in km) of cells of the horizontal grid.",
         "items": {
            "type": "number"
         },
         "maxItems": 2,
         "minItems": 2,
         "title": "Resolution Range Km",
         "type": "array"
      },
      "mean_resolution_km": {
         "description": "The mean resolution (in km) of cells of the horizontal grid.",
         "exclusiveMinimum": 0,
         "title": "Mean Resolution Km",
         "type": "number"
      },
      "nominal_resolution": {
         "description": "The nominal resolution characterises the approximate resolution of a horizontal grid. Taken from a standardised list: 7.10 nominal_resolution CV.",
         "title": "Nominal Resolution",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "grid",
      "grid_mapping",
      "region",
      "temporal_refinement",
      "arrangement",
      "n_cells",
      "resolution_range_km",
      "mean_resolution_km",
      "nominal_resolution"
   ]
}
```

</details></p>
* **Validators:**
  - `validate_mean_resolution_in_range` » `mean_resolution_km`
  - `validate_required_strings` » `arrangement`
  - `validate_required_strings` » `grid`
  - `validate_required_strings` » `grid_mapping`
  - `validate_required_strings` » `nominal_resolution`
  - `validate_required_strings` » `region`
  - `validate_required_strings` » `temporal_refinement`
  - `validate_resolution_range` » `resolution_range_km`
  - `validate_units_requirement` » `horizontal_units`

#### *field* arrangement *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

A characterisation of the relative positions on a grid of mass-, velocity- or flux-related fields. Taken from a standardised list: 7.7 arrangement CV.

* **Validated by:**
  - `validate_required_strings`

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

A free-text description of the grid. A description is only required if there is information that is not covered by any of the other properties.

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* grid *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The horizontal grid type, i.e. the method of distributing grid points over the sphere. Taken from a standardised list: 7.3 grid CV. If there is no horizontal grid, then the value ‘none’ must be selected.

* **Validated by:**
  - `validate_required_strings`

#### *field* grid_mapping *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The name of the coordinate reference system of the horizontal coordinates. Taken from a standardised list: 7.4 grid_mapping CV.

* **Validated by:**
  - `validate_required_strings`

#### *field* horizontal_units *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The physical units of the resolution_x and resolution_y property values. Taken from a standardised list: 7.8 horizontal_units CV.

* **Validated by:**
  - `validate_units_requirement`

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* mean_resolution_km *: [float](https://docs.python.org/3/library/functions.html#float)* *[Required]*

The mean resolution (in km) of cells of the horizontal grid.

* **Constraints:**
  - **gt** = 0
* **Validated by:**
  - `validate_mean_resolution_in_range`

#### *field* n_cells *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

The total number of cells in the horizontal grid.

* **Constraints:**
  - **ge** = 1

#### *field* n_sides *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

For unstructured horizontal grids only, the total number of unique cell sides.

* **Constraints:**
  - **ge** = 1

#### *field* n_vertices *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

For unstructured horizontal grids only, the number of unique cell vertices.

* **Constraints:**
  - **ge** = 1

#### *field* nominal_resolution *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The nominal resolution characterises the approximate resolution of a horizontal grid. Taken from a standardised list: 7.10 nominal_resolution CV.

* **Validated by:**
  - `validate_required_strings`

#### *field* region *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The geographical region, or regions, over which the component is simulated. Taken from a standardised list: 7.5 region CV.

* **Validated by:**
  - `validate_required_strings`

#### *field* resolution_range_km *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[float](https://docs.python.org/3/library/functions.html#float)]* *[Required]*

The minimum and maximum resolution (in km) of cells of the horizontal grid.

* **Constraints:**
  - **min_length** = 2
  - **max_length** = 2
* **Validated by:**
  - `validate_resolution_range`

#### *field* resolution_x *: [float](https://docs.python.org/3/library/functions.html#float) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The size of grid cells in the X direction. The value’s physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.

* **Constraints:**
  - **gt** = 0

#### *field* resolution_y *: [float](https://docs.python.org/3/library/functions.html#float) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The size of grid cells in the Y direction. The value’s physical units are given by the horizontal_units property. Report only when cell sizes are identical or else reasonably uniform.

* **Constraints:**
  - **gt** = 0

#### *field* temporal_refinement *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The grid temporal refinement, indicating how the distribution of grid cells varies with time. Taken from a standardised list: 7.6 temporal_refinement CV.

* **Validated by:**
  - `validate_required_strings`

#### *field* truncation_method *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The method for truncating the spherical harmonic representation of a spectral model. Taken from a standardised list: 7.9 truncation_method CV.

#### *field* truncation_number *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The zonal (east-west) wave number at which a spectral model is truncated.

* **Constraints:**
  - **ge** = 1

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *validator* validate_mean_resolution_in_range  *»*  *mean_resolution_km*

Validate that mean resolution is within the resolution range.

#### *validator* validate_required_strings  *»*  *nominal_resolution* *,* *grid_mapping* *,* *arrangement* *,* *region* *,* *temporal_refinement* *,* *grid*

Validate that required string fields are not empty.

#### *validator* validate_resolution_range  *»*  *resolution_range_km*

Validate that resolution range has exactly 2 values and min <= max.

#### *validator* validate_units_requirement  *»*  *horizontal_units*

Validate that horizontal_units is provided when resolution values are set.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.NativeVerticalGrid

Bases: [`DataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)

4.2. Vertical grid
The model component’s native vertical grid is described by a subset of the following properties:

> • Description
>   : ◦ A free-text description of the vertical grid.
>     ◦ A description is only required if there is information that is not covered by any of the other properties.
>     ◦ Omit if not needed.
> • Coordinate
>   : ◦ The coordinate type of the vertical grid.
>     ◦ Taken from a standardised list: 7.11. coordinate CV.
>     ◦ If there is no vertical grid, then the value “none” must be selected, and no other properties should be set.
>     ◦ E.g. height
>     ◦ E.g. none
> • N z
>   : ◦ The number of layers (i.e. grid cells) in the Z direction.
>     ◦ Omit when not applicable or not constant.
>     ◦ If the number of layers varies in time or across the horizontal grid, then the N z range property may be used instead.
>     ◦ E.g. 70
> • N z range
>   : ◦ The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers.
>     ◦ Omit if the N z property has been set.
>     ◦ E.g. 5, 15
> • Bottom layer thickness
>   : ◦ The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth).
>     ◦ The value should be reported as a dimensional (as opposed to parametric) quantity.
>     ◦ If the value varies in time or across the horizontal grid, then provide a nominal or typical value.
>     ◦ The value’s physical units are given by the vertical_units property.
>     ◦ Omit when not applicable.
>     ◦ E.g. 10
> • Top layer thickness
>   : ◦ The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth).
>     ◦ The value should be reported as a dimensional (as opposed to parametric) quantity.
>     ◦ If the value varies in time or across the horizontal grid, then provide a nominal or typical value.
>     ◦ The value’s physical units are given by the vertical_units property.
>     ◦ Omit when not applicable.
>     ◦ E.g. 10
> • Top of model
>   : ◦ The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth).
>     ◦ The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level).
>     ◦ The value should be reported as a dimensional (as opposed to parametric) quantity.
>     ◦ The value’s physical units are given by the vertical_units property.
>     ◦ Omit when not applicable or not constant.
>     ◦ E.g. 85003.5
> • Vertical units
>   : ◦ The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values.
>     ◦ Taken from a standardised list: 7.12. vertical_units CV.
>     ◦ Omit when not applicable.
>     ◦ E.g. m
<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "NativeVerticalGrid",
   "description": "4.2. Vertical grid\nThe model component's native vertical grid is described by a subset of the following properties:\n    \u2022 Description\n        \u25e6 A free-text description of the vertical grid.\n        \u25e6 A description is only required if there is information that is not covered by any of the other properties.\n        \u25e6 Omit if not needed.\n    \u2022 Coordinate\n        \u25e6 The coordinate type of the vertical grid.\n        \u25e6 Taken from a standardised list: 7.11. coordinate CV.\n        \u25e6 If there is no vertical grid, then the value \"none\" must be selected, and no other properties should be set.\n        \u25e6 E.g. height\n        \u25e6 E.g. none\n    \u2022 N z\n        \u25e6 The number of layers (i.e. grid cells) in the Z direction.\n        \u25e6 Omit when not applicable or not constant.\n        \u25e6 If the number of layers varies in time or across the horizontal grid, then the N z range property may be used instead.\n        \u25e6 E.g. 70\n    \u2022 N z range\n        \u25e6 The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers.\n        \u25e6 Omit if the N z property has been set.\n        \u25e6 E.g. 5, 15\n    \u2022 Bottom layer thickness\n        \u25e6 The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 If the value varies in time or across the horizontal grid, then provide a nominal or typical value.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. 10\n    \u2022 Top layer thickness\n        \u25e6 The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 If the value varies in time or across the horizontal grid, then provide a nominal or typical value.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. 10\n    \u2022 Top of model\n        \u25e6 The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth).\n        \u25e6 The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level).\n        \u25e6 The value should be reported as a dimensional (as opposed to parametric) quantity.\n        \u25e6 The value's physical units are given by the vertical_units property.\n        \u25e6 Omit when not applicable or not constant.\n        \u25e6 E.g. 85003.5\n    \u2022 Vertical units\n        \u25e6 The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values.\n        \u25e6 Taken from a standardised list: 7.12. vertical_units CV.\n        \u25e6 Omit when not applicable.\n        \u25e6 E.g. m",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "coordinate": {
         "description": "The coordinate type of the vertical grid. Taken from a standardised list: 7.11 coordinate CV. If there is no vertical grid, then the value 'none' must be selected.",
         "title": "Coordinate",
         "type": "string"
      },
      "description": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "A free-text description of the vertical grid. A description is only required if there is information that is not covered by any of the other properties.",
         "title": "Description"
      },
      "n_z": {
         "anyOf": [
            {
               "minimum": 1,
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The number of layers (i.e. grid cells) in the Z direction. Omit when not applicable or not constant. If the number of layers varies in time or across the horizontal grid, then the n_z_range property may be used instead.",
         "title": "N Z"
      },
      "n_z_range": {
         "anyOf": [
            {
               "items": {
                  "type": "integer"
               },
               "maxItems": 2,
               "minItems": 2,
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers. Omit if the n_z property has been set.",
         "title": "N Z Range"
      },
      "bottom_layer_thickness": {
         "anyOf": [
            {
               "exclusiveMinimum": 0,
               "type": "number"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value's physical units are given by the vertical_units property.",
         "title": "Bottom Layer Thickness"
      },
      "top_layer_thickness": {
         "anyOf": [
            {
               "exclusiveMinimum": 0,
               "type": "number"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value's physical units are given by the vertical_units property.",
         "title": "Top Layer Thickness"
      },
      "top_of_model": {
         "anyOf": [
            {
               "type": "number"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth). The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level). The value's physical units are given by the vertical_units property.",
         "title": "Top Of Model"
      },
      "vertical_units": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "description": "The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values. Taken from a standardised list: 7.12 vertical_units CV.",
         "title": "Vertical Units"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "coordinate"
   ]
}
```

</details></p>
* **Validators:**
  - `validate_coordinate` » `coordinate`
  - `validate_n_z_exclusivity` » `n_z`
  - `validate_n_z_range` » `n_z_range`
  - `validate_units_requirement` » `vertical_units`

#### *field* bottom_layer_thickness *: [float](https://docs.python.org/3/library/functions.html#float) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The thickness of the bottom model layer (i.e. the layer closest to the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value’s physical units are given by the vertical_units property.

* **Constraints:**
  - **gt** = 0

#### *field* coordinate *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The coordinate type of the vertical grid. Taken from a standardised list: 7.11 coordinate CV. If there is no vertical grid, then the value ‘none’ must be selected.

* **Validated by:**
  - `validate_coordinate`

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

A free-text description of the vertical grid. A description is only required if there is information that is not covered by any of the other properties.

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* n_z *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The number of layers (i.e. grid cells) in the Z direction. Omit when not applicable or not constant. If the number of layers varies in time or across the horizontal grid, then the n_z_range property may be used instead.

* **Constraints:**
  - **ge** = 1
* **Validated by:**
  - `validate_n_z_exclusivity`

#### *field* n_z_range *: [List](https://docs.python.org/3/library/typing.html#typing.List)[[int](https://docs.python.org/3/library/functions.html#int)] | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The minimum and maximum number of layers for vertical grids with a time- or space-varying number of layers. Omit if the n_z property has been set.

* **Constraints:**
  - **min_length** = 2
  - **max_length** = 2
* **Validated by:**
  - `validate_n_z_range`

#### *field* top_layer_thickness *: [float](https://docs.python.org/3/library/functions.html#float) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The thickness of the top model layer (i.e. the layer furthest away from the centre of the Earth). The value should be reported as a dimensional (as opposed to parametric) quantity. The value’s physical units are given by the vertical_units property.

* **Constraints:**
  - **gt** = 0

#### *field* top_of_model *: [float](https://docs.python.org/3/library/functions.html#float) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The upper boundary of the top model layer (i.e. the upper boundary of the layer that is furthest away from the centre of the Earth). The value should be relative to the lower boundary of the bottom layer of the model, or an appropriate datum (such as mean sea level). The value’s physical units are given by the vertical_units property.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* vertical_units *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The physical units of the bottom_layer_thickness, top_layer_thickness, and top_of_model property values. Taken from a standardised list: 7.12 vertical_units CV.

* **Validated by:**
  - `validate_units_requirement`

#### *validator* validate_coordinate  *»*  *coordinate*

Validate that coordinate is not empty.

#### *validator* validate_n_z_exclusivity  *»*  *n_z*

Validate that n_z and n_z_range are mutually exclusive.

#### *validator* validate_n_z_range  *»*  *n_z_range*

Validate that n_z_range has exactly 2 values and min <= max.

#### *validator* validate_units_requirement  *»*  *vertical_units*

Validate that vertical_units is provided when thickness/top_of_model values are set.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept a data descriptor visitor.

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.ObsType

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ObsType",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Organisation

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Organisation",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.PhysicIndex

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "PhysicIndex",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Product

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Product",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "kind": {
         "title": "Kind",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "kind"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* kind *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.PublicationStatus

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "PublicationStatus",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.RealisationIndex

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "RealisationIndex",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Realm

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Realm",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "name": {
         "title": "Name",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "name"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Reference

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

The top-level model and its model components must each have at least one reference, defined by the following properties:

• Citation
  : ◦ A human-readable citation for the work.
    ◦ E.g. Smith, R. S., Mathiot, P., Siahaan, A., Lee, V., Cornford, S. L., Gregory, J. M., et al. (2021). Coupling the U.K. Earth System model to dynamic models of the Greenland and Antarctic ice sheets. Journal of Advances in Modeling Earth Systems, 13, e2021MS002520. [https://doi.org/10.1029/2021MS002520](https://doi.org/10.1029/2021MS002520), 2023
• DOI
  : ◦ The persistent identifier (DOI) used to identify the work.
    ◦ A DOI is required for all references. A reference that does not already have a DOI (as could be the case for some technical reports, for instance) must be given one (e.g. with a service like Zenodo).
    ◦ E.g. [https://doi.org/10.1029/2021MS002520](https://doi.org/10.1029/2021MS002520)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Reference",
   "description": "The top-level model and its model components must each have at least one reference, defined by the following properties:\n\n\u2022 Citation\n    \u25e6 A human-readable citation for the work.\n    \u25e6 E.g. Smith, R. S., Mathiot, P., Siahaan, A., Lee, V., Cornford, S. L., Gregory, J. M., et al. (2021). Coupling the U.K. Earth System model to dynamic models of the Greenland and Antarctic ice sheets. Journal of Advances in Modeling Earth Systems, 13, e2021MS002520. https://doi.org/10.1029/2021MS002520, 2023\n\u2022 DOI\n    \u25e6 The persistent identifier (DOI) used to identify the work.\n    \u25e6 A DOI is required for all references. A reference that does not already have a DOI (as could be the case for some technical reports, for instance) must be given one (e.g. with a service like Zenodo).\n    \u25e6 E.g. https://doi.org/10.1029/2021MS002520",
   "type": "object",
   "properties": {
      "citation": {
         "description": "A human-readable citation for the work.",
         "minLength": 1,
         "title": "Citation",
         "type": "string"
      },
      "doi": {
         "description": "The persistent identifier (DOI) used to identify the work. Must be a valid DOI URL.",
         "minLength": 1,
         "title": "Doi",
         "type": "string"
      }
   },
   "required": [
      "citation",
      "doi"
   ]
}
```

</details></p>
* **Validators:**
  - `validate_citation` » `citation`
  - `validate_doi` » `doi`

#### *field* citation *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

A human-readable citation for the work.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_citation`

#### *field* doi *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The persistent identifier (DOI) used to identify the work. Must be a valid DOI URL.

* **Constraints:**
  - **min_length** = 1
* **Validated by:**
  - `validate_doi`

#### *validator* validate_citation  *»*  *citation*

Validate that citation is not empty.

#### *validator* validate_doi  *»*  *doi*

Validate that DOI follows proper format.

### *Pydantic model* esgvoc.api.data_descriptors.Regex

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Regex",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Region

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Region",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Resolution

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Resolution",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "value": {
         "title": "Value",
         "type": "string"
      },
      "name": {
         "title": "Name",
         "type": "string"
      },
      "unit": {
         "title": "Unit",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "value",
      "name",
      "unit"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* unit *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* value *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Source

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

A ‘source’ refers to a numerical representations of the Earth’s climate system. They simulate     the interactions between the atmosphere, oceans, land surface, and ice. These models are based     on fundamental physical, chemical, and biological processes and are used to understand past,     present, and future climate conditions. Each source or model is typically associated with a     specific research institution, center, or group. For instance, models like ‘EC-Earth’ are     developed by a consortium of European institutes, while ‘GFDL-CM4’ is developed by the     Geophysical Fluid Dynamics Laboratory (GFDL) in the United States.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Source",
   "description": "A 'source' refers to a numerical representations of the Earth's climate system. They simulate     the interactions between the atmosphere, oceans, land surface, and ice. These models are based     on fundamental physical, chemical, and biological processes and are used to understand past,     present, and future climate conditions. Each source or model is typically associated with a     specific research institution, center, or group. For instance, models like 'EC-Earth' are     developed by a consortium of European institutes, while 'GFDL-CM4' is developed by the     Geophysical Fluid Dynamics Laboratory (GFDL) in the United States.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "activity_participation": {
         "anyOf": [
            {
               "items": {
                  "type": "string"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "title": "Activity Participation"
      },
      "cohort": {
         "items": {
            "type": "string"
         },
         "title": "Cohort",
         "type": "array"
      },
      "organisation_id": {
         "items": {
            "type": "string"
         },
         "title": "Organisation Id",
         "type": "array"
      },
      "label": {
         "title": "Label",
         "type": "string"
      },
      "label_extended": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Label Extended"
      },
      "license": {
         "additionalProperties": true,
         "title": "License",
         "type": "object"
      },
      "model_component": {
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
         "description": "Dictionary containing the model components that make up this climate source, including their types, resolutions, and other technical specifications",
         "title": "Model Component"
      },
      "release_year": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Release Year"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "activity_participation",
      "label"
   ]
}
```

</details></p>

#### *field* activity_participation *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* cohort *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* label_extended *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

#### *field* license *: [dict](https://docs.python.org/3/library/stdtypes.html#dict)* *[Optional]*

#### *field* model_component *: [dict](https://docs.python.org/3/library/stdtypes.html#dict) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

Dictionary containing the model components that make up this climate source, including their types, resolutions, and other technical specifications

#### *field* organisation_id *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

#### *field* release_year *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.SourceType

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "SourceType",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.SubExperiment

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "SubExperiment",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Table

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Table",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "product": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Product"
      },
      "table_date": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Table Date"
      },
      "variable_entry": {
         "items": {
            "type": "string"
         },
         "title": "Variable Entry",
         "type": "array"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "product",
      "table_date"
   ]
}
```

</details></p>
* **Validators:**
  - `normalize_variable_entry` » `variable_entry`

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* product *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* table_date *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* variable_entry *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Optional]*

* **Validated by:**
  - `normalize_variable_entry`

#### *validator* normalize_variable_entry  *»*  *variable_entry*

Normalize variable_entry to ensure all items are strings.
If items are dicts (resolved references), extract the ‘id’ field.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.TemporalLabel

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Temporal sampling label.

This label provides information about the temporal sampling of a given dataset.
For a list of allowed values, see
[TODO think about how to cross-reference to somewhere where people can look up the allowed values,
e.g. some summary of the values in [https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/temporal_label](https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/temporal_label).]

This label is used as the temporal component of a branded variable’s suffix
(see [`BrandedSuffix`](#esgvoc.api.data_descriptors.BrandedSuffix)).
By definition, the temporal label must be consistent with the branded suffix.
Temporal labels must not contain the separator used when constructing the branded suffix.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "TemporalLabel",
   "description": "Temporal sampling label.\n\nThis label provides information about the temporal sampling of a given dataset.\nFor a list of allowed values, see\n[TODO think about how to cross-reference to somewhere where people can look up the allowed values,\ne.g. some summary of the values in https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/temporal_label.]\n\nThis label is used as the temporal component of a branded variable's suffix\n(see :py:class:`BrandedSuffix`).\nBy definition, the temporal label must be consistent with the branded suffix.\nTemporal labels must not contain the separator used when constructing the branded suffix.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      },
      "label": {
         "title": "Label",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description",
      "label"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* label *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.TimeRange

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "TimeRange",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Title

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Title",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.TrackingId

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "TrackingId",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Unit

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Native vertical grid units of the top level boundary or top layer thickness value. See section 5.2 Native vertical grid properties.
Options for the native vertical grid Units property:

> • m
>   : ◦ metre (unit for length).
> • Pa
>   : ◦ pascal (unit for pressure).
> • K
>   : ◦ kelvin (unit for temperature).
>     ◦
<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Unit",
   "description": "Native vertical grid units of the top level boundary or top layer thickness value. See section 5.2 Native vertical grid properties.\nOptions for the native vertical grid Units property:\n    \u2022 m\n        \u25e6 metre (unit for length).\n    \u2022 Pa\n        \u25e6 pascal (unit for pressure).\n    \u2022 K\n        \u25e6 kelvin (unit for temperature).\n        \u25e6",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.Variable

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

A climate-related quantity or measurement.

These quantities represent key physical, chemical or biological properties of the Earth system
and can be the result of direct observation of the climate system or simulations.
Variables cover a range of aspects of the climate system,
such as temperature, precipitation, sea level, radiation, or atmospheric composition.
Some examples of variables that have been used in CMIP:

- *tas*: Near-surface air temperature (often measured at 2 meters above the surface)
- *pr*: Precipitation
- *psl*: Sea-level pressure
- *zg*: Geopotential height
- *rlut*: Top-of-atmosphere longwave radiation
- *siconc*: Sea-ice concentration
- *co2*: Atmospheric CO2 concentration

Since CMIP7, the concept of a variable has been augmented with the idea of ‘branding’,
leading to the idea of a ‘branded variable’.
For details, see [`BrandedVariable`](#esgvoc.api.data_descriptors.BrandedVariable).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Variable",
   "description": "A climate-related quantity or measurement.\n\nThese quantities represent key physical, chemical or biological properties of the Earth system\nand can be the result of direct observation of the climate system or simulations.\nVariables cover a range of aspects of the climate system,\nsuch as temperature, precipitation, sea level, radiation, or atmospheric composition.\nSome examples of variables that have been used in CMIP:\n\n- *tas*: Near-surface air temperature (often measured at 2 meters above the surface)\n- *pr*: Precipitation\n- *psl*: Sea-level pressure\n- *zg*: Geopotential height\n- *rlut*: Top-of-atmosphere longwave radiation\n- *siconc*: Sea-ice concentration\n- *co2*: Atmospheric CO2 concentration\n\nSince CMIP7, the concept of a variable has been augmented with the idea of 'branding',\nleading to the idea of a 'branded variable'.\nFor details, see :py:class:`BrandedVariable`.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      },
      "validation_method": {
         "default": "list",
         "title": "Validation Method",
         "type": "string"
      },
      "long_name": {
         "title": "Long Name",
         "type": "string"
      },
      "standard_name": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Standard Name"
      },
      "units": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Units"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name",
      "long_name",
      "standard_name",
      "units"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* long_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* standard_name *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *field* units *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

#### *field* validation_method *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *= 'list'*

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.VariantLabel

Bases: [`PatternTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "VariantLabel",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      },
      "description": {
         "title": "Description",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex",
      "description"
   ]
}
```

</details></p>

#### *field* description *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.VerticalLabel

Bases: [`PlainTermDataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)

Vertical label.

This label provides information about the vertical sampling of a given dataset.
For a list of allowed values, see
[TODO think about how to cross-reference to somewhere where people can look up the allowed values,
e.g. some summary of the values in [https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/vertical_label](https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/vertical_label).]

This label is used as the vertical component of a branded variable’s suffix
(see [`BrandedSuffix`](#esgvoc.api.data_descriptors.BrandedSuffix)).
By definition, the vertical label must be consistent with the branded suffix.
Vertical labels must not contain the separator used when constructing the branded suffix.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "VerticalLabel",
   "description": "Vertical label.\n\nThis label provides information about the vertical sampling of a given dataset.\nFor a list of allowed values, see\n[TODO think about how to cross-reference to somewhere where people can look up the allowed values,\ne.g. some summary of the values in https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc/vertical_label.]\n\nThis label is used as the vertical component of a branded variable's suffix\n(see :py:class:`BrandedSuffix`).\nBy definition, the vertical label must be consistent with the branded suffix.\nVertical labels must not contain the separator used when constructing the branded suffix.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

## Generic classes

### *Pydantic model* esgvoc.api.data_descriptors.data_descriptor.CompositeTermDataDescriptor

Bases: [`DataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)

A data descriptor that describes terms composed of other terms.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CompositeTermDataDescriptor",
   "description": "A data descriptor that describes terms composed of other terms.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "separator": {
         "title": "Separator",
         "type": "string"
      },
      "parts": {
         "items": {
            "$ref": "#/$defs/CompositeTermPart"
         },
         "title": "Parts",
         "type": "array"
      }
   },
   "$defs": {
      "CompositeTermPart": {
         "additionalProperties": true,
         "description": "A reference to a term, part of a composite term.",
         "properties": {
            "id": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "items": {
                        "type": "string"
                     },
                     "type": "array"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Id"
            },
            "type": {
               "title": "Type",
               "type": "string"
            },
            "is_required": {
               "title": "Is Required",
               "type": "boolean"
            }
         },
         "required": [
            "type",
            "is_required"
         ],
         "title": "CompositeTermPart",
         "type": "object"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "separator",
      "parts"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* parts *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[CompositeTermPart](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermPart)]* *[Required]*

The components.

#### *field* separator *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The components separator character.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.data_descriptor.CompositeTermPart

Bases: [`ConfiguredBaseModel`](#esgvoc.api.data_descriptors.data_descriptor.ConfiguredBaseModel)

A reference to a term, part of a composite term.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "CompositeTermPart",
   "description": "A reference to a term, part of a composite term.",
   "type": "object",
   "properties": {
      "id": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "items": {
                  "type": "string"
               },
               "type": "array"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Id"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "is_required": {
         "title": "Is Required",
         "type": "boolean"
      }
   },
   "additionalProperties": true,
   "required": [
      "type",
      "is_required"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)] | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

The id of the referenced term.

#### *field* is_required *: [bool](https://docs.python.org/3/library/functions.html#bool)* *[Required]*

Denote if the term is optional as part of a composite term.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The type of the referenced term.

### *Pydantic model* esgvoc.api.data_descriptors.data_descriptor.ConfiguredBaseModel

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ConfiguredBaseModel",
   "type": "object",
   "properties": {},
   "additionalProperties": true
}
```

</details></p>

### *Pydantic model* esgvoc.api.data_descriptors.data_descriptor.DataDescriptor

Bases: [`ConfiguredBaseModel`](#esgvoc.api.data_descriptors.data_descriptor.ConfiguredBaseModel), [`ABC`](https://docs.python.org/3/library/abc.html#abc.ABC)

Generic class for the data descriptor classes.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DataDescriptor",
   "description": "Generic class for the data descriptor classes.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### *abstractmethod* accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.data_descriptor.DataDescriptorSubSet

Bases: [`DataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)

A sub set of the information contains in a term.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DataDescriptorSubSet",
   "description": "A sub set of the information contains in a term.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### MANDATORY_TERM_FIELDS *: [ClassVar](https://docs.python.org/3/library/typing.html#typing.ClassVar)[[tuple](https://docs.python.org/3/library/stdtypes.html#tuple)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str)]]* *= ('id', 'type')*

The set of mandatory term fields.

#### *property* describe

### *class* esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor(\*args, \*\*kwargs)

Bases: [`Protocol`](https://docs.python.org/3/library/typing.html#typing.Protocol)

The specifications for a term visitor.

#### visit_composite_term(term: [CompositeTermDataDescriptor](#esgvoc.api.data_descriptors.data_descriptor.CompositeTermDataDescriptor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a composite term.

#### visit_pattern_term(term: [PatternTermDataDescriptor](#esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a pattern term.

#### visit_plain_term(term: [PlainTermDataDescriptor](#esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a plain term.

#### visit_sub_set_term(term: [DataDescriptorSubSet](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorSubSet)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a sub set of the information of a term.

### *Pydantic model* esgvoc.api.data_descriptors.data_descriptor.PatternTermDataDescriptor

Bases: [`DataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)

A data descriptor that describes terms defined by a regular expression.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "PatternTermDataDescriptor",
   "description": "A data descriptor that describes terms defined by a regular expression.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "regex": {
         "title": "Regex",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "regex"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* regex *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The regular expression.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe

### *Pydantic model* esgvoc.api.data_descriptors.data_descriptor.PlainTermDataDescriptor

Bases: [`DataDescriptor`](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptor)

A data descriptor that describes hand written terms.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "PlainTermDataDescriptor",
   "description": "A data descriptor that describes hand written terms.",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "type": {
         "title": "Type",
         "type": "string"
      },
      "drs_name": {
         "title": "Drs Name",
         "type": "string"
      }
   },
   "additionalProperties": true,
   "required": [
      "id",
      "type",
      "drs_name"
   ]
}
```

</details></p>

#### *field* drs_name *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The identifier of the terms.

#### *field* type *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The data descriptor to which the term belongs.

#### accept(visitor: [DataDescriptorVisitor](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an term visitor.

* **Parameters:**
  **visitor** ([*DataDescriptorVisitor*](#esgvoc.api.data_descriptors.data_descriptor.DataDescriptorVisitor)) – The term visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

#### *property* describe
