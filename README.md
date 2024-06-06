# Overview

These are gradle templates I am hosting on a GitHub repository to use within other projects.

## Site Publisher
To use a site publisher, simply add the following line to the top of the `build.gradle`:
```groovy
apply from: 'https://raw.githubusercontent.com/CodinGlitch/gradle-templates/main/site-publishers/SITE-NAME.gradle'
```
\
\
You will also need to provide new properties in your `gradle.properties` file, as follows:
```properties
# required, sample below
# Will show as [FABRIC] My Mod Name 1.0.0
name_template=[$uppercase_loader] My Mod Name $version

# optional
# If using a multi-loader project, omit this property and it will use the subproject name.
loader=[forge, fabric, etc.]

# required
modrinth_id=[ID_HERE]
# AND/OR
curseforge_id=[ID_HERE]

# required
supported_versions=[minecraft versions separated by commas]

# required
requiredDependencies=[project ids of required dependencies separated by commas]
optionalDependencies=[project ids of optional dependencies separated by commas]

# optional, default release
release_type=[release, beta, or alpha]
# optional, default false
debug_mode=[if true, will not publish the file and print to console]
```
\
\
For the name template, several values can be used for substitution:

| ID                    | Substitution                                                    |
|-----------------------|-----------------------------------------------------------------|
| `$uppercase_loader`   | The current loader in uppercase, i.e. `FABRIC`                  |
| `$uppercase_loader`   | The current loader in lowercase, i.e. `fabric`                  |
| `$capitalized_loader` | The current loader capitalized, i.e. `Fabric`                   |
| `$version`            | Your version number as provided by the properties, i.e. `1.0.0` |
