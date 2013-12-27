# Schemas ("Schemata")

This section pertains to:

* The creation and use of Theos schemas ("Schemata")

## Concept

%INDENT%

Schemas are a way to manage a group of [specific master variables](./2_1_1_4_SCHEMATA.md#affected-variables) which can have their effect easily turned off or on.

An example is the built-in `debug` schema, which when enabled adds extra options to CFLAGS.

%INDENTEND%

## Enabling

%INDENT%

###### SCHEMA
Specifies enabled schemas.

Schemas are enabled by their names separated by spaces.

Example:

%CODE%

\# enable schemas "schema1" and "schema2"
<br>
SCHEMA = schema1 schema2

%CODEEND%

Defaults to empty.  
Defined in `common.mk`.

%INDENTEND%

## Describing the Schema

%INDENT%

The schema is described by specifying what variables have their values affected by its enabling. Doing so can be done by declaring a variable with the format `schema.VARIABLE`, so that enabling `schema` will do changes to a possible query of variable `VARIABLE`.

Example:
	
	# Enabling schema1 will add the '-DSCHEMA1ENABLED' additional compiler flags.
	schema1.CFLAGS = -DSCHEMA1ENABLED

%INDENTEND%

## Affected Variables

%INDENT%

These variables can be changed by schemas, with different behavior:

(we need description)

* SUBPROJECTS: how?
* OBJ_FILES
* FRAMEWORKS
* LIBRARIES
* PRIVATE_FRAMEWORKS
* CFLAGS
* CCFLAGS
* OBJCFLAGS
* OBJCCFLAGS
* LOGOSFLAGS
* LDFLAGS
* CODESIGN_FLAGS
* STRIP_FLAGS

%INDENTEND%

## Conventions

%INDENT%

* Schema names should be lowercase.

%INDENTEND%
