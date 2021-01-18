# Ele_VID

Learning the Ele VID method and correlated information, follow https://twiki.cern.ch/twiki/bin/view/Main/VIDTutorial2017:

``Getting the code`` //install release
```
scram project -n CMSSW-8-0-26-p1-VID CMSSW CMSSW_8_0_26_patch1
cd CMSSW-8-0-26-p1-VID/src  
cmsenv
voms-proxy-init -voms cms
```
``copy needed cmssw code``
```
git cms-init
git cms-addpkg RecoEgamma/ElectronIdentification
git cms-addpkg PhysicsTools/SelectorUtils
git clone https://github.com/ikrav/EgammaWork.git
cd EgammaWork/
git checkout ntupler_and_VID_demos_8.0.3
cd ../
```

and change the input rootfile in ``runElectrons_VID_CutBased_Summer16_80X_demo.py``:
```
inputFilesMiniAOD = cms.untracked.vstring('file:/eos/cms/store/mc/RunIISummer16MiniAODv2/DY2JetsToLL_M-50_TuneCUETP8M1_13TeV-madgraphMLM-pythia8/MINIAODSIM/PUMoriond17_80X_mcRun2_asymptotic_2016_TrancheIV_v6-v1/80000/E0976CCD-33BE-E611-879D-E41D2D08DFE0.root'
    )
```
then cp the ``ElectronNtuplerVIDDemo.cc`` to the ``plugins`` directory, 
```
cd $CMSSW_BASE/src
scram b
```

In order to check that everything is ok, run the demo ntuplizer:
```
cd EgammaWork/ElectronNtupler/test
cmsRun runElectrons_VID_CutBased_Summer16_80X_demo.py
```

<font color=Blue>the output is like following</font>:
```
Begin processing the 64th record. Run 1, Event 381641, LumiSection 256 at 18-Jan-2021 07:53:45.361 CET
MENG test---->>>ele size---->>> 2ele pt---->>> 83.220009
IdBit:2

Meng test--->>>1019

DEBUG CutFlow, full info for cand with pt=83.220009:
    CutFlow name= cutBasedElectronID-Summer16-80X-V1-medium    decision is 0
 Index                               cut name              isMasked    value-cut-upon     pass?
   0                                              MinPtCut_0    0        83.220009          1
   1                              GsfEleSCEtaMultiRangeCut_0    0        0.245101          1
   2                                   GsfEleDEtaInSeedCut_0    0        0.004014          0
   3                                       GsfEleDPhiInCut_0    0        0.011771          1
   4                         GsfEleFull5x5SigmaIEtaIEtaCut_0    0        0.008891          1
   5                               GsfEleHadronicOverEMCut_0    0        0.015428          1
   6                        GsfEleEInverseMinusPInverseCut_0    0        0.017043          1
   7                                 GsfEleEffAreaPFIsoCut_0    0        0.021371          1
   8                               GsfEleConversionVetoCut_0    0        1.000000          1
   9                                  GsfEleMissingHitsCut_0    0        0.000000          1
DEBUG CutFlow, the result with cut GsfEleFull5x5SigmaIEtaIEtaCut_0 masked out
    CutFlow name= cutBasedElectronID-Summer16-80X-V1-medium    decision is 0
 Index                               cut name              isMasked    value-cut-upon     pass?
   0                                              MinPtCut_0    0        83.220009          1
   1                              GsfEleSCEtaMultiRangeCut_0    0        0.245101          1
   2                                   GsfEleDEtaInSeedCut_0    0        0.004014          0
   3                                       GsfEleDPhiInCut_0    0        0.011771          1
   4                         GsfEleFull5x5SigmaIEtaIEtaCut_0    1        0.008891          1
   5                               GsfEleHadronicOverEMCut_0    0        0.015428          1
   6                        GsfEleEInverseMinusPInverseCut_0    0        0.017043          1
   7                                 GsfEleEffAreaPFIsoCut_0    0        0.021371          1
   8                               GsfEleConversionVetoCut_0    0        1.000000          1
   9                                  GsfEleMissingHitsCut_0    0        0.000000          1
ele size---->>> 2ele pt---->>> 57.086735
IdBit:2

Meng test--->>>1003

DEBUG CutFlow, full info for cand with pt=57.086735:
    CutFlow name= cutBasedElectronID-Summer16-80X-V1-medium    decision is 0
 Index                               cut name              isMasked    value-cut-upon     pass?
   0                                              MinPtCut_0    0        57.086735          1
   1                              GsfEleSCEtaMultiRangeCut_0    0        0.735629          1
   2                                   GsfEleDEtaInSeedCut_0    0        0.005562          0
   3                                       GsfEleDPhiInCut_0    0        0.004975          1
   4                         GsfEleFull5x5SigmaIEtaIEtaCut_0    0        0.010015          0
   5                               GsfEleHadronicOverEMCut_0    0        0.000000          1
   6                        GsfEleEInverseMinusPInverseCut_0    0        0.003293          1
   7                                 GsfEleEffAreaPFIsoCut_0    0        0.000000          1
   8                               GsfEleConversionVetoCut_0    0        1.000000          1
   9                                  GsfEleMissingHitsCut_0    0        0.000000          1
DEBUG CutFlow, the result with cut GsfEleFull5x5SigmaIEtaIEtaCut_0 masked out
    CutFlow name= cutBasedElectronID-Summer16-80X-V1-medium    decision is 0
 Index                               cut name              isMasked    value-cut-upon     pass?
   0                                              MinPtCut_0    0        57.086735          1
   1                              GsfEleSCEtaMultiRangeCut_0    0        0.735629          1
   2                                   GsfEleDEtaInSeedCut_0    0        0.005562          0
   3                                       GsfEleDPhiInCut_0    0        0.004975          1
   4                         GsfEleFull5x5SigmaIEtaIEtaCut_0    1        0.010015          1
   5                               GsfEleHadronicOverEMCut_0    0        0.000000          1
   6                        GsfEleEInverseMinusPInverseCut_0    0        0.003293          1
   7                                 GsfEleEffAreaPFIsoCut_0    0        0.000000          1
   8                               GsfEleConversionVetoCut_0    0        1.000000          1
   9                                  GsfEleMissingHitsCut_0    0        0.000000          1
```
<font color=red>the illustraion of the output</font>
