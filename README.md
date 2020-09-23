<div align="center">

## Make a companion \(kinda\)


</div>

### Description

Have you ever needed a to hear something from your computer besides that grinding it makes and the humming? MAKE IT TALK!!!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[everlasting](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/everlasting.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Graphics/ Sound](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/graphics-sound__3-15.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/everlasting-make-a-companion-kinda__3-2917/archive/master.zip)





### Source Code

<H3>Introduction</H3>
Programming is basically makeing the computer bow at your every wim. You can make your computer do everything, EVEN TALK! Making your computer speak isnt that hard and you can have it talkin in less than 10 min.
<h3>Download this now!!!</h3>
If you dont your never gonna be able to compile this code. www.microsoft.com/speech
<h3>Finally it begins</h3>
You can make this happen in nearly any computer language. I just so happen to know C++, so thats what I use.
<ol>To begin open Microsoft Visual C++.
<ol>Start a new project, for this tutorial I am making a windows 32 Application. Make a name for it that will make sence for later use (I named mine "tutorialtts")
<ol>Choose the radio button that says "a simple windows 32 application" (the middle one)</ol>
<H4>Coding</h4>
Now that youve got you environment set up, we can begin coding.
The first thing you have to do is open up StdAfx.h there will be a line that says <p>
<textcolor="green">//TODO ADD ADITIONAL HEADERS HERE</text></p>
add the following code on the line that is directly beneath that line
<H7>
<p>#define _ATL_APARTMENT_THREADED</p>
<p>//Dont change anything!!!</p>
<p>#include < atlbase.h></p>
<p>extern CComModule _Module;/<p>
<p>#include < atlcom.h></p>
</H7>
<p>now we need to rely on the compiler to do a job for us.</p>
<p>Under go the the menu "project > Settings". Click on the C++ tag near the top of the dialog box</p>
<p>Choose "Preproccesser" from the drop-down form.
and in the "additional include directories" box add this</p>
<p>C:\Program Files\Microsoft Speech SDK 5.1\Include.</p>
<p>Next go one tab over to the "Link" tab, in the category box choose "Input"
in the first box ("Object/library modules") add sapi.lib.</p>
<p>In the additional library path add</p>
<p>"C:\Program Files\Microsoft Speech SDK 5.1\Lib\i386"</p>
Choose the OK button
<h3>I lied, this is the actual coding part</h3>
Open the file projectname.cpp and add this code
<H7>
<p>#include <stdafx.h>
<p>#include <sapi.h>
<p>int main(int argc, char* argv[])
<p>{
<p> ISpVoice * pVoice = NULL;
<p> if (FAILED(::CoInitialize(NULL)))
<p> return FALSE;</p>
<p> HRESULT hr = CoCreateInstance</p><p>(CLSID_SpVoice, NULL, CLSCTX_ALL, IID_ISpVoice, <(void **)&pVoice);</p>
<p> if( SUCCEEDED( hr ) )</p>
<p> {</p>
<p> hr = pVoice->Speak(L"Hey, I can say what ever you want.", 0, NULL);</p>
<p> // Change pitch</p>
<p> hr = pVoice->Speak(L"My voice can even<pitch middle = '-10'/> drop pitches.", SPF_IS_XML, NULL );</p>
<p> pVoice->Release();</p>
<p> pVoice = NULL;</p>
<p> }</p>
<p> ::CoUninitialize();</p>
<p> return TRUE;</p>
<p>}</p>
</H7>
This code initializes COM and sets up what the program will say and makes it says it, thats all.
Thats all the code you need to add to the entire project, nothing more, maybe less(depends on what you are going for)
<p>If you need the files I made go to my website.</p>
<h3>Note</h3>
This tutorial is also included in the files you need to compile these files (install them all the way before you send any complaints)

