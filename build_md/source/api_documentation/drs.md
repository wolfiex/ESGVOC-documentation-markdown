# DRS applications

## Validation

### *class* esgvoc.apps.drs.validator.DrsApplication(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), pedantic: [bool](https://docs.python.org/3/library/functions.html#bool) = False)

Bases: [`object`](https://docs.python.org/3/library/functions.html#object)

Generic DRS application class.

#### dataset_id_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS dataset id specs of the project.

#### directory_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS directory specs of the project.

#### file_name_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS file name specs of the project.

#### pedantic *: [bool](https://docs.python.org/3/library/functions.html#bool)*

Same as the option of GCC: turn warnings into errors. Default False.

#### project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)*

The project id.

### *class* esgvoc.apps.drs.validator.DrsValidator(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), pedantic: [bool](https://docs.python.org/3/library/functions.html#bool) = False)

Bases: [`DrsApplication`](#esgvoc.apps.drs.validator.DrsApplication)

Valid a DRS directory, dataset id and file name expression against a project.

#### validate(drs_expression: [str](https://docs.python.org/3/library/stdtypes.html#str), drs_type: [DrsType](project_specs.md#esgvoc.api.project_specs.DrsType) | [str](https://docs.python.org/3/library/stdtypes.html#str)) → [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

Validate a DRS expression.

* **Parameters:**
  * **drs_expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A DRS expression.
  * **drs_type** ([*DrsType*](project_specs.md#esgvoc.api.project_specs.DrsType) *|*[*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The type of the given DRS expression (directory, file_name or dataset_id)
* **Returns:**
  A validation report.
* **Return type:**
  [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

#### validate_dataset_id(drs_expression: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

Validate a DRS dataset id expression.

* **Parameters:**
  **drs_expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A DRS dataset id expression.
* **Returns:**
  A validation report.
* **Return type:**
  [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

#### validate_directory(drs_expression: [str](https://docs.python.org/3/library/stdtypes.html#str), prefix: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None) = None) → [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

Validate a DRS directory expression.

* **Parameters:**
  * **drs_expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A DRS directory expression.
  * **prefix** ([*str*](https://docs.python.org/3/library/stdtypes.html#str) *|**None*) – A directory prefix to be removed from the directory expression.
* **Returns:**
  A validation report.
* **Return type:**
  [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

#### validate_file_name(drs_expression: [str](https://docs.python.org/3/library/stdtypes.html#str)) → [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

Validate a file name expression.

* **Parameters:**
  **drs_expression** ([*str*](https://docs.python.org/3/library/stdtypes.html#str)) – A DRS file name expression.
* **Returns:**
  A validation report.
* **Return type:**
  [DrsValidationReport](#esgvoc.apps.drs.report.DrsValidationReport)

#### dataset_id_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS dataset id specs of the project.

#### directory_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS directory specs of the project.

#### file_name_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS file name specs of the project.

#### pedantic *: [bool](https://docs.python.org/3/library/functions.html#bool)*

Same as the option of GCC: turn warnings into errors. Default False.

#### project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)*

The project id.

## Generation

### *class* esgvoc.apps.drs.generator.DrsGenerator(project_id: [str](https://docs.python.org/3/library/stdtypes.html#str), pedantic: [bool](https://docs.python.org/3/library/functions.html#bool) = False)

Bases: [`DrsApplication`](#esgvoc.apps.drs.validator.DrsApplication)

Generate a directory, dataset id and file name expression specified by the given project from
a mapping of collection ids and terms or an unordered bag of terms.

#### generate_dataset_id_from_bag_of_terms(terms: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)]) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a dataset id DRS expression from an unordered bag of terms.

* **Parameters:**
  **terms** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – An unordered bag of terms.
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### generate_dataset_id_from_mapping(mapping: [Mapping](https://docs.python.org/3/library/typing.html#typing.Mapping)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str)]) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a dataset id DRS expression from a mapping of collection ids and terms.

* **Parameters:**
  **mapping** (*Mapping* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *,* [*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – A mapping of collection ids (keys) and terms (values).
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### generate_directory_from_bag_of_terms(terms: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)]) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a directory DRS expression from an unordered bag of terms.

* **Parameters:**
  **terms** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – An unordered bag of terms.
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### generate_directory_from_mapping(mapping: [Mapping](https://docs.python.org/3/library/typing.html#typing.Mapping)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str)]) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a directory DRS expression from a mapping of collection ids and terms.

* **Parameters:**
  **mapping** (*Mapping* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *,* [*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – A mapping of collection ids (keys) and terms (values).
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### generate_file_name_from_bag_of_terms(terms: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)]) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a file name DRS expression from an unordered bag of terms.
The file name extension is append automatically, according to the DRS specification,
so none of the terms given must include the extension.

* **Parameters:**
  **terms** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – An unordered bag of terms.
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### generate_file_name_from_mapping(mapping: [Mapping](https://docs.python.org/3/library/typing.html#typing.Mapping)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str)]) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a file name DRS expression from a mapping of collection ids and terms.
The file name extension is append automatically, according to the DRS specification,
so none of the terms given must include the extension.

* **Parameters:**
  **mapping** (*Mapping* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *,* [*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – A mapping of collection ids (keys) and terms (values).
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### generate_from_bag_of_terms(terms: [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)[[str](https://docs.python.org/3/library/stdtypes.html#str)], drs_type: [DrsType](project_specs.md#esgvoc.api.project_specs.DrsType) | [str](https://docs.python.org/3/library/stdtypes.html#str)) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a DRS expression from an unordered bag of terms.

* **Parameters:**
  * **terms** (*Iterable* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – An unordered bag of terms.
  * **drs_type** ([*DrsType*](project_specs.md#esgvoc.api.project_specs.DrsType) *|*[*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The type of the given DRS expression (directory, file_name or dataset_id)
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### generate_from_mapping(mapping: [Mapping](https://docs.python.org/3/library/typing.html#typing.Mapping)[[str](https://docs.python.org/3/library/stdtypes.html#str), [str](https://docs.python.org/3/library/stdtypes.html#str)], drs_type: [DrsType](project_specs.md#esgvoc.api.project_specs.DrsType) | [str](https://docs.python.org/3/library/stdtypes.html#str)) → [DrsGenerationReport](#esgvoc.apps.drs.report.DrsGenerationReport)

Generate a DRS expression from a mapping of collection ids and terms.

* **Parameters:**
  * **mapping** (*Mapping* *[*[*str*](https://docs.python.org/3/library/stdtypes.html#str) *,* [*str*](https://docs.python.org/3/library/stdtypes.html#str) *]*) – A mapping of collection ids (keys) and terms (values).
  * **drs_type** ([*DrsType*](project_specs.md#esgvoc.api.project_specs.DrsType) *|*[*str*](https://docs.python.org/3/library/stdtypes.html#str)) – The type of the given DRS expression (directory, file_name or dataset_id)
* **Returns:**
  A generation report.
* **Return type:**
  DrsGeneratorReport

#### dataset_id_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS dataset id specs of the project.

#### directory_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS directory specs of the project.

#### file_name_specs *: [DrsSpecification](project_specs.md#esgvoc.api.project_specs.DrsSpecification)*

The DRS file name specs of the project.

#### pedantic *: [bool](https://docs.python.org/3/library/functions.html#bool)*

Same as the option of GCC: turn warnings into errors. Default False.

#### project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)*

The project id.

## Issue reporting

### *Pydantic model* esgvoc.apps.drs.report.AssignedTerm

Bases: [`GenerationIssue`](#esgvoc.apps.drs.report.GenerationIssue)

Represents a decision of the Generator to assign this term to the collection, that may not be.
relevant.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "AssignedTerm",
   "description": "Represents a decision of the Generator to assign this term to the collection, that may not be.\nrelevant.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "AssignedTerm",
         "default": "AssignedTerm",
         "title": "Kind",
         "type": "string"
      },
      "collection_id": {
         "title": "Collection Id",
         "type": "string"
      },
      "term": {
         "title": "Term",
         "type": "string"
      }
   },
   "required": [
      "collection_id",
      "term"
   ]
}
```

</details></p>

#### *field* collection_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The collection id.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.ASSIGNED]* *= IssueKind.ASSIGNED*

The class name of the issue for JSON serialization/deserialization.

#### *field* term *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The term.

#### accept(visitor: [GenerationIssueVisitor](#esgvoc.apps.drs.report.GenerationIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS generation issue visitor.

* **Parameters:**
  **visitor** ([*GenerationIssueVisitor*](#esgvoc.apps.drs.report.GenerationIssueVisitor)) – The DRS generation issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.BlankTerm

Bases: [`ParsingIssue`](#esgvoc.apps.drs.report.ParsingIssue)

Represents a problem of blank term in the DRS expression (i.e., space[s] surrounded by separators).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "BlankTerm",
   "description": "Represents a problem of blank term in the DRS expression (i.e., space[s] surrounded by separators).",
   "type": "object",
   "properties": {
      "kind": {
         "const": "BlankTerm",
         "default": "BlankTerm",
         "title": "Kind",
         "type": "string"
      },
      "column": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Column"
      }
   }
}
```

</details></p>

#### *field* column *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

the column of faulty characters.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.BLANK_TERM]* *= IssueKind.BLANK_TERM*

The class name of the issue for JSON serialization/deserialization.

#### accept(visitor: [ParsingIssueVisitor](#esgvoc.apps.drs.report.ParsingIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS parsing issue visitor.

* **Parameters:**
  **visitor** ([*ParsingIssueVisitor*](#esgvoc.apps.drs.report.ParsingIssueVisitor)) – The DRS parsing issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.ComplianceIssue

Bases: [`DrsIssue`](#esgvoc.apps.drs.report.DrsIssue)

Generic class for the compliance issues.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ComplianceIssue",
   "description": "Generic class for the compliance issues.",
   "type": "object",
   "properties": {
      "kind": {
         "title": "Kind",
         "type": "string"
      }
   },
   "required": [
      "kind"
   ]
}
```

</details></p>

#### *field* kind *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The class name of the issue for JSON serialization/deserialization.

#### *abstractmethod* accept(visitor: [ComplianceIssueVisitor](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS compliance issue visitor.

* **Parameters:**
  **visitor** ([*ComplianceIssueVisitor*](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) – The DRS compliance issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *class* esgvoc.apps.drs.report.ComplianceIssueVisitor(\*args, \*\*kwargs)

Bases: [`Protocol`](https://docs.python.org/3/library/typing.html#typing.Protocol)

Specifications for a compliance issues visitor.

#### visit_extra_term_issue(issue: [ExtraTerm](#esgvoc.apps.drs.report.ExtraTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an extra term issue.

#### visit_filename_extension_issue(issue: [FileNameExtensionIssue](#esgvoc.apps.drs.report.FileNameExtensionIssue)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a file name extension issue.

#### visit_invalid_term_issue(issue: [InvalidTerm](#esgvoc.apps.drs.report.InvalidTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an invalid term issue.

#### visit_missing_term_issue(issue: [MissingTerm](#esgvoc.apps.drs.report.MissingTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a missing term issue.

### *Pydantic model* esgvoc.apps.drs.report.ConflictingCollections

Bases: [`GenerationIssue`](#esgvoc.apps.drs.report.GenerationIssue)

Represents a problem while inferring a mapping collection - term in the generation
of a DRS expression based on a bag of terms. The problem is that these collections shares the
very same terms. The generator is unable to choose which term for which collection.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ConflictingCollections",
   "description": "Represents a problem while inferring a mapping collection - term in the generation\nof a DRS expression based on a bag of terms. The problem is that these collections shares the\nvery same terms. The generator is unable to choose which term for which collection.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "ConflictingCollections",
         "default": "ConflictingCollections",
         "title": "Kind",
         "type": "string"
      },
      "collection_ids": {
         "items": {
            "type": "string"
         },
         "title": "Collection Ids",
         "type": "array"
      },
      "terms": {
         "items": {
            "type": "string"
         },
         "title": "Terms",
         "type": "array"
      }
   },
   "required": [
      "collection_ids",
      "terms"
   ]
}
```

</details></p>

#### *field* collection_ids *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Required]*

The ids of the collections.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.CONFLICT]* *= IssueKind.CONFLICT*

The class name of the issue for JSON serialization/deserialization.

#### *field* terms *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Required]*

The shared terms.

#### accept(visitor: [GenerationIssueVisitor](#esgvoc.apps.drs.report.GenerationIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS generation issue visitor.

* **Parameters:**
  **visitor** ([*GenerationIssueVisitor*](#esgvoc.apps.drs.report.GenerationIssueVisitor)) – The DRS generation issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.DrsGenerationReport

Bases: [`DrsReport`](#esgvoc.apps.drs.report.DrsReport)

The DRS generation report.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DrsGenerationReport",
   "description": "The DRS generation report.",
   "type": "object",
   "properties": {
      "project_id": {
         "title": "Project Id",
         "type": "string"
      },
      "type": {
         "$ref": "#/$defs/DrsType"
      },
      "errors": {
         "items": {
            "discriminator": {
               "mapping": {
                  "AssignedTerm": "#/$defs/AssignedTerm",
                  "ConflictingCollections": "#/$defs/ConflictingCollections",
                  "InvalidTerm": "#/$defs/InvalidTerm",
                  "MissingTerm": "#/$defs/MissingTerm",
                  "TooManyTermsCollection": "#/$defs/TooManyTermCollection"
               },
               "propertyName": "kind"
            },
            "oneOf": [
               {
                  "$ref": "#/$defs/AssignedTerm"
               },
               {
                  "$ref": "#/$defs/ConflictingCollections"
               },
               {
                  "$ref": "#/$defs/InvalidTerm"
               },
               {
                  "$ref": "#/$defs/MissingTerm"
               },
               {
                  "$ref": "#/$defs/TooManyTermCollection"
               }
            ]
         },
         "title": "Errors",
         "type": "array"
      },
      "warnings": {
         "items": {
            "discriminator": {
               "mapping": {
                  "AssignedTerm": "#/$defs/AssignedTerm",
                  "MissingTerm": "#/$defs/MissingTerm"
               },
               "propertyName": "kind"
            },
            "oneOf": [
               {
                  "$ref": "#/$defs/AssignedTerm"
               },
               {
                  "$ref": "#/$defs/MissingTerm"
               }
            ]
         },
         "title": "Warnings",
         "type": "array"
      },
      "given_mapping_or_bag_of_terms": {
         "anyOf": [
            {
               "additionalProperties": true,
               "type": "object"
            },
            {
               "items": {},
               "type": "array"
            }
         ],
         "title": "Given Mapping Or Bag Of Terms"
      },
      "mapping_used": {
         "additionalProperties": true,
         "title": "Mapping Used",
         "type": "object"
      },
      "generated_drs_expression": {
         "title": "Generated Drs Expression",
         "type": "string"
      }
   },
   "$defs": {
      "AssignedTerm": {
         "description": "Represents a decision of the Generator to assign this term to the collection, that may not be.\nrelevant.",
         "properties": {
            "kind": {
               "const": "AssignedTerm",
               "default": "AssignedTerm",
               "title": "Kind",
               "type": "string"
            },
            "collection_id": {
               "title": "Collection Id",
               "type": "string"
            },
            "term": {
               "title": "Term",
               "type": "string"
            }
         },
         "required": [
            "collection_id",
            "term"
         ],
         "title": "AssignedTerm",
         "type": "object"
      },
      "ConflictingCollections": {
         "description": "Represents a problem while inferring a mapping collection - term in the generation\nof a DRS expression based on a bag of terms. The problem is that these collections shares the\nvery same terms. The generator is unable to choose which term for which collection.",
         "properties": {
            "kind": {
               "const": "ConflictingCollections",
               "default": "ConflictingCollections",
               "title": "Kind",
               "type": "string"
            },
            "collection_ids": {
               "items": {
                  "type": "string"
               },
               "title": "Collection Ids",
               "type": "array"
            },
            "terms": {
               "items": {
                  "type": "string"
               },
               "title": "Terms",
               "type": "array"
            }
         },
         "required": [
            "collection_ids",
            "terms"
         ],
         "title": "ConflictingCollections",
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
      },
      "InvalidTerm": {
         "description": "Represents a problem of invalid term against a collection or a constant part of a DRS specification.",
         "properties": {
            "kind": {
               "const": "InvalidTerm",
               "default": "InvalidTerm",
               "title": "Kind",
               "type": "string"
            },
            "term": {
               "title": "Term",
               "type": "string"
            },
            "term_position": {
               "title": "Term Position",
               "type": "integer"
            },
            "collection_id_or_constant_value": {
               "title": "Collection Id Or Constant Value",
               "type": "string"
            }
         },
         "required": [
            "term",
            "term_position",
            "collection_id_or_constant_value"
         ],
         "title": "InvalidTerm",
         "type": "object"
      },
      "MissingTerm": {
         "description": "Represents a problem of missing term for a collection part of the DRS specification.",
         "properties": {
            "kind": {
               "const": "MissingTerm",
               "default": "MissingTerm",
               "title": "Kind",
               "type": "string"
            },
            "collection_id": {
               "title": "Collection Id",
               "type": "string"
            },
            "collection_position": {
               "title": "Collection Position",
               "type": "integer"
            }
         },
         "required": [
            "collection_id",
            "collection_position"
         ],
         "title": "MissingTerm",
         "type": "object"
      },
      "TooManyTermCollection": {
         "description": "Represents a problem while inferring a mapping collection - term in the generation\nof a DRS expression based on a bag of terms. The problem is that more than one term\nis able to match this collection. The generator is unable to choose from these terms",
         "properties": {
            "kind": {
               "const": "TooManyTermsCollection",
               "default": "TooManyTermsCollection",
               "title": "Kind",
               "type": "string"
            },
            "collection_id": {
               "title": "Collection Id",
               "type": "string"
            },
            "terms": {
               "items": {
                  "type": "string"
               },
               "title": "Terms",
               "type": "array"
            }
         },
         "required": [
            "collection_id",
            "terms"
         ],
         "title": "TooManyTermCollection",
         "type": "object"
      }
   },
   "required": [
      "project_id",
      "type",
      "errors",
      "warnings",
      "given_mapping_or_bag_of_terms",
      "mapping_used",
      "generated_drs_expression"
   ]
}
```

</details></p>

#### *field* errors *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[Annotated](https://docs.python.org/3/library/typing.html#typing.Annotated)[[AssignedTerm](#esgvoc.apps.drs.report.AssignedTerm) | [ConflictingCollections](#esgvoc.apps.drs.report.ConflictingCollections) | [InvalidTerm](#esgvoc.apps.drs.report.InvalidTerm) | [MissingTerm](#esgvoc.apps.drs.report.MissingTerm) | [TooManyTermCollection](#esgvoc.apps.drs.report.TooManyTermCollection), FieldInfo(annotation=NoneType, required=True, discriminator='kind')]]* *[Required]*

A list of DRS generation issues that are considered as errors.

#### *field* generated_drs_expression *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The generated DRS expression with possible tags to replace missing or invalid terms.

#### *field* given_mapping_or_bag_of_terms *: [Mapping](https://docs.python.org/3/library/typing.html#typing.Mapping) | [Iterable](https://docs.python.org/3/library/typing.html#typing.Iterable)* *[Required]*

The mapping or the bag of terms given.

#### *field* mapping_used *: [Mapping](https://docs.python.org/3/library/typing.html#typing.Mapping)* *[Required]*

The mapping inferred from the given bag of terms (same mapping otherwise).

#### *field* project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The project id associated to the result of the DRS application.

#### *field* type *: [DrsType](project_specs.md#esgvoc.api.project_specs.DrsType)* *[Required]*

The type of the DRS

#### *field* warnings *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[Annotated](https://docs.python.org/3/library/typing.html#typing.Annotated)[[AssignedTerm](#esgvoc.apps.drs.report.AssignedTerm) | [MissingTerm](#esgvoc.apps.drs.report.MissingTerm), FieldInfo(annotation=NoneType, required=True, discriminator='kind')]]* *[Required]*

A list of DRS generation issues that are considered as warnings.

#### INVALID_TAG *: [ClassVar](https://docs.python.org/3/library/typing.html#typing.ClassVar)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *= '[INVALID]'*

Tag used in the DRS generated expression to replace a invalid term.

#### MISSING_TAG *: [ClassVar](https://docs.python.org/3/library/typing.html#typing.ClassVar)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *= '[MISSING]'*

Tag used in the DRS generated expression to replace a missing term.

#### *property* nb_errors *: [int](https://docs.python.org/3/library/functions.html#int)*

The number of errors.

#### *property* nb_warnings *: [int](https://docs.python.org/3/library/functions.html#int)*

The number of warnings.

#### *property* validated *: [bool](https://docs.python.org/3/library/functions.html#bool)*

The correctness of the result of the DRS application.

### *Pydantic model* esgvoc.apps.drs.report.DrsIssue

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel), [`ABC`](https://docs.python.org/3/library/abc.html#abc.ABC)

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DrsIssue",
   "type": "object",
   "properties": {
      "kind": {
         "title": "Kind",
         "type": "string"
      }
   },
   "required": [
      "kind"
   ]
}
```

</details></p>

#### *field* kind *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The class name of the issue for JSON serialization/deserialization.

#### *abstractmethod* accept(visitor) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS issue visitor.

* **Parameters:**
  **visitor** – The DRS issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.DrsReport

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

Generic DRS application report class.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DrsReport",
   "description": "Generic DRS application report class.",
   "type": "object",
   "properties": {
      "project_id": {
         "title": "Project Id",
         "type": "string"
      },
      "type": {
         "$ref": "#/$defs/DrsType"
      },
      "errors": {
         "items": {},
         "title": "Errors",
         "type": "array"
      },
      "warnings": {
         "items": {},
         "title": "Warnings",
         "type": "array"
      }
   },
   "$defs": {
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
      "project_id",
      "type",
      "errors",
      "warnings"
   ]
}
```

</details></p>

#### *field* errors *: [list](https://docs.python.org/3/library/stdtypes.html#list)* *[Required]*

A list of DRS issues that are considered as errors.

#### *field* project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The project id associated to the result of the DRS application.

#### *field* type *: [DrsType](project_specs.md#esgvoc.api.project_specs.DrsType)* *[Required]*

The type of the DRS

#### *field* warnings *: [list](https://docs.python.org/3/library/stdtypes.html#list)* *[Required]*

A list of DRS issues that are considered as warnings.

#### *property* nb_errors *: [int](https://docs.python.org/3/library/functions.html#int)*

The number of errors.

#### *property* nb_warnings *: [int](https://docs.python.org/3/library/functions.html#int)*

The number of warnings.

#### *property* validated *: [bool](https://docs.python.org/3/library/functions.html#bool)*

The correctness of the result of the DRS application.

### *Pydantic model* esgvoc.apps.drs.report.DrsValidationReport

Bases: [`DrsReport`](#esgvoc.apps.drs.report.DrsReport)

The DRS validation report class.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "DrsValidationReport",
   "description": "The DRS validation report class.",
   "type": "object",
   "properties": {
      "project_id": {
         "title": "Project Id",
         "type": "string"
      },
      "type": {
         "$ref": "#/$defs/DrsType"
      },
      "errors": {
         "items": {
            "discriminator": {
               "mapping": {
                  "BlankTerm": "#/$defs/BlankTerm",
                  "ExtraChar": "#/$defs/ExtraChar",
                  "ExtraSeparator": "#/$defs/ExtraSeparator",
                  "ExtraTerm": "#/$defs/ExtraTerm",
                  "FileNameExtensionIssue": "#/$defs/FileNameExtensionIssue",
                  "InvalidTerm": "#/$defs/InvalidTerm",
                  "MissingTerm": "#/$defs/MissingTerm",
                  "Space": "#/$defs/Space",
                  "Unparsable": "#/$defs/Unparsable"
               },
               "propertyName": "kind"
            },
            "oneOf": [
               {
                  "$ref": "#/$defs/BlankTerm"
               },
               {
                  "$ref": "#/$defs/ExtraChar"
               },
               {
                  "$ref": "#/$defs/ExtraSeparator"
               },
               {
                  "$ref": "#/$defs/ExtraTerm"
               },
               {
                  "$ref": "#/$defs/FileNameExtensionIssue"
               },
               {
                  "$ref": "#/$defs/InvalidTerm"
               },
               {
                  "$ref": "#/$defs/MissingTerm"
               },
               {
                  "$ref": "#/$defs/Space"
               },
               {
                  "$ref": "#/$defs/Unparsable"
               }
            ]
         },
         "title": "Errors",
         "type": "array"
      },
      "warnings": {
         "items": {
            "discriminator": {
               "mapping": {
                  "ExtraSeparator": "#/$defs/ExtraSeparator",
                  "MissingTerm": "#/$defs/MissingTerm",
                  "Space": "#/$defs/Space"
               },
               "propertyName": "kind"
            },
            "oneOf": [
               {
                  "$ref": "#/$defs/ExtraSeparator"
               },
               {
                  "$ref": "#/$defs/MissingTerm"
               },
               {
                  "$ref": "#/$defs/Space"
               }
            ]
         },
         "title": "Warnings",
         "type": "array"
      },
      "expression": {
         "title": "Expression",
         "type": "string"
      },
      "mapping_used": {
         "additionalProperties": true,
         "title": "Mapping Used",
         "type": "object"
      }
   },
   "$defs": {
      "BlankTerm": {
         "description": "Represents a problem of blank term in the DRS expression (i.e., space[s] surrounded by separators).",
         "properties": {
            "kind": {
               "const": "BlankTerm",
               "default": "BlankTerm",
               "title": "Kind",
               "type": "string"
            },
            "column": {
               "anyOf": [
                  {
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Column"
            }
         },
         "title": "BlankTerm",
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
      },
      "ExtraChar": {
         "description": "Represents a problem of extra characters at the end of the DRS expression.",
         "properties": {
            "kind": {
               "const": "ExtraChar",
               "default": "ExtraChar",
               "title": "Kind",
               "type": "string"
            },
            "column": {
               "anyOf": [
                  {
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Column"
            }
         },
         "title": "ExtraChar",
         "type": "object"
      },
      "ExtraSeparator": {
         "description": "Represents a problem of multiple separator occurrences in the DRS expression.",
         "properties": {
            "kind": {
               "const": "ExtraSeparator",
               "default": "ExtraSeparator",
               "title": "Kind",
               "type": "string"
            },
            "column": {
               "anyOf": [
                  {
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Column"
            }
         },
         "title": "ExtraSeparator",
         "type": "object"
      },
      "ExtraTerm": {
         "description": "Represents a problem of extra term at the end of the given DRS expression.\nAll part of the DRS specification have been processed and this term is not necessary\n(`collection_id` is `None`) or it has been invalidated by an optional collection part\nof the DRS specification (`collection_id` is set).",
         "properties": {
            "kind": {
               "const": "ExtraTerm",
               "default": "ExtraTerm",
               "title": "Kind",
               "type": "string"
            },
            "term": {
               "title": "Term",
               "type": "string"
            },
            "term_position": {
               "title": "Term Position",
               "type": "integer"
            },
            "collection_id": {
               "anyOf": [
                  {
                     "type": "string"
                  },
                  {
                     "type": "null"
                  }
               ],
               "title": "Collection Id"
            }
         },
         "required": [
            "term",
            "term_position",
            "collection_id"
         ],
         "title": "ExtraTerm",
         "type": "object"
      },
      "FileNameExtensionIssue": {
         "description": "Represents a problem on the given file name extension (missing or not compliant).",
         "properties": {
            "kind": {
               "const": "FileNameExtensionIssue",
               "default": "FileNameExtensionIssue",
               "title": "Kind",
               "type": "string"
            },
            "expected_extension": {
               "title": "Expected Extension",
               "type": "string"
            }
         },
         "required": [
            "expected_extension"
         ],
         "title": "FileNameExtensionIssue",
         "type": "object"
      },
      "InvalidTerm": {
         "description": "Represents a problem of invalid term against a collection or a constant part of a DRS specification.",
         "properties": {
            "kind": {
               "const": "InvalidTerm",
               "default": "InvalidTerm",
               "title": "Kind",
               "type": "string"
            },
            "term": {
               "title": "Term",
               "type": "string"
            },
            "term_position": {
               "title": "Term Position",
               "type": "integer"
            },
            "collection_id_or_constant_value": {
               "title": "Collection Id Or Constant Value",
               "type": "string"
            }
         },
         "required": [
            "term",
            "term_position",
            "collection_id_or_constant_value"
         ],
         "title": "InvalidTerm",
         "type": "object"
      },
      "MissingTerm": {
         "description": "Represents a problem of missing term for a collection part of the DRS specification.",
         "properties": {
            "kind": {
               "const": "MissingTerm",
               "default": "MissingTerm",
               "title": "Kind",
               "type": "string"
            },
            "collection_id": {
               "title": "Collection Id",
               "type": "string"
            },
            "collection_position": {
               "title": "Collection Position",
               "type": "integer"
            }
         },
         "required": [
            "collection_id",
            "collection_position"
         ],
         "title": "MissingTerm",
         "type": "object"
      },
      "Space": {
         "description": "Represents a problem of unnecessary space[s] at the beginning or end of the DRS expression.\nNote: `column` is `None`.",
         "properties": {
            "kind": {
               "const": "Space",
               "default": "Space",
               "title": "Kind",
               "type": "string"
            },
            "column": {
               "anyOf": [
                  {
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Column"
            }
         },
         "title": "Space",
         "type": "object"
      },
      "Unparsable": {
         "description": "Represents a problem of non-compliance of the DRS expression.\nNote: `column` is `None`.",
         "properties": {
            "kind": {
               "const": "Unparsable",
               "default": "Unparsable",
               "title": "Kind",
               "type": "string"
            },
            "column": {
               "anyOf": [
                  {
                     "type": "integer"
                  },
                  {
                     "type": "null"
                  }
               ],
               "default": null,
               "title": "Column"
            },
            "expected_drs_type": {
               "$ref": "#/$defs/DrsType"
            }
         },
         "required": [
            "expected_drs_type"
         ],
         "title": "Unparsable",
         "type": "object"
      }
   },
   "required": [
      "project_id",
      "type",
      "errors",
      "warnings",
      "expression",
      "mapping_used"
   ]
}
```

</details></p>

#### *field* errors *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[Annotated](https://docs.python.org/3/library/typing.html#typing.Annotated)[[BlankTerm](#esgvoc.apps.drs.report.BlankTerm) | [ExtraChar](#esgvoc.apps.drs.report.ExtraChar) | [ExtraSeparator](#esgvoc.apps.drs.report.ExtraSeparator) | [ExtraTerm](#esgvoc.apps.drs.report.ExtraTerm) | [FileNameExtensionIssue](#esgvoc.apps.drs.report.FileNameExtensionIssue) | [InvalidTerm](#esgvoc.apps.drs.report.InvalidTerm) | [MissingTerm](#esgvoc.apps.drs.report.MissingTerm) | [Space](#esgvoc.apps.drs.report.Space) | [Unparsable](#esgvoc.apps.drs.report.Unparsable), FieldInfo(annotation=NoneType, required=True, discriminator='kind')]]* *[Required]*

A list of DRS parsing and compliance issues that are considered as errors.

#### *field* expression *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The DRS expression been checked.

#### *field* mapping_used *: [Mapping](https://docs.python.org/3/library/typing.html#typing.Mapping)* *[Required]*

The mapping of collection ids to validated terms.

#### *field* project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The project id associated to the result of the DRS application.

#### *field* type *: [DrsType](project_specs.md#esgvoc.api.project_specs.DrsType)* *[Required]*

The type of the DRS

#### *field* warnings *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[Annotated](https://docs.python.org/3/library/typing.html#typing.Annotated)[[ExtraSeparator](#esgvoc.apps.drs.report.ExtraSeparator) | [MissingTerm](#esgvoc.apps.drs.report.MissingTerm) | [Space](#esgvoc.apps.drs.report.Space), FieldInfo(annotation=NoneType, required=True, discriminator='kind')]]* *[Required]*

A list of DRS parsing and compliance issues that are considered as warnings.

#### *property* nb_errors *: [int](https://docs.python.org/3/library/functions.html#int)*

The number of errors.

#### *property* nb_warnings *: [int](https://docs.python.org/3/library/functions.html#int)*

The number of warnings.

#### *property* validated *: [bool](https://docs.python.org/3/library/functions.html#bool)*

The correctness of the result of the DRS application.

### *Pydantic model* esgvoc.apps.drs.report.ExtraChar

Bases: [`ParsingIssue`](#esgvoc.apps.drs.report.ParsingIssue)

Represents a problem of extra characters at the end of the DRS expression.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ExtraChar",
   "description": "Represents a problem of extra characters at the end of the DRS expression.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "ExtraChar",
         "default": "ExtraChar",
         "title": "Kind",
         "type": "string"
      },
      "column": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Column"
      }
   }
}
```

</details></p>

#### *field* column *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

the column of faulty characters.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.EXTRA_CHAR]* *= IssueKind.EXTRA_CHAR*

The class name of the issue for JSON serialization/deserialization.

#### accept(visitor: [ParsingIssueVisitor](#esgvoc.apps.drs.report.ParsingIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS parsing issue visitor.

* **Parameters:**
  **visitor** ([*ParsingIssueVisitor*](#esgvoc.apps.drs.report.ParsingIssueVisitor)) – The DRS parsing issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.ExtraSeparator

Bases: [`ParsingIssue`](#esgvoc.apps.drs.report.ParsingIssue)

Represents a problem of multiple separator occurrences in the DRS expression.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ExtraSeparator",
   "description": "Represents a problem of multiple separator occurrences in the DRS expression.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "ExtraSeparator",
         "default": "ExtraSeparator",
         "title": "Kind",
         "type": "string"
      },
      "column": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Column"
      }
   }
}
```

</details></p>

#### *field* column *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

the column of faulty characters.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.EXTRA_SEPARATOR]* *= IssueKind.EXTRA_SEPARATOR*

The class name of the issue for JSON serialization/deserialization.

#### accept(visitor: [ParsingIssueVisitor](#esgvoc.apps.drs.report.ParsingIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS parsing issue visitor.

* **Parameters:**
  **visitor** ([*ParsingIssueVisitor*](#esgvoc.apps.drs.report.ParsingIssueVisitor)) – The DRS parsing issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.ExtraTerm

Bases: [`TermIssue`](#esgvoc.apps.drs.report.TermIssue)

Represents a problem of extra term at the end of the given DRS expression.
All part of the DRS specification have been processed and this term is not necessary
(collection_id is None) or it has been invalidated by an optional collection part
of the DRS specification (collection_id is set).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ExtraTerm",
   "description": "Represents a problem of extra term at the end of the given DRS expression.\nAll part of the DRS specification have been processed and this term is not necessary\n(`collection_id` is `None`) or it has been invalidated by an optional collection part\nof the DRS specification (`collection_id` is set).",
   "type": "object",
   "properties": {
      "kind": {
         "const": "ExtraTerm",
         "default": "ExtraTerm",
         "title": "Kind",
         "type": "string"
      },
      "term": {
         "title": "Term",
         "type": "string"
      },
      "term_position": {
         "title": "Term Position",
         "type": "integer"
      },
      "collection_id": {
         "anyOf": [
            {
               "type": "string"
            },
            {
               "type": "null"
            }
         ],
         "title": "Collection Id"
      }
   },
   "required": [
      "term",
      "term_position",
      "collection_id"
   ]
}
```

</details></p>

#### *field* collection_id *: [str](https://docs.python.org/3/library/stdtypes.html#str) | [None](https://docs.python.org/3/library/constants.html#None)* *[Required]*

The optional collection id or None.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.EXTRA_TERM]* *= IssueKind.EXTRA_TERM*

The class name of the issue for JSON serialization/deserialization.

#### *field* term *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The faulty term.

#### *field* term_position *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

The position of the faulty term (the part position, not the column of the characters.

#### accept(visitor: [ComplianceIssueVisitor](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS compliance issue visitor.

* **Parameters:**
  **visitor** ([*ComplianceIssueVisitor*](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) – The DRS compliance issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.FileNameExtensionIssue

Bases: [`ComplianceIssue`](#esgvoc.apps.drs.report.ComplianceIssue)

Represents a problem on the given file name extension (missing or not compliant).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "FileNameExtensionIssue",
   "description": "Represents a problem on the given file name extension (missing or not compliant).",
   "type": "object",
   "properties": {
      "kind": {
         "const": "FileNameExtensionIssue",
         "default": "FileNameExtensionIssue",
         "title": "Kind",
         "type": "string"
      },
      "expected_extension": {
         "title": "Expected Extension",
         "type": "string"
      }
   },
   "required": [
      "expected_extension"
   ]
}
```

</details></p>

#### *field* expected_extension *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The expected file name extension.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.FILE_NAME]* *= IssueKind.FILE_NAME*

The class name of the issue for JSON serialization/deserialization.

#### accept(visitor: [ComplianceIssueVisitor](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS compliance issue visitor.

* **Parameters:**
  **visitor** ([*ComplianceIssueVisitor*](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) – The DRS compliance issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.GenerationIssue

Bases: [`DrsIssue`](#esgvoc.apps.drs.report.DrsIssue)

Generic class for the DRS generation issues.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "GenerationIssue",
   "description": "Generic class for the DRS generation issues.",
   "type": "object",
   "properties": {
      "kind": {
         "title": "Kind",
         "type": "string"
      }
   },
   "required": [
      "kind"
   ]
}
```

</details></p>

#### *field* kind *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The class name of the issue for JSON serialization/deserialization.

#### *abstractmethod* accept(visitor: [GenerationIssueVisitor](#esgvoc.apps.drs.report.GenerationIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS generation issue visitor.

* **Parameters:**
  **visitor** ([*GenerationIssueVisitor*](#esgvoc.apps.drs.report.GenerationIssueVisitor)) – The DRS generation issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *class* esgvoc.apps.drs.report.GenerationIssueVisitor(\*args, \*\*kwargs)

Bases: [`Protocol`](https://docs.python.org/3/library/typing.html#typing.Protocol)

Specifications for a generator issues visitor.

#### visit_assign_term_issue(issue: [AssignedTerm](#esgvoc.apps.drs.report.AssignedTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an assign term issue.

#### visit_conflicting_collections_issue(issue: [ConflictingCollections](#esgvoc.apps.drs.report.ConflictingCollections)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a conflicting collections issue.

#### visit_invalid_term_issue(issue: [InvalidTerm](#esgvoc.apps.drs.report.InvalidTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an invalid term issue.

#### visit_missing_term_issue(issue: [MissingTerm](#esgvoc.apps.drs.report.MissingTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a missing term issue.

#### visit_too_many_terms_collection_issue(issue: [TooManyTermCollection](#esgvoc.apps.drs.report.TooManyTermCollection)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a too many terms collection issue.

### *Pydantic model* esgvoc.apps.drs.report.InvalidTerm

Bases: [`TermIssue`](#esgvoc.apps.drs.report.TermIssue), [`GenerationIssue`](#esgvoc.apps.drs.report.GenerationIssue)

Represents a problem of invalid term against a collection or a constant part of a DRS specification.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "InvalidTerm",
   "description": "Represents a problem of invalid term against a collection or a constant part of a DRS specification.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "InvalidTerm",
         "default": "InvalidTerm",
         "title": "Kind",
         "type": "string"
      },
      "term": {
         "title": "Term",
         "type": "string"
      },
      "term_position": {
         "title": "Term Position",
         "type": "integer"
      },
      "collection_id_or_constant_value": {
         "title": "Collection Id Or Constant Value",
         "type": "string"
      }
   },
   "required": [
      "term",
      "term_position",
      "collection_id_or_constant_value"
   ]
}
```

</details></p>

#### *field* collection_id_or_constant_value *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The collection id or the constant part of a DRS specification.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.INVALID_TERM]* *= IssueKind.INVALID_TERM*

The class name of the issue for JSON serialization/deserialization.

#### *field* term *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The faulty term.

#### *field* term_position *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

The position of the faulty term (the part position, not the column of the characters.

#### accept(visitor: [ComplianceIssueVisitor](#esgvoc.apps.drs.report.ComplianceIssueVisitor) | [GenerationIssueVisitor](#esgvoc.apps.drs.report.GenerationIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS compliance issue visitor.

* **Parameters:**
  **visitor** ([*ComplianceIssueVisitor*](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) – The DRS compliance issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *class* esgvoc.apps.drs.report.IssueKind(\*values)

Bases: [`str`](https://docs.python.org/3/library/stdtypes.html#str), [`Enum`](https://docs.python.org/3/library/enum.html#enum.Enum)

The kinds of validation and generation issues.

#### ASSIGNED *= 'AssignedTerm'*

Represents a decision of the Generator to assign a term to a collection, that may not be.

#### BLANK_TERM *= 'BlankTerm'*

Represents a problem of blank term in the DRS expression (i.e., space[s] surrounded by separators).

#### CONFLICT *= 'ConflictingCollections'*

Represents a problem while inferring a mapping: collections shares the very same terms

#### EXTRA_CHAR *= 'ExtraChar'*

Represents a problem of extra characters at the end of the DRS expression.

#### EXTRA_SEPARATOR *= 'ExtraSeparator'*

Represents a problem of multiple separator occurrences in the DRS expression.

#### EXTRA_TERM *= 'ExtraTerm'*

Represents a problem of extra term at the end of the given DRS expression.

#### FILE_NAME *= 'FileNameExtensionIssue'*

Represents a problem on the given file name extension (missing or not compliant).

#### INVALID_TERM *= 'InvalidTerm'*

Represents a problem of invalid term against a collection or a constant part of a DRS specification.

#### MISSING_TERM *= 'MissingTerm'*

Represents a problem of missing term for a collection part of the DRS specification.

#### SPACE *= 'Space'*

Represents a problem of unnecessary space[s] at the beginning or end of the DRS expression.

#### TOO_MANY *= 'TooManyTermsCollection'*

Represents a problem while inferring a mapping: one term is able to match a collection

#### UNPARSABLE *= 'Unparsable'*

Represents a problem of non-compliance of the DRS expression.

### *Pydantic model* esgvoc.apps.drs.report.MissingTerm

Bases: [`ComplianceIssue`](#esgvoc.apps.drs.report.ComplianceIssue), [`GenerationIssue`](#esgvoc.apps.drs.report.GenerationIssue)

Represents a problem of missing term for a collection part of the DRS specification.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "MissingTerm",
   "description": "Represents a problem of missing term for a collection part of the DRS specification.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "MissingTerm",
         "default": "MissingTerm",
         "title": "Kind",
         "type": "string"
      },
      "collection_id": {
         "title": "Collection Id",
         "type": "string"
      },
      "collection_position": {
         "title": "Collection Position",
         "type": "integer"
      }
   },
   "required": [
      "collection_id",
      "collection_position"
   ]
}
```

</details></p>

#### *field* collection_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The collection id.

#### *field* collection_position *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

The collection part position (not the column of the characters).

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.MISSING_TERM]* *= IssueKind.MISSING_TERM*

The class name of the issue for JSON serialization/deserialization.

#### accept(visitor: [ComplianceIssueVisitor](#esgvoc.apps.drs.report.ComplianceIssueVisitor) | [GenerationIssueVisitor](#esgvoc.apps.drs.report.GenerationIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS compliance issue visitor.

* **Parameters:**
  **visitor** ([*ComplianceIssueVisitor*](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) – The DRS compliance issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.ParsingIssue

Bases: [`DrsIssue`](#esgvoc.apps.drs.report.DrsIssue)

Generic class for the DRS parsing issues.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "ParsingIssue",
   "description": "Generic class for the DRS parsing issues.",
   "type": "object",
   "properties": {
      "kind": {
         "title": "Kind",
         "type": "string"
      },
      "column": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Column"
      }
   },
   "required": [
      "kind"
   ]
}
```

</details></p>

#### *field* column *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

the column of faulty characters.

#### *field* kind *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The class name of the issue for JSON serialization/deserialization.

#### *abstractmethod* accept(visitor: [ParsingIssueVisitor](#esgvoc.apps.drs.report.ParsingIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS parsing issue visitor.

* **Parameters:**
  **visitor** ([*ParsingIssueVisitor*](#esgvoc.apps.drs.report.ParsingIssueVisitor)) – The DRS parsing issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *class* esgvoc.apps.drs.report.ParsingIssueVisitor(\*args, \*\*kwargs)

Bases: [`Protocol`](https://docs.python.org/3/library/typing.html#typing.Protocol)

Specifications for a parsing issues visitor.

#### visit_blank_term_issue(issue: [BlankTerm](#esgvoc.apps.drs.report.BlankTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a blank term issue.

#### visit_extra_char_issue(issue: [ExtraChar](#esgvoc.apps.drs.report.ExtraChar)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an extra char issue.

#### visit_extra_separator_issue(issue: [ExtraSeparator](#esgvoc.apps.drs.report.ExtraSeparator)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an extra separator issue.

#### visit_space_issue(issue: [Space](#esgvoc.apps.drs.report.Space)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a space issue.

#### visit_unparsable_issue(issue: [Unparsable](#esgvoc.apps.drs.report.Unparsable)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a unparsable issue.

### *Pydantic model* esgvoc.apps.drs.report.Space

Bases: [`ParsingIssue`](#esgvoc.apps.drs.report.ParsingIssue)

Represents a problem of unnecessary space[s] at the beginning or end of the DRS expression.
Note: column is None.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Space",
   "description": "Represents a problem of unnecessary space[s] at the beginning or end of the DRS expression.\nNote: `column` is `None`.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "Space",
         "default": "Space",
         "title": "Kind",
         "type": "string"
      },
      "column": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Column"
      }
   }
}
```

</details></p>

#### *field* column *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

the column of faulty characters.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.SPACE]* *= IssueKind.SPACE*

The class name of the issue for JSON serialization/deserialization.

#### accept(visitor: [ParsingIssueVisitor](#esgvoc.apps.drs.report.ParsingIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS parsing issue visitor.

* **Parameters:**
  **visitor** ([*ParsingIssueVisitor*](#esgvoc.apps.drs.report.ParsingIssueVisitor)) – The DRS parsing issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.TermIssue

Bases: [`ComplianceIssue`](#esgvoc.apps.drs.report.ComplianceIssue)

Generic class for the DRS term issues.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "TermIssue",
   "description": "Generic class for the DRS term issues.",
   "type": "object",
   "properties": {
      "kind": {
         "title": "Kind",
         "type": "string"
      },
      "term": {
         "title": "Term",
         "type": "string"
      },
      "term_position": {
         "title": "Term Position",
         "type": "integer"
      }
   },
   "required": [
      "kind",
      "term",
      "term_position"
   ]
}
```

</details></p>

#### *field* kind *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The class name of the issue for JSON serialization/deserialization.

#### *field* term *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The faulty term.

#### *field* term_position *: [int](https://docs.python.org/3/library/functions.html#int)* *[Required]*

The position of the faulty term (the part position, not the column of the characters.

#### *abstractmethod* accept(visitor: [ComplianceIssueVisitor](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS compliance issue visitor.

* **Parameters:**
  **visitor** ([*ComplianceIssueVisitor*](#esgvoc.apps.drs.report.ComplianceIssueVisitor)) – The DRS compliance issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.TooManyTermCollection

Bases: [`GenerationIssue`](#esgvoc.apps.drs.report.GenerationIssue)

Represents a problem while inferring a mapping collection - term in the generation
of a DRS expression based on a bag of terms. The problem is that more than one term
is able to match this collection. The generator is unable to choose from these terms

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "TooManyTermCollection",
   "description": "Represents a problem while inferring a mapping collection - term in the generation\nof a DRS expression based on a bag of terms. The problem is that more than one term\nis able to match this collection. The generator is unable to choose from these terms",
   "type": "object",
   "properties": {
      "kind": {
         "const": "TooManyTermsCollection",
         "default": "TooManyTermsCollection",
         "title": "Kind",
         "type": "string"
      },
      "collection_id": {
         "title": "Collection Id",
         "type": "string"
      },
      "terms": {
         "items": {
            "type": "string"
         },
         "title": "Terms",
         "type": "array"
      }
   },
   "required": [
      "collection_id",
      "terms"
   ]
}
```

</details></p>

#### *field* collection_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The collection id.

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.TOO_MANY]* *= IssueKind.TOO_MANY*

The class name of the issue for JSON serialization/deserialization.

#### *field* terms *: [list](https://docs.python.org/3/library/stdtypes.html#list)[[str](https://docs.python.org/3/library/stdtypes.html#str)]* *[Required]*

The faulty terms.

#### accept(visitor: [GenerationIssueVisitor](#esgvoc.apps.drs.report.GenerationIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS generation issue visitor.

* **Parameters:**
  **visitor** ([*GenerationIssueVisitor*](#esgvoc.apps.drs.report.GenerationIssueVisitor)) – The DRS generation issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *Pydantic model* esgvoc.apps.drs.report.Unparsable

Bases: [`ParsingIssue`](#esgvoc.apps.drs.report.ParsingIssue)

Represents a problem of non-compliance of the DRS expression.
Note: column is None.

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Unparsable",
   "description": "Represents a problem of non-compliance of the DRS expression.\nNote: `column` is `None`.",
   "type": "object",
   "properties": {
      "kind": {
         "const": "Unparsable",
         "default": "Unparsable",
         "title": "Kind",
         "type": "string"
      },
      "column": {
         "anyOf": [
            {
               "type": "integer"
            },
            {
               "type": "null"
            }
         ],
         "default": null,
         "title": "Column"
      },
      "expected_drs_type": {
         "$ref": "#/$defs/DrsType"
      }
   },
   "$defs": {
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
      "expected_drs_type"
   ]
}
```

</details></p>

#### *field* column *: [int](https://docs.python.org/3/library/functions.html#int) | [None](https://docs.python.org/3/library/constants.html#None)* *= None*

the column of faulty characters.

#### *field* expected_drs_type *: [DrsType](project_specs.md#esgvoc.api.project_specs.DrsType)* *[Required]*

The expected DRS type of the expression (directory, file name or dataset id).

#### *field* kind *: [Literal](https://docs.python.org/3/library/typing.html#typing.Literal)[IssueKind.UNPARSABLE]* *= IssueKind.UNPARSABLE*

The class name of the issue for JSON serialization/deserialization.

#### accept(visitor: [ParsingIssueVisitor](#esgvoc.apps.drs.report.ParsingIssueVisitor)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Accept an DRS parsing issue visitor.

* **Parameters:**
  **visitor** ([*ParsingIssueVisitor*](#esgvoc.apps.drs.report.ParsingIssueVisitor)) – The DRS parsing issue visitor.
* **Returns:**
  Depending on the visitor.
* **Return type:**
  Any

### *class* esgvoc.apps.drs.report.ValidationIssueVisitor(\*args, \*\*kwargs)

Bases: [`ParsingIssueVisitor`](#esgvoc.apps.drs.report.ParsingIssueVisitor), [`ComplianceIssueVisitor`](#esgvoc.apps.drs.report.ComplianceIssueVisitor)

#### visit_blank_term_issue(issue: [BlankTerm](#esgvoc.apps.drs.report.BlankTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a blank term issue.

#### visit_extra_char_issue(issue: [ExtraChar](#esgvoc.apps.drs.report.ExtraChar)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an extra char issue.

#### visit_extra_separator_issue(issue: [ExtraSeparator](#esgvoc.apps.drs.report.ExtraSeparator)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an extra separator issue.

#### visit_extra_term_issue(issue: [ExtraTerm](#esgvoc.apps.drs.report.ExtraTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an extra term issue.

#### visit_filename_extension_issue(issue: [FileNameExtensionIssue](#esgvoc.apps.drs.report.FileNameExtensionIssue)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a file name extension issue.

#### visit_invalid_term_issue(issue: [InvalidTerm](#esgvoc.apps.drs.report.InvalidTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit an invalid term issue.

#### visit_missing_term_issue(issue: [MissingTerm](#esgvoc.apps.drs.report.MissingTerm)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a missing term issue.

#### visit_space_issue(issue: [Space](#esgvoc.apps.drs.report.Space)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a space issue.

#### visit_unparsable_issue(issue: [Unparsable](#esgvoc.apps.drs.report.Unparsable)) → [Any](https://docs.python.org/3/library/typing.html#typing.Any)

Visit a unparsable issue.
