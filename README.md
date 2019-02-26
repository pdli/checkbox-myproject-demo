# checkbox-myproject-demo

#### Project Introduction:
Checkbox is a system testing platform for Ubuntu. It aims to provide a common framework to run all types of tests, from hardware tests, to command line tests, unit tests or desktop tests. It is developed & maintained by Canonical and used by Canonical QA to run validation test on both Client & Server. It includes both manual and automation validation testing.

The project will demo how to customize test plan and launcher of the Checkbox.


#### User Guide:

1. Commands to run checkbox-cli
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
```
2. Customize test plan in a new Provider
```
Build checkbox snap >> snapcraft
Install checkbox snap >> snap install <snappy_name> --devmode
Launch checkbox >> launcher_name
```
3. Customize an app with new Launcher
```
xxx
```

#### Reference Links:
- [CheckBox User Guide](https://checkbox.readthedocs.io/en/latest/using.html#getting-started)
- [Customize Launcher](https://checkbox.readthedocs.io/en/latest/custom-app.html)
