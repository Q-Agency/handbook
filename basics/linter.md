#Linter
In your IDE turn on "Format code on save" and "Organise imports on save" to make sure that your code is well-structured and your imports are organised in almost any moment. Also, set you line length to 80.
To make sure our code follows some good practices and recommendations, we use **flutter_lints** and **dart_code_metrics** packages and their rules which we fine tune in analysis_options.yaml file.

First, here are some main **flutter_lints** rules we use are using and then we will go through useful **dart_code_metrics** rules as well:
* prefer_single_quotes: using single ' quote instead of double " quote in the whole project to have consistency
* avoid_print: use logger methods for logging instead
* sized_box_for_whitespace: use SizedBox instead of Container if you only need width or height
* parameter_assignments: avoid assigning new values to parameters of methods or functions
* avoid_relative_lib_imports: avoid relative imports for files in lib/

Useful dart_code_metrics rules:
* avoid-returning-widgets: this is performance related rule, it is always better to create new widget than returning a widget from the method
* member-ordering:\
   order:
   - public-fields
   - private-fields
   - constructors
   - public-methods
   - private-methods\
   to have clear ordering in each class, public and private fields on the top, then constructors and on the bottom public and private methods
* prefer-trailing-comma: in helps in formatting the code when adding comma after the last parameter, exception is if everything can be displayed in a single line
* prefer-match-file-name:\
  exclude:
  - "**/main.dart"\
  to make it easier finding certain class you are looking for
  