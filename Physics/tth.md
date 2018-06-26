 Generally information of the ttH multilepton analysis :

Please read the following support note if you want to have a overview the analysis(only cover the experimental part.)

Support note reading

https://cds.cern.ch/record/2244753/files/ATL-COM-PHYS-2017-101.pdf (towards 2017 Paper)

https://cds.cern.ch/record/2150024/files/ATL-COM-PHYS-2016-419.pdf (towards ICHEP)

Concerning the analysis strategy changes,

ICHEP: analysis is based on the cut based, and fake estimate is with fake factor method.

2017 Paper: fakes estimate is with Matrix Method and MVA is adopted.

Fake estimation:

The related slides of the fakes estimate are in the CERN BOX:

Matrix method:

The explanation of the method is in the appendix of the support

https://cds.cern.ch/record/2244753/files/ATL-COM-PHYS-2017-101.pdf

Here are the framework which is used to have the fake estimate.

Actually there are two, one is from Marseille as the cross check of the official one which is already implemented in GFW2.

Marseille FW:

https://svnweb.cern.ch/cern/wsvn/atlas-kliu/kliu/MatrixMethod_ttH_2SS/?#a5b20334963942b9f9c238aaf4399afb6

or you can access the

/quark1/wangc/Fake_Ets/test/MatrixMethod_ttH/

The Matrix Method in GFW2 (for details, you can contact Marco Milesi <marco.milesi@cern.ch>)

https://gitlab.cern.ch/atlasHTop/ttHMultiGFW2/tree/master/ttHMultilepton/Root

Multivariate analysis:

The official one is the multi-class MVA which is proposed by CERN,

The related slides are also in the CERN BOX and support.

The 2D BDT is also studied in 3l and related is in the CERNBOX as well.

Analysis code are in the

/quark1/wangc/TMVA/TMVA_train_app/TMVA_lxplus_input

Fit:

Generally, the analysis uses the ttHFitter to have the final fit results, and related twiki of the ttH

Fitter is:

https://twiki.cern.ch/twiki/bin/view/AtlasProtected/TtHFitter

The official package:

ttHFitter:

https://gitlab.cern.c h/atlasHTop/ttHMultiGFW2/tree/master/fit

You can also access the code in Margluon:

/quark1/wangc/GFW2/ttHFitter/TRExFitter

Please contact me, if you have any questions, thanks:

c.wang@cern.ch 
