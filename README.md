# plp-week-4-dart-assignment
import 'dart:io';
import 'dart:convert';

void main() {
  // ** String Manipulation **
  String input = "Hello, Dart!";
  String reversed = input.split('').reversed.join('');
  String upperCase = input.toUpperCase();
  String lowerCase = input.toLowerCase();
  print("Original: $input");
  print("Reversed: $reversed");
  print("Uppercase: $upperCase");
  print("Lowercase: $lowerCase");

  // ** Collections **
  List<int> numbers = [1, 2, 3, 4, 5];
  Set<String> uniqueWords = {"Dart", "Flutter", "Dart"};
  Map<String, int> wordCount = {"Dart": 2, "Flutter": 1};
  print("\nList: $numbers");
  print("Set (Unique): $uniqueWords");
  print("Map (Word Count): $wordCount");

  // ** File Handling **
  String filePath = "sample.txt";
  String outputFilePath = "output.txt";
  try {
    File file = File(filePath);
    if (!file.existsSync()) {
      file.writeAsStringSync("This is a sample file with Dart!");
    }
    String content = file.readAsStringSync();
    File outputFile = File(outputFilePath);
    outputFile.writeAsStringSync("Reversed Content: ${content.split('').reversed.join('')}");
    print("\nFile Read and Written Successfully!");
  } catch (e) {
    print("Error Handling File: $e");
  }

  // ** Date and Time **
  DateTime now = DateTime.now();
  DateTime future = now.add(Duration(days: 5, hours: 2));
  Duration difference = future.difference(now);
  print("\nCurrent Date and Time: $now");
  print("Future Date and Time: $future");
  print("Difference: ${difference.inDays} days and ${difference.inHours % 24} hours.");
}
