#!/usr/bin/python3

from datetime import date, timedelta, datetime
# from math import floor, sin, pi
from numpy import arange, floor, sin, pi # need arange to calculate x vector
from matplotlib.pyplot import figure, show

import argparse
import os

ap = argparse.ArgumentParser(prog="bioplot",
    description="Biorythm plotter of 11 curves on 4 different plots.",
    formatter_class=argparse.RawDescriptionHelpFormatter,
    epilog='''\
      Plot #1 - Shows Physical, Intellectual, Emotional
      Plot #2 - Shows Passion, Wisdom, Mastery
      Plot #3 - Shows Intuitional, Aesthetic, Self-Awareness, Spiritual
      Plot #4 - Shows Physical, Intellectual, Emotional, Average
      Plot #5 - Shows all the above seperately
    
      ''')
ap.add_argument(
      '-n',
      '--name',
      default='Person Name',
      nargs=1, 
      type=str,
      help="Person's Full name for plot title (default: %(default)s)")
ap.add_argument(
      '-bd',
      '--birth_date',
      default='1946-10-26',  
      nargs=1, 
      type=str,
      help="Person's birth date yyyy-mm-dd (default: %(default)s)")
ap.add_argument(
      '-td',
      '--target_date',
      default=str(date.today()),
      nargs=1, 
      type=str,
      help="Target date on plot yyyy-mm-dd (default: %(default)s)")
ap.add_argument(
      '-d',
      '--debug',
      default=False,
      action='store_true',
      help='print debug statements(default: %(default)s)')
ap.add_argument(
      '-f',
      '--file',
      action='store_true',
      help='Output csv file of plot data (default: %(default)s)')
ap.add_argument(
      '-q',
      '--query',
      action='store_true',
      help='Query user with questions: Name, Birth Date, Target Date. (default: %(default)s)')
ap.add_argument(
      '-u',
      '--usage',
      action='store_true',
      help='Show usage for %(prog)s (default: %(default)s)')
ap.add_argument(
      '-v',
      '--version',
      action='store_true',
      help='Display version (default: %(default)s)')
ap.add_argument(
      '-p',
      '--plot',
      default=1,
      nargs=1, 
      type=int,
      help="Number (1-5) of plots to show (default: %(default)s)")

args = ap.parse_args()

if args.usage:
    ap.print_usage()
    os._exit(0)

# clean up types of input arguments
if args.version:
    print("$RCSfile: bioplot.py,v $ - $Revision: 1.2 $ $Date: 2022/02/16 00:50:34 $")
    os._exit(0)

if type(args.name) == list:
    name = args.name[0]
else:
    name = args.name

if type(args.birth_date) == list:
    birth_date = args.birth_date[0]
else:
    birth_date = args.birth_date

if type(args.target_date) == list:
    target_date = args.target_date[0]
else:
    target_date = args.target_date

if type(args.plot) == int:
    plot = args.plot
else:
    plot = args.plot[0]

if args.debug:
    print('DEBUG: args.name   \ttype: ', type(args.name), args.name)
    print('DEBUG: args.birth_date\ttype: ', type(args.birth_date), args.birth_date)
    print('DEBUG: args.target_date\ttype: ', type(args.target_date), args.target_date)
    print('DEBUG: args.plot   \ttype: ', type(args.plot), args.plot)
    print('DEBUG: Args ',args)
    print('DEBUG: name   \t\ttype: ', type(name), name)
    print('DEBUG: birth_date\ttype: ', type(birth_date), birth_date)
    print('DEBUG: target_date\ttype: ', type(target_date), target_date)
    print('DEBUG: plot   \t\ttype: ', type(plot), plot)

if args.debug:
    print("file: ",args.file)


person=name # to match input arguments
byear=birth_date[:4]
bmonth=birth_date[-5:-3]
bday=birth_date[-2:]
# target_date = birth_date    # test all zeros?
# following test must be done at targetdate below for syntax reasons
#target_date = birth_date + timedelta(days=int(21252))    # test all zeros? 23*28*33 = 21252 = 58y 2m 6d 12h 42m 52s 483622.4us
tyear=target_date[:4]
tmonth=target_date[-5:-3]
tday=target_date[-2:]

def bioplot(xx,yy1,label1,color1,yy2,label2,color2,yy3,label3,color3,figs):
    """

    bioplot function will plot three biorythm curves with a legend

    """
    fig = figure(figs,figsize=(10,8))
    ax1 = fig.add_subplot(111)
    ax1.grid(True)
    ax1.set_xlabel('Dates')
    ax1.set_title(person + "'s Biorythm")
    ax1.set_ylim((-1,1))
    ax1.plot(xx,yy1,label=label1,color=color1)
    ax1.plot(xx,yy2,label=label2,color=color2)
    ax1.plot(xx,yy3,label=label3,color=color3)
    #ax1.plot([targetdate,targetdate,targetdate], [-1,0,1] , color='black',label='Today')
    # Add a cursor on target date + 12 hours
    ax1.plot([xx[372],xx[372],xx[372]], [-1,0,1] , color='black',label=None)
    # add dots to cursor
    ax1.plot([xx[372],xx[372],xx[372]], [yy1[372],yy2[372],yy3[372]] , color='black',label=None,marker="o")
    ax1.xaxis.set_tick_params(rotation=30, labelsize=10)
    ax1.legend(loc="upper left")
    show()

