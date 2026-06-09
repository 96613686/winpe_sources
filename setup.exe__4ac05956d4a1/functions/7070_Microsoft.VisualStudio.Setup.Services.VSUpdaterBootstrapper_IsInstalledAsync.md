# Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::IsInstalledAsync

- ea: `0x7070`
- end: `0x7113`
- name: `Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::IsInstalledAsync`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x90450`

## callees

- `0x7070`
- `0x7120`
- `0x7210`
- `0x72c0`
- `0x76a0`
- `0x76e0`

## string_xrefs

- `0x709b`: `VSUpdater does not exist.`
- `0x70ca`: `VSUpdater is not properly signed.`
- `0x70f8`: `VSUpdater is not registered.`

## pseudocode

```c

```

## disassembly

```asm
0x7070  ldarg.0
0x7071  call     instance string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetVSUpdaterPath()
0x7076  stloc.0
0x7077  ldarg.0
0x7078  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x707d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x7082  ldloc.0
0x7083  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x7088  brtrue.s loc_70B0
0x708a  ldarg.0
0x708b  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x7090  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x7095  dup
0x7096  brtrue.s loc_709B
0x7098  pop
0x7099  br.s     loc_70AA
0x709b  ldstr    aVsupdaterDoesN// "VSUpdater does not exist."
0x70a0  call     T0x2B000010
0x70a5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x70aa  ldsfld   class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.TplExtensions::FalseTask
0x70af  ret
0x70b0  ldarg.0
0x70b1  ldloc.0
0x70b2  call     instance bool Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::IsFileMicrosoftSigned(string filePath)
0x70b7  brtrue.s loc_70DF
0x70b9  ldarg.0
0x70ba  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x70bf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x70c4  dup
0x70c5  brtrue.s loc_70CA
0x70c7  pop
0x70c8  br.s     loc_70D9
0x70ca  ldstr    aVsupdaterIsNot// "VSUpdater is not properly signed."
0x70cf  call     T0x2B000010
0x70d4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x70d9  ldsfld   class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.TplExtensions::FalseTask
0x70de  ret
0x70df  ldarg.0
0x70e0  call     instance bool Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::IsVSUpdaterRegistered()
0x70e5  brtrue.s loc_710D
0x70e7  ldarg.0
0x70e8  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x70ed  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x70f2  dup
0x70f3  brtrue.s loc_70F8
0x70f5  pop
0x70f6  br.s     loc_7107
0x70f8  ldstr    aVsupdaterIsNot_0// "VSUpdater is not registered."
0x70fd  call     T0x2B000010
0x7102  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7107  ldsfld   class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.TplExtensions::FalseTask
0x710c  ret
0x710d  ldsfld   class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.TplExtensions::TrueTask
0x7112  ret
```
