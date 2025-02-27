# Technical Informations

@tableofcontents

## Helper Command Functionality

With the `python3 <scriptname> -h` command you will see a help message for all commands valid for the CLI. CLI has same formatted messages in O2-DPL. It is recommended to use this command at least once before using the interface. If you do not remember the parameters related to the interface, you can list all valid parameters and the values that these parameters can take with this command. In addition, helper messages are integrated into helper messages for all values that are valid for each very important parameter. For example, if you want to get a help message with the `python3 runTableMaker.py -h` command:

P.S The default values you see in the helper messages are the default values for the interface. The values you see None will directly take the default values from JSON

```ruby
usage: runTableMaker.py [-h] [-runData] [-runMC] [--run {2,3}]
                         [--add_mc_conv] [--add_fdd_conv] [--add_track_prop]
                         [--aod AOD] [--onlySelect ONLYSELECT]
                         [--autoDummy {true,false}]
                         [--cfgEventCuts [CFGEVENTCUTS [CFGEVENTCUTS ...]]]
                         [--cfgBarrelTrackCuts [CFGBARRELTRACKCUTS [CFGBARRELTRACKCUTS ...]]]
                         [--cfgMuonCuts [CFGMUONCUTS [CFGMUONCUTS ...]]]
                         [--cfgBarrelLowPt CFGBARRELLOWPT]
                         [--cfgMuonLowPt CFGMUONLOWPT] [--cfgNoQA CFGNOQA]
                         [--cfgDetailedQA {true,false}]
                         [--cfgMinTpcSignal CFGMINTPCSIGNAL]
                         [--cfgMaxTpcSignal CFGMAXTPCSIGNAL]
                         [--cfgMCsignals [CFGMCSIGNALS [CFGMCSIGNALS ...]]]
                         [--process [PROCESS [PROCESS ...]]]
                         [--syst {PbPb,pp,pPb,Pbp,XeXe}]
                         [--muonSelection {0,1,2}]
                         [--customDeltaBC CUSTOMDELTABC]
                         [--isCovariance {true,false}]
                         [--tof-expreso TOF_EXPRESO]
                         [--isProcessEvTime {true,false}]
                         [--isBarrelSelectionTiny {true,false}]
                         [--cfgMuonsCuts [CFGMUONSCUT [CFGMUONSCUT ...]]]
                         [--cfgPairCuts [CFGPAIRCUTS [CFGPAIRCUTS ...]]]
                         [--cfgBarrelSels [CFGBARRELSELS [CFGBARRELSELS ...]]]
                         [--cfgMuonSels [CFGMUONSELS [CFGMUONSELS ...]]]
                         [--isFilterPPTiny {true,false}]
                         [--est [EST [EST ...]]] [--cfgWithQA {true,false}]
                         [--d_bz D_BZ] [--v0cospa V0COSPA]
                         [--dcav0dau DCAV0DAU] [--v0Rmin V0RMIN]
                         [--v0Rmax V0RMAX] [--dcamin DCAMIN] [--dcamax DCAMAX]
                         [--mincrossedrows MINCROSSEDROWS]
                         [--maxchi2tpc MAXCHI2TPC] [--pid [PID [PID ...]]]
                         [--cutLister] [--MCSignalsLister] [--debug DEBUG]
                         [--logFile]
                         Config.json

Arguments to pass

optional arguments:
  -h, --help            show this help message and exit

Core configurations that must be configured:
  Config.json           config JSON file name
  -runData              Run over data (default: False)
  -runMC                Run over MC (default: False)
  --run {2,3}           Run Number Selection (2 or 3) (default: None)

Additional Task Adding Options:
  --add_mc_conv         Add the converter from mcparticle to mcparticle+001
                        (Adds your workflow o2-analysis-mc-converter task)
                        (default: False)
  --add_fdd_conv        Add the fdd converter (Adds your workflow o2-analysis-
                        fdd-converter task) (default: False)
  --add_track_prop      Add track propagation to the innermost layer (TPC or
                        ITS) (Adds your workflow o2-analysis-track-propagation
                        task) (default: False)

Data processor options: internal-dpl-aod-reader:
  --aod AOD             Add your AOD File with path (default: None)

Automation Parameters:
  --onlySelect ONLYSELECT
                        An Automate parameter for keep options for only
                        selection in process, pid and centrality table (true
                        is highly recomended for automation) (default: true)
  --autoDummy {true,false}
                        Dummy automize parameter (don't configure it, true is
                        highly recomended for automation) (default: true)

Data processor options: table-maker:
  --cfgEventCuts [CFGEVENTCUTS [CFGEVENTCUTS ...]]
                        Space separated list of event cuts (default: None)
  --cfgBarrelTrackCuts [CFGBARRELTRACKCUTS [CFGBARRELTRACKCUTS ...]]
                        Space separated list of barrel track cuts (default:
                        None)
  --cfgMuonCuts [CFGMUONCUTS [CFGMUONCUTS ...]]
                        Space separated list of muon cuts in table-maker
                        (default: None)
  --cfgBarrelLowPt CFGBARRELLOWPT
                        Low pt cut for tracks in the barrel (default: None)
  --cfgMuonLowPt CFGMUONLOWPT
                        Low pt cut for muons (default: None)
  --cfgNoQA CFGNOQA     If true, no QA histograms (default: None)
  --cfgDetailedQA {true,false}
                        If true, include more QA histograms (BeforeCuts
                        classes and more) (default: None)
  --cfgMinTpcSignal CFGMINTPCSIGNAL
                        Minimum TPC signal (default: None)
  --cfgMaxTpcSignal CFGMAXTPCSIGNAL
                        Maximum TPC signal (default: None)
  --cfgMCsignals [CFGMCSIGNALS [CFGMCSIGNALS ...]]
                        Space separated list of MC signals (default: None)

Data processor options: table-maker/table-maker-m-c:
  --process [PROCESS [PROCESS ...]]
                        Process Selection options for tableMaker/tableMakerMC
                        Data Processing and Skimming (default: None)
  Full                  Build full DQ skimmed data model, w/o centrality
  FullTiny              Build full DQ skimmed data model tiny
  FullWithCov           Build full DQ skimmed data model, w/ track and
                        fwdtrack covariance tables
  FullWithCent          Build full DQ skimmed data model, w/ centrality
  BarrelOnly            Build barrel-only DQ skimmed data model, w/o
                        centrality
  BarrelOnlyWithCov     Build barrel-only DQ skimmed data model, w/ track cov
                        matrix
  BarrelOnlyWithV0Bits  Build full DQ skimmed data model, w/o centrality, w/
                        V0Bits
  BarrelOnlyWithEventFilter
                        Build full DQ skimmed data model, w/o centrality, w/
                        event filter
  BarrelOnlyWithCent    Build barrel-only DQ skimmed data model, w/ centrality
  MuonOnly              Build muon-only DQ skimmed data model
  MuonOnlyWithCov       Build muon-only DQ skimmed data model, w/ muon cov
                        matrix
  MuonOnlyWithCent      Build muon-only DQ skimmed data model, w/ centrality
  MuonOnlyWithFilter    Build muon-only DQ skimmed data model, w/ event filter
  OnlyBCs               Analyze the BCs to store sampled lumi

Data processor options: event-selection-task:
  --syst {PbPb,pp,pPb,Pbp,XeXe}
                        Collision System Selection ex. pp (default: None)
  --muonSelection {0,1,2}
                        0 - barrel, 1 - muon selection with pileup cuts, 2 -
                        muon selection without pileup cuts (default: None)
  --customDeltaBC CUSTOMDELTABC
                        custom BC delta for FIT-collision matching (default:
                        None)

Data processor options: track-propagation:
  --isCovariance {true,false}
                        track-propagation : If false, Process without
                        covariance, If true Process with covariance (default:
                        None)

Data processor options: tof-pid-beta:
  --tof-expreso TOF_EXPRESO
                        Expected resolution for the computation of the
                        expected beta (default: None)
  --isProcessEvTime {true,false}
                        tof-pid -> processEvTime : Process Selection options
                        true or false (string) (default: None)

Data processor options: d-q-track barrel-task:
  --isBarrelSelectionTiny {true,false}
                        Run barrel track selection instead of normal(process
                        func. for barrel selection must be true) (default:
                        false)

Data processor options: d-q muons selection:
  --cfgMuonsCuts [CFGMUONSCUT [CFGMUONSCUT ...]]
                        Space separated list of muon cuts in d-q muons
                        selection (default: None)

Data processor options: d-q-filter-p-p-task:
  --cfgPairCuts [CFGPAIRCUTS [CFGPAIRCUTS ...]]
                        Space separated list of pair cuts (default: None)
  --cfgBarrelSels [CFGBARRELSELS [CFGBARRELSELS ...]]
                        Configure Barrel Selection <track-cut>:[<pair-
                        cut>]:<n>,[<track-cut>:[<pair-cut>]:<n>],... | example
                        jpsiO2MCdebugCuts2::1 (default: None)
  --cfgMuonSels [CFGMUONSELS [CFGMUONSELS ...]]
                        Configure Muon Selection <muon-cut>:[<pair-cut>]:<n>
                        example muonQualityCuts:pairNoCut:1 (default: None)
  --isFilterPPTiny {true,false}
                        Run filter tiny task instead of normal
                        (processFilterPP must be true) (default: None)

Data processor options: centrality-table:
  --est [EST [EST ...]]
                        Produces centrality percentiles parameters (default:
                        None)
  V0M                   Produces centrality percentiles using V0 multiplicity.
                        -1: auto, 0: don't, 1: yes. Default: auto (-1)
  Run2SPDtks            Produces Run2 centrality percentiles using SPD
                        tracklets multiplicity. -1: auto, 0: don't, 1: yes.
                        Default: auto (-1)
  Run2SPDcls            Produces Run2 centrality percentiles using SPD
                        clusters multiplicity. -1: auto, 0: don't, 1: yes.
                        Default: auto (-1)
  Run2CL0               Produces Run2 centrality percentiles using CL0
                        multiplicity. -1: auto, 0: don't, 1: yes. Default:
                        auto (-1)
  Run2CL1               Produces Run2 centrality percentiles using CL1
                        multiplicity. -1: auto, 0: don't, 1: yes. Default:
                        auto (-1)

Data processor options: d-q-barrel-track-selection-task, d-q-muons-selection, d-q-event-selection-task, d-q-filter-p-p-task:
  --cfgWithQA {true,false}
                        If true, fill QA histograms (default: None)

Data processor options: v0-selector:
  --d_bz D_BZ           bz field (default: None)
  --v0cospa V0COSPA     v0cospa (default: None)
  --dcav0dau DCAV0DAU   DCA V0 Daughters (default: None)
  --v0Rmin V0RMIN       v0Rmin (default: None)
  --v0Rmax V0RMAX       v0Rmax (default: None)
  --dcamin DCAMIN       dcamin (default: None)
  --dcamax DCAMAX       dcamax (default: None)
  --mincrossedrows MINCROSSEDROWS
                        Min crossed rows (default: None)
  --maxchi2tpc MAXCHI2TPC
                        max chi2/NclsTPC (default: None)

Data processor options: tof-pid, tpc-pid, tpc-pid-full:
  --pid [PID [PID ...]]
                        Produce PID information for the <particle> mass
                        hypothesis (default: None)
  el                    Produce PID information for the Electron mass
                        hypothesis, overrides the automatic setup: the
                        corresponding table can be set off (0) or on (1)
  mu                    Produce PID information for the Muon mass hypothesis,
                        overrides the automatic setup: the corresponding table
                        can be set off (0) or on (1)
  pi                    Produce PID information for the Pion mass hypothesis,
                        overrides the automatic setup: the corresponding table
                        can be set off (0) or on (1)
  ka                    Produce PID information for the Kaon mass hypothesis,
                        overrides the automatic setup: the corresponding table
                        can be set off (0) or on (1)
  pr                    Produce PID information for the Proton mass
                        hypothesis, overrides the automatic setup: the
                        corresponding table can be set off (0) or on (1)
  de                    Produce PID information for the Deuterons mass
                        hypothesis, overrides the automatic setup: the
                        corresponding table can be set off (0) or on (1)
  tr                    Produce PID information for the Triton mass
                        hypothesis, overrides the automatic setup: the
                        corresponding table can be set off (0) or on (1)
  he                    Produce PID information for the Helium3 mass
                        hypothesis, overrides the automatic setup: the
                        corresponding table can be set off (0) or on (1)
  al                    Produce PID information for the Alpha mass hypothesis,
                        overrides the automatic setup: the corresponding table
                        can be set off (0) or on (1)

Additional Helper Command Options:
  --cutLister           List all of the analysis cuts from CutsLibrary.h
                        (default: False)
  --MCSignalsLister     List all of the MCSignals from MCSignalLibrary.h
                        (default: False)
  --debug DEBUG         execute with debug options (default: INFO)
  --logFile             Enable logger for both file and CLI (default: False)

Choice List for debug Parameters:
  NOTSET                Set Debug Level to NOTSET
  DEBUG                 Set Debug Level to DEBUG
  INFO                  Set Debug Level to INFO
  WARNING               Set Debug Level to WARNING
  ERROR                 Set Debug Level to ERROR
  CRITICAL              Set Debug Level to CRITICAL
```

