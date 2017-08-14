# iTextPdfTest
A project to demonstrate an issue seen in dex2jar.

This project utilizes iTextPdf <http://itextpdf.com/>.

Steps to reproduce issue:

1.  Compile the project `gradlew clean build`
2.  Use dex2jar to convert the apk to dex: `d2j-dex2jar.sh app/build/outputs/apk/app-debug.apk`
3.  Use dex2jar to convert the jar to dex: `d2j-jar2dex.sh app-debug-dex2jar.jar`

You will see an error like the following:

```
EXCEPTION FROM SIMULATION:
expected type int[] but found float[]

...at bytecode offset 00000117
locals[0000]: Lcom/itextpdf/text/pdf/PdfDeviceNColor;
locals[0001]: Lcom/itextpdf/text/pdf/PdfWriter;
locals[0002]: <invalid>
locals[0003]: <invalid>
locals[0004]: <invalid>
locals[0005]: <invalid>
locals[0006]: <invalid>
locals[0007]: <invalid>
locals[0008]: I
locals[0009]: <invalid>
locals[000a]: I
locals[000b]: string{""}
locals[000c]: Lcom/itextpdf/text/pdf/PdfArray;
locals[000d]: Lcom/itextpdf/text/pdf/PdfArray;
locals[000e]: Lcom/itextpdf/text/pdf/PdfDictionary;
locals[000f]: [F
locals[0010]: [[F
locals[0011]: Lcom/itextpdf/text/BaseColor;
...while working on block 0114
...while working on method getPdfObject:(Lcom/itextpdf/text/pdf/PdfWriter;)Lcom/itextpdf/text/pdf/PdfObject;
...while processing getPdfObject (Lcom/itextpdf/text/pdf/PdfWriter;)Lcom/itextpdf/text/pdf/PdfObject;
...while processing com/itextpdf/text/pdf/PdfDeviceNColor.class

1 error; aborting
``` 
