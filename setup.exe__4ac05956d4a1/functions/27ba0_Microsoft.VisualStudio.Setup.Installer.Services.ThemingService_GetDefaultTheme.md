# Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::GetDefaultTheme

- ea: `0x27ba0`
- end: `0x27cc4`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::GetDefaultTheme`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x279f0`
- `0x27b70`

## callees

- `0x27ba0`
- `0x27cd0`
- `0x2bcb0`
- `0x2d4c0`
- `0x2d4d0`

## string_xrefs

- `0x27be6`: `Reading the stored theme ({0}) to installer.`
- `0x27c5f`: `Using registry value of (`
- `0x27c6e`: `) to theme installer.`

## pseudocode

```c

```

## disassembly

```asm
0x27ba0  ldarg.0
0x27ba1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::serviceOptions
0x27ba6  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IInstallerUserSettingsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions::get_UserSettingsRepository()
0x27bab  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IInstallerUserSettingsRepository::get_Theme()
0x27bb0  brfalse.s loc_27C02
0x27bb2  ldarg.0
0x27bb3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::serviceOptions
0x27bb8  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IInstallerUserSettingsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions::get_UserSettingsRepository()
0x27bbd  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IInstallerUserSettingsRepository::get_Theme()
0x27bc2  ldc.i4.1
0x27bc3  ldloca.s 0
0x27bc5  call     T0x2B000180
0x27bca  brfalse.s loc_27C02
0x27bcc  ldarg.0
0x27bcd  ldloc.0
0x27bce  call     instance bool Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::IsSettableTheme(valuetype Microsoft.VisualStudio.Setup.Installer.Theme theme)
0x27bd3  brfalse.s loc_27C02
0x27bd5  ldarg.0
0x27bd6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::serviceOptions
0x27bdb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x27be0  dup
0x27be1  brtrue.s loc_27BE6
0x27be3  pop
0x27be4  br.s     loc_27C00
0x27be6  ldstr    aReadingTheStor// "Reading the stored theme ({0}) to insta"...
0x27beb  ldloc.0
0x27bec  box      Microsoft.VisualStudio.Setup.Installer.Theme
0x27bf1  call     string [mscorlib]System.String::Format(string, object)
0x27bf6  call     T0x2B000010
0x27bfb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x27c00  ldloc.0
0x27c01  ret
0x27c02  nop
0x27c03  ldarg.0
0x27c04  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::serviceOptions
0x27c09  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions::get_Registry()
0x27c0e  dup
0x27c0f  brtrue.s loc_27C15
0x27c11  pop
0x27c12  ldnull
0x27c13  br.s     loc_27C1C
0x27c15  ldc.i4.3
0x27c16  ldc.i4.0
0x27c17  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x27c1c  stloc.1
0x27c1d  ldloc.1
0x27c1e  brtrue.s loc_27C23
0x27c20  ldnull
0x27c21  br.s     loc_27C2F
0x27c23  ldloc.1
0x27c24  ldstr    aSoftwareMicros// "Software\\Microsoft\\Windows\\CurrentVe"...
0x27c29  ldc.i4.0
0x27c2a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x27c2f  stloc.2
0x27c30  ldloc.2
0x27c31  brtrue.s loc_27C36
0x27c33  ldnull
0x27c34  br.s     loc_27C4D
0x27c36  ldloc.2
0x27c37  ldstr    aAppsuselightth// "AppsUseLightTheme"
0x27c3c  callvirt instance object [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::GetValue(string)
0x27c41  dup
0x27c42  brtrue.s loc_27C48
0x27c44  pop
0x27c45  ldnull
0x27c46  br.s     loc_27C4D
0x27c48  callvirt instance string [mscorlib]System.Object::ToString()
0x27c4d  stloc.3
0x27c4e  ldarg.0
0x27c4f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::serviceOptions
0x27c54  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x27c59  dup
0x27c5a  brtrue.s loc_27C5F
0x27c5c  pop
0x27c5d  br.s     loc_27C82
0x27c5f  ldstr    aUsingRegistryV// "Using registry value of ("
0x27c64  ldloc.3
0x27c65  dup
0x27c66  brtrue.s loc_27C6E
0x27c68  pop
0x27c69  ldstr    aNA// "N/A"
0x27c6e  ldstr    aToThemeInstall// ") to theme installer."
0x27c73  call     string [mscorlib]System.String::Concat(string, string, string)
0x27c78  call     T0x2B000010
0x27c7d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x27c82  ldloc.3
0x27c83  ldstr    a1// "1"
0x27c88  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27c8d  brtrue.s loc_27C94
0x27c8f  ldloc.3
0x27c90  brfalse.s loc_27C99
0x27c92  br.s     loc_27C9E
0x27c94  ldc.i4.0
0x27c95  stloc.s  4
0x27c97  br.s     loc_27CA1
0x27c99  ldc.i4.0
0x27c9a  stloc.s  4
0x27c9c  br.s     loc_27CA1
0x27c9e  ldc.i4.1
0x27c9f  stloc.s  4
0x27ca1  ldloc.s  4
0x27ca3  stloc.s  5
0x27ca5  leave.s  loc_27CC1
0x27ca7  ldloc.2
0x27ca8  brfalse.s loc_27CB0
0x27caa  ldloc.2
0x27cab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27cb0  endfinally
0x27cb1  ldloc.1
0x27cb2  brfalse.s loc_27CBA
0x27cb4  ldloc.1
0x27cb5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27cba  endfinally
0x27cbb  pop
0x27cbc  ldc.i4.0
0x27cbd  stloc.s  5
0x27cbf  leave.s  loc_27CC1
0x27cc1  ldloc.s  5
0x27cc3  ret
```
