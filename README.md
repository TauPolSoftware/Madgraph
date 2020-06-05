# Madgraph
Creating a madgraph gridpack


Clone this repo
```
git clone git@github.com:TauPolSoftware/Madgraph.git
```



one needs to clone the CMS setup for creating a gridpack out of many generators
```
git clone git@github.com:cms-sw/genproductions.git
```

copy the directory DYTauTau_HT-incl to genproductions/bin/MadGraph5_aMCatNLO/cards/production/2017/13TeV/DYJets_HT_LO_MLM/DYJets_HT_mll50/

```
cp -r DYTauTau_HT-incl genproductions/bin/MadGraph5_aMCatNLO/cards/production/2017/13TeV/DYJets_HT_LO_MLM/DYJets_HT_mll50/
```

go to MG

```
cd  genproductions/bin/MadGraph5_aMCatNLO/
```

create a gridpack


```
./gridpack_generation.sh DYTauTau_HT-incl  cards/production/2017/13TeV/DYJets_HT_LO_MLM/DYJets_HT_mll50/DYTauTau_HT-incl/
```


The last should produce the gridpack DYTauTau_HT-incl_slc6_amd64_gcc630_CMSSW_9_3_16_tarball.tar.xz

Move it to some working directory

```OD
mkdir MyGeneration
mv DYTauTau_HT-incl_slc6_amd64_gcc630_CMSSW_9_3_16_tarball.tar.xz MyGeneration/	
cd MyGeneration
tar -xvf DYTauTau_HT-incl_slc6_amd64_gcc630_CMSSW_9_3_16_tarball.tar.xz
```

Generate 1000 events with random seed 123

```
./runcmsgrid.sh  1000 123 1
```

This will produce the lhe file, you can convert it to root tree by running makelhetree from the base dir;

```
./makelhetree.py -i genproductions/bin/MadGraph5_aMCatNLO/MyGeneration/cmsgrid_final.lhe
```




The MG parameters canbe set in  MyGeneration/process/madevent/Cards/param_card.dat
