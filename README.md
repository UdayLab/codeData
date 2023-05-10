# codeData
To evaluate with each dataset:
python3 spaitialSPADE.py inputFile, neighborFile, OutputFile, minSup separater:
*three different maxdistance neighborfiles for each dataset.Air and Traffic datasets are real distance.The others are randomly taken.

# Example
 ## 1 Air Pollution
  inputdata:airDataset.txt
  neighbordata:Air_60k.txt,Air_80k.txt,Air_100k.txt
  minSup: 0.3,0.4,0.5
  sep="\t"
 ## 2 Trafic consestion
  inputdata:TraficData.txt
  neighbordata:Tra_60k.txt,Tra_80k.txt,Tra_100k.txt
  #neighbor files are so large to upload.
  minSup: 0.3,0.4,0.5
  sep="\t"
 ## 3 S10
  inputdata:s10t1seq6.txt
  neighbordata:S10_250fre.txt,S10_500fre.txt,S10_750fre.txt
    #s10's neighbor file is so large to upload. So only about frequent datas uproaded.
  minSup: 0.3,0.4,0.5
  sep="\t"
 ## 4 Retail
  inputdata:retail.txt
  neighbordata:retail_250.txt,retail_500.txt,retail_750fre.txt
  minSup: 0.3,0.4,0.5
  sep="\t"
  
