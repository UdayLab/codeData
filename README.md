# codeData
To evaluate with each dataset:<br>
python3 spaitialSPADE.py inputFile, neighborFile, OutputFile, minSup separater<br>
*three different maxdistance neighborfiles for each dataset.Air and Traffic datasets are real distance.The others are randomly taken.

# Example
 ## 1 Air Pollution<br>
  inputdata:airDataset.txt<br>
  neighbordata:Air_60k.txt,Air_80k.txt,Air_100k.txt<br>
  minSup: 0.3,0.4,0.5<br>
  sep="\t"<br>
 ## 2 Trafic consestion<br>
  inputdata:TraficData.txt<br>
  neighbordata:Tra_60k.txt,Tra_80k.txt,Tra_100k.txt<br>
  #neighbor files are so large to upload.<br>
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
  neighbordata:retail_250.txt,retail_500.txt,retail_750fre.txt<br>
  minSup: 0.1,0.15,0.2<br>
  sep="\t"<br>
  
