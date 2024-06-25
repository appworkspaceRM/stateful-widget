# flutter_application_11

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

# Stateful

penggunaan stateful pada flutter salah satu widget yang dapat melakukan perubahan atau interactive UI. perubahan tampilan yang tidak dapat dilakukan oleh stateless maka class stateful dapat melakukan perubahan sebuah UI sesuai dengan kondisi tertentu. untuk merubah tampilan harus memberitahu pada UI stateful dengan menggunakan sebuah fungsi setState untuk merender ualng sebuah tampilan.

```dart
(){
	setState(){
		function()
	}
}
```

```dart
import 'package:flutter/material.dart';

void main(List<String> args) {
  runApp(MyApp());
}

class MyApp extends StatefulWidget {
  MyApp({super.key});

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  int counter = 1;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.grey.shade300,
        appBar: AppBar(
          title: const Text(
            "Stateful",
          ),
        ),
        body: Column(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: [
            Text(
              "$counter",
              style: TextStyle(
                fontSize: 20 + double.parse(counter.toString()),
              ),
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      if (counter != 1) {
                        counter--;
                      } else if (counter == 1) {
                        return;
                      }
                    });
                  },
                  child: Icon(
                    Icons.remove,
                  ),
                ),
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      counter++;
                    });
                  },
                  child: Icon(
                    Icons.add,
                  ),
                )
              ],
            )
          ],
        ),
      ),
    );
  }
}
```
![code-snapshot](https://github.com/appworkspaceRM/stateful-widget/assets/135511281/1369456d-db94-46c0-a9e3-4f2c78869c63)