def bioplot4(xx,yy1,label1,color1,yy2,label2,color2,yy3,label3,color3,yy4,label4,color4,figs):
    """

    bioplot4 function will plot four biorythm curves with a legend

    """
    fig = figure(figs,figsize=(10,8))
    ax1 = fig.add_subplot(111)
    ax1.grid(True)
    ax1.set_xlabel('Dates')
    ax1.set_title(person + "'s Biorythm")
    ax1.set_ylim((-1,1))
    ax1.plot(xx,yy1,label=label1,color=color1)
    ax1.plot(xx,yy2,label=label2,color=color2)
    ax1.plot(xx,yy3,label=label3,color=color3)
    ax1.plot(xx,yy4,label=label4,color=color4)
    # Add a cursor on target date + 12 hours
    ax1.plot([xx[372],xx[372],xx[372]], [-1,0,1] , color='black',label=None)
    # add dots to cursor
    ax1.plot([xx[372],xx[372],xx[372],xx[372]], [yy1[372],yy2[372],yy3[372],yy4[372]] , color='black',label=None,marker="o")
    ax1.xaxis.set_tick_params(rotation=30, labelsize=10)
    ax1.legend(loc="upper left")
    show()

def writecsv(name):
    """

    writecsv function will write all the biorythm data to a cvs file

    """
    import csv
    file1 = open(name, mode='w')
    data1 = csv.writer(file1)
    headers = ['Date','Physical','Intellectual','Emotional','Passion','Wisdom','Mastery','Average','Intuitional','Aesthetic','Self-Awareness','Spiritual' ]
    data1.writerow(headers)
    for i in range(0,len(xd),1):
        p = [ xd[i], physical[i], intellectual[i], emotional[i], passion[i], wisdom[i], mastery[i], aver[i], aesthetic[i], selfaware[i], spiritual[i] ]
        data1.writerow(p)
    file1.close()
    print('File: ', name, ' written.')

def check_wave(curve,cycle,label):
    """

    check_wave function will check when the peaks and troughs appear for the three main characteristics:
    Physical, Emotional, and Intelectual. one curve at a time.

    """
    xpeak_s='3000-12-31' # start of peak
    xpeaks=datetime.fromisoformat(xpeak_s)
    xpeakS=xpeaks
    xvales=xpeaks
    zerosS=xpeaks
    xpeak_e='1600-01-01' # end of peak
    xpeake=datetime.fromisoformat(xpeak_e)
    xvalee=xpeake
    zerose=xpeake
    lastE=xpeake
    peaks = 0
    zeros = 0
    vales = 0
    # check every point for peaks and valleys
    for i in range(0,len(curve),1):
        position = x[i] % cycle
        quadrant = int(floor((4 * position) / cycle))
        point=curve[i]
        if point > 0.95 and quadrant == 0:
            xpeaks=min(xpeaks,xd[i])
        if point > 0.95 and quadrant == 1:
            xpeake=max(xpeake,xd[i])
        if point < 0.90 and quadrant == 1 and xpeaks != xpeakS:
            peaks = peaks + 1
            outs=green+label+"\t peak   #"+str(peaks)+" from "+str(xpeaks)+' to '+str(xpeake)+off
            print(outs)
            # print(label, "\t peak   #", peaks, " from ", xpeaks, ' to ',xpeake) # no color
            # reset peak ids
            xpeaks=datetime.fromisoformat(xpeak_s)
            xpeake=datetime.fromisoformat(xpeak_e)
        if point > -0.05 and point < 0.05:
            zerosS=min(zerosS,xd[i])
            zerose=max(zerose,xd[i])
        elif point > 0.06 and quadrant == 0:
            lastS=zerosS
            lastE=zerose
        elif point < -0.06 and quadrant == 2:
            lastS=zerosS
            lastE=zerose
        elif lastE != zerose:
            zeros = zeros + 1
            outs=red+bold+label+"\t zero   #"+ str(zeros)+" from "+str(zerosS)+" to "+str(zerose)+off
            print(outs)
            zerosS=datetime.fromisoformat(xpeak_s)
            zerose=datetime.fromisoformat(xpeak_e)
        if point < -0.95 and quadrant == 2:
            xvales=min(xvales,xd[i])
        if point < -0.95 and quadrant == 3:
            xvalee=max(xvalee,xd[i])
        if point > -0.90 and quadrant == 3 and xvales != xpeakS:
            vales = vales + 1
            outs=Bblack+bold+yellow+label+"\t valley #"+str(vales)+" from "+str(xvales)+' to '+str(xvalee)+off
            print(outs)
            # print(label, "\t valley #", vales, " from ", xvales, ' to ',xvalee) # nocolor
            # reset vale ids
            xvales=datetime.fromisoformat(xpeak_s)
            xvalee=datetime.fromisoformat(xpeak_e)

