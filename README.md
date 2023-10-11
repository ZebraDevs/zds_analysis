# ZDS Analysis

This package provides lint rules for Dart and Flutter which are used at Zebra Technologies Corporation.

**Note**: This package was heavily inspired by both [Very Good Analysis](https://pub.dev/packages/very_good_analysis) and [RydMike](https://rydmike.com/blog_flutter_linting.html).

## Usage

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

## Suppressing Lints

There may be cases where specific lint rules are undesirable. Lint rules can be suppressed at the line, file, or project level.

An example use case for suppressing lint rules at the file level is suppressing the `prefer_const_constructors` in order to achieve 100% code coverage. This is due to the fact that const constructors are executed before the tests are run, resulting in no coverage collection.

### Line Level

To suppress a specific lint rule for a specific line of code, use an `ignore` comment directly above the line:

```dart
// ignore: public_member_api_docs
class A {}
```

### File Level

To suppress a specific lint rule of a specific file, use an `ignore_for_file` comment at the top of the file:

```dart
// ignore_for_file: public_member_api_docs

class A {}

class B {}
```

### Project Level

To suppress a specific lint rule for an entire project, modify `analysis_options.yaml`:

```yaml
include: package:zds_analysis/analysis_options.yaml
linter:
  rules:
    public_member_api_docs: false
```
