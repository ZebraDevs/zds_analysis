To use the lints, add as a dev dependency in your `pubspec.yaml`:

```yaml
dev_dependencies:
  zds_analysis: ^1.0.0
```

Then, add an include in `analysis_options.yaml`:

```yaml
include: package:zds_analysis/analysis_options.yaml
```

This will ensure you always use the latest version of the lints.

Our versions follow the Dart SDK versions. If you wish to restrict the lint version, specify a version of `analysis_options.yaml`.
For example, for projects using Dark SDK versions 2.18.x:

```yaml
include: package:zds_analysis/analysis_options.2.18.yaml
```

For strict typed rules, use:

```yaml
include: package:zds_analysis/analysis_options_strict.yaml
```

Or, specific version:

```yaml
include: package:zds_analysis/analysis_options_strict.2.18.yaml
```

For library specific lints (not for use in applications):

```yaml
include: package:zds_analysis/analysis_options_lib.yaml
```
