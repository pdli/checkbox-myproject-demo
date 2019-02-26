# checkbox-myproject-demo

#### Project Introduction:
Checkbox is a system testing platform for Ubuntu. It aims to provide a common framework to run all types of tests, from hardware tests, to command line tests, unit tests or desktop tests. It is developed & maintained by Canonical and used by Canonical QA to run validation test on both Client & Server. It includes both manual and automation validation testing.

The project will demo how to customize test plan and launcher of the Checkbox.


#### User Guide:
1. Entities
``` 
- Launcher
  1) Interactive Dashboard
  2) Run CMD: >> checkbox-cli <my-launcher>
  
- Provider
  1) Test Plan - (listed in Dashboard, calling jobs to be run)
  2) Jobs - (commands, categorized)
  3) Run CMD: >> ./manage.py install
```
2. Commands to run checkbox-cli
```
- Run interactive session: 
  >> checkbox-cli
  
- List job/test plan/ category/ file/ template/ all-jobs:
  >> checkbox-cli run <individual test plan> [--non-interactive] [-o FILE] [-f FORMAT]
    
- List jobs of a test plan: 
  >> checkbox-cli list-bootstrapped <test plan>

- Export a test plan:
  >> checkbox-cli tp-export <test plan>

- Launch a custom checkbox:
  >> checkbox-cli <my-launcher>
  
- Run job/test plan: 
  >> checkbox-cli run <test-plan / jobs>
  
- Remotely run checkbox:
  - slave node: >> checkbox-cli slave
  - master node: >> checkbox-cli master HOST [/Path/To/Launcher]
```
3. Create a new Provider
```
- Step-1 Create an empty provider
  >> checkbox-cli startprovider --empty <com.canonical.qa.myproject>:<plainbox-provider-myproject>
  >> cd <com.canonical.qa.myproject>:<plainbox-provider-myproject>
  >> mkdir units
  
- Step-2(optional) Add jobs
  >> touch units/jobs.pxu
  
- Step-3 Add test plan
  >> touch units/test-plan.pxu
  
- Step-4 Running jobs from a newly created provider
  >> ./manage.py <install | develop>
  >> checkbox-cli [run] [test-plan | jobs]
  
- (Recommended) Side-loading Providers
  == Installed provider will be overwriten, if it is located here: 
  >> /var/tmp/checkbox-proviers/
```
4. Create a new Launcher/App(For snappy Ubuntu Core)
```
- Step-1 Initialize
  >> snapcraft init
  >> git init
 
- Step-1 Create a new Provider

- Step-2 Create a new Launcher
  >> mkdir launchers
  >> touch launchers/<myproject>-test-runner
  >> touch launchers/checkbox-cli-wrapper
  >> chmod +x launchers/*
 
 - Step-3 Declard the launcher in your Snap
  >> vim snap/snapcraft.yaml
 
 - Step-4 Snap it
  >> snapcraft
 
 - Step-5 Run new App
  >> snap install <new-snap> --devmode
```

#### Reference Links:
- [Checkbox User Guide](https://checkbox.readthedocs.io/en/latest/using.html#getting-started)
- [Checkbox Projects](https://launchpad.net/checkbox-project)
- [Checkbox Stack](https://checkbox.readthedocs.io/en/latest/stack.html)