def removes(string):
    # from www.geeksforgeeks.org
    return string.replace(" ","_")

def ask(string,value):
    # get inupt with default value
    answer = input(string+"("+str(value)+"): ")
    if answer == "":
        return value
    else:
        return answer

# Brute force terminal colors
bold="\033[1m"     # xterm
faint="\033[2m"
italic="\033[3m"
underline="\033[4m"# xterm
blinkslow="\033[5m"# xterm
blinkfast="\033[6m"
negative="\033[7m" # xterm
conceal="\033[8m"  # xterm
strike="\033[9m"
black="\033[30m"   # foreground color
red="\033[31m"
green="\033[32m"
yellow="\033[33m"
blue="\033[34m"
magenta="\033[35m"
cyan="\033[36m"
white="\033[37m"
Bblack="\033[40m"  # background color
Bred="\033[41m"
Bgreen="\033[42m"
Byellow="\033[43m"
Bblue="\033[44m"
Bmagenta="\033[45m"
Bcyan="\033[46m"
Bwhite="\033[47m"
off="\033[0m"     # turn off codes
if args.debug:
    print(red+bold+'color test'+off)
if args.query:
    person = ask("Enter person's name ",person)
    birth_date = ask("Enter Birth Date ",birth_date)
    target_date = ask("Enter Target Date ",target_date)

# datetime function needed for time points to get smooth curve
birthdate = datetime.fromisoformat(birth_date)  
targetdate = datetime.fromisoformat(target_date)
#targetdate = datetime.fromisoformat(birth_date) + timedelta(days=int(21252))    # test all zeros? 23*28*33 = 21252 = 58y 2m 6d 12h 42m 52s 483622.4us
print("Birth: ",birth_date,birthdate,"   Target: ",target_date,targetdate)
days = (targetdate - birthdate).days
x=arange(days-15,days+15,1/24)
xd=[range(0,720,1)]          # 720 = 30*24
for i in range(0,30,1):      # 30 days
    for j in range(0,24,1):  # 24 hours/day
        d=targetdate + timedelta(days=int(i-15),hours=j)
        if i == 0 and j == 0:
            xd[i]=d
        else:
            xd.append(d)

physical =     sin((2*pi*x)/23)
intellectual = sin((2*pi*x)/28)
emotional =    sin((2*pi*x)/33)
passion = (physical+emotional)/2
wisdom =  (intellectual+emotional)/2
mastery = (physical+intellectual)/2
aver = (physical+intellectual+emotional)/3
intuitional =  sin((2*pi*x)/38)
aesthetic =    sin((2*pi*x)/43)
selfaware =    sin((2*pi*x)/48)
spiritual =    sin((2*pi*x)/53)
# Half of 30days*24hour(=720 items) dataset is 360 + 12 hours later (Noon) = 372
print(xd[372], person+" was "+str(days)+" days old = ",days/365.25,"years",
      "\n\tPhysical       (23): ",physical[372],
      "\n\tIntellectual   (28): ",intellectual[372],
      "\n\tEmotional      (33): ",emotional[372],
      "\n\tPassion   [(P+E)/2]: ",passion[372],
      "\n\tWisdom    [(E+I)/2]: ",wisdom[372],
      "\n\tMastery   [(P+I)/2]: ",mastery[372],
      "\n\tAverage [(P+E+I)/3]: ",aver[372],
      "\n\tIntuitional    (38): ",intuitional[372],
      "\n\tAesthetic      (43): ",aesthetic[372],
      "\n\tSelf-Awareness (48): ",selfaware[372],
      "\n\tSpiritual      (53): ",spiritual[372])
"""
print(" I Days    Date  Physical  Intellectual  emotional  Average   Passion   Wisdom   Mastery  Aesthetic  Self-Awareness  Spiritual")
for i in range(0,30,1):
    print(i,x[i],xd[i],physical[i],intellectual[i],emotional[i],aver[i],
          passion[i],wisdom[i],mastery[i],aesthetic[i],selfaware[i],spiritual[i])
"""
check_wave(physical,23,'Physical')
check_wave(intellectual,28,'Intellectual')
check_wave(emotional,33,'Emotional')
nicename=person+"_"
if args.debug:
    print('Nice Name: "' + removes(nicename) + '"')
fname=str('bioplot_') + removes(nicename) + str(target_date) + '.csv'
if args.file:
    writecsv(fname)
if plot == 1 or plot == 5:
    bioplot(xd,physical,"Physical",'red',intellectual,"Intellectual",'green',emotional,"Emotional",'blue',1)
if plot == 2 or plot == 5:
    bioplot(xd,passion,"Passion",'orange',wisdom,"Wisdom",'cyan',mastery,"Mastery",'yellow',2)
if plot == 3 or plot == 5:
    bioplot4(xd,intuitional,'Intuitional','pink',aesthetic,"Aesthetic",'grey',selfaware,"Self Awareness",'red',spiritual,"Spiritual",'blue',3)
if plot == 4 or plot == 5:
    bioplot4(xd,physical,"Physical",'red',intellectual,"Intellectual",'green',emotional,"Emotional",'blue',aver,"Average",'orange',4)
print('Done')
