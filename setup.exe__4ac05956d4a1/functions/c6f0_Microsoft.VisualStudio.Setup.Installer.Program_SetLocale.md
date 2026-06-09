# Microsoft.VisualStudio.Setup.Installer.Program::SetLocale

- ea: `0xc6f0`
- end: `0xc7b8`
- name: `Microsoft.VisualStudio.Setup.Installer.Program::SetLocale`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xc5c0`

## callees

- `0xc6f0`
- `0x29be0`
- `0x29bf0`
- `0x55b50`
- `0x59170`
- `0x59180`

## string_xrefs

- `0xc7a3`: `Saving the current locale ({0}) to user.json.`

## pseudocode

```c

```

## disassembly

```asm
0xc6f0  ldarg.0
0xc6f1  ldc.i4.0
0xc6f2  call     T0x2B00004E
0xc6f7  stloc.0
0xc6f8  ldarg.2
0xc6f9  brfalse.s loc_C70C
0xc6fb  ldarg.2
0xc6fc  callvirt instance bool class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_HasErrors()
0xc701  brfalse.s loc_C70C
0xc703  ldarg.1
0xc704  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetLocaleFromUnparsedArgs(string[])
0xc709  stloc.1
0xc70a  br.s     loc_C725
0xc70c  ldarg.2
0xc70d  brtrue.s loc_C712
0xc70f  ldnull
0xc710  br.s     loc_C718
0xc712  ldarg.2
0xc713  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_Options()
0xc718  dup
0xc719  brtrue.s loc_C71F
0xc71b  pop
0xc71c  ldnull
0xc71d  br.s     loc_C724
0xc71f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions::get_Locale()
0xc724  stloc.1
0xc725  ldarg.0
0xc726  ldc.i4.1
0xc727  call     T0x2B000063
0xc72c  stloc.2
0xc72d  ldloc.1
0xc72e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xc733  brtrue.s loc_C754
0xc735  ldloc.2
0xc736  ldloc.1
0xc737  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.Globalization.ILocaleService::SetLocale(string locale)
0xc73c  ldloc.0
0xc73d  brfalse.s loc_C754
0xc73f  ldloc.0
0xc740  ldstr    aSettingTheLoca// "Setting the locale to {0}."
0xc745  ldc.i4.1
0xc746  newarr   [mscorlib]System.Object
0xc74b  dup
0xc74c  ldc.i4.0
0xc74d  ldloc.1
0xc74e  stelem.ref
0xc74f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0xc754  ldloc.2
0xc755  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.Installer.Services.Globalization.ILocaleService::GetLocale()
0xc75a  stloc.3
0xc75b  ldarg.2
0xc75c  brtrue.s loc_C761
0xc75e  ldc.i4.1
0xc75f  br.s     loc_C790
0xc761  ldarg.2
0xc762  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_Options()
0xc767  dup
0xc768  brtrue.s loc_C777
0xc76a  pop
0xc76b  ldloca.s 4
0xc76d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineVerb>
0xc773  ldloc.s  4
0xc775  br.s     loc_C781
0xc777  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineVerb Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions::get_Verb()
0xc77c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineVerb>::.ctor(var<u1>)
0xc781  stloc.s  4
0xc783  ldloca.s 4
0xc785  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineVerb>::GetValueOrDefault()
0xc78a  ldc.i4.7
0xc78b  ceq
0xc78d  ldc.i4.0
0xc78e  ceq
0xc790  brfalse.s loc_C79F
0xc792  ldarg.0
0xc793  ldc.i4.1
0xc794  call     T0x2B000050
0xc799  ldloc.3
0xc79a  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IInstallerUserSettingsRepository::SaveLocale(class [mscorlib]System.Globalization.CultureInfo)
0xc79f  ldloc.0
0xc7a0  brfalse.s loc_C7B7
0xc7a2  ldloc.0
0xc7a3  ldstr    aSavingTheCurre// "Saving the current locale ({0}) to user"...
0xc7a8  ldc.i4.1
0xc7a9  newarr   [mscorlib]System.Object
0xc7ae  dup
0xc7af  ldc.i4.0
0xc7b0  ldloc.3
0xc7b1  stelem.ref
0xc7b2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0xc7b7  ret
```
