# Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::CreateWindow

- ea: `0x5fca0`
- end: `0x5fce1`
- name: `Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::CreateWindow`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5f9a0`

## callees

- `0x2b6b0`
- `0x2d6b0`
- `0x5bf60`
- `0x5fca0`

## string_xrefs

- `0x5fcb9`: `CreateWindow`
- `0x5fcc1`: `CommandLineDetailsWindow`
- `0x5fcc9`: `ICommandLineDetailsViewModel`

## pseudocode

```c

```

## disassembly

```asm
0x5fca0  ldarg.1
0x5fca1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x5fca6  dup
0x5fca7  brtrue.s loc_5FCAC
0x5fca9  pop
0x5fcaa  br.s     loc_5FCD4
0x5fcac  ldstr    a0Launching1Wit// "{0}: Launching {1} with {2}"
0x5fcb1  ldc.i4.3
0x5fcb2  newarr   [mscorlib]System.Object
0x5fcb7  dup
0x5fcb8  ldc.i4.0
0x5fcb9  ldstr    aCreatewindow// "CreateWindow"
0x5fcbe  stelem.ref
0x5fcbf  dup
0x5fcc0  ldc.i4.1
0x5fcc1  ldstr    aCommandlinedet// "CommandLineDetailsWindow"
0x5fcc6  stelem.ref
0x5fcc7  dup
0x5fcc8  ldc.i4.2
0x5fcc9  ldstr    aIcommandlinede// "ICommandLineDetailsViewModel"
0x5fcce  stelem.ref
0x5fccf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5fcd4  ldarg.1
0x5fcd5  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x5fcda  ldarg.2
0x5fcdb  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.Views.CommandLineDetailsWindow::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.ICommandLineDetailsViewModel vm)
0x5fce0  ret
```
