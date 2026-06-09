# Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::DeleteShortcut

- ea: `0x8350`
- end: `0x83f5`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::DeleteShortcut`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x62300`

## callees

- `0x7480`
- `0x7490`
- `0x74b0`
- `0x8350`
- `0x8400`

## string_xrefs

- `0x838d`: `Failed to delete the installer shortcut`
- `0x83c0`: `No installer shortcut found to delete`
- `0x83e3`: `Failed to delete installer shortcut`

## pseudocode

```c

```

## disassembly

```asm
0x8350  ldarg.0
0x8351  ldarg.1
0x8352  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::GetInstallerShortcut(string shortcutName)
0x8357  stloc.0
0x8358  ldarg.0
0x8359  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x835e  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IShortcutService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ShortcutService()
0x8363  ldc.i4.1
0x8364  newarr   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut
0x8369  dup
0x836a  ldc.i4.0
0x836b  ldloc.0
0x836c  stelem.ref
0x836d  ldnull
0x836e  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IShortcutService::DeleteShortcuts(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation>, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x8373  pop
0x8374  leave.s  loc_83F4
0x8376  stloc.1
0x8377  ldarg.0
0x8378  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x837d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Telemetry()
0x8382  dup
0x8383  brtrue.s loc_8388
0x8385  pop
0x8386  br.s     loc_839F
0x8388  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::DELETEINSTALLERSHORTCUTFAILEDEVENT
0x838d  ldstr    aFailedToDelete_0// "Failed to delete the installer shortcut"
0x8392  ldnull
0x8393  ldloc.1
0x8394  ldnull
0x8395  ldc.i4.0
0x8396  ldnull
0x8397  ldc.i4.0
0x8398  ldnull
0x8399  ldc.i4.0
0x839a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x839f  ldloc.1
0x83a0  isinst   [mscorlib]System.IO.FileNotFoundException
0x83a5  brtrue.s loc_83AF
0x83a7  ldloc.1
0x83a8  isinst   [mscorlib]System.IO.DirectoryNotFoundException
0x83ad  brfalse.s loc_83D1
0x83af  ldarg.0
0x83b0  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x83b5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x83ba  dup
0x83bb  brtrue.s loc_83C0
0x83bd  pop
0x83be  br.s     loc_83CF
0x83c0  ldstr    aNoInstallerSho// "No installer shortcut found to delete"
0x83c5  call     T0x2B000010
0x83ca  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x83cf  leave.s  loc_83F4
0x83d1  ldarg.0
0x83d2  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x83d7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x83dc  dup
0x83dd  brtrue.s loc_83E2
0x83df  pop
0x83e0  br.s     loc_83F2
0x83e2  ldloc.1
0x83e3  ldstr    aFailedToDelete_1// "Failed to delete installer shortcut"
0x83e8  call     T0x2B000010
0x83ed  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x83f2  leave.s  loc_83F4
0x83f4  ret
```
