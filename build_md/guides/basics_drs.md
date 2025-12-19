# DRS applications tutorial

The following DRS applications are mainly based on the validation functions (seen in the API tutorial). They ease the verification of DRS expressions or their generation.

## DRS validation

The DRS validation is the process to validate an character expression against a DRS specification of a project.

### Instantiation

Import the validator class:

```ipython3
from esgvoc.apps.drs.validator import DrsValidator
```

Instantiate a validator object (documentation of the class is [here](https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.validator.DrsValidator)), for the CMIP6Plus CV, for example:

```ipython3
validator = DrsValidator(project_id="cmip6plus")
```

Instantiation takes some time (parsing of DRS specifications). As the validator (and generator) does not keep any information about the expression to be verified (or generated) from one validation to the next (or generation), it is advisable to **reuse the same object** and avoid instantiating a new one for each validation (or generation).

### Validation methods

Check the compliance of a DRS expression. For example a dataset id:

```ipython3
expr = "CMIP6Plus.CMIP.IPSL.MIROC6.amip.r2i2p1f2.ACmon.od550aer.gn"
validator.validate_dataset_id(drs_expression=expr)
```

You can also check directories and file names:

```ipython3
expr = "CMIP6Plus/CMIP/NCC/MIROC6/amip/r2i2p1f2/ACmon/od550aer/gn/v20190923"
validator.validate_directory(drs_expression=expr)
```

```ipython3
expr = "od550aer_ACmon_MIROC6_amip_r2i2p1f2_gn_201211-201212.nc"
validator.validate_file_name(drs_expression=expr)
```

The last method depends of the DRS type:

```ipython3
expr = "CMIP6Plus.CMIP.IPSL.MIROC6.amip.r2i2p1f2.ACmon.od550aer.gn"
validator.validate(drs_expression=expr, drs_type='dataset_id')
```

### Reporting

The validator returns value is not a string, but a report:

```ipython3
expr = "od550aer_ACmon_MIROC6_amip_r2i2p1f2_gn.nc"
report = validator.validate_file_name(drs_expression=expr)
if report:
    print('valid')
else:
    print('unvalid')
```

```myst-ansi
valid
```

And has any errors and warnings (e.g., missing period at the end of the file name). See the full API documentation [here](https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.report.DrsValidationReport).

```ipython3
report.warnings
```

The validator supports a wild range issues, such as blank term:

```ipython3
expr = "CMIP6Plus/CMIP/ /NCC/MIROC6/amip/r2i2p1f2/ACmon/od550aer/gn/v20190923"
report = validator.validate_directory(drs_expression=expr)
print(report)
print(f'{report.errors=}')
```

```myst-ansi
'CMIP6Plus/CMIP/ /NCC/MIROC6/amip/r2i2p1f2/ACmon/od550aer/gn/v20190923' has 1 error(s) and 0 warning(s)
report.errors=[blank term at column 16]
```

Extra terms at the end of the expression or separator stuttering:

```ipython3
expr = "CMIP6Plus.CMIP.IPSL.MIROC6.amip..r2i2p1f2.ACmon.od550aer.gn.some_thing"
report = validator.validate_dataset_id(drs_expression=expr)
print(report)
print(f'{report.errors=}')
```

```myst-ansi
'CMIP6Plus.CMIP.IPSL.MIROC6.amip..r2i2p1f2.ACmon.od550aer.gn.some_thing' has 2 error(s) and 0 warning(s)
report.errors=[extra separator(s) at column 33, extra term some_thing at position 9]
```

And of course invalid terms:

```ipython3
expr = "CMIP6Plus/CMIP_ERROR_HERE/NCC/MIROC6/amip/r2i2p1f2/ACmon/od550aer/gn/v20190923"
report = validator.validate_directory(drs_expression=expr)
print(report)
print(f'{report.errors=}')
```

```myst-ansi
'CMIP6Plus/CMIP_ERROR_HERE/NCC/MIROC6/amip/r2i2p1f2/ACmon/od550aer/gn/v20190923' has 1 error(s) and 0 warning(s)
report.errors=[term 'CMIP_ERROR_HERE' not compliant with activity_id at position 2]
```

The validation issues can be processed by implementing a [parsing issue visitor](https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.report.ParsingIssueVisitor) and a [compliance issue visitor](https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.report.ComplianceIssueVisitor):

```ipython3
class MyValidationVisitor:
    def visit_invalid_term_issue(self, issue):
        print('Doing something automatically with a invalid term issue, ' +
              'rather then printing it')
    # You should implement the other methods of ParsingIssueVisitor and 
    # ComplianceIssueVisitor too!
    # Read https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.report.ValidationIssueVisitor

my_visitor = MyValidationVisitor()
report.errors[0].accept(my_visitor)
```

```myst-ansi
Doing something automatically with a invalid term issue, rather then printing it
```

## DRS generation

The DRS generation consists of generate a DRS expression from an unordered mapping of collections and terms or a bag of unordered terms.

### Instantiation

Import the generator class:

```ipython3
from esgvoc.apps.drs.generator import DrsGenerator
```

