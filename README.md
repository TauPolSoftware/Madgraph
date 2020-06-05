# Madgraph
Creating a madgraph gridpack



First of all one needs to clone the CMS setup for creating a gridpack out of many generators
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

```
mkdir MyGeneration
mv DYTauTau_HT-incl_slc6_amd64_gcc630_CMSSW_9_3_16_tarball.tar.xz MyGeneration/	
cd MyGeneration
tar -xvf DYTauTau_HT-incl_slc6_amd64_gcc630_CMSSW_9_3_16_tarball.tar.xz
```