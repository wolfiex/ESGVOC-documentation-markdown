# Miscellaneous

### *Pydantic model* esgvoc.api.search.Item

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

An item from the universe or a project (data descriptor, collection or term).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "Item",
   "description": "An item from the universe or a project (data descriptor, collection or term).",
   "type": "object",
   "properties": {
      "id": {
         "title": "Id",
         "type": "string"
      },
      "kind": {
         "$ref": "#/$defs/ItemKind"
      },
      "parent_id": {
         "title": "Parent Id",
         "type": "string"
      }
   },
   "$defs": {
      "ItemKind": {
         "enum": [
            "data_descriptor",
            "collection",
            "term"
         ],
         "title": "ItemKind",
         "type": "string"
      }
   },
   "required": [
      "id",
      "kind",
      "parent_id"
   ]
}
```

</details></p>

#### *field* id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The id of the item.

#### *field* kind *: [ItemKind](../source/api_documentation/miscellaneous.md#esgvoc.api.search.ItemKind)* *[Required]*

The kind of the item.

#### *field* parent_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The id of the parent of the item.

### *Pydantic model* esgvoc.api.search.MatchingTerm

Bases: [`BaseModel`](https://docs.pydantic.dev/latest/api/base_model/#pydantic.BaseModel)

Place holder for a term that matches a value (term validation).

<p><details  class="autodoc_pydantic_collapsable_json">
<summary>Show JSON schema</summary>
```json
{
   "title": "MatchingTerm",
   "description": "Place holder for a term that matches a value (term validation).",
   "type": "object",
   "properties": {
      "project_id": {
         "title": "Project Id",
         "type": "string"
      },
      "collection_id": {
         "title": "Collection Id",
         "type": "string"
      },
      "term_id": {
         "title": "Term Id",
         "type": "string"
      }
   },
   "required": [
      "project_id",
      "collection_id",
      "term_id"
   ]
}
```

</details></p>

#### *field* collection_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The collection id to which the term belongs.

#### *field* project_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The project id to which the term belongs.

#### *field* term_id *: [str](https://docs.python.org/3/library/stdtypes.html#str)* *[Required]*

The term id.

### *class* esgvoc.api.search.ItemKind(\*values)

Bases: [`Enum`](https://docs.python.org/3/library/enum.html#enum.Enum)

#### COLLECTION *= 'collection'*

Corresponds to a collection

#### DATA_DESCRIPTOR *= 'data_descriptor'*

Corresponds to a data descriptor

#### TERM *= 'term'*

Corresponds to a term

### *class* esgvoc.core.db.models.mixins.TermKind(\*values)

Bases: [`Enum`](https://docs.python.org/3/library/enum.html#enum.Enum)

The kinds of term.

#### COMPOSITE *= 'composite'*

Term composed of terms.

#### MIXED *= 'mixed'*

To be defined.

#### PATTERN *= 'pattern'*

Regex based terms

#### PLAIN *= 'plain'*

End written term.

<a id="module-esgvoc.core.exceptions"></a>

### *exception* esgvoc.core.exceptions.EsgvocDbError

Bases: [`EsgvocException`](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocException)

Represents errors relative to data base management.

### *exception* esgvoc.core.exceptions.EsgvocException

Bases: [`Exception`](https://docs.python.org/3/library/exceptions.html#Exception)

Class base of all ESGVOC errors.

### *exception* esgvoc.core.exceptions.EsgvocNotFoundError

Bases: [`EsgvocException`](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocException)

Represents the not found errors.

### *exception* esgvoc.core.exceptions.EsgvocNotImplementedError

Bases: [`EsgvocException`](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocException)

Represents not implemented errors.

### *exception* esgvoc.core.exceptions.EsgvocValueError

Bases: [`EsgvocException`](../source/api_documentation/miscellaneous.md#esgvoc.core.exceptions.EsgvocException)

Represents value errors.
