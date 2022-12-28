#Dependencies

There are many useful packages that can speed up development. Here will be listed the ones that should be included in every project. Keep in mind that some of these packages offer many more features than those described here and you can use them if you have a good reason for that! 

* [beamer](https://pub.dev/packages/beamer) is our preferred library for navigation, alternatives are go_router and auto_route libraries.

* [dartz](https://pub.dev/packages/dartz) for error handling using Either to express a type of value that can be either an error or an actual return value.

* [hooks_riverpod](https://pub.dev/packages/hooks_riverpod) for state management.

* [intl](https://pub.dev/packages/intl) package for internationalization and localization facilities.

* [build_runner](https://pub.dev/packages/build_runner) is a build system for Dart code generation and modular compilation. In other words, a tool that invokes the code-generating code used to generate the repetitive and boilerplate code. 

* [json_serializable](https://pub.dev/packages/json_serializable) for generating JSON serialization/deserialization code.

* [dio](https://pub.dev/packages/dio) rich http client for easier communication with remote servers or APIs, supports Interceptors, Global configuration, FormData, Request Cancellation, File Downloading, Timeout etc.

* [retrofit](https://pub.dev/packages/retrofit) is a dio client generator. It manages the process of receiving, sending, and creating HTTP requests and responses.

* [freezed](https://pub.dev/packages/freezed) for creation of a union/sealed class. Very convenient when defining multiple states for notifiers. 

* [equatable](https://pub.dev/packages/equatable) for creating entities and models for the desired feature with properties, copyWith and equatable.

* [flutter_flavorizr](https://pub.dev/packages/flutter_flavorizr) used to create flavors. Allows you to quickly configure and define dynamic variables for each flavor in your project.

* [state_notifier_test](https://pub.dev/packages/state_notifier_test) used to easily write unit tests for riverpod's state_notifier subclasses

* [mockito](https://pub.dev/packages/mockito) used for the creation of mocks. Enables the tester to remove external dependencies from a test case by mocking them out.

* [dart_code_metrics](https://pub.dev/packages/dart_code_metrics) is a static analysis tool that helps you analyze and improve your code quality.

* [pretty_dio_logger](https://pub.dev/packages/pretty_dio_logger) is dio interceptor that logs network calls in a pretty, easy-to-read format.

* [sentry_flutter](https://pub.dev/packages/sentry_flutter) used for crash reporting.

* [logger](https://pub.dev/packages/logger) used for debug and info logging to a console with many options (e.g. to enable logging only in debug mode or non production environments)
