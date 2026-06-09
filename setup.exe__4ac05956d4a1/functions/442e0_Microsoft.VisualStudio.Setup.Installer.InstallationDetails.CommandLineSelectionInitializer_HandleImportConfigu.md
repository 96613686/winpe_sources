# Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CommandLineSelectionInitializer::HandleImportConfigurationException

- ea: `0x442e0`
- end: `0x44329`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CommandLineSelectionInitializer::HandleImportConfigurationException`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2d6b0`
- `0x3d110`
- `0x442e0`
- `0x46610`
- `0x46620`
- `0x46630`

## string_xrefs

- `0x442f2`: `CommandLine - Failed to import configuration: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x442e0  ldarg.0
0x442e1  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.SelectionInitializerBase::get_ServiceOptions()
0x442e6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x442eb  dup
0x442ec  brtrue.s loc_442F1
0x442ee  pop
0x442ef  br.s     loc_4430B
0x442f1  ldarg.1
0x442f2  ldstr    aCommandlineFai// "CommandLine - Failed to import configur"...
0x442f7  ldc.i4.1
0x442f8  newarr   [mscorlib]System.Object
0x442fd  dup
0x442fe  ldc.i4.0
0x442ff  ldarg.1
0x44300  callvirt instance string [mscorlib]System.Exception::get_Message()
0x44305  stelem.ref
0x44306  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4430b  ldarg.1
0x4430c  ldarg.0
0x4430d  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallationDetails.SelectionInitializerBase::get_ConfigPath()
0x44312  ldloca.s 1
0x44314  ldloca.s 0
0x44316  call     void Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::GetTitleAndMessageForConfigurationReadError(class [mscorlib]System.Exception exception, string filePath, [out] string& title, [out] string& message)
0x4431b  ldarg.0
0x4431c  ldloc.0
0x4431d  call     instance void Microsoft.VisualStudio.Setup.Installer.InstallationDetails.SelectionInitializerBase::set_ErrorMessage(string value)
0x44322  ldc.i4.0
0x44323  call     T0x2B00008D
0x44328  ret
```
