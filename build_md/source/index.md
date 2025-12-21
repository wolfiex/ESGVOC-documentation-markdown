# ESGVOC Library

ESGVOC is a Python library designed to simplify interaction with controlled vocabularies (CVs) used in WCRP climate data projects. It supports querying, caching, and validating terms across various CV repositories like the [universe](https://github.com/WCRP-CMIP/WCRP-universe/tree/esgvoc) and project-specific repositories (e.g., [CMIP6Plus](https://github.com/WCRP-CMIP/CMIP6Plus_CVs/tree/esgvoc), [CMIP6](https://github.com/WCRP-CMIP/CMIP6_CVs/tree/esgvoc), etc.)

---

## Features

- **Query controlled vocabularies**:
  - Retrieve terms, collections, or descriptors.
  - Perform cross-validation and search operations.
  - Supports case-sensitive, wildcard, and approximate matching.
- **Caching**:
  - Download CVs to a local database for offline use.
  - Keep the local cache up-to-date.
- **Validation**:
  - Validate string values against CV terms (DRS).

---

## Use cases

The ESGVOC library supports a wide range of use cases, including:

### Caching

- Usage without internet access.
- Downloading CVs to a local archive or database.
- Updating the local cache.
- Performing consistency checks between the local cache and remote CV repositories.

### Listing

- All data descriptors from the universe.
- All terms of one data descriptor from the universe.
- All available projects.
- All collections from a project.
- All terms from a project.
- All terms of a collection from a project.

### Searching

- Data descriptors in the universe.
- Terms in the universe or data descriptors.
- Collections in projects.
- Terms in collections of projects.

#### NOTE
Searching is based on the term id and not its regex nor DRS name. It may be case-sensitive or not, supports wildcards (%) and regex.

### DRS validation

- Terms of a project.
- Terms of a collection from a project.
- Terms from all projects (cross-validation).

DRS validation is a feature that validates a character string against a vocabulary term. This feature is based on the DRS semantics of the terms, i.e. :

- The drs_name field of a plain term
- Or the regex field of a pattern term.

For composite terms, each part of the term is validated one by one and falls under one or other of the validation conditions described above.

#### NOTE
Don’t confuse the term identifier (id) with its DRS semantics.

### DRS applications

The DRS applications are based on the functionalities described above. They provide
convenient way to check DRS expressions of a project (directory, dataset id and file name)
and also generate expressions from mappings of collections and terms or an
unordered bag of terms.

=======

### Welcome

* [Introduction](user/introduction.md)
  * [Why ESGVOC?](user/introduction.md#why-esgvoc)
  * [Installation](user/introduction.md#installation)
    * [Using UV (preferred)](user/introduction.md#using-uv-preferred)
    * [Using pip in a virtual environment](user/introduction.md#using-pip-in-a-virtual-environment)
  * [Fetching vocabulary data](user/introduction.md#fetching-vocabulary-data)
    * [Offline use](user/introduction.md#offline-use)
  * [Official controlled vocabulary repositories](user/introduction.md#official-controlled-vocabulary-repositories)
    * [Flexibility for other repositories](user/introduction.md#flexibility-for-other-repositories)
  * [Requirements](user/introduction.md#requirements)
* [Controlled vocabulary](user/terms.md)
  * [Data Descriptor](user/terms.md#data-descriptor)
  * [Term](user/terms.md#term)
  * [Universe](user/terms.md#universe)
  * [Collection](user/terms.md#collection)
  * [Project](user/terms.md#project)
  * [ESGVOC](user/terms.md#esgvoc)
* [Database and functionality](user/cached_database.md)
  * [Overview of database management](user/cached_database.md#overview-of-database-management)
    * [Synchronization workflow](user/cached_database.md#synchronization-workflow)
    * [Viewing synchronization status](user/cached_database.md#viewing-synchronization-status)
* [ESGVOC API](user/api.md)
  * [Overview](user/api.md#overview)
  * [Key features](user/api.md#key-features)
  * [Example usage](user/api.md#example-usage)
  * [Structured data with Pydantic models](user/api.md#structured-data-with-pydantic-models)
    * [Structured data](user/api.md#structured-data)
    * [Ease of integration](user/api.md#ease-of-integration)
* [Command Line Interface (CLI)](user/cli.md)
  * [Overview](user/cli.md#overview)
  * [Installation and access](user/cli.md#installation-and-access)
  * [Command syntax](user/cli.md#command-syntax)
    * [Understanding `::`](user/cli.md#understanding)
    * [Case Sensitivity](user/cli.md#case-sensitivity)
  * [Basic commands](user/cli.md#basic-commands)
    * [Querying data](user/cli.md#querying-data)
    * [Validating data](user/cli.md#validating-data)
  * [Features and limitations](user/cli.md#features-and-limitations)
    * [Filtering and querying](user/cli.md#filtering-and-querying)
    * [Error handling](user/cli.md#error-handling)
    * [Batch operations](user/cli.md#batch-operations)
  * [Advanced use cases](user/cli.md#advanced-use-cases)
  * [Summary](user/cli.md#summary)

### How to

* [Get](how_to/get.md)
  * [One term](how_to/get.md#one-term)
  * [All terms from one data descriptor or collection](how_to/get.md#all-terms-from-one-data-descriptor-or-collection)
  * [A term from a CV](how_to/get.md#a-term-from-a-cv)
* [Valid](how_to/valid.md)
  * [Knowing the term id:](how_to/valid.md#knowing-the-term-id)
  * [Knowing the only the collection id:](how_to/valid.md#knowing-the-only-the-collection-id)
  * [Knowing the only the project id:](how_to/valid.md#knowing-the-only-the-project-id)
  * [Find it in all known projects](how_to/valid.md#find-it-in-all-known-projects)
* [Valid DRS](how_to/validate_drs.md)
  * [One DRS](how_to/validate_drs.md#one-drs)
* [Generate DRS](how_to/generate_drs.md)
  * [From mapping collection:term drs_name](how_to/generate_drs.md#from-mapping-collection-term-drs-name)
  * [From a bag of drs_name](how_to/generate_drs.md#from-a-bag-of-drs-name)

### Guides

* [ESGVOC library tutorial](guides/basics_esgvoc.md)
  * [Universe and projects organization](guides/basics_esgvoc.md#universe-and-projects-organization)
  * [ESGVOC API organization](guides/basics_esgvoc.md#esgvoc-api-organization)
  * [Universe](guides/basics_esgvoc.md#universe)
    * [Listing](guides/basics_esgvoc.md#listing)
    * [Little detour: pydantic model instance return](guides/basics_esgvoc.md#little-detour-pydantic-model-instance-return)
    * [Find terms in universe](guides/basics_esgvoc.md#find-terms-in-universe)
    * [Find terms or data decriptors in universe](guides/basics_esgvoc.md#find-terms-or-data-decriptors-in-universe)
  * [Project example: CMIP6plus](guides/basics_esgvoc.md#project-example-cmip6plus)
    * [Find terms in a project](guides/basics_esgvoc.md#find-terms-in-a-project)
    * [Find terms and collections](guides/basics_esgvoc.md#find-terms-and-collections)
  * [Validating string against the project CV](guides/basics_esgvoc.md#validating-string-against-the-project-cv)
    * [Queries based on the project and the collection ids](guides/basics_esgvoc.md#queries-based-on-the-project-and-the-collection-ids)
    * [Queries based only on the project id](guides/basics_esgvoc.md#queries-based-only-on-the-project-id)
    * [Across all projects](guides/basics_esgvoc.md#across-all-projects)
* [DRS applications tutorial](guides/basics_drs.md)
  * [DRS validation](guides/basics_drs.md#drs-validation)
    * [Instantiation](guides/basics_drs.md#instantiation)
    * [Validation methods](guides/basics_drs.md#validation-methods)
    * [Reporting](guides/basics_drs.md#reporting)
  * [DRS generation](guides/basics_drs.md#drs-generation)
    * [Instantiation](guides/basics_drs.md#id1)
    * [Mapping](guides/basics_drs.md#mapping)
    * [Bag of terms](guides/basics_drs.md#bag-of-terms)
