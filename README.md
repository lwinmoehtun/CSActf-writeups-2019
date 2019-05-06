# CSActf-writeups-2019

### Forensics

 #### Zippy (50pts)

  In this challenge, we were given a zip file and a message:
  > Got a zip file, but our stupid admin, Blue, couldn't even open it. Can you?
  
  When I tried to unzip the zip file, got nothing but an error. Then I checked with <tt>file</tt> command to know it is zip file or something else. (Don't trust extensions LOL!:joy:)
  
  ![alt file](https://github.com/Towtex/CSActf-writeups-2019/blob/master/zippy/file)
  
  OK, it is a zip file. Let's check with <tt>bless</tt> or your favourite hex editor.
  
  ![alt bless](https://github.com/Towtex/CSActf-writeups-2019/blob/master/zippy/bless.png)
  
  After googling, I found the structure a zip file [here](https://users.cs.jmu.edu/buchhofp/forensics/formats/pkzip.html "The structure of a PKzip file")
  
  ![alt zip-structure](https://github.com/Towtex/CSActf-writeups-2019/blob/master/zippy/zip-structure)
  
  But our zip file is missing **50 4B 03 04**.
  
  ![alt bless](https://github.com/Towtex/CSActf-writeups-2019/blob/master/zippy/bless)
  
  Let's add these magic number in it.
  
  ![alt bless-edited](https://github.com/Towtex/CSActf-writeups-2019/blob/master/zippy/bless-edited)
  
  Then extract the zip...
  
  ![alt flag](https://github.com/Towtex/CSActf-writeups-2019/blob/master/zippy/flag.png)
  
  Bingo! We got the flag.
  
  *CSACTF{z1ppy_z1p_z1p}*