You will receive a message that. also the command can likewise be added after configuring other parameters. For example:
```ruby
 python3 runTableMakerMC.py configs/configTableMakerMCRun3.json -runMC --run 3 --process MuonOnlyWithCov OnlyBCs --cfgMCsignals muFromJpsi Jpsi muFromPsi2S Psi2S --aod Datas/AO2D -h
 ```
 
You will see helper messages again. As long as this command is added in the parameters, the script will not run and will only show a help message.

## Debug and Logging Options for O2DQWorkflows and DownloadLibs.py

We have Debug options if you want to follow the flow in the Interface. For this, you can configure your script as `--debug` `<Level>` in the terminal. You can check which levels are valid and at which level to debug from the table. Also if you want to keep your LOG log in a file then the `--logFile` parameter should be added to the workflow.

The LOG file will be created the same as the workflow name. For example, the file that will be created for tableMaker will be `tableMaker.log`. In addition, if you work with the debug option, the old LOG file will be automatically deleted first, so that there is no confusion in the log files and it does not override. Then a new LOG file will be created.

* You can See Debug Levels in the table:
  
Level | Numeric Value |
| --- | --- |
`NOTSET` | 0 |
`DEBUG` | 10 |
`INFO` | 20 |
`WARNING` | 30 |
`ERROR` | 40 |
`CRITICAL` | 50 |

