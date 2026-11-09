# Uetlib Parent

Bill of Materials maven POM for uetlib libraries.

## Using

### As parent

You can use this artifact as parent for your maven project. 
This will set the dependency management, plugin management and set some basic maven properties. 
You can use it as following:

```xml
<parent>
    <groupId>ch.uetlib</groupId>
    <artifactId>uetlib-parent</artifactId>
    <version>2026.11.0</version>
</parent>
```

To set up sonar cloud with coverage reports, add the following to your properties:

```xml
<properties>
    <sonar.projectName>my-project</sonar.projectName>
    <sonar.coverage.module>my-project-coverage</sonar.coverage.module>
</properties>
```

## Changelog

See [CHANGELOG.md](CHANGELOG.md)

## Git pre-commit hook (format with spotless)

To automatically format code before each commit, run this once from the repository root:

```bash
mkdir -p .git/hooks && cat > .git/hooks/pre-commit <<'EOF'
#!/bin/sh
mvn spotless:apply
EOF
chmod +x .git/hooks/pre-commit

## License

Except where otherwise noted, original uetlib code is licensed under the [Apache License 2.0](LICENSE). Third-party files retain their original license terms; see [NOTICE](NOTICE) and any third-party notices in this repository.

## Publishing and license metadata

This parent has no default deployment destination. Consuming projects must configure their own publishing destination, such as an internal registry. Maven Central publishing is invoked explicitly by uetlib release workflows. The parent's Apache-2.0 metadata describes this parent; inheriting it does not license your application. Applications should declare their own project/license metadata rather than relying on inherited library metadata.
