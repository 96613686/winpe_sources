# Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::<InitializeAsync>b__5_0

- ea: `0x5c3f0`
- end: `0x5c520`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::<InitializeAsync>b__5_0`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2d6b0`
- `0x558c0`
- `0x55a20`
- `0x5c0a0`
- `0x5c0b0`
- `0x5c0e0`
- `0x5c1b0`
- `0x5c1f0`
- `0x5c370`
- `0x5c390`
- `0x5c3f0`

## string_xrefs

- `0x5c4e8`: `Command line errors:`

## pseudocode

```c

```

## disassembly

```asm
0x5c3f0  ldarg.0
0x5c3f1  call     instance string Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::GetVerb()
0x5c3f6  stloc.0
0x5c3f7  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_CommandLineUsage_Args2()
0x5c3fc  ldarg.0
0x5c3fd  call     instance string Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::ProcessFileName()
0x5c402  ldloc.0
0x5c403  dup
0x5c404  brtrue.s loc_5C41B
0x5c406  pop
0x5c407  ldstr    asc_A8648// "<"
0x5c40c  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_Command()
0x5c411  ldstr    asc_A864C// ">"
0x5c416  call     string [mscorlib]System.String::Concat(string, string, string)
0x5c41b  call     string [mscorlib]System.String::Format(string, object, object)
0x5c420  stloc.1
0x5c421  ldarg.0
0x5c422  ldarg.0
0x5c423  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineDetail> Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::GetCommandLineDetails()
0x5c428  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::set_CommandLineDetails(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineDetail> value)
0x5c42d  ldc.i4.0
0x5c42e  stloc.2
0x5c42f  ldarg.0
0x5c430  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::parserResult
0x5c435  callvirt instance bool class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_HasErrors()
0x5c43a  brfalse.s loc_5C452
0x5c43c  ldarg.0
0x5c43d  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::parserResult
0x5c442  callvirt instance class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineErrorInformation class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_ErrorInformation()
0x5c447  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineError> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineErrorInformation::get_Errors()
0x5c44c  call     bool Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::IsAnyHelpOrVersionError(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineError> errors)
0x5c451  stloc.2
0x5c452  ldloc.2
0x5c453  brfalse.s loc_5C47D
0x5c455  ldarg.0
0x5c456  ldloc.1
0x5c457  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::set_ErrorText(string value)
0x5c45c  ldarg.0
0x5c45d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ApplicationViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::options
0x5c462  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x5c467  dup
0x5c468  brtrue.s loc_5C46C
0x5c46a  pop
0x5c46b  ret
0x5c46c  ldarg.0
0x5c46d  call     instance string Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::get_ErrorText()
0x5c472  call     T0x2B000010
0x5c477  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5c47c  ret
0x5c47d  ldarg.0
0x5c47e  ldarg.0
0x5c47f  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::parserResult
0x5c484  callvirt instance class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineErrorInformation class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_ErrorInformation()
0x5c489  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineError> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineErrorInformation::get_Errors()
0x5c48e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::RenderParsingErrors(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineError> errors)
0x5c493  stloc.3
0x5c494  ldloc.3
0x5c495  call     T0x2B000239
0x5c49a  ldc.i4.1
0x5c49b  bgt.s    loc_5C4A5
0x5c49d  ldloc.3
0x5c49e  call     T0x2B000369
0x5c4a3  br.s     loc_5C4BA
0x5c4a5  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_CommandLineMultipleErrors()
0x5c4aa  ldstr    asc_9D4A4// " "
0x5c4af  ldloc.3
0x5c4b0  call     T0x2B000369
0x5c4b5  call     string [mscorlib]System.String::Concat(string, string, string)
0x5c4ba  stloc.s  4
0x5c4bc  ldarg.0
0x5c4bd  ldstr    asc_9D4A4// " "
0x5c4c2  ldc.i4.2
0x5c4c3  newarr   [mscorlib]System.String
0x5c4c8  dup
0x5c4c9  ldc.i4.0
0x5c4ca  ldloc.s  4
0x5c4cc  stelem.ref
0x5c4cd  dup
0x5c4ce  ldc.i4.1
0x5c4cf  ldloc.1
0x5c4d0  stelem.ref
0x5c4d1  call     string [mscorlib]System.String::Join(string, string[])
0x5c4d6  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::set_ErrorText(string value)
0x5c4db  call     string [mscorlib]System.Environment::get_NewLine()
0x5c4e0  ldc.i4.2
0x5c4e1  newarr   [mscorlib]System.String
0x5c4e6  dup
0x5c4e7  ldc.i4.0
0x5c4e8  ldstr    aCommandLineErr// "Command line errors:"
0x5c4ed  stelem.ref
0x5c4ee  dup
0x5c4ef  ldc.i4.1
0x5c4f0  call     string [mscorlib]System.Environment::get_NewLine()
0x5c4f5  ldloc.3
0x5c4f6  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x5c4fb  stelem.ref
0x5c4fc  call     string [mscorlib]System.String::Join(string, string[])
0x5c501  stloc.s  5
0x5c503  ldarg.0
0x5c504  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ApplicationViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::options
0x5c509  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x5c50e  dup
0x5c50f  brtrue.s loc_5C513
0x5c511  pop
0x5c512  ret
0x5c513  ldloc.s  5
0x5c515  call     T0x2B000010
0x5c51a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5c51f  ret
```
