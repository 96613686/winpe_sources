# Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::.ctor

- ea: `0x7790`
- end: `0x780f`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::.ctor`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x63050`
- `0x644d0`

## string_xrefs

- `0x77e4`: `targetPath`
- `0x77ef`: `elevationServicePath`

## pseudocode

```c

```

## disassembly

```asm
0x7790  ldarg.0
0x7791  ldsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::InstallerShortcutName
0x7796  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<ApplicationShortcutName>k__BackingField
0x779b  ldarg.0
0x779c  ldsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::InstallerAddRemoveProgramsDesciption
0x77a1  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<ApplicationDescription>k__BackingField
0x77a6  ldarg.0
0x77a7  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::LegacyInstallerAppUserModelId
0x77ac  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<AppplicationUserModelId>k__BackingField
0x77b1  ldarg.0
0x77b2  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceName
0x77b7  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<ElevationServiceName>k__BackingField
0x77bc  ldarg.0
0x77bd  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDisplayName
0x77c2  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<ElevationServiceDisplayName>k__BackingField
0x77c7  ldarg.0
0x77c8  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDescription
0x77cd  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<ElevationServiceDescription>k__BackingField
0x77d2  ldarg.0
0x77d3  call     instance void [mscorlib]System.Object::.ctor()
0x77d8  ldarg.1
0x77d9  ldstr    aApplicationver// "applicationVersion"
0x77de  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x77e3  ldarg.2
0x77e4  ldstr    aTargetpath// "targetPath"
0x77e9  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x77ee  ldarg.3
0x77ef  ldstr    aElevationservi// "elevationServicePath"
0x77f4  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x77f9  ldarg.0
0x77fa  ldarg.1
0x77fb  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<ApplicationVersion>k__BackingField
0x7800  ldarg.0
0x7801  ldarg.2
0x7802  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<TargetPath>k__BackingField
0x7807  ldarg.0
0x7808  ldarg.3
0x7809  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::<ElevationServicePath>k__BackingField
0x780e  ret
```
