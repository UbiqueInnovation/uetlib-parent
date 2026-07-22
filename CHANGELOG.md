# CHANGELOG

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

- Explicit null marking is now enforced by default. When using this as a parent, either make sure to
  mark everything with jspecify or configure a lower marking level, e.g.:
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
  `package-info.java` for
  null-marking.
  ```xml
  <westemeyer-version-artifact-package-name>ch.your.project.version</westemeyer-version-artifact-package-name>
  ```

  ```java
  @NullMarked
  package ch.your.project.version;
  
  import org.jspecify.annotations.NullMarked;
  ```

## 2026.3.0

- Added nullaway step to maven-compiler-plugin. If your module is fully annotated, add the following
  maven property to enforce explicit null marking:
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