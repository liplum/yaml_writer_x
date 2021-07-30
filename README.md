# yaml_writer

[![pub package](https://img.shields.io/pub/v/yaml_writer.svg?logo=dart&logoColor=00b9fc)](https://pub.dartlang.org/packages/yaml_writer)
[![Null Safety](https://img.shields.io/badge/null-safety-brightgreen)](https://dart.dev/null-safety)
[![CI](https://img.shields.io/github/workflow/status/gmpassos/yaml_writer/Dart%20CI/master?logo=github-actions&logoColor=white)](https://github.com/gmpassos/yaml_writer/actions)
[![GitHub Tag](https://img.shields.io/github/v/tag/gmpassos/yaml_writer?logo=git&logoColor=white)](https://github.com/gmpassos/yaml_writer/releases)
[![New Commits](https://img.shields.io/github/commits-since/gmpassos/yaml_writer/latest?logo=git&logoColor=white)](https://github.com/gmpassos/yaml_writer/network)
[![Last Commits](https://img.shields.io/github/last-commit/gmpassos/yaml_writer?logo=git&logoColor=white)](https://github.com/gmpassos/yaml_writer/commits/master)
[![Pull Requests](https://img.shields.io/github/issues-pr/gmpassos/yaml_writer?logo=github&logoColor=white)](https://github.com/gmpassos/yaml_writer/pulls)
[![Code size](https://img.shields.io/github/languages/code-size/gmpassos/yaml_writer?logo=github&logoColor=white)](https://github.com/gmpassos/yaml_writer)
[![License](https://img.shields.io/github/license/gmpassos/yaml_writer?logo=open-source-initiative&logoColor=green)](https://github.com/gmpassos/yaml_writer/blob/master/LICENSE)

A library to write YAML documents.

## Usage

A simple usage example:

```dart
import 'package:yaml_writer/yaml_writer.dart';

void main() {
  var yamlWriter = YAMLWriter();

  var yamlDoc = yamlWriter.write({
    'name': 'Joe',
    'ids': [10, 20, 30],
    'desc': 'This is\na multiline\ntext',
    'enabled': true,
  });

  print(yamlDoc);
}
```

OUTPUT:

```text
name: 'Joe'
ids: 
  - 10
  - 20
  - 30
desc: |-
    This is
    a multiline
    text
enabled: true
```

## YAML Strings

The writer will try to encode strings using the best format depending on the text,
avoiding to escape `"` and using `|` for multiline texts.

## Encoding Objects

You can use `YAMLWriter.toEncodable` to convert an Object to an encodable version,
similar to what is done by `dart:convert` `JsonEncoder`.

If `YAMLWriter.toEncodable` is not set, it will try to call `toJson()`.

## Features and bugs

Please file feature requests and bugs at the [issue tracker][tracker].

[tracker]: https://github.com/gmpassos/yaml_writer/issues


## Author

Graciliano M. Passos: [gmpassos@GitHub][github].

[github]: https://github.com/gmpassos

## License

Dart free & open-source [license](https://github.com/dart-lang/stagehand/blob/master/LICENSE).
