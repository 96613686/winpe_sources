# Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::CreateShortcut

- ea: `0x82b0`
- end: `0x8350`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::CreateShortcut`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x62200`

## callees

- `0x7480`
- `0x7490`
- `0x74b0`
- `0x7810`
- `0x7880`
- `0x78a0`
- `0x82b0`
- `0x8400`

## string_xrefs

- `0x831b`: `Failed to create installer shortcut`
- `0x833e`: `Failed to create installer shortcut`

## pseudocode

```c

```

## disassembly

```asm
0x82b0  ldarg.0
0x82b1  ldarg.1
0x82b2  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ApplicationShortcutName()
0x82b7  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::GetInstallerShortcut(string shortcutName)
0x82bc  stloc.0
0x82bd  ldloc.0
0x82be  ldarg.1
0x82bf  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_TargetPath()
0x82c4  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x82c9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut::set_WorkingDirectory(string)
0x82ce  ldloc.0
0x82cf  ldarg.1
0x82d0  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_TargetPath()
0x82d5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut::set_TargetPath(string)
0x82da  ldloc.0
0x82db  ldarg.1
0x82dc  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_AppplicationUserModelId()
0x82e1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut::set_AppUserModelId(string)
0x82e6  ldarg.0
0x82e7  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x82ec  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IShortcutService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ShortcutService()
0x82f1  ldc.i4.1
0x82f2  newarr   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut
0x82f7  dup
0x82f8  ldc.i4.0
0x82f9  ldloc.0
0x82fa  stelem.ref
0x82fb  ldnull
0x82fc  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IShortcutService::CreateShortcuts(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut>, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x8301  pop
0x8302  leave.s  loc_834F
0x8304  stloc.1
0x8305  ldarg.0
0x8306  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x830b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Telemetry()
0x8310  dup
0x8311  brtrue.s loc_8316
0x8313  pop
0x8314  br.s     loc_832D
0x8316  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CREATEINSTALLERSHORTCUTFAILEDEVENT
0x831b  ldstr    aFailedToCreate// "Failed to create installer shortcut"
0x8320  ldnull
0x8321  ldloc.1
0x8322  ldnull
0x8323  ldc.i4.0
0x8324  ldnull
0x8325  ldc.i4.0
0x8326  ldnull
0x8327  ldc.i4.0
0x8328  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x832d  ldarg.0
0x832e  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x8333  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x8338  dup
0x8339  brtrue.s loc_833E
0x833b  pop
0x833c  br.s     loc_834D
0x833e  ldstr    aFailedToCreate// "Failed to create installer shortcut"
0x8343  call     T0x2B000010
0x8348  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x834d  leave.s  loc_834F
0x834f  ret
```
