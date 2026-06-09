# Microsoft.VisualStudio.Setup.Installer.Program::Execute

- ea: `0xc0f0`
- end: `0xc1a2`
- name: `Microsoft.VisualStudio.Setup.Installer.Program::Execute`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbf50`

## callees

- `0xb290`
- `0xc0f0`
- `0xc1b0`
- `0xd0f0`

## string_xrefs

- `0xc10c`: `Visual Studio Installer Version: {0}`
- `0xc128`: `Raw Command line: {0}`
- `0xc152`: `Parsed command line options: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xc0f0  ldarg.0
0xc0f1  ldc.i4.1
0xc0f2  call     T0x2B000052
0xc0f7  stloc.0
0xc0f8  ldarg.0
0xc0f9  ldc.i4.1
0xc0fa  call     T0x2B00004E
0xc0ff  stloc.1
0xc100  ldarg.0
0xc101  ldc.i4.1
0xc102  call     T0x2B000053
0xc107  stloc.2
0xc108  ldloc.1
0xc109  brfalse.s loc_C124
0xc10b  ldloc.1
0xc10c  ldstr    aVisualStudioIn_0// "Visual Studio Installer Version: {0}"
0xc111  ldc.i4.1
0xc112  newarr   [mscorlib]System.Object
0xc117  dup
0xc118  ldc.i4.0
0xc119  call     string Microsoft.VisualStudio.Setup.Installer.InstallerInfo::get_InformationalVersion()
0xc11e  stelem.ref
0xc11f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0xc124  ldloc.1
0xc125  brfalse.s loc_C140
0xc127  ldloc.1
0xc128  ldstr    aRawCommandLine// "Raw Command line: {0}"
0xc12d  ldc.i4.1
0xc12e  newarr   [mscorlib]System.Object
0xc133  dup
0xc134  ldc.i4.0
0xc135  call     string [mscorlib]System.Environment::get_CommandLine()
0xc13a  stelem.ref
0xc13b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0xc140  ldarg.1
0xc141  brtrue.s loc_C146
0xc143  ldnull
0xc144  br.s     loc_C14C
0xc146  ldarg.1
0xc147  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_Options()
0xc14c  brfalse.s loc_C171
0xc14e  ldloc.1
0xc14f  brfalse.s loc_C171
0xc151  ldloc.1
0xc152  ldstr    aParsedCommandL// "Parsed command line options: {0}"
0xc157  ldc.i4.1
0xc158  newarr   [mscorlib]System.Object
0xc15d  dup
0xc15e  ldc.i4.0
0xc15f  ldarg.1
0xc160  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_Options()
0xc165  ldc.i4.1
0xc166  call     T0x2B000054
0xc16b  stelem.ref
0xc16c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0xc171  ldloc.0
0xc172  ldarg.1
0xc173  ldloc.2
0xc174  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SetInitialSharedProperties(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> parserResult, class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService installerSettingService)
0xc179  ldarg.0
0xc17a  ldarg.1
0xc17b  ldloc.0
0xc17c  ldloc.1
0xc17d  call     int32 Microsoft.VisualStudio.Setup.Installer.Program::ExecuteInternal(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer services, class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> parserResult, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0xc182  stloc.3
0xc183  ldloc.1
0xc184  brfalse.s loc_C1A0
0xc186  ldloc.1
0xc187  ldstr    aExitCode0// "Exit Code: {0}"
0xc18c  ldc.i4.1
0xc18d  newarr   [mscorlib]System.Object
0xc192  dup
0xc193  ldc.i4.0
0xc194  ldloc.3
0xc195  box      [mscorlib]System.Int32
0xc19a  stelem.ref
0xc19b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0xc1a0  ldloc.3
0xc1a1  ret
```