You can see the debug messages of the numeric value you selected and the level above. If you want debug with `--debug` parameter, you must select the Level you want to debug.

Example usage Logging for Both File and terminal:

```ruby 
  python3 runTableMakerMC.py configs/configTableMakerMCRun3.json -runMC --run 3  --debug DEBUG --logFile --process MuonOnlyWithCov OnlyBCs --cfgMCsignals muFromJpsi Jpsi muFromPsi2S Psi2S --aod Datas/AO2D.root --cfgMuonCuts muonQualityCuts muonTightQualityCutsForTests --syst pp --add_track_prop
```

Example usage for only logging to terminal:

```ruby 
  python3 runTableMakerMC.py configs/configTableMakerMCRun3.json -runMC --run 3 --debug DEBUG --process MuonOnlyWithCov OnlyBCs --cfgMCsignals muFromJpsi Jpsi muFromPsi2S Psi2S --aod Datas/AO2D.root --cfgMuonCuts muonQualityCuts muonTightQualityCutsForTests --syst pp --add_track_prop
```

For example, when the file is logged, you should see a result like this when you open the relevant file.

```ruby 
  2022-08-17 17:15:06,628 - [DEBUG]  - [internal-dpl-aod-reader] aod-file : reducedAod.root
  2022-08-17 17:15:06,628 - [DEBUG]  - [internal-dpl-aod-reader] aod-reader-json : configs/readerConfiguration_reducedEventMC.json
  2022-08-17 17:15:06,628 - [DEBUG]  - [analysis-event-selection] processSkimmed : true
  2022-08-17 17:15:06,628 - [DEBUG]  - [analysis-track-selection] processSkimmed : false
  2022-08-17 17:15:06,628 - [DEBUG]  - [analysis-muon-selection] cfgMuonCuts : muonQualityCuts,muonTightQualityCutsForTests
  2022-08-17 17:15:06,629 - [DEBUG]  - [analysis-muon-selection] cfgMuonMCSignals : muFromJpsi,muFromPsi2S
  2022-08-17 17:15:06,629 - [DEBUG]  - [analysis-muon-selection] processSkimmed : true
  2022-08-17 17:15:06,629 - [DEBUG]  - [analysis-same-event-pairing] cfgMuonCuts : muonQualityCuts,muonTightQualityCutsForTests
  2022-08-17 17:15:06,629 - [DEBUG]  - [analysis-same-event-pairing] cfgBarrelMCRecSignals : mumuFromJpsi,mumuFromPsi2S,dimuon
  2022-08-17 17:15:06,629 - [DEBUG]  - [analysis-same-event-pairing] cfgBarrelMCGenSignals : Jpsi,Psi2S
  2022-08-17 17:15:06,629 - [DEBUG]  - [analysis-same-event-pairing] processJpsiToEESkimmed : false
  2022-08-17 17:15:06,629 - [DEBUG]  - [analysis-same-event-pairing] processJpsiToMuMuSkimmed : true
  2022-08-17 17:15:06,630 - [DEBUG]  - [analysis-same-event-pairing] processJpsiToMuMuVertexingSkimmed : false
  2022-08-17 17:15:06,630 - [DEBUG]  - [analysis-dilepton-track] processDimuonMuonSkimmed : false
  2022-08-17 17:15:06,630 - [INFO] Command to run:
  2022-08-17 17:15:06,630 - [INFO] o2-analysis-dq-efficiency --configuration json://tempConfigDQEfficiency.json -b --aod-writer-json configs/writerConfiguration_dileptonMC.json
  2022-08-17 17:15:06,630 - [INFO] Args provided configurations List
  2022-08-17 17:15:06,631 - [INFO] --cfgFileName : configs/configAnalysisMC.json 
  2022-08-17 17:15:06,631 - [INFO] --add_mc_conv : False 
  2022-08-17 17:15:06,631 - [INFO] --add_fdd_conv : False 
  2022-08-17 17:15:06,631 - [INFO] --add_track_prop : False 
  2022-08-17 17:15:06,631 - [INFO] --logFile : True 
  2022-08-17 17:15:06,631 - [INFO] --aod : reducedAod.root 
  2022-08-17 17:15:06,631 - [INFO] --reader : configs/readerConfiguration_reducedEventMC.json 
  2022-08-17 17:15:06,632 - [INFO] --writer : configs/writerConfiguration_dileptonMC.json 
  2022-08-17 17:15:06,632 - [INFO] --analysis : ['muonSelection', 'eventSelection', 'sameEventPairing'] 
  2022-08-17 17:15:06,632 - [INFO] --process : ['JpsiToMuMu'] 
  2022-08-17 17:15:06,632 - [INFO] --autoDummy : true 
  2022-08-17 17:15:06,632 - [INFO] --cfgMuonCuts : muonQualityCuts,muonTightQualityCutsForTests 
  2022-08-17 17:15:06,632 - [INFO] --cfgMuonMCSignals : muFromJpsi,muFromPsi2S 
  2022-08-17 17:15:06,633 - [INFO] --cfgBarrelMCRecSignals : mumuFromJpsi,mumuFromPsi2S,dimuon 
  2022-08-17 17:15:06,633 - [INFO] --cfgBarrelMCGenSignals : Jpsi,Psi2S 
  2022-08-17 17:15:06,633 - [INFO] --cutLister : False 
  2022-08-17 17:15:06,633 - [INFO] --MCSignalsLister : False 
  2022-08-17 17:15:06,633 - [INFO] --debug : DEBUG 
```
## Some Things You Should Be Careful For Using and Development

