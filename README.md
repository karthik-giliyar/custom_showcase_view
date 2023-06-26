<!-- 
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages). 

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages). 
-->

The CustomShowCaseView Flutter package allows you to create custom showcase views with flexible designs for highlighting specific widgets and providing informative popups. With this package, you have the freedom to design your own showcase views according to your requirements.

## Features

1. Highlight and showcase specific widgets in your app.
2. Customize the design of the showcase view.
3. Display a popup above or below the highlighted widget.
4. Provide information and details about the widget.
5. Control the visibility of the showcase view.
6. Specify the dimensions of the showcase view.
7. Customize the background color and transparency.
8. Enable or disable background clicks outside the popup.
9. Use a triangular pointer indicator to highlight the widget.

## Getting started

To start using the CustomShowCaseView package, make sure you have Flutter installed. You can find more information on how to install Flutter at flutter.dev. Once Flutter is set up, you can add the package to your project by adding it as a dependency in your pubspec.yaml file:


dependencies:
  custom_show_case_view: ^0.0.1

For more information on how to use packages in Flutter, refer to the Flutter Packages Documentation.  


## Usage

Here's an example of how you can use the CustomShowCaseView package in your Flutter app:

```dart
import 'package:flutter/material.dart';
import 'package:custom_show_case_view/custom_show_case_view.dart';

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  bool show = true;

  final GlobalKey<State<StatefulWidget>> widgetKeyOne = GlobalKey();

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Custom Showcase View Example'),
        ),
        body: CustomShowCaseView(
          globalKey: widgetKeyOne,
          show: show,
          height: 100,
          width: 300,
          pointerIndicatorColor: Colors.blue,
          overlayBackground: Colors.black.withOpacity(0.25),
          enableBackgroundClick: false,
          customShowCase: InkWell(
            onTap: () {
              setState(() {
                show = false;
              });
            },
            child: Container(
              height: 100,
              width: 300,
              padding: const EdgeInsets.fromLTRB(16, 8, 16, 8),
              decoration: BoxDecoration(
                color: Colors.blue,
                borderRadius: BorderRadius.circular(12),
              ),
              child: Column(
                mainAxisAlignment: MainAxisAlignment.spaceAround,
                crossAxisAlignment: CrossAxisAlignment.center,
                children: [
                  const Text(
                    "This is a Custom Container",
                    style: TextStyle(color: Colors.white, fontSize: 14),
                  ),
                  Row(
                    mainAxisAlignment: MainAxisAlignment.spaceAround,
                    crossAxisAlignment: CrossAxisAlignment.center,
                    children: const [
                      Text(
                        "Done",
                        style: TextStyle(color: Colors.white, fontSize: 14),
                      ),
                      Expanded(child: SizedBox()),
                      Icon(
                        Icons.close,
                        color: Colors.white,
                      ),
                      SizedBox(
                        width: 12,
                      ),
                      Icon(
                        Icons.done,
                        color: Colors.white,
                      ),
                    ],
                  )
                ],
              ),
            ),
          ),
          child: Text(
            "Custom Showcase",
            key: widgetKeyOne,
          ),
        ),
      ),
    );
  }
}
```

For more detailed examples, check the /example folder in the CustomShowCaseView GitHub repository.

## Additional information

Feel free to explore and customize the CustomShowCaseView package to suit your needs. We hope this package enhances your app's user experience by providing interactive and informative showcases for your widgets.