Instantiate a generator object (documentation of the class is [here](https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.generator.DrsGenerator)), for the CMIP6Plus CV, for example:

```ipython3
generator = DrsGenerator("cmip6plus")
```

Instantiation takes some time (parsing of DRS specifications). As the generator (and validator) does not keep any information about the expression to be generated (or verified) from one generation to the next (or validation), it is advisable to **reuse the same object** and avoid instantiating a new one for each generation (or validation).

### Mapping

Build a dictionary that maps terms with their collections:

```ipython3
mapping = {
    'member_id': 'r2i2p1f2',
    'activity_id': 'CMIP',
    'source_id': 'MIROC6',
    'mip_era': 'CMIP6Plus',
    'experiment_id': 'amip',
    'variable_id': 'od550aer',
    'table_id': 'ACmon',
    'grid_label': 'gn',
    'version': 'v20190923',
    'institution_id': 'IPSL',
    'extra_information': 'some_value'
}
```

Then generate a DRS directory expression:

```ipython3
generator.generate_directory_from_mapping(mapping=mapping)
```

It has successfully generate the directory expression, even if the mapping has some extra information (quite the opposite of the DRS validation). The same mapping can also generate the associated dataset id and file name expressions, **provided it has all information needed!** Note that the generator adds automatically the extension for the generation of DRS file names.

```ipython3
generator.generate_dataset_id_from_mapping(mapping=mapping)
```

```ipython3
# This one has a warning because the period is missing.
generator.generate_file_name_from_mapping(mapping=mapping)
```

As for the DRS validation, the generator returns a report that you can display or visit (generation report [class](https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.report.DrsGenerationReport), generator visitor [specifications](https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.report.GeneratorIssueVisitor)):

```ipython3
report = generator.generate_file_name_from_mapping(mapping=mapping)
print(f'{report.warnings=}') # The warning a bit earlier. 
```

```myst-ansi
report.warnings=[missing term for time_range at position 7]
```

```ipython3
class MyGeneratorVisitor:
    def visit_missing_term_issue(self, issue):
            print('Doing something automatically with a missing term issue, ' +
                  'rather then printing it')
    # You should implement the other methods of GeneratorIssueVisitor too!
    # Read https://esgf.github.io/esgf-vocab/api_documentation/drs.html#esgvoc.apps.drs.report.GeneratorIssueVisitor

my_visitor =  MyGeneratorVisitor()
report.warnings[0].accept(my_visitor)
```

```myst-ansi
Doing something automatically with a missing term issue, rather then printing it
```

Like the validator, the generator provides a parametric method based on the type of DRS:

```ipython3
generator.generate_from_mapping(mapping=mapping, drs_type='directory')
```

The mapping methods of the generator class supports invalid and missing terms. Despite of the errors and warnings, the generator returns a DRS expression with parsable tags in place of the faulty terms.

```ipython3
invalid_mapping = mapping.copy()
del invalid_mapping['member_id']
invalid_mapping['source_id'] = 'MiRoC6'
report = generator.generate_from_mapping(mapping=invalid_mapping,
                                         drs_type='file_name')
print(report)
print(f'{report.errors=}')
print(f'{report.warnings=}')
```

```myst-ansi
'od550aer_ACmon_[INVALID]_amip_[MISSING]_gn.nc' has 2 error(s) and 1 warning(s)
report.errors=[term 'MiRoC6' not compliant with source_id at position 3, missing term for member_id at position 5]
report.warnings=[missing term for time_range at position 7]
```

### Bag of terms

The bag of terms methods consist of generating a DRS expression from a set of unordered terms. The generator try to build a mapping between the collections of the DRS specification target and the given terms, then it generates an expression.

```ipython3
bag_of_terms = list(mapping.values())
print(f'{bag_of_terms=}')
generator.generate_from_bag_of_terms(terms=bag_of_terms, drs_type='dataset_id')
```

```myst-ansi
bag_of_terms=['r2i2p1f2', 'CMIP', 'MIROC6', 'CMIP6Plus', 'amip', 'od550aer', 'ACmon', 'gn', 'v20190923', 'IPSL', 'some_value']
```

Due to the lack of precision of some pattern terms, some terms can fit to more than one collection or fit the same collection. The generator supports these cases and try to untangle terms and collections as it is possible to be. Warnings are raised if the generator makes unobvious assignments. But most of the time, the generator will raise errors. **So the mapping methods should always be preferred**.

```ipython3
# UA and IPSL can be assigned to the collection institution_id, both.
# This leads to two kinds of error:
#    - The collection institution_id has more than one choice.
#    - As the generator cannot choose, UA and IPSL are withdrawn,
#      hence the missing term error.
bag_of_terms.append('UA')
report = generator.generate_from_bag_of_terms(terms=bag_of_terms,
                                               drs_type='dataset_id')
print(report)
print(f'{report.errors=}')
```

```myst-ansi
'CMIP6Plus.CMIP.[MISSING].MIROC6.amip.r2i2p1f2.ACmon.od550aer.gn' has 2 error(s) and 0 warning(s)
report.errors=[collection institution_id has more than one term (IPSL, UA), missing term for institution_id at position 3]
```
