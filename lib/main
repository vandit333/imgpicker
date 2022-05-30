import 'dart:io';

import 'package:flutter/material.dart';
import 'package:image_picker/image_picker.dart';

void main() {
  runApp(MaterialApp(home: imgpicker(),));
}
class imgpicker extends StatefulWidget {

  @override
  _imgpickerState createState() => _imgpickerState();
}
class _imgpickerState extends State<imgpicker> {

  final ImagePicker _picker = ImagePicker();
  String imageparth="";
  bool imagestatus=false;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(),
      body: Column(
        children: [
        InkWell(
          onTap: () {
            showDialog(context: context, builder: (context) {
              return SimpleDialog(
                title: Text("Select your choice"),
                children: [
                  ListTile(
                    leading: Icon(Icons.camera_alt),
                    title: Text("camera"),
                    onTap: () async {
                      Navigator.pop(context);
                      final XFile? photo = await _picker.pickImage(source: ImageSource.camera);
                      if(photo!=null)
                        {
                          imageparth =photo.path;
                          imagestatus=true;
                        }
                      else
                        {
                          imagestatus=false;
                        }
                      setState(() {
                      });
                    },
                  ),
                  ListTile(
                    leading: Icon(Icons.camera_alt),
                    title: Text("gallery"),
                    onTap: () async {
                      Navigator.pop(context);
                      final XFile? image = await _picker.pickImage(source: ImageSource.gallery);
                      if(image!=null)
                      {
                        imageparth =image.path;
                        imagestatus=true;
                      }
                      else
                      {
                        imagestatus=false;
                      }
                      setState(() {
                      });
                    },
                  ),
                ],
              );
            },);
          },
          child: Container(
            height: 200,
            width: 200,
            child: imagestatus?
            Image.file(File(imageparth),
              height: 100,
              width: 100,
            ):Icon(Icons.photo,size: 50,)
          ),
        )
        ],
      ),
    );
  }
}
