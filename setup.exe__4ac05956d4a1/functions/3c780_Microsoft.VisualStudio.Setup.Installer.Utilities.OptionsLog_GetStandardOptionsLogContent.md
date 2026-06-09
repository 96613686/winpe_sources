# Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::GetStandardOptionsLogContent

- ea: `0x3c780`
- end: `0x3c894`
- name: `Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::GetStandardOptionsLogContent`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3c8a0`
- `0x3fc00`

## callees

- `0x3c780`

## string_xrefs

- `0x3c786`: `\nInstallerPath: {0}`
- `0x3c848`: `\nInstallerFlight: `
- `0x3c878`: `\nInstallerFlight: None`

## pseudocode

```c

```

## disassembly

```asm
0x3c780  ldarg.0
0x3c781  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c786  ldstr    aInstallerpath0// "\nInstallerPath: {0}"
0x3c78b  ldarg.0
0x3c78c  ldfld    string Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::installerPath
0x3c791  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3c796  pop
0x3c797  ldarg.0
0x3c798  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c79d  ldstr    aResumeargument// "\nResumeArguments.ActivityID: {0}, Resu"...
0x3c7a2  ldarg.0
0x3c7a3  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::resumeArguments
0x3c7a8  dup
0x3c7a9  brtrue.s loc_3C7AF
0x3c7ab  pop
0x3c7ac  ldnull
0x3c7ad  br.s     loc_3C7B4
0x3c7af  call     instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_ActivityId()
0x3c7b4  ldarg.0
0x3c7b5  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::resumeArguments
0x3c7ba  dup
0x3c7bb  brtrue.s loc_3C7C9
0x3c7bd  pop
0x3c7be  ldloca.s 0
0x3c7c0  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x3c7c6  ldloc.0
0x3c7c7  br.s     loc_3C7D3
0x3c7c9  call     instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_IsPassive()
0x3c7ce  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3c7d3  box      valuetype [mscorlib]System.Nullable`1<bool>
0x3c7d8  ldarg.0
0x3c7d9  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::resumeArguments
0x3c7de  dup
0x3c7df  brtrue.s loc_3C7ED
0x3c7e1  pop
0x3c7e2  ldloca.s 0
0x3c7e4  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x3c7ea  ldloc.0
0x3c7eb  br.s     loc_3C7F7
0x3c7ed  call     instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_IsQuiet()
0x3c7f2  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3c7f7  box      valuetype [mscorlib]System.Nullable`1<bool>
0x3c7fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x3c801  pop
0x3c802  ldarg.0
0x3c803  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c808  ldstr    aInstanceid0// "\nInstanceId: {0}"
0x3c80d  ldarg.0
0x3c80e  ldfld    string Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::instanceId
0x3c813  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3c818  pop
0x3c819  ldarg.0
0x3c81a  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c81f  ldstr    aOperationmode0// "\nOperationMode: {0}"
0x3c824  ldarg.0
0x3c825  ldfld    valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::downloadThenInstall
0x3c82a  box      [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode
0x3c82f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3c834  pop
0x3c835  ldarg.0
0x3c836  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::installerFlight
0x3c83b  call     T0x2B000074
0x3c840  brfalse.s loc_3C872
0x3c842  ldarg.0
0x3c843  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c848  ldstr    aInstallerfligh// "\nInstallerFlight: "
0x3c84d  call     T0x2B000010
0x3c852  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object[])
0x3c857  pop
0x3c858  ldarg.0
0x3c859  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::installerFlight
0x3c85e  ldarg.0
0x3c85f  ldftn    instance class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::<GetStandardOptionsLogContent>b__8_0(string x)
0x3c865  newobj   instance void class [mscorlib]System.Func`2<string, class [mscorlib]System.Text.StringBuilder>::.ctor(object, native int)
0x3c86a  call     T0x2B00026A
0x3c86f  pop
0x3c870  br.s     loc_3C888
0x3c872  ldarg.0
0x3c873  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c878  ldstr    aInstallerfligh_0// "\nInstallerFlight: None"
0x3c87d  call     T0x2B000010
0x3c882  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object[])
0x3c887  pop
0x3c888  ldarg.0
0x3c889  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c88e  callvirt instance string [mscorlib]System.Object::ToString()
0x3c893  ret
```
