import 'package:flutter/material.dart';
import 'screens/language_selector.dart';

void main() {
  runApp(LingoFlashApp());
}

class LingoFlashApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'LingoFlash',
      theme: ThemeData(primarySwatch: Colors.indigo),
      home: LanguageSelector(),
      debugShowCheckedModeBanner: false,
    );
  }
}
import 'package:flutter/material.dart';
import 'spanish_home.dart';
import 'italian_home.dart';

class LanguageSelector extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('LingoFlash - اختر اللغة')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton.icon(
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (_) => SpanishHome()),
                );
              },
              icon: Icon(Icons.language),
              label: Text('الإسبانية'),
            ),
            SizedBox(height: 20),
            ElevatedButton.icon(
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (_) => ItalianHome()),
                );
              },
              icon: Icon(Icons.language),
              label: Text('الإيطالية'),
            ),
          ],
        ),
      ),
    );
  }
}
import 'package:flutter/material.dart';

class SpanishHome extends StatelessWidget {
  final List<Map<String, String>> words = [
    {'es': 'Hola', 'ar': 'مرحبا'},
    {'es': 'Gracias', 'ar': 'شكرا'},
    {'es': 'Por favor', 'ar': 'من فضلك'},
    {'es': 'Adiós', 'ar': 'وداعا'},
    {'es': 'Agua', 'ar': 'ماء'},
    {'es': 'Comida', 'ar': 'طعام'},
    {'es': 'Casa', 'ar': 'منزل'},
    {'es': 'Escuela', 'ar': 'مدرسة'},
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('الإسبانية')),
      body: ListView.builder(
        itemCount: words.length,
        itemBuilder: (context, index) {
          final word = words[index];
          return ListTile(
            title: Text(word['es']!, style: TextStyle(fontSize: 20)),
            subtitle: Text(word['ar']!, style: TextStyle(fontSize: 16)),
          );
        },
      ),
    );
  }
}
import 'package:flutter/material.dart';

class ItalianHome extends StatelessWidget {
  final List<Map<String, String>> words = [
    {'it': 'Ciao', 'ar': 'مرحبا'},
    {'it': 'Grazie', 'ar': 'شكرا'},
    {'it': 'Per favore', 'ar': 'من فضلك'},
    {'it': 'Arrivederci', 'ar': 'وداعا'},
    {'it': 'Acqua', 'ar': 'ماء'},
    {'it': 'Cibo', 'ar': 'طعام'},
    {'it': 'Casa', 'ar': 'منزل'},
    {'it': 'Scuola', 'ar': 'مدرسة'},
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('الإيطالية')),
      body: ListView.builder(
        itemCount: words.length,
        itemBuilder: (context, index) {
          final word = words[index];
          return ListTile(
            title: Text(word['it']!, style: TextStyle(fontSize: 20)),
            subtitle: Text(word['ar']!, style: TextStyle(fontSize: 16)),
          );
        },
      ),
    );
  }
}
name: lingoflash
description: A language learning app for Spanish and Italian.
version: 1.0.0+1

environment:
  sdk: ">=2.12.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter

flutter:
  uses-material-design: true
