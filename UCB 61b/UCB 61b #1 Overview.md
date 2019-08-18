weekly time spending: 10 hrs (3hrs video + 4 hrs assignments + 3 hrs reading)

# Record
- Lecture Video: Aug 17th
- Reading: Sierra & Bates, pp. 1–9, 18–19, 84

# Notes
objected-oriented: can identify what class it is and choose/assign relative methods based on the class

## Constructor

*example:*

    String myString;            // step1: delare a variable
    myString = new String();    // step2 & step3: construct emply string, ie. construct an object; and assign it to myString
    myString = "Yow!";          // myString now points to a new String object with data 'Yow!'
  
allowcate a chunck of memory and name it (use a name, which is also stored in a chunck of memory, to reference/ point to it), but it has not initialized with data
- "new string()" is a constructor, or a constructor signature
    
Java programs must be compiled before you run them. \[interpreter language, complier language]
- .java is complied .class (in a lower-level language)
- .class to Java Virtual Machine, and run it, and get the answer

<br/><br/>
*example:*

    String s;
    String s2 = s;            // The constructor well copy what is saved in s. Usually there would be an address, but this time, there is nothing. So nothing copied, s2 points to nothing.
    s = "Yow!"
    - s2 = "Yow!"             // Java may reuse the string which s points to, in the sake of saving memory
    - s2 = new String(s);     // Force Java to create a new object with data "Yow!"

<br/><br/>
3 string constructors:
1. new Stirng() constructs a new, empty string (0 characters)
2. "Yow!"
3. new String(s) takes a parameter s, makes copy of the object that s references
4. and there are more string constructors which share the same constructor name. Which constructor to call depends on the parameters you passed, and the result it returned would vary accordingly.

## Methods
    s2 = s.toUppercase();             // s2 → YOW!
    String s3 = s2.concat("!!");      // s3 = s2 + "!!"; s3 → YOW!!!; no variable was changed, all the methods do is constructing new objects

Strings in Java are immutable. Once they are constucted, you can never change the content. Most Java classes allow changes of their inner field, but String is an exception.

## I/O Classes & Objects
    system.out: a printstream object that outputs to the screen. It references a printstream object
    system.in: an inputstream object that reads from the keyboard.

<br/><br/>
readline is defined on BufferedReader objects

    Q: How do we construct a BufferedReader?      A: with an InputStreamReader
    Q: How do we construct a InputStreamReader?   A: with an InputStream
    Q: How do we construct a InputStream?      A: system.in is one            //Figure all the stuff out via online java libraries API - java.io
    InputStream - read raw data
    InputStreamReader - compose raw data into characters (2 bytes long in Java, 2-byte unicode)
    BufferedReader - composed characters into a line
    
    ##Why 3 parts? Because in that way you can replace a part of them. Input from internet or a file; Character coding
    
<br/><br/>
*coding example*

    import java.io.*;
    class SimpleIO{
        // this class/program reads a line, print the line and then it terminates.
    
        // main method is the FIRST method being executed when you call the class from a Java program
        public static void main(String[] arg) throws Exception{
            BufferedReader keybd = new BufferedReader(new InputStreamReader(new InputStream(System.in)));
            System.out.println(keybd.readLine());
        }
    }

Notice:
- To use Java libraries other than java.lang, you need to "import" them
- java.io includes InputStreamReader, BufferedReader, etc
- Java program always begins at a method called "main"




