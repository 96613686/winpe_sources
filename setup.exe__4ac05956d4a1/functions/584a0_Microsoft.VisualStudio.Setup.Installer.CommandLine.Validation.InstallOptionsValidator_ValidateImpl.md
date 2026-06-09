# Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.InstallOptionsValidator::ValidateImpl

- ea: `0x584a0`
- end: `0x58651`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.InstallOptionsValidator::ValidateImpl`
- size: `433`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3cd20`
- `0x572d0`
- `0x57330`
- `0x58400`
- `0x584a0`
- `0x58c90`
- `0x58cd0`
- `0x58cf0`
- `0x59280`
- `0x59320`
- `0x59360`
- `0x59380`
- `0x59480`
- `0x595a0`
- `0x595e0`
- `0x5a020`
- `0x5a040`

## string_xrefs

- `0x5852d`: `ChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x584a0  ldarg.1
0x584a1  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x584a6  stloc.0
0x584a7  ldloc.0
0x584a8  brfalse  loc_5864F
0x584ad  ldarg.0
0x584ae  ldloc.0
0x584af  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.InstallerOptionsBaseValidator::ValidateImpl(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions options)
0x584b4  pop
0x584b5  ldloc.0
0x584b6  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x584bb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x584c0  brfalse.s loc_584E4
0x584c2  ldloc.0
0x584c3  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_Migrate()
0x584c8  brtrue.s loc_584E4
0x584ca  ldtoken  Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x584cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x584d4  ldstr    aProductid_0// "ProductId"
0x584d9  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption)
0x584de  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x584e3  throw
0x584e4  ldloc.0
0x584e5  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_Migrate()
0x584ea  brfalse.s loc_584FF
0x584ec  ldloc.0
0x584ed  call     bool Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::IsQuietOrPassive(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions options)
0x584f2  brfalse.s loc_584FF
0x584f4  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InvalidMigrateOnQuietPassive()
0x584f9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x584fe  throw
0x584ff  ldloc.0
0x58500  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelId()
0x58505  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5850a  brfalse.s loc_5853D
0x5850c  ldloc.0
0x5850d  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelUri()
0x58512  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58517  brfalse.s loc_5853D
0x58519  ldtoken  Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x5851e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x58523  ldstr    aProductid_0// "ProductId"
0x58528  ldstr    aChannelid_0// "ChannelId"
0x5852d  ldstr    aChanneluri_0// "ChannelUri"
0x58532  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string providedOption, string requiredOption1, string requiredOption2)
0x58537  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5853c  throw
0x5853d  ldloc.0
0x5853e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_VisualStudioFlight()
0x58543  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FlightService::ValidateFlights(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x58548  brtrue.s loc_5856A
0x5854a  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InvalidFlights_Args1()
0x5854f  ldstr    asc_98B4C// ","
0x58554  ldloc.0
0x58555  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_VisualStudioFlight()
0x5855a  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x5855f  call     string [mscorlib]System.String::Format(string, object)
0x58564  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58569  throw
0x5856a  ldloc.0
0x5856b  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Continue()
0x58570  brtrue.s loc_5859E
0x58572  ldloc.0
0x58573  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.SelectionOptions::get_SelectedPackages()
0x58578  call     T0x2B00002F
0x5857d  brtrue.s loc_5859E
0x5857f  ldtoken  Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x58584  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x58589  ldstr    aContinue// "Continue"
0x5858e  ldstr    aSelectedpackag_1// "SelectedPackages"
0x58593  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption, string providedOption)
0x58598  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5859d  throw
0x5859e  ldarg.0
0x5859f  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ISelectedPackageParser Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.InstallOptionsValidator::selectedPackageParser
0x585a4  ldloc.0
0x585a5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.SelectionOptions::get_SelectedPackages()
0x585aa  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.ISelectedPackageParser::IsValid(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedPackages)
0x585af  brtrue.s loc_585D1
0x585b1  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InvalidSelectedPackages_Args1()
0x585b6  ldstr    asc_98B4C// ","
0x585bb  ldloc.0
0x585bc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.SelectionOptions::get_SelectedPackages()
0x585c1  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x585c6  call     string [mscorlib]System.String::Format(string, object)
0x585cb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x585d0  throw
0x585d1  ldloc.0
0x585d2  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Continue()
0x585d7  brfalse.s loc_5860D
0x585d9  ldloc.0
0x585da  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_InstallerOnlyUpdate()
0x585df  brtrue.s loc_5860D
0x585e1  ldloc.0
0x585e2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.SelectionOptions::get_SelectedLanguages()
0x585e7  call     T0x2B00002F
0x585ec  brfalse.s loc_58641
0x585ee  ldtoken  Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x585f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x585f8  ldstr    aSelectedlangua// "SelectedLanguages"
0x585fd  ldstr    aContinue// "Continue"
0x58602  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption, string providedOption)
0x58607  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5860c  throw
0x5860d  ldloc.0
0x5860e  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Continue()
0x58613  brtrue.s loc_58641
0x58615  ldloc.0
0x58616  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.SelectionOptions::get_SelectedLanguages()
0x5861b  call     T0x2B00002F
0x58620  brtrue.s loc_58641
0x58622  ldtoken  Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x58627  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5862c  ldstr    aContinue// "Continue"
0x58631  ldstr    aSelectedlangua// "SelectedLanguages"
0x58636  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption, string providedOption)
0x5863b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58640  throw
0x58641  ldarg.0
0x58642  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.IPathParser Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.InstallOptionsValidator::pathParser
0x58647  ldloc.0
0x58648  callvirt instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.IPathParser::Validate(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options)
0x5864d  ldc.i4.1
0x5864e  ret
0x5864f  ldc.i4.0
0x58650  ret
```
