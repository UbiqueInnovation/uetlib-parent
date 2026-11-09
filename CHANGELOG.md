# CHANGELOG

## 2026.11.1

- Load `ch.uetlib:uetlib-errorprone:0.1.1` on the annotation processor path and enable the
  `OpenEnumStructure` and `OpenEnumNestedTypeImport` checks as errors.
- Update shared Maven build and publish workflows to v0.2.4.
- Clarify configuration-property migration guidance for consumers.

## 2026.11.0

- Move Java packages and class references from `ch.ubique.uetlib` to `ch.uetlib`.

### Breaking changes

- Move Java packages from `ch.ubique.backend` to `ch.uetlib`, including class-name resources. The combined OpenRewrite
  migration also renames known Spring configuration keys to `ch.uetlib.*`.
- Remove the inherited Ubique Artifactory repository and deployment destination; private consumers must configure their
  own registry.
- Add Apache-2.0 licensing for original code, preserve third-party licenses, and add public project metadata and
  contribution/security guidance.

- Move Maven coordinates from `ch.ubique:uetlib-*` to `ch.uetlib:uetlib-*`.
- Align uetlib parent, BOM and library references with the migration releases.

# 2026.10.1

- Enable Error Prone checks for incompatible collection and equality types, ignored return values, `equals`/`hashCode`,
  array comparisons, primitive arrays passed to `Arrays.asList`, `compareTo`, dead exceptions, and format strings.
  Enable `ReferenceEquality` and `FutureReturnValueIgnored` as warnings. Exclude generated sources from these checks.

# 2026.10.0

