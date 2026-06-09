# Microsoft.VisualStudio.Setup.Installer.Services.MigrationEligibilityService::OptionsSupportAutoMigration

- ea: `0x23bf0`
- end: `0x23caf`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.MigrationEligibilityService::OptionsSupportAutoMigration`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x23b10`

## callees

- `0x23b50`
- `0x23bf0`
- `0x2caa0`
- `0x59280`
- `0x593a0`
- `0x593e0`
- `0x59500`
- `0x595a0`

## string_xrefs

- `0x23c09`: `The automatic migration cannot be started because specific selections were made in the command line options.`
- `0x23c9c`: `The automatic migration cannot be started because this is an installer update with install options already predefined`

## pseudocode

```c

```

## disassembly

```asm
0x23bf0  ldarg.1
0x23bf1  call     bool Microsoft.VisualStudio.Setup.Installer.Services.MigrationEligibilityService::OptionsSpecifySelections(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions installOptions)
0x23bf6  brfalse.s loc_23C1A
0x23bf8  ldarg.0
0x23bf9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.MigrationEligibilityService::serviceOptions
0x23bfe  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions::get_Logger()
0x23c03  dup
0x23c04  brtrue.s loc_23C09
0x23c06  pop
0x23c07  br.s     loc_23C18
0x23c09  ldstr    aTheAutomaticMi_1// "The automatic migration cannot be start"...
0x23c0e  call     T0x2B000010
0x23c13  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x23c18  ldc.i4.0
0x23c19  ret
0x23c1a  ldarg.1
0x23c1b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutPath()
0x23c20  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x23c25  brfalse.s loc_23C2F
0x23c27  ldarg.1
0x23c28  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutUri()
0x23c2d  brfalse.s loc_23C51
0x23c2f  ldarg.0
0x23c30  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.MigrationEligibilityService::serviceOptions
0x23c35  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions::get_Logger()
0x23c3a  dup
0x23c3b  brtrue.s loc_23C40
0x23c3d  pop
0x23c3e  br.s     loc_23C4F
0x23c40  ldstr    aTheAutomaticMi_2// "The automatic migration cannot be start"...
0x23c45  call     T0x2B000010
0x23c4a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x23c4f  ldc.i4.0
0x23c50  ret
0x23c51  ldarg.1
0x23c52  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_FocusedUi()
0x23c57  brfalse.s loc_23C7B
0x23c59  ldarg.0
0x23c5a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.MigrationEligibilityService::serviceOptions
0x23c5f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions::get_Logger()
0x23c64  dup
0x23c65  brtrue.s loc_23C6A
0x23c67  pop
0x23c68  br.s     loc_23C79
0x23c6a  ldstr    aTheAutomaticMi_3// "The automatic migration cannot be start"...
0x23c6f  call     T0x2B000010
0x23c74  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x23c79  ldc.i4.0
0x23c7a  ret
0x23c7b  ldarg.1
0x23c7c  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Continue()
0x23c81  brfalse.s loc_23CAD
0x23c83  ldarg.1
0x23c84  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_InstallerOnlyUpdate()
0x23c89  brtrue.s loc_23CAD
0x23c8b  ldarg.0
0x23c8c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.MigrationEligibilityService::serviceOptions
0x23c91  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.MigrationEligibilityServiceOptions::get_Logger()
0x23c96  dup
0x23c97  brtrue.s loc_23C9C
0x23c99  pop
0x23c9a  br.s     loc_23CAB
0x23c9c  ldstr    aTheAutomaticMi_4// "The automatic migration cannot be start"...
0x23ca1  call     T0x2B000010
0x23ca6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x23cab  ldc.i4.0
0x23cac  ret
0x23cad  ldc.i4.1
0x23cae  ret
```
