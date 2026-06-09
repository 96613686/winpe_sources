# Microsoft.VisualStudio.Setup.Installer.Feedback.Providers.SetupActivityLogFeedbackDiagnosticFileProvider::GetFiles

- ea: `0x4f9e0`
- end: `0x4fa88`
- name: `Microsoft.VisualStudio.Setup.Installer.Feedback.Providers.SetupActivityLogFeedbackDiagnosticFileProvider::GetFiles`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2c150`
- `0x4e140`
- `0x4e1b0`
- `0x4e1d0`
- `0x4f9e0`

## string_xrefs

- `0x4fa62`: `ActivityLog.Setup.xml`

## pseudocode

```c

```

## disassembly

```asm
0x4f9e0  ldarg.2
0x4f9e1  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackOptions::get_DiagnosticCollectionOptions()
0x4f9e6  stloc.0
0x4f9e7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4f9ec  stloc.1
0x4f9ed  ldloc.0
0x4f9ee  brfalse  loc_4FA86
0x4f9f3  ldloc.0
0x4f9f4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions::get_InstanceVersion()
0x4f9f9  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x4f9fe  call     instance int32 [mscorlib]System.Version::get_Major()
0x4fa03  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Implicit(int32)
0x4fa08  ldc.i4.0
0x4fa09  ldc.i4.0
0x4fa0a  ldc.i4.0
0x4fa0b  ldc.i4.0
0x4fa0c  ldc.i4.1
0x4fa0d  newobj   instance void [mscorlib]System.Decimal::.ctor(int32, int32, int32, bool, unsigned int8)
0x4fa12  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Addition(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x4fa17  stloc.2
0x4fa18  ldloc.0
0x4fa19  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions::get_InstanceId()
0x4fa1e  stloc.3
0x4fa1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x4fa24  ldstr    a01_2// "{0}_{1}"
0x4fa29  ldloc.2
0x4fa2a  box      [mscorlib]System.Decimal
0x4fa2f  ldloc.3
0x4fa30  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x4fa35  stloc.s  4
0x4fa37  ldc.i4.5
0x4fa38  newarr   [mscorlib]System.String
0x4fa3d  dup
0x4fa3e  ldc.i4.0
0x4fa3f  ldarg.1
0x4fa40  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4fa45  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_UserDirectory()
0x4fa4a  stelem.ref
0x4fa4b  dup
0x4fa4c  ldc.i4.1
0x4fa4d  ldstr    aMicrosoft// "Microsoft"
0x4fa52  stelem.ref
0x4fa53  dup
0x4fa54  ldc.i4.2
0x4fa55  ldstr    aVisualstudio// "VisualStudio"
0x4fa5a  stelem.ref
0x4fa5b  dup
0x4fa5c  ldc.i4.3
0x4fa5d  ldloc.s  4
0x4fa5f  stelem.ref
0x4fa60  dup
0x4fa61  ldc.i4.4
0x4fa62  ldstr    aActivitylogSet// "ActivityLog.Setup.xml"
0x4fa67  stelem.ref
0x4fa68  call     string [mscorlib]System.IO.Path::Combine(string[])
0x4fa6d  stloc.s  5
0x4fa6f  ldarg.1
0x4fa70  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4fa75  ldloc.s  5
0x4fa77  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x4fa7c  brfalse.s loc_4FA86
0x4fa7e  ldloc.1
0x4fa7f  ldloc.s  5
0x4fa81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4fa86  ldloc.1
0x4fa87  ret
```
