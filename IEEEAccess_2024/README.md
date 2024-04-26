# Requirements
Python 3.8 or above is recommended to execute our program. Once you have an appropriate Python version, please install the following packages to execute our program.

'''terminal
pip install pami psutil urllib
'''

# Datasets
 The datasets need to conduct experiments are available at the following directories.
   - database:
   - neighbors:
   - tablesForNeighbors:
   
# Executing our programs

## Terminal execution
       
       The format to execute our program in the terminal is as follows:
       ```terminal
       python3 GFSPm.py inputFile, neighborFile, OutputFile, minSup separater
       '''
       An example:
       
       ```terminal
           python3 GFSPm.py ????????
       '''
       
## Python execution
Python
#Step 1: Import the library
import GFSPm as gf

#Step 2: Define the input parameters
inputFile = '<specify the sequence database file name>'
neighborhoodFile = '<specify the neighborhood file name'
outputFileName = '<specify the output file name to store the patterns>'

minSup =<specifyMinSup>

seperator = '<specifyYourSeperator>' # default sepereator is tabSpace

#Step 3: calling the algorithm
'''


You can execute our program on a terminal or in a jupyter notebook. 

# codeData
To evaluate with each dataset:<br>
python3 GFSPm.py inputFile, neighborFile, OutputFile, minSup separater<br>
*three different maxdistance neighborfiles for each dataset.Air and Traffic datasets are real distance.The others are randomly taken.<br>
*some large neighbor files(add "!") cannot uproad because of limit of github strage.<br>


# Input Example
 import GFSPm as gf
 
 _ap = gf.GFSPm('inputFile',"neighborFile",minSup,"separator")
 _ap.startMine()
 _Patterns = _ap.getPatterns()
 _memUSS = _ap.getMemoryUSS()
 print("Total Memory in USS:", _memUSS)
 _memRSS = _ap.getMemoryRSS()
 print("Total Memory in RSS", _memRSS)
 _run = _ap.getRuntime()
 print("Total ExecutionTime in ms:", _run)
 print("Total number of Frequent Patterns:", len(_Patterns))
 print("Error! The number of input parameters do not match the total number of parameters provided")
 _ap.save("priOut3.txt")
# datasets and minimmum support
 ## 1 Air Pollution<br>
  inputdata:airDataset.txt<br>
  neighbordata:Air_60k.txt,Air_80k.txt,Air_100k.txt<br>
  minSup: 0.3,0.4,0.5<br>
  sep="\t"<br>
 ## 2 Trafic consestion<br>
  inputdata:TraficData.txt<br>
  "!"neighbordata:Tra_60k.txt,Tra_80k.txt,Tra_100k.txt<br>
  minSup: 0.865,0.87,0.875<br>
  sep="\t"<br>
 ## 3 S10
  inputdata:s10t1seq6.txt<br>
  neighbordata:S10_250fre.txt,S10_500fre.txt,S10_750fre.txt<br>
    #s10's neighbor file is so large to upload. So only about frequent datas uproaded.<br>
  minSup: 0.002,0.0015,0.001<br>
  sep="\t"<br>
 ## 4 Retail
  inputdata:retail.txt<br>
  "!"neighbordata:retail_250.txt,retail_500.txt,retail_750fre.txt<br>
  minSup: 0.1,0.15,0.2<br>
  sep="\t"<br>
  ## 5 FIFA
  inputdata:fifa.txt<br>
  neighbordata:fifa5.txt,fifa7.txt, "!"fifa9.txt
  minsup:0.15,0.16,0.17...<br>

  ## 6 BMS1
  inputdata:BMS1.txt<br>
  neighbordata:BMS1_5.txt,BMS1_7.txt, BMS1_9.txt
  minsup:0.1,0.12,0.14...<br>

  ## 7 Kosarak
  inputdata:Kosarak.txt<br>
  "!"neighbordata:Kosarak5.txt,Kosarak7.txt, Kosarak9.txt
  minsup:2,3,4...<br>

  ## 7 BIKE
  inputdata:bike.txt<br>
  neighbordata:bike5.txt,bike7.txt, bike9.txt
  minsup:2,3,4...<br>
  
