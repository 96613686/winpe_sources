# Microsoft.VisualStudio.Setup.Installer.LoggerFactory::Create

- ea: `0xbea0`
- end: `0xbeda`
- name: `Microsoft.VisualStudio.Setup.Installer.LoggerFactory::Create`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc3e0`

## callees

- `0xbea0`
- `0xbee0`
- `0x55a60`
- `0x55cc0`

## string_xrefs

- `0xbeb0`: `installer`
- `0xbeb7`: `installer_elevated`

## pseudocode

```c

```

## disassembly

```asm
0xbea0  ldarg.1
0xbea1  call     bool Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::IsElevatedProcess(string[] args)
0xbea6  stloc.0
0xbea7  ldarg.1
0xbea8  call     bool Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::IsQuietOrPassive(string[] args)
0xbead  ldloc.0
0xbeae  brtrue.s loc_BEB7
0xbeb0  ldstr    aInstaller// "installer"
0xbeb5  br.s     loc_BEBC
0xbeb7  ldstr    aInstallerEleva// "installer_elevated"
0xbebc  stloc.1
0xbebd  ldarg.0
0xbebe  ldnull
0xbebf  ldloc.1
0xbec0  ldc.i4.5
0xbec1  ldc.i4   0xBB8
0xbec6  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::OpenFileLogger(class [mscorlib]System.IServiceProvider, string, string, int32, int32)
0xbecb  stloc.2
0xbecc  brfalse.s loc_BED8
0xbece  ldloc.0
0xbecf  brtrue.s loc_BED8
0xbed1  ldloc.2
0xbed2  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.LoggerFactory::TryCreateConsoleLogger(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0xbed7  stloc.2
0xbed8  ldloc.2
0xbed9  ret
```