- `uetlib-bom` updated to
  `2026.10.0`: [Changelog/2026.10.0](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#2026100) [Diff/2026.9.1-2026.10.0](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.9.1...v2026.10.0)
- Update `spotless-maven-plugin` to `3.10.3`, which supports Java 27
- Version Updates

# 2026.9.3

- Activate `spotless-maven-plugin` in `plugins`, not just declare it in `pluginManagement`

# 2026.9.2

- `uetlib-bom` updated to
  `2026.9.1`: [Changelog/2026.9.1](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202691) [Diff/2026.9.0-2026.9.1](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.9.0...v2026.9.1)
- Update `spotless`, `nullaway` and `kotlin`

# 2026.9.1

- add `uetlib-cores` annotations `NullOrNotBlank` and `NullOrNotEmpty` as custom nullable annotations

### Migration

After the migration releases and `uetlib-rewrite` are published, run this from the consuming project, then review
the diff and run its tests:

```sh
mvn -U org.openrewrite.maven:rewrite-maven-plugin:6.46.1:run \
  -Drewrite.recipeArtifactCoordinates=ch.uetlib:uetlib-rewrite:RELEASE \
  -Drewrite.activeRecipes=ch.uetlib.MigrateToPublicUetlib
```

The recipe updates Maven coordinates/versions, Java references and known class-name resources. Review application-owned
packages under the old namespace, Kotlin, reflection patterns, native-access module flags and persisted class names
separately. Use `:dryRun` instead of `:run` to preview a patch.

## 2026.9.0

- `uetlib-bom` updated to
  `2026.9.0`: [Changelog/2026.9.0](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202680) [Diff/2026.8.3-2026.9.0](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.8.3...v2026.9.0)
- Fix `sonar.coverage.jacoco.xmlReportPaths` for single-module projects: `sonar.coverage.module` now defaults to `.`
  (the root of the Maven build) instead of `${project.artifactId}`, which resolved to `<root>/<artifactId>/target/...`
  and made Sonar report *"No coverage report can be found"*. Multi-module projects are unaffected: they keep overriding
  `sonar.coverage.module` with their dedicated `{{project}}-coverage` module.
- Updated `nullaway`, `spotless` and `hibernate-orm-plugin`

## 2026.8.3

- Update `de.westemeyer:artifact-version-maven-plugin` to `3.0.0`

## 2026.8.2

- Add `org:jspecify:jspecify` for activation of NullMarked in `de.westemeyer:artifact-version-maven-plugin`

## 2026.8.1

- `spring-boot-dependencies` updated to `4.1.1`
- `uetlib-bom` updated to
  `2026.8.3`: [Changelog/2026.8.3](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202683) [Diff/2026.8.2-2026.8.3](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.8.2...v2026.8.3)
- Update `de.westemeyer:artifact-version-maven-plugin` to `2.1.0`, wich is fully null-marked. Property
  `westemeyer-version-package-name` is not longer used and can be removed.
- Version updates

## 2026.8.0

- Java 25 required
- `uetlib-bom` updated to
  `2026.8.0`: [Changelog/2026.8.0](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202680) [Diff/2026.7.5-2026.8.0](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.7.5...v2026.8.0)

## 2026.7.6

- updated actions to not run tests twice for sonar
- `uetlib-bom` updated to
  `2026.7.5`: [Changelog/2026.7.5](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202675) [Diff/2026.7.4-2026.7.5](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.7.4...v2026.7.5)

## 2026.7.5

- hard-code null-marking level to ERROR, no chickening out for uetlib
- Configure `spotless` with `ktfmt` for Kotlin
- `uetlib-bom` updated to
  `2026.7.4`: [Changelog/2026.7.4](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202674) [Diff/2026.7.3-2026.7.4](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.7.3...v2026.7.4)

## 2026.7.4

- `uetlib-bom` updated to
  `2026.7.3`: [Changelog/2026.7.3](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202673) [Diff/2026.06.0-2026.7.3](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.06.0...v2026.7.3)
- Update dependencies, plugins and actions

## 2026.07.3

- Remove accidental inclusion of uetlib-core in annotation processor paths

## 2026.07.2

- Add back sonar properties
- Auto-apply spotless on `mvn install` locally but not on `mvn valdiate` on CI

## 2026.07.1

- Add `spotless`: Run with `mvn spotless:apply`. See
  also [README.md](README.md#git-pre-commit-hook-format-with-spotless)

## 2026.07.0

- Make `XepExcludedPaths` configurable with property `error-prone-excluded-paths`
- Add `maven-javadoc-plugin`

## 2026.06.1

- Update `uetlib-bom` to
  `2026.06.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#2026060)
- Update to Spring Boot 4.1 (with Spring Cloud 2025.1.2 and Spring Integration 7.1.0)
- Latest dependencies

## 2026.06.0

- Explicit null marking is now enforced by default. When using this as a parent, either make sure to mark everything
  with jspecify or configure a lower marking level, e.g.:
  ```xml
  <explicit-null-marking-level>WARN</explicit-null-marking-level>
  ```
- Newest minor version for `org.hibernate.orm:hibernate-maven-plugin`
- Newest patch version for `org.apache.maven.plugins:maven-surefire-plugin`

## 2026.05.0

- Updated dependencies
- Updated to Spring Boot 4.0.6
- Updated to uetlib BOM 2026.4.0
- Added property to set the artifact package name for westemeryer so you can create a
  `package-info.java` for null-marking.
  ```xml
  <westemeyer-version-artifact-package-name>ch.your.project.version</westemeyer-version-artifact-package-name>
  ```

  ```java
  @NullMarked
  package ch.your.project.version;
  
  import org.jspecify.annotations.NullMarked;
  ```

## 2026.3.0

- Added nullaway step to maven-compiler-plugin. If your module is fully annotated, add the following maven property to
  enforce explicit null marking:
  ```xml
  <explicit-null-marking-level>ERROR</explicit-null-marking-level>
  ```

## 2026.2.0

- Update de.westemeyer:artifact-version-maven-plugin to v2 for compatibility with de.westemeyer:
  artifact-version-service v2
- uetlib-bom 2026.2.0
- Spring Boot 4.0.3
- other upgrades

## 2026.0.0

We adopt Calendar versioning (CalVer) `YYYY.MM.PATCH`

### Version Upgrades

- Upgrade to Spring Boot 4.0.0
- Upgrade to Spring Cloud 2025.1.0 for Spring Boot 4 support

## 1.3.0

- Latest `uetlib-bom` and fix ordering in dependency management

## 1.2.6

### Improvements

- Renovate version updates

## 1.2.5

### Improvements

- Add `kotlin-maven-plugin`

## 1.2.4

### Improvements

- Renovate version updates

## 1.2.3

### Improvements

- Renovate version updates

## 1.2.2

### Improvements

- Renovate version updates

## 1.2.1

### Improvements

- Latest uetlib dependencies with Spring Boot 3.5 / Spring Cloud 2025.0.0 support

## 1.2.0

Upgrade to Spring Boot 3.5.0 and Spring Cloud 2025.0.0

## 1.0.0

First release.
