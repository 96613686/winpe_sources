# Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::ChangeTheme

- ea: `0x27930`
- end: `0x279e1`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::ChangeTheme`
- size: `177`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x27b70`
- `0x5f410`
- `0x5fcf0`

## callees

- `0x27910`
- `0x27920`
- `0x27930`
- `0x27a90`
- `0x27cd0`
- `0x2bcb0`
- `0x2d4c0`

## string_xrefs

- `0x27979`: `Saving the current theme ({0}) to user.json.`

## pseudocode

```c

```

## disassembly

```asm
0x27930  ldarg.0
0x27931  stloc.0
0x27932  ldc.i4.0
0x27933  stloc.1
0x27934  ldloc.0
0x27935  ldloca.s 1
0x27937  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2793c  ldarg.0
0x2793d  ldarg.1
0x2793e  call     instance bool Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::IsSettableTheme(valuetype Microsoft.VisualStudio.Setup.Installer.Theme theme)
0x27943  brfalse  loc_279D4
0x27948  ldarg.2
0x27949  brfalse.s loc_27993
0x2794b  ldarg.0
0x2794c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::serviceOptions
0x27951  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IInstallerUserSettingsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions::get_UserSettingsRepository()
0x27956  ldarga.s 1
0x27958  constrained. Microsoft.VisualStudio.Setup.Installer.Theme
0x2795e  callvirt instance string [mscorlib]System.Object::ToString()
0x27963  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IInstallerUserSettingsRepository::set_Theme(string)
0x27968  ldarg.0
0x27969  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ThemingServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::serviceOptions
0x2796e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x27973  dup
0x27974  brtrue.s loc_27979
0x27976  pop
0x27977  br.s     loc_27993
0x27979  ldstr    aSavingTheCurre_0// "Saving the current theme ({0}) to user."...
0x2797e  ldarg.1
0x2797f  box      Microsoft.VisualStudio.Setup.Installer.Theme
0x27984  call     string [mscorlib]System.String::Format(string, object)
0x27989  call     T0x2B000010
0x2798e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x27993  ldarg.0
0x27994  ldfld    bool Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::isHighContrastEnabled
0x27999  brfalse.s loc_279A9
0x2799b  ldarg.0
0x2799c  ldarg.1
0x2799d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme>::.ctor(var<u1>)
0x279a2  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::previousTheme
0x279a7  leave.s  loc_279E0
0x279a9  ldarg.0
0x279aa  ldarg.0
0x279ab  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.Theme Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::get_CurrentTheme()
0x279b0  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme>::.ctor(var<u1>)
0x279b5  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::previousTheme
0x279ba  ldarg.0
0x279bb  ldarg.1
0x279bc  call     instance void Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::set_CurrentTheme(valuetype Microsoft.VisualStudio.Setup.Installer.Theme value)
0x279c1  ldarg.0
0x279c2  ldarg.0
0x279c3  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.Theme Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::get_CurrentTheme()
0x279c8  ldarg.0
0x279c9  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::previousTheme
0x279ce  ldarg.2
0x279cf  call     instance void Microsoft.VisualStudio.Setup.Installer.Services.ThemingService::UpdateLoadedTheme(valuetype Microsoft.VisualStudio.Setup.Installer.Theme themeToLoad, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> themeToUnload, bool saved)
0x279d4  leave.s  loc_279E0
0x279d6  ldloc.1
0x279d7  brfalse.s loc_279DF
0x279d9  ldloc.0
0x279da  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x279df  endfinally
0x279e0  ret
```
