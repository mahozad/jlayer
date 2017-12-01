 [![GitHub release](https://img.shields.io/github/release/mdihos/jlayer.svg)](https://github.com/mdihos/jlayer/releases)
 [![Scrutinizer](https://img.shields.io/scrutinizer/g/mdihos/jlayer.svg)](https://scrutinizer-ci.com/g/mdihos/jlayer/)
 [![license](https://img.shields.io/github/license/mdihos/jlayer.svg)]()
 
 # JavaZOOM 1999-2008

 [Project Homepage](http://www.javazoom.net/javalayer/javalayer.html)
 
 [JAVA and MP3 online Forums](http://www.javazoom.net/services/forums/index.jsp)


 ## DESCRIPTION
JLayer is a library that decodes/plays/converts MPEG 1/2/2.5 Layer 1/2/3
(i.e. MP3) in real time for the JAVA(tm) platform. This is a non-commercial project 
and anyone can add his contribution. JLayer is licensed under LGPL (see LICENSE).


 ## FAQ

- How to install JLayer?
  </br>Before running JLayer you must set PATH and CLASSPATH for JAVA
  and you must add jl1.0.1.jar to the CLASSPATH.

- Do I need JMF to run JLayer player?
  </br>No, JMF is not required. You just need a JVM JavaSound 1.0 compliant.
  (i.e. JVM1.3 or higher).

- How to run the MP3TOWAV converter?
  </br>java javazoom.jl.converter.jlc -v -p output.wav yourfile.mp3
  </br>(Note : MP3TOWAV converter should work under jdk1.1.x or higher)

- How to run the simple MP3 player?
  </br>java javazoom.jl.player.jlp localfile.mp3
  </br> or
  </br>java javazoom.jl.player.jlp -url http://www.aserver.com/remotefile.mp3
  </br>Note : MP3 simple player only works under JVM that supports JavaSound 1.0 (i.e JDK1.3.x+)

- How to run the advanced (threaded) MP3 player?
  </br>java javazoom.jl.player.advanced.jlap localfile.mp3

- Does simple MP3 player support streaming?
  </br>Yes, use the following command to play music from stream:
  </br>java javazoom.jl.player.jlp -url http://www.shoutcastserver.com:8000
  </br>(If JLayer returns without playing SHOUTcast stream then it might mean 
   that the server expect a winamp like "User-Agent" in HTTP request).

- Does JLayer support MPEG 2.5?
  </br>Yes, it works fine for all files generated with LAME.

- Does JLayer support VBR?
  </br>Yes, It supports VBRI and XING VBR header too. 

- How to get ID3v1 or ID3v2 tags from JLayer API?
  </br>The API provides a getRawID3v2() method to get an InputStream on ID3v2 frames.

- How to skip frames to have a seek feature?
  </br>See javazoom.jl.player.advanced.jlap source to learn how to skip frames.

- How much memory/CPU JLayer needs to run?
  </br>Here are our benchmark notes:
    - Heap use range: 1380KB to 1900KB - 370 classes loaded. 
    - Footprint:
    </br>~8MB under WinNT4/Win2K + J2SE 1.3 (Hotspot).
    </br>~10MB under WinNT4/Win2K + J2SE 1.4.1 (Hotspot).
    - CPU usage: 
    </br>~12% under PIII 800Mhz/WinNT4+J2SE 1.3 (Hotspot).
    </br>~8% under PIII 1Ghz/Win2K+J2SE 1.3.1 (Hotspot).
    </br>~12% under PIII 1Ghz/Win2K+J2SE 1.4.1 (Hotspot).
    </br>~1% under PIII 1Ghz/Win2K+J2SE 1.5.0 (Hotspot).

- How to contact JLayer developers?
  </br>Try to post a thread on Java&MP3 online forums at:
  </br>http://www.javazoom.net/services/forums/index.jsp
  </br>You can also contact us at jlayer@javazoom.net for contributions.
 

## KNOWN PROBLEMS

99% of MP3 plays well with JLayer but some (1%) return an ArrayIndexOutOfBoundsException 
while playing. It might come from invalid audio frames. 
</br>Workaround: Just try/catch ArrayIndexOutOfBoundsException in your code to skip 
             non-detected invalid frames.
