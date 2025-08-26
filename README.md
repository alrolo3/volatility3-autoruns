# Volatility3 Autoruns plugin
Modified of PXS-LU-CSIRT autoruns plugin for Volatility 3

This plugin has been tested using tomchop's own test_data image and does match the expected output.

## Changes

change requeriments to new volatility version 2.26.0 and also all callings to self.context and config across all plugin.

```
requirements.ModuleRequirement(
    name = 'kernel',
    description = 'Windows kernel',
    architectures = ["Intel32", "Intel64"]
),
```

## How-to

Drop the autorun.py file in the ```plugins/windows``` directory of volatility 3. Volatility should automatically detect it, then call it by typing ```windows.autorun.Autoruns```

Here are the available options for this plugin:

```--verbose``` Shows extra information that would normally be filtered (like Services from the System32 folder)

```--asep=autoruns services appinit winlogon tasks activesetup``` - Use it to focus on specific ASEPS. Options are: autoruns (Run, RunOnce, etc.), services, appinit, winlogon, tasks, and activesetup. You can specify any combination of them with a space-separated list: autoruns services. Leave blank to get all ASEPs.

## Special thanks

Special thanks to tomchop and PXS-LU-CSIRT for making the plugin available for the community.
