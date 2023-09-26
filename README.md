<img src="https://img.shields.io/github/license/imairi/RIBsTreeMaker.svg">

# RIBsTreeMaker

<p align="center">
  <img src="https://raw.githubusercontent.com/imairi/RIBsTreeMaker/master/images/logo.png" width="500">
</p>

RIBsTreeMaker visualize [RIBs](https://github.com/uber/RIBs) business logic tree. The output style is org-mode mindmap.

## Usage
```
swift run RIBsTreeMaker [path/to/iOSproject] --under [RIB name] [--format [plantUML or whimsical (default: plantUML)]] [--summary]
```

### Options

* **under**: The tree will be displayed only under the RIB.
* **format**: Specify the output format. The format that can be specified is as follows:
  * **plantUML(Default)**: The output is in PlantUML format.
  * **whimsical**: Outputs code that can be used in [Whimsical](https://whimsical.com).
* **summary**: The RIB's summary is displayed in the node. The summary is retrieved `// SUMMARY: RIB summary` from the Builder file.

## Visualize for mindmap
The output style is org-mode mindmap.

```uml
@startmindmap
* Root
** LoggedOut<<noView>>
*** TermsOfUse
**** FailedLoading
*** Welcome
**** SignInFailedDialog
**** ForgotPassword
***** SMSAuthentication
****** ResetPassword
** LoggedIn<<noView>>
@endmindmap
```

Additionally, the mindmap style is set to detect easily the RIB has own view or not.

```
<style>
mindmapDiagram {
  . * {
    BackGroundColor #FFF
    LineColor #192f60
    Shadowing 0.0
    RoundCorner 20
    LineThickness 2.0
  }
  .noView * {
    BackGroundColor #FFF
    LineColor #d20b52
  }
}
</style>
```

For example, if use PlantUML the RIBs tree is visualized like the below.


<p align="center">
  <img src="https://raw.githubusercontent.com/imairi/RIBsTreeMaker/master/images/example_tree.png" width="800">
</p>

# Credits
RIBsTreeMaker is inspired by [flock](https://github.com/naoty/flock/). Modified and adapted to RIBs architecture.
