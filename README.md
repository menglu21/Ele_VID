# Ele_VID

Learning the Ele VID method and correlated information, follow https://twiki.cern.ch/twiki/bin/view/Main/VIDTutorial2017:

Getting the code
#install release
scram project -n CMSSW-8-0-26-p1-VID CMSSW CMSSW_8_0_26_patch1
cd CMSSW-8-0-26-p1-VID/src  
cmsenv
voms-proxy-init -voms cms
#copy needed cmssw code
git cms-init
git cms-addpkg RecoEgamma/ElectronIdentification
git cms-addpkg PhysicsTools/SelectorUtils
git clone https://github.com/ikrav/EgammaWork.git
cd EgammaWork/
git checkout ntupler_and_VID_demos_8.0.3
cd ../
