# Requirements
Python 3.8 or above is recommended to execute our program. Once you have an appropriate Python version, please install the following packages to execute our program.

'''terminal
pip install pami psutil urllib
'''

# Datasets
 The datasets need to conduct experiments are available at the following directories.<br>
   - database:seqencial databases<br>
            airDataset.txt,TraficData.txt,retail.txt,s10t1seq6.txt,test.txt<br>
   - neighbors:neighbor files<br>
                Air_100k.txt, Air_80k.txt, Air_60k.txt<br>
                s10_250fre.txt, s10_500fre.txt, s10_750fre.txt<br>
                testDis=1.txt, testDis=2.txt<br>
   - tablesForNeighbors: The nighbor files made from this table<br>
              tableForTest.txt,tableforair.txt,tableforretail.txt,tablefors10.txt<br>
      *three different maxdistance neighborfiles for each dataset.Air and Traffic datasets are real distance.The others are randomly taken.<br>
      *some large neighbor files(add "!") cannot uproad because of limit of github strage.<br>  
      *retail.txt and s10t1seq6.txt can be downloaded by this site(https://www.philippe-fournier-viger.com/spmf/index.php?link=datasets.php) 
# Executing our programs

## Terminal execution
   The format to execute our program in the terminal is as follows:
   ```terminal
   python3 spaitialSPADE.py inputFile OutputFile  neighborFile   minSup separater
   ```
      
An example:
       
   ```terminal
   python3 spaitialSPADE.py s10t1seq6.txt result.txt S10_250fre.txt
   ```
       
## Python execution
```Python 
#for single minsup
#Step 1: Import the library
import spaitialSPADE as sp

#Step 2: Define the input parameters
inputFile = '<specify the sequence database file name>'
neighborhoodFile = '<specify the neighborhood file name'
outputFileName = '<specify the output file name to store the patterns>'
minSup =<specifyMinSup>
seperator = '<specifyYourSeperator>' # default sepereator is tabSpace

#Step 3: calling the algorithm
_ap = sp.Spade(inputFile,neighborFile,minSup,separator)
_ap.startMine()

#Step 4 showing results<br>
_Patterns = _ap.getPatterns()
_memUSS = _ap.getMemoryUSS()
print("Total Memory in USS:", _memUSS)
_memRSS = _ap.getMemoryRSS()
print("Total Memory in RSS", _memRSS)
_run = _ap.getRuntime()
print("Total ExecutionTime in ms:", _run)
print("Total number of Frequent Patterns:", len(_Patterns))

#Step 5 saving patterns
_ap.save("priOut3.txt")
```


```Python 
#for multiple minsup
#Step 1: Import the library<br>
import spaitialSPADE as sp
import pandas as pd

#Step 2: Define the input parameters<br>
inputFile = '<specify the sequence database file name>'
neighborhoodFile = '<specify the neighborhood file name>'
outputFileName = '<specify the output file name to store the patterns>'
minSupList =<specify some MinSup in List>
seperator = '<specifyYourSeperator>' # default sepereator is tabSpace
result = pd.DataFrame(columns=['algorithm', 'minSup', 'patterns', 'runtime', 'memory']) 
#initialize a data frame to store the results of Apriori algorithm

#Step 3: calling the algorithm<br>
algorithm = 'SpaitialSPADE'  #specify the algorithm name
for minSupCount in minSupList:
    obj =sp.Spade(inputFile,neighborhoodFile,minSupCount seperator)
    obj.startMine()
    #store the results in the data frame
    result.loc[result.shape[0]] = [algorithm, minSupCount, len(obj.getPatterns()), obj.getRuntime(), obj.getMemoryRSS()]
print(result)

#Step 4: Plotting the results<br>
from PAMI.extras.graph import plotLineGraphsFromDataFrame as plt
ab = plt.plotGraphsFromDataFrame(result)
ab.plotGraphsFromDataFrame() #drawPlots()
#Step 5: Saving the results in a latex format<br>
from PAMI.extras.graph import generateLatexFileFromDataFrame as gdf
gdf.generateLatexCode(result)
```


You can execute our program on a terminal or in a jupyter notebook. <br>




# datasets and minimum support
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
  
