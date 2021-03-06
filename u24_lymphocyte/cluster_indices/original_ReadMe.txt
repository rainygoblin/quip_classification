The code assumes the following structure of directories:

InitialDirectory (say,"Y:/Desktop/StonyBrookData") 
├───RawData
│   ├───paad
│   │   └───paad
│   ├───brca
│   │   └───brca
│   ├───lusc
│   │   └───lusc
│   ├───uvm
│   │   └───uvm
│   ├───luad
│   │   └───luad
│   ├───skcm
│   │   └───skcm
│   ├───prad
│   │   └───prad
│   └───coad
│       └───coad
├───Results_priority
└───R_code

-------------------------------------------------------------------------

Variables and Parameters that could be changed/tuned-

min_num_datapts: files with greater than min_num_datapts will be processed

max_num_datapts: files with less than max_num_datapts will be processed

save_images: TRUE or FALSE depending on if we woulld like to save the images (heatmap and cluster plot) or not

study: name of the study such as "SKCM", "LUAD", etc.

starts: first file number in the list of files to be processed (default value = 1, process from beginning of the list)

ends: last file number in the list of files to be processed (default value = length(path))

intCindex_ap: cluster indices when we use apcluster to get the clusters

intCindex_km: cluster indices when we use kmeans to get the clusters (apcluster to get the number of clusters)

datalen: number of data points in each file and number of clusters

line 70: 
apclus = apcluster(negDistMat(r=2), tmp1, q=0)
In here, one could set q to take a fixed value between 0 an 1; q=0 gives the minimum number of clusters.

We save all the variables every 10 steps or whenever all the files are processed.
