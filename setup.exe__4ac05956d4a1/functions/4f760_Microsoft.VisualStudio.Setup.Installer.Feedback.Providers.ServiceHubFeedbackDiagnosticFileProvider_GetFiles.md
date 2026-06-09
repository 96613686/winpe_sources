# Microsoft.VisualStudio.Setup.Installer.Feedback.Providers.ServiceHubFeedbackDiagnosticFileProvider::GetFiles

- ea: `0x4f760`
- end: `0x4f92c`
- name: `Microsoft.VisualStudio.Setup.Installer.Feedback.Providers.ServiceHubFeedbackDiagnosticFileProvider::GetFiles`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2c140`
- `0x2c150`
- `0x4e140`
- `0x4e1b0`
- `0x4e1d0`
- `0x4f760`
- `0x4f930`
- `0x4f980`

## string_xrefs

- `0x4f771`: `servicehub`
- `0x4f78f`: `ServiceHubLogs_`
- `0x4f886`: `componentmodelcache`
- `0x4f8aa`: `ComponentModelCache_`
- `0x4f919`: `Error getting ServiceHub or MEF logs`

## pseudocode

```c

```

## disassembly

```asm
0x4f760  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4f765  stloc.0
0x4f766  ldarg.1
0x4f767  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4f76c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_TemporaryDirectory()
0x4f771  ldstr    aServicehub// "servicehub"
0x4f776  ldstr    aLogs// "logs"
0x4f77b  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x4f780  stloc.1
0x4f781  ldarg.1
0x4f782  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4f787  ldloc.1
0x4f788  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x4f78d  brfalse.s loc_4F7DE
0x4f78f  ldstr    aServicehublogs// "ServiceHubLogs_"
0x4f794  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f799  stloc.s  6
0x4f79b  ldloca.s 6
0x4f79d  ldstr    aYyyyMmDdHhMmSs// "yyyy-MM-dd-HH-mm-ss"
0x4f7a2  call     instance string [mscorlib]System.DateTime::ToString(string)
0x4f7a7  ldstr    aZip// ".zip"
0x4f7ac  call     string [mscorlib]System.String::Concat(string, string, string)
0x4f7b1  stloc.s  4
0x4f7b3  ldarg.1
0x4f7b4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4f7b9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_TemporaryDirectory()
0x4f7be  ldloc.s  4
0x4f7c0  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4f7c5  stloc.s  5
0x4f7c7  ldarg.0
0x4f7c8  ldarg.1
0x4f7c9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4f7ce  ldloc.1
0x4f7cf  ldloc.s  5
0x4f7d1  call     instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Providers.ServiceHubFeedbackDiagnosticFileProvider::ZipServiceHubLogs(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string serviceHubPath, string zipFilePath)
0x4f7d6  ldloc.0
0x4f7d7  ldloc.s  5
0x4f7d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4f7de  ldarg.2
0x4f7df  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackOptions::get_DiagnosticCollectionOptions()
0x4f7e4  pop
0x4f7e5  ldarg.2
0x4f7e6  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackOptions::get_DiagnosticCollectionOptions()
0x4f7eb  dup
0x4f7ec  brtrue.s loc_4F7F2
0x4f7ee  pop
0x4f7ef  ldnull
0x4f7f0  br.s     loc_4F7F7
0x4f7f2  call     instance string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions::get_InstanceId()
0x4f7f7  stloc.2
0x4f7f8  ldarg.2
0x4f7f9  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackOptions::get_DiagnosticCollectionOptions()
0x4f7fe  dup
0x4f7ff  brtrue.s loc_4F805
0x4f801  pop
0x4f802  ldnull
0x4f803  br.s     loc_4F80A
0x4f805  call     instance string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackDiagnosticCollectionOptions::get_InstanceVersion()
0x4f80a  stloc.3
0x4f80b  ldloc.2
0x4f80c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f811  brtrue   loc_4F907
0x4f816  ldloc.3
0x4f817  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f81c  brtrue   loc_4F907
0x4f821  ldloc.3
0x4f822  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x4f827  call     instance int32 [mscorlib]System.Version::get_Major()
0x4f82c  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Implicit(int32)
0x4f831  ldc.i4.0
0x4f832  ldc.i4.0
0x4f833  ldc.i4.0
0x4f834  ldc.i4.0
0x4f835  ldc.i4.1
0x4f836  newobj   instance void [mscorlib]System.Decimal::.ctor(int32, int32, int32, bool, unsigned int8)
0x4f83b  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Addition(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x4f840  stloc.s  7
0x4f842  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x4f847  ldstr    a01_2// "{0}_{1}"
0x4f84c  ldloc.s  7
0x4f84e  box      [mscorlib]System.Decimal
0x4f853  ldloc.2
0x4f854  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x4f859  stloc.s  8
0x4f85b  ldc.i4.5
0x4f85c  newarr   [mscorlib]System.String
0x4f861  dup
0x4f862  ldc.i4.0
0x4f863  ldarg.1
0x4f864  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4f869  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_LocalUserDirectory()
0x4f86e  stelem.ref
0x4f86f  dup
0x4f870  ldc.i4.1
0x4f871  ldstr    aMicrosoft// "Microsoft"
0x4f876  stelem.ref
0x4f877  dup
0x4f878  ldc.i4.2
0x4f879  ldstr    aVisualstudio// "VisualStudio"
0x4f87e  stelem.ref
0x4f87f  dup
0x4f880  ldc.i4.3
0x4f881  ldloc.s  8
0x4f883  stelem.ref
0x4f884  dup
0x4f885  ldc.i4.4
0x4f886  ldstr    aComponentmodel// "componentmodelcache"
0x4f88b  stelem.ref
0x4f88c  call     string [mscorlib]System.IO.Path::Combine(string[])
0x4f891  stloc.s  9
0x4f893  ldarg.1
0x4f894  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4f899  ldloc.s  9
0x4f89b  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x4f8a0  brfalse.s loc_4F907
0x4f8a2  ldc.i4.5
0x4f8a3  newarr   [mscorlib]System.String
0x4f8a8  dup
0x4f8a9  ldc.i4.0
0x4f8aa  ldstr    aComponentmodel_0// "ComponentModelCache_"
0x4f8af  stelem.ref
0x4f8b0  dup
0x4f8b1  ldc.i4.1
0x4f8b2  ldloc.2
0x4f8b3  stelem.ref
0x4f8b4  dup
0x4f8b5  ldc.i4.2
0x4f8b6  ldstr    asc_A54B2// "_"
0x4f8bb  stelem.ref
0x4f8bc  dup
0x4f8bd  ldc.i4.3
0x4f8be  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f8c3  stloc.s  6
0x4f8c5  ldloca.s 6
0x4f8c7  ldstr    aYyyyMmDdHhMmSs// "yyyy-MM-dd-HH-mm-ss"
0x4f8cc  call     instance string [mscorlib]System.DateTime::ToString(string)
0x4f8d1  stelem.ref
0x4f8d2  dup
0x4f8d3  ldc.i4.4
0x4f8d4  ldstr    aZip// ".zip"
0x4f8d9  stelem.ref
0x4f8da  call     string [mscorlib]System.String::Concat(string[])
0x4f8df  stloc.s  0xA
0x4f8e1  call     string [mscorlib]System.IO.Path::GetTempPath()
0x4f8e6  ldloc.s  0xA
0x4f8e8  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4f8ed  stloc.s  0xB
0x4f8ef  ldarg.0
0x4f8f0  ldarg.1
0x4f8f1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_FileSystem()
0x4f8f6  ldloc.s  9
0x4f8f8  ldloc.s  0xB
0x4f8fa  call     instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Providers.ServiceHubFeedbackDiagnosticFileProvider::ZipMefLogs(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string mefPath, string zipFilePath)
0x4f8ff  ldloc.0
0x4f900  ldloc.s  0xB
0x4f902  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4f907  leave.s  loc_4F92A
0x4f909  stloc.s  0xC
0x4f90b  ldarg.1
0x4f90c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_Logger()
0x4f911  dup
0x4f912  brtrue.s loc_4F917
0x4f914  pop
0x4f915  br.s     loc_4F928
0x4f917  ldloc.s  0xC
0x4f919  ldstr    aErrorGettingSe// "Error getting ServiceHub or MEF logs"
0x4f91e  call     T0x2B000010
0x4f923  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4f928  leave.s  loc_4F92A
0x4f92a  ldloc.0
0x4f92b  ret
```
