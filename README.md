# dipoc

An http request POC Flutter project.

## Getting Started

# Dependencies needed

- dio: ^4.0.4 or higger
- json_serializable: ^6.1.5 or higger

# Auto generating .g classes

- Make sure you have build_runner as a dev_dependency
- add this boilerplate code to your model class:
  - as an import part '[classname].g.dart';
  - @JsonSerializable() as a class annotattion
  - @JsonKey(name: "[property_name]") as property annotation, example:
    @JsonKey(name: "data")
    late User user;
  - the following block of code:
    factory [ClassName].fromJson(Map<String, dynamic> json) =>
    _$S[ClassName]FromJson(json);
    Map<String, dynamic> toJson() => _$[ClassName]ToJson(this);
- After that run this command in a terminal:
  flutter pub run build_runner build
  This will auto generate your json parsing code
