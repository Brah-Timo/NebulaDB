
# 🧠 NebulaDB

 ⚡ Lightweight embedded SQL database engine written in pure Dart

<img width="256" height="256" alt="Sans titre" src="https://github.com/user-attachments/assets/a35cd42b-e39b-4099-bde0-6af49912b904" />


[![pub.dev](https://img.shields.io/pub/v/nebula_db.svg?style=flat-square)](https://pub.dev/packages/nebula_db)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](LICENSE)
[![Dart](https://img.shields.io/badge/dart-%3E%3D3.0.0-0175C2?style=flat-square)](https://dart.dev)

---

## 🚀 Overview

**NebulaDB** is a lightweight, embedded relational database engine built entirely in Dart.

It provides a full SQL execution pipeline with persistent storage and Write-Ahead Logging (WAL).

---

## ✨ Features

- SQL parser & executor  
- WHERE / JOIN / GROUP BY  
- B-Tree indexing  
- Page-based storage (4KB)  
- WAL + crash recovery  
- Basic transactions  

---

## 📦 Installation

```bash
dart pub add nebula_db
````

---

## ⚡ Quick Example

```dart
import 'nebula_db.dart';

void main() async {
  final db = await NebulaDB.open('./my_db');

  await db.execute('''
    CREATE TABLE users (
      id INT,
      name TEXT,
      age INT
    )
  ''');

  await db.execute("INSERT INTO users VALUES (1, 'Ahmed', 25)");

  final result = await db.execute('SELECT * FROM users');
  result.prettyPrint();

  await db.close();
}
```

---

## 🎯 Use Cases

* Flutter apps (offline-first)
* Embedded/local databases
* Learning database internals

---

## ⚠️ Limitations

* Single-process only
* No advanced concurrency yet
* Not designed for large-scale production

---

## 🧪 Testing

```bash
dart test
```

---

## 📄 License

MIT License



---
