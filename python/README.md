**Program: bioplot.py Overview**

        This program calculates seven biorhythm curves and four derived 
        curves. To calculate these curves two things are needed: 1) the birth 
        date; and 2) a target date. The target date is automatically today's 
        date.

        The program also checks the three main curves Physical, Intellectual,
        Emotional (PIE) for three regions of operation: Peaks (good areas where 
        you ar at your peak); Zero crossings (bad areas were you don't know if
        you are coming or going); Valleys (when you are weakest in this
        characteristic). If your terminal supports it, you will see peaks in
        green, zeros in red and valleys in yellow.

        Janis Joplin's birth date and death date are used as an example.
        ![Janis Joplin Plot 4 Image](https://github.com/AZdave/bioplot/tree/main/python/Figure_4.jpg)

**Biorhythm Curves**  

        Name          Cycle (days)
        Physical       (23): 
        Intellectual   (28): 
        Emotional      (33): 
        Intuitional    (38): 
        Aesthetic      (43): 
        Self-Awareness (48): 
        Spiritual      (53): 

**Derived Curves**

        Name
        Passion   [(P+E)/2]:  Average of Physical  and Emotional rhythms
        Wisdom    [(E+I)/2]:  Average of Emotional and Intellectual rhythms 
        Mastery   [(P+I)/2]:  Average of Physical  and Intellectual rhythms 
        Average [(P+E+I)/3]:  Average of Physical  and Emotional and 
                                         Intellectual rhythms 

**Files                                   Description**

```
bioplot_Janis_Joplin_1943-01-19.csv     Birth data
bioplot_Janis_Joplin_1970-10-04.csv     Death data
bioplot_Janis_Joplin_2001-03-27.csv     58y Middle Age Crisis
bioplot.py                              program
command_line.jpg                        Shows peak,zero,valley colors
Figure_1.jpg                            Physical,Intelectual,Emotional plot
Figure_2.jpg                            Passion,Wisdom,Mastery plot
Figure_3.jpg                            Intuitional,Aesthetic,Self-Awareness,Spiritual
Figure_4.jpg                            Physical,Intelectual,Emotional,Average plot
Figure_4B.jpg                           Birth starts at zero
Figure_4M.jpg                           MAC same as birth
```


**Help**

```
$ python bioplot.py -h
usage: bioplot \[-h] \[-n NAME] \[-bd BIRTH_DATE] \[-td TARGET_DATE] \[-d] \[-f] \[-q] \[-u] \[-v] \[-p PLOT]

Biorythm plotter of 11 curves on 4 different plots.

optional arguments:
  -h, --help            show this help message and exit
  -n NAME, --name NAME  Person's Full name for plot title (default: Person Name)
  -bd BIRTH\_DATE, --birth\_date BIRTH\_DATE
                        Person's birth date yyyy-mm-dd (default: 1946-10-26)
  -td TARGET\_DATE, --target\_date TARGET\_DATE
                        Target date on plot yyyy-mm-dd (default: 2022-02-15)
  -bh BIRTH_TZ_DIFF, --birth_tz_diff BIRTH_TZ_DIFF
                        Person's birth time zone difference to current tz (default: 0) hours(+/-0-23)
  -d, --debug           print debug statements(default: False)
  -f, --file            Output csv file of plot data (default: False)
  -sb, --show_birth_date
                        Show Birth Date of plot, (default: False)
  -st, --show_target_date
                        Show Target Date of plot, (default: True)
  -q, --query           Query user with questions: Name, Birth Date, Target Date. (default: False)
  -u, --usage           Show usage for bioplot (default: False)
  -v, --version         Display version (default: False)
  -p PLOT, --plot PLOT  Number (1-5) of plots to show (default: 1)

      Plot #1 - Shows Physical, Intellectual, Emotional
      Plot #2 - Shows Passion, Wisdom, Mastery
      Plot #3 - Shows Intuitional, Aesthetic, Self-Awareness, Spiritual
      Plot #4 - Shows Physical, Intellectual, Emotional, Average
      Plot #5 - Shows all the above seperately

```
    
**Biorhythm Quirks:**

        1.) I call this your Middle Age crisis. The PEI curves repeat
            in  58y 2m 6d 12h 42m 52s 483622.4us from birth. At birth
            all curves atart at zero and increase. The program showed this
            behaviour in the files: bioplot_Janis_Joplin_1943-01-19.csv
            birth and bioplot_Janis_Joplin_2001-03-25.csv Middle Age
            crisis.

        2.) If biorhythms were accurate and useful, then you should 
            consider time zones.  Add birth time and zone to the birthdate.
            My time difference is two hours hardly noticable on the plots.
            The program has a crude time zone difference in hours by using 
            the -bh switch.

        3.) It seems to me that the chances of finding a problem have 
            increased with the number of biorhythm curves. Keep to three 
            main curves (PIE).

**Python Notes**

        There are many ways to do things. This program doesn't use dataforms.
        Also if I could brute force the colorized text, why load a special 
        module.

**Acknowledgements**

        1. https://www.daniweb.com/programming/software-development/code/216724/biorhythm-values-python
           This is were the checking: peak, zero, valley routines are. Mine 
           are in function to be able to check any curve.

        2. https://github.com/mmanlai/Biorythm/blob/main/biorhytm.py
           The plot functions of my code ar a minimal version of these.
           This site also calculates the birth day of the week.

        3.  http://en.wikipedia.org/wiki/Biorhythm has a more detailed version
            of biorhythms and the history associated with them.
