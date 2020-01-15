import yfinance as yf
import datetime
import matplotlib.pyplot as plt
import os
import getpass
Company= "GE"
try:
    for y in range(1,21):    # loop through decade 2001-2020
        for x in range(1,13): # loop through months 1-12
            plt.clf 
            if x<12:
                xdate = datetime.datetime(2000+y, x, 1)
                start = str(xdate.strftime("%Y-%m-%d"))
                ydate = datetime.datetime(2000+y, x+1, 1)
                finish = str(ydate.strftime("%Y-%m-%d"))
            if x==12:
                xdate = datetime.datetime(2000+y, 12, 1)
                start = str(xdate.strftime("%Y-%m-%d"))
                ydate = datetime.datetime(2000+y+1, 1, 1)
                finish = str(ydate.strftime("%Y-%m-%d"))  
            data = yf.download(Company,start,finish)
            data.Close.plot()
            xis = str(x)
            yis = str(2000+y)
            directory = "C:\\Users\\"+getpass.getuser()+"\\Desktop\\pyStockPlots\\"+Company+"\\"
            if not os.path.exists(directory): # if folder does not exist create it
                os.makedirs(directory)
            plt.savefig(directory+ " "+yis+" "+xis+" "+Company+'.png')
            plt.close()
except Exception as e:
    print("Date not valid")