* There are also filters for some arguments. No value should be entered outside of these filters (look at the
choices).
* If the argument can take more than one value, when adding a new property choices is a list and the values
must be converted to comma-separated strings
* if your dataset is for run3, o2-analysis-trackextension will be automatically deleted from your workflow as if you define `--add_track_prop` argument for track-propagation. If the production of the data you want to analyze is new, you should add the o2-analysis-track-propagation task to your workflow with the `--add_track_prop` parameter. You can found detalis from there [`Click Here`](https://aliceo2group.github.io/analysis-framework/docs/helperTasks/trackselection.html?highlight=some%20of%20the%20track%20parameters)

## Some Notes Before The Instructions

* You don't have to configure all the parameters in the Python interface. the parameter you did not configure will remain as the value in the JSON.
* Don't forget to configure your Config JSON file in interface for each workflow and also configure extra `-run<Data|MC>` parameters for tableMaker workflow only.
* Sometimes you may need to add extra tables and transformations to your workflow to resolve the errors you get. These are related to the data model and the production tag. It is stated in the steps that they will be used when errors are received. If you get an error about these add the relevant parameter to your workflow.

## Interface Modes: JSON Overrider and JSON Additional

The only select parameter gives you a choice depending on whether you want to keep your old configurations of the interface.

If `--onlySelect` is configured to true, you will run in JSON overrider interface mode (default value of this parameter is true).
only commands entered in the terminal for some parameters will preserved, while others are set to false.

If --onlySelect is false, you will run in JSON additional interface mode. the values ​​in your original JSON file will be preserved, values ​​entered from the terminal will be appended to the JSON. It would be much better to explain this through an example.

For example, let's say we're working on a tableMaker:

  ```ruby
    "table-maker": {
        "cfgEventCuts": "eventStandardNoINT7",
        "cfgBarrelTrackCuts": "jpsiO2MCdebugCuts2,jpsiO2MCdebugCuts3,jpsiO2MCdebugCuts,kaonPID",
        "cfgMuonCuts": "muonQualityCuts,muonTightQualityCutsForTests",
        "cfgBarrelLowPt": "0.5",
        "cfgMuonLowPt": "0.5",
        "cfgMinTpcSignal": "50",
        "cfgMaxTpcSignal": "200",
        "cfgNoQA": "false",
        "cfgDetailedQA": "true",
        "cfgIsRun2": "false",
        "processFull": "true",
        "processFullWithCov": "true",
        "processFullWithCent": "false",
        "processBarrelOnlyWithV0Bits": "false",
        "processBarrelOnlyWithEventFilter": "false",
        "processBarrelOnlyWithQvector" : "false",
        "processBarrelOnlyWithCent": "false",
        "processBarrelOnlyWithCov": "false",
        "processBarrelOnly": "false",
        "processMuonOnlyWithCent": "false",
        "processMuonOnlyWithCov": "false",
        "processMuonOnly": "false",
        "processMuonOnlyWithQvector": "false",
        "processMuonOnlyWithFilter": "false",
        "processOnlyBCs": "true"
    },
  ```

As seen here, the process functions for Full, FullWithCov, and OnlyBCs are true. Let's assume that we made the following configuration for the interface in the terminal:

```ruby
python3 runTableMaker.py configs/configTableMakerDataRun2.json -runData --aod Datas/AO2D_PbPbDataRun2_LHC15o.root --process OnlyBCs BarrelOnlyWithCent --onlySelect true
```
P.S. Since onlySelect is true (you don't need to add it to your workflow when configuring `--onlySelect` to true, its default value is true I just added it to show, JSON Overrider Mode):

  ```ruby
    "table-maker": {
        "cfgEventCuts": "eventStandardNoINT7",
        "cfgBarrelTrackCuts": "jpsiO2MCdebugCuts2,jpsiO2MCdebugCuts3,jpsiO2MCdebugCuts,kaonPID",
        "cfgMuonCuts": "muonQualityCuts,muonTightQualityCutsForTests",
        "cfgBarrelLowPt": "0.5",
        "cfgMuonLowPt": "0.5",
        "cfgMinTpcSignal": "50",
        "cfgMaxTpcSignal": "200",
        "cfgNoQA": "false",
        "cfgDetailedQA": "true",
        "cfgIsRun2": "false",
        "processFull": "false",
        "processFullWithCov": "false",
        "processFullWithCent": "false",
        "processBarrelOnlyWithV0Bits": "false",
        "processBarrelOnlyWithEventFilter": "false",
        "processBarrelOnlyWithQvector" : "false",
        "processBarrelOnlyWithCent": "true",
        "processBarrelOnlyWithCov": "false",
        "processBarrelOnly": "false",
        "processMuonOnlyWithCent": "false",
        "processMuonOnlyWithCov": "false",
        "processMuonOnly": "false",
        "processMuonOnlyWithQvector": "false",
        "processMuonOnlyWithFilter": "false",
        "processOnlyBCs": "true"
    },
  ```

As you can see, only the OnlyBCs and BarrelOnlyWithCent process functions are set to true, while all other process functions in the tableMaker are set to false.

If we configured onlySelect to false:

```ruby
python3 runTableMaker.py configs/configTableMakerDataRun2.json -runData --aod Datas/AO2D_PbPbDataRun2_LHC15o.root --process OnlyBCs BarrelOnlyWithCent --onlySelect false (JSON Additional Mode)
```

Then our output would be:

  ```ruby
    "table-maker": {
        "cfgEventCuts": "eventStandardNoINT7",
        "cfgBarrelTrackCuts": "jpsiO2MCdebugCuts2,jpsiO2MCdebugCuts3,jpsiO2MCdebugCuts,kaonPID",
        "cfgMuonCuts": "muonQualityCuts,muonTightQualityCutsForTests",
        "cfgBarrelLowPt": "0.5",
        "cfgMuonLowPt": "0.5",
        "cfgMinTpcSignal": "50",
        "cfgMaxTpcSignal": "200",
        "cfgNoQA": "false",
        "cfgDetailedQA": "true",
        "cfgIsRun2": "false",
        "processFull": "true",
        "processFullWithCov": "true",
        "processFullWithCent": "false",
        "processBarrelOnlyWithV0Bits": "false",
        "processBarrelOnlyWithEventFilter": "false",
        "processBarrelOnlyWithQvector" : "false",
        "processBarrelOnlyWithCent": "true",
        "processBarrelOnlyWithCov": "false",
        "processBarrelOnly": "false",
        "processMuonOnlyWithCent": "false",
        "processMuonOnlyWithCov": "false",
        "processMuonOnly": "false",
        "processMuonOnlyWithQvector": "false",
        "processMuonOnlyWithFilter": "false",
        "processOnlyBCs": "true"
    },
  ```

As you can see, the old process values ​​Full and FullWithCov remained true, in addition, the BarrelOnlyWithCent process function was set to true. OnlyBCs was already true and remains true.

This is the case for the `--analysis`, `--process`, `--pid` and `--est` parameters.

A similar situation applies to Analysis Cut configurations and MC Signal configurations. Suppose there is a configuration like this in it (for tableReader):

  ```ruby
    "analysis-track-selection": {
        "cfgTrackCuts": "jpsiO2MCdebugCuts2",
        "cfgTrackMCSignals": "eFromJpsi,eFromLMeeLF",
        "cfgQA": "true",
        "processSkimmed": "true",
        "processDummy": "false"
    },
  ```

Here we will configure the track cuts:

```ruby
python3 runTableReader.py configs/configAnalysisData.json --aod reducedAod.root --cfgTrackCuts jpsiPID1 jpsiPID2
```

The JSON is in overrider mode as the default is onlySelect true and the equivalent of this configuration is:

  ```ruby
    "analysis-track-selection": {
        "cfgTrackCuts": "jpsiPID1,jpsiPID2",
        "cfgTrackMCSignals": "eFromJpsi,eFromLMeeLF",
        "cfgQA": "true",
        "processSkimmed": "true",
        "processDummy": "false"
    },
  ```

As we can see, the old cut values ​​were deleted, the new cut values ​​were taken from the CLI.

If onlySelect is False:

```ruby
python3 runTableReader.py configs/configAnalysisData.json --aod reducedAod.root --cfgTrackCuts jpsiPID1 jpsiPID2 --onlySelect false
```

Then the JSON is in additional mode and the equivalent of this configuration is:

  ```ruby
    "analysis-track-selection": {
        "cfgTrackCuts": "jpsiO2MCdebugCuts2,jpsiPID1,jpsiPID2",
        "cfgTrackMCSignals": "eFromJpsi,eFromLMeeLF",
        "cfgQA": "true",
        "processSkimmed": "true",
        "processDummy": "false"
    },
  ```

As we can see, our old track cut value has been preserved and extra new ones have been added.

This is the same for all analysis cuts, MC Signals, barrel and muon sels in filterPP and mixing vars.

This is the main reason why Interface works in these two modes. If you already have a JSON configuration file prepared for a specific data for analysis, it makes sense to use JSON additional mode if you just want to add some values. Because you will want to preserve the old values.

If you are going to do an analysis from zero and you will prepare your JSON configuration file accordingly, or if you want to completely change your analysis values, then it makes sense to use JSON overrider mode. Because the default JSON files must be manipulated in accordance with the analysis (like configAnalysisData.json) or you choose this mode to change the complete analysis values



## Project Architecture For Per Script

For the architecture of the project, you can view the diagrams below for each dq workflow script.


<div align="center">
<img src="images/table-maker_script.jpg" width="100%" alt="TableMaker Workflow">
</div>


[← Go back to Instructions For Instructions for TAB Autocomplete](3_InstructionsforTABAutocomplete.md) | [↑ Go to the Table of Content ↑](../README.md) | [Continue to Instructions For Python Scripts →](5_InstructionsForPythonScripts.md)