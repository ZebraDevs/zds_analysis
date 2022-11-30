# Zebra Technologies Corporation

<details>
    <summary>Zebra Repository Information</summary>
    <ul>
        <li> Zebra Business Unit : ZTM  </li>
        <li> Zebra Manager : aw7799 </li>
        <li> Zebra Repo Admin: as3228 </li>
        <li> Zebra Jira Project ID: TM  </li>
        <li> Product: MyWork </li>
        <li> Topics: no_codeql </li>
    </ul>
</details>

This package provides lint rules for Dart and Flutter which are used at Zebra Technologies Corporation.

**Note**: This package was heavily inspired by [very_good_analysis][https://pub.dev/packages/very_good_analysis].

## Usage

To use the lints, add as a dev dependency in your `pubspec.yaml`:

```yaml
dev_dependencies:
  ztmf_analysis: ^1.0.0
```

Then, add an include in `analysis_options.yaml`:

```yaml
include: package:ztmf_analysis/analysis_options.yaml
```

This will ensure you always use the latest version of the lints. If you wish to restrict the lint version, specify a version of `analysis_options.yaml` instead:

```yaml
include: package:ztmf_analysis/analysis_options.3.1.0.yaml
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
include: package:ztmf_analysis/analysis_options.yaml
linter:
  rules:
    public_member_api_docs: false
```