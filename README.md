[![GitHub release](https://img.shields.io/github/release/mahozad/jlayer.svg)](https://github.com/mahozad/jlayer/releases)
[![GitHub top language](https://img.shields.io/github/languages/top/mahozad/jlayer.svg)]()
[![GitHub last commit](https://img.shields.io/github/last-commit/mahozad/jlayer.svg)]()
[![license](https://img.shields.io/github/license/mahozad/jlayer.svg)](https://www.gnu.org/licenses/lgpl-3.0.en.html)

[//]: # ( [![Codacy Badge]&#40;https://api.codacy.com/project/badge/Grade/61f2c09a2a3e49b59e863755076e9024&#41;]&#40;https://www.codacy.com/app/mahozad/jlayer?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=mahozad/jlayer&amp;utm_campaign=Badge_Grade&#41;)

# JavaZOOM 1999-2008
  - [Project Homepage](http://www.javazoom.net/javalayer/javalayer.html)
  - [Java and MP3 online Forums](http://www.javazoom.net/services/forums/index.jsp)

## DESCRIPTION
JLayer is a library that decodes/plays/converts MPEG 1/2/2.5 Layer 1/2/3
(i.e. MP3) in real time for the Java<sup>tm</sup> platform. This is a non-commercial project 
and anyone can add his contribution. JLayer is licensed under LGPL (see [LICENSE](LICENSE)).

## FAQ
  - How to install JLayer?  
    Before running JLayer you must set `PATH` and `CLASSPATH` for Java
    and you must add jl1.0.1.jar to the `CLASSPATH`.

  - Do I need JMF to run JLayer player?  
    No, JMF is not required. You just need a JVM JavaSound 1.0 compliant.
    (i.e. JVM1.3 or higher).

  - How to run the MP3TOWAV converter?  
    `java javazoom.jl.converter.jlc -v -p output.wav yourfile.mp3`  
    > Note: MP3TOWAV converter should work under jdk1.1.x or higher

  - How to run the simple MP3 player?  
    `java javazoom.jl.player.jlp localfile.mp3`  
    or  
    `java javazoom.jl.player.jlp -url http://www.aserver.com/remotefile.mp3`  
    > Note: MP3 simple player only works under JVM that supports JavaSound 1.0 (i.e JDK1.3.x+)

  - How to run the advanced (threaded) MP3 player?  
    `java javazoom.jl.player.advanced.jlap localfile.mp3`

  - Does simple MP3 player support streaming?  
    Yes, use the following command to play music from stream:  
    `java javazoom.jl.player.jlp -url http://www.shoutcastserver.com:8000`  
    (If JLayer returns without playing SHOUTcast stream then it might mean 
     that the server expect a winamp like "User-Agent" in HTTP request).

  - Does JLayer support MPEG 2.5?  
    Yes, it works fine for all files generated with LAME.

  - Does JLayer support VBR?  
    Yes, It supports VBRI and XING VBR header too. 

  - How to get ID3v1 or ID3v2 tags from JLayer API?  
    The API provides a getRawID3v2() method to get an InputStream on ID3v2 frames.

  - How to skip frames to have a seek feature?  
    See javazoom.jl.player.advanced.jlap source to learn how to skip frames.

  - How much memory/CPU JLayer needs to run?  
    Here are our benchmark notes:
      + Heap use range:  
        * 1380KB to 1900KB - 370 classes loaded. 
      + Footprint:  
        * ~8MB under WinNT4/Win2K + J2SE 1.3 (Hotspot).
        * ~10MB under WinNT4/Win2K + J2SE 1.4.1 (Hotspot).
      + CPU usage:  
        * ~12% under PIII 800Mhz/WinNT4+J2SE 1.3 (Hotspot).
        * ~8% under PIII 1Ghz/Win2K+J2SE 1.3.1 (Hotspot).
        * ~12% under PIII 1Ghz/Win2K+J2SE 1.4.1 (Hotspot).
        * ~1% under PIII 1Ghz/Win2K+J2SE 1.5.0 (Hotspot).

  - How to contact JLayer developers?  
    Try to post a thread on Java&MP3 online forums at:  
    http://www.javazoom.net/services/forums/index.jsp  
    You can also contact us at jlayer@javazoom.net for contributions. 

## KNOWN PROBLEMS
99% of MP3 plays well with JLayer but some (1%) return an `ArrayIndexOutOfBoundsException`
while playing. It might come from invalid audio frames.  
Workaround: Just `try/catch` `ArrayIndexOutOfBoundsException` in your code to
skip non-detected invalid frames.
