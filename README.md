# flutter_first
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  return runApp(
    MaterialApp(
        home: Scaffold(
          backgroundColor: Colors.deepOrange,
          appBar: AppBar(
            title: Text(
              'Application',
              style: TextStyle(
                  color: Colors.white,
                  fontFamily: 'Lora',
                  fontSize: 30.0
              ),
            ),
            backgroundColor: Colors.orangeAccent,
          ),
          body: Center(
            child: DicePage(),
          ),
        )
    ),
  );
}

class DicePage extends StatefulWidget {
  @override
  _DicePageState createState() => _DicePageState();
}

class _DicePageState extends State<DicePage> {
  int leftDiceNumber = 1;

  void changeDiceFace(){
    setState(() {
      leftDiceNumber = Random(). nextInt(3) + 1;
    });
  }

  @override
  Widget build(BuildContext context) {


    return Center(
      child: Row(
        children: <Widget>[
          Expanded(
            child: Padding(
              padding: const EdgeInsets.all(26.0),
              child: TextButton(
                onPressed: (){
                  changeDiceFace();
                },
                child: Image.asset('images/pic1$leftDiceNumber.jpg'),
              ),
            ),
            flex: 15,
          ),
        ],
      ),
    );
  }
}




