# Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::AddUpdateRelatedGroupPolicyRegValues

- ea: `0xdaf0`
- end: `0xdb52`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::AddUpdateRelatedGroupPolicyRegValues`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xd130`

## callees

- `0xdaf0`
- `0xdb60`

## string_xrefs

- `0xdb0c`: `ActiveDirectoryJoined`
- `0xdb21`: `AzureActiveDirectoryJoined`

## pseudocode

```c

```

## disassembly

```asm
0xdaf0  ldstr    aWufbpolicynots// "WUfBPolicyNotSet"
0xdaf5  stloc.0
0xdaf6  ldarg.1
0xdaf7  ldc.i4.2
0xdaf8  ldc.i4.0
0xdaf9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0xdafe  stloc.1
0xdaff  ldloc.1
0xdb00  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::ActiveDirectoryRegKey
0xdb05  call     bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::IsKeyValueSet(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey baseKey, string activeDirectoryRegKey)
0xdb0a  brfalse.s loc_DB14
0xdb0c  ldstr    aActivedirector// "ActiveDirectoryJoined"
0xdb11  stloc.0
0xdb12  leave.s  loc_DB45
0xdb14  ldloc.1
0xdb15  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AzureActiveDirectoryRegKey
0xdb1a  call     bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::IsKeyValueSet(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey baseKey, string activeDirectoryRegKey)
0xdb1f  brfalse.s loc_DB29
0xdb21  ldstr    aAzureactivedir// "AzureActiveDirectoryJoined"
0xdb26  stloc.0
0xdb27  leave.s  loc_DB45
0xdb29  ldarg.1
0xdb2a  ldnull
0xdb2b  call     int32 [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Utility.MicrosoftUpdateUtilities::GetConsumerAutomaticUpdateRegKey(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger)
0xdb30  ldc.i4.1
0xdb31  bne.un.s loc_DB39
0xdb33  ldstr    aAdvancedoption// "AdvancedOptionsConsumerSet"
0xdb38  stloc.0
0xdb39  leave.s  loc_DB45
0xdb3b  ldloc.1
0xdb3c  brfalse.s loc_DB44
0xdb3e  ldloc.1
0xdb3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb44  endfinally
0xdb45  ldarg.0
0xdb46  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AllowMUUpdateServiceProperty
0xdb4b  ldloc.0
0xdb4c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xdb51  ret
```
