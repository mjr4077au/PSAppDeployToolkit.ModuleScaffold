# PSAppDeployToolkit.ModuleScaffold

## Synopsis

A baseline scaffolding for PSAppDeployToolkit modules. Based on Catesta with some fixes for correctness.

## Description

This is PSAppDeployToolkit's build system extrapolated into an isolated component for use with developing new PSAppDeployToolkit modules.

Right now, it's rather static and requires manual renaming/rebranding. At some point I'll look at making a script to generate a scaffold with whatever name is required.

## Why

The build system for PSAppDeployToolkit has some cool things in it that enforce a high level of code quality upon built modules. Some of these things are:

* CommandTable generation to ensure that common functions like `ForEach-Object`, `Where-Object`, etc, cannot be redefined.
* Ensures some secure practices on the PowerShell code, such as preventing use of the `$env:` provider, which can be redefined at runtime.
* Ensures all script files are UTF-8 with BOM, which is important for internationalisation in Windows PowerShell 5.1 targets.
* Automates documentation generation with platyPS and Docusaurus for use with your websites.
* Many other things as provided by Catesta out of the box.

## Getting Started

### Prerequisites

From PowerShell, run `& .\actions_bootstrap.ps1` to install the required pre-requisites. This is only needed once.

### Building

Run `Invoke-Build -File .\src\PSAppDeployToolkit.ModuleScaffold.build.ps1`, which will compile this module (and your own if you use this project as your basis).

## Author

Mitch Richters

