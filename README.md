# flutter_alert_dialog

|<img src="/preview/preview1.png" width="300"/>|<img src="/preview/preview2.png" width="300"/>|<img src="/preview/preview3.png" width="300"/>|
|--|--|--|

```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  static const String _title = 'Flutter Code Sample';

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: _title,
      home: Scaffold(
        appBar: AppBar(title: const Text(_title)),
        body: const Center(
          child: MyStatelessWidget(),
        ),
      ),
    );
  }
}

class MyStatelessWidget extends StatelessWidget {
  const MyStatelessWidget({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      crossAxisAlignment: CrossAxisAlignment.center,
      children: [
        TextButton(
          onPressed: () => showDialog<String>(
            context: context,
            builder: (BuildContext context) => buildAlertDialog(context),
          ),
          child: const Text('Show Dialog'),
        ),
        TextButton(
          onPressed: () => showDialog<String>(
            context: context,
            builder: (BuildContext context) => buildAlertDialogV2(context),
          ),
          child: const Text('Show Dialog Bottom'),
        ),
      ],
    );
  }

  //Show Dialog
  AlertDialog buildAlertDialog(BuildContext context) {
    return AlertDialog(
      title: const Text('AlertDialog Title'),
      content: const Text('AlertDialog description'),
      actions: <Widget>[
        TextButton(
          onPressed: () => Navigator.pop(context, 'Cancel'),
          child: const Text('Cancel'),
        ),
        TextButton(
          onPressed: () => Navigator.pop(context, 'OK'),
          child: const Text('OK'),
        ),
      ],
    );
  }

  //Show Dialog Bottom
  AlertDialog buildAlertDialogV2(BuildContext context) {
    return AlertDialog(
      backgroundColor: Colors.transparent,
      contentPadding: EdgeInsets.zero,
      elevation: 0.0,
      // title: Center(child: Text("Evaluation our APP")),
      content: Column(
        mainAxisAlignment: MainAxisAlignment.end,
        children: [
          Container(
            padding: const EdgeInsets.all(8.0),
            decoration: const BoxDecoration(
              color: Colors.white,
              borderRadius: BorderRadius.all(
                Radius.circular(10.0),
              ),
            ),
            child: Column(
              children: const [
                Text('AlertDialog Title'),
                Divider(),
                Text('AlertDialog description'),
              ],
            ),
          ),
          const SizedBox(
            height: 10,
          ),
          Container(
            padding: const EdgeInsets.all(8.0),
            decoration: const BoxDecoration(
              color: Colors.white,
              borderRadius: BorderRadius.all(
                Radius.circular(10.0),
              ),
            ),
            child: Row(
              mainAxisAlignment: MainAxisAlignment.end,
              crossAxisAlignment: CrossAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: () => Navigator.pop(context, 'Cancel'),
                  child: const Text('Cancel'),
                ),
                SizedBox(width: 10,),
                ElevatedButton(
                  onPressed: () => Navigator.pop(context, 'OK'),
                  child: const Text('OK'),
                ),
              ],
            ),
          )
        ],
      ),
    );
  }
}
```

---

```
Copyright 2022 M. Fadli Zein
```