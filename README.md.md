# Flutter Utils
Flutter Development Helper Classes for improving code structure.

<h4> Flutter ViewState Template </h4>

This is android studio file template to separate UI and Code. If we manage UI and Code in single file it gets really messy in large projects and it makes difficult to navigate to file structure.

We will create two files Screen and Controller to represent UI and code. To create template file go to Android Studio ***Settings > Editor > File and Code Templates > Create Template*** 

**Screen Template**

Name: Flutter ViewState
Extension: dart
File Name: ${NAME}_screen

    #set($class = ${NAME})
    #set( $nameparts = $NAME.split("_"))
    #set( $namepart = '')
    #set( $classname = '')
    #foreach( $namepart in $nameparts )
        #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
    #end
    
    part '${NAME}_controller.dart';
    
    class ${classname}Screen extends StatefulWidget {
      const ${classname}Screen({Key? key}) : super(key: key);
    
      @override
      createState() => _${classname}Screen();
    }
    
    class _${classname}Screen extends ${classname}Controller {
      @override
      Widget build(BuildContext context) {
        return Container();
      }
    }

**Controller Template**
Create Child Template File from Flutter ViewState 
File Name: ${NAME}_controller
Extension: dart

    #set($class = ${NAME})
    #set( $nameparts = $NAME.split("_"))
    #set( $namepart = '')
    #set( $classname = '')
    #foreach( $namepart in $nameparts )
        #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
    #end
    
    part of '${NAME}_screen.dart';
    
    abstract class ${classname}Controller extends State<${classname}Screen> {
    
      @override
      void initState() {
        // TODO: implement initState
        super.initState();
      }
    
      @override
      void dispose() {
        // TODO: implement dispose
        super.dispose();
      }
    }

We have complete Flutter ViewState template. Now, whenever you try to create file in android studio below Dart File will show new option Flutter ViewState and after selection Flutter ViewState new dart file (user_profile) will create have automatically two files user_profile_screen.dart and user_profile_controller.dart file 
