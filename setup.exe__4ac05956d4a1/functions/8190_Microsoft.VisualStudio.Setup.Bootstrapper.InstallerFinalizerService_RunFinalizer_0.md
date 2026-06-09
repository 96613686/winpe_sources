# Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::RunFinalizer_0

- ea: `0x8190`
- end: `0x82a5`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::RunFinalizer_0`
- size: `277`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x8170`
- `0x62300`

## callees

- `0x7420`
- `0x7450`
- `0x7480`
- `0x8190`

## string_xrefs

- `0x827a`: `Failed to start the installer finalizer`

## pseudocode

```c

```

## disassembly

```asm
0x8190  ldarg.0
0x8191  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x8196  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_FileSystem()
0x819b  ldarg.1
0x819c  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x81a1  brtrue.s loc_81D3
0x81a3  ldstr    aFinalizerNotFo// "Finalizer not found: {0}"
0x81a8  ldarg.1
0x81a9  call     string [mscorlib]System.String::Format(string, object)
0x81ae  stloc.1
0x81af  ldarg.0
0x81b0  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x81b5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x81ba  dup
0x81bb  brtrue.s loc_81C0
0x81bd  pop
0x81be  br.s     loc_81CB
0x81c0  ldloc.1
0x81c1  call     T0x2B000010
0x81c6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x81cb  ldloc.1
0x81cc  ldarg.1
0x81cd  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x81d2  throw
0x81d3  ldarg.0
0x81d4  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x81d9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ProcessService()
0x81de  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::CreateProcess()
0x81e3  stloc.0
0x81e4  ldloc.0
0x81e5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x81ea  ldarg.1
0x81eb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_FileName(string)
0x81f0  ldloc.0
0x81f1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x81f6  ldarg.2
0x81f7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Arguments(string)
0x81fc  ldloc.0
0x81fd  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x8202  ldc.i4.0
0x8203  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_UseShellExecute(bool)
0x8208  ldloc.0
0x8209  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x820e  ldc.i4.1
0x820f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_CreateNoWindow(bool)
0x8214  ldloc.0
0x8215  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x821a  ldstr    aRunas// "runas"
0x821f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Verb(string)
0x8224  ldloc.0
0x8225  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x822a  ldarg.1
0x822b  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x8230  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_WorkingDirectory(string)
0x8235  ldarg.0
0x8236  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x823b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x8240  dup
0x8241  brtrue.s loc_8246
0x8243  pop
0x8244  br.s     loc_8272
0x8246  ldstr    aStarting0WithA// "Starting {0} with arguments {1}"
0x824b  ldc.i4.2
0x824c  newarr   [mscorlib]System.Object
0x8251  dup
0x8252  ldc.i4.0
0x8253  ldloc.0
0x8254  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x8259  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::get_FileName()
0x825e  stelem.ref
0x825f  dup
0x8260  ldc.i4.1
0x8261  ldloc.0
0x8262  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x8267  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::get_Arguments()
0x826c  stelem.ref
0x826d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x8272  ldloc.0
0x8273  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0x8278  brtrue.s loc_82A3
0x827a  ldstr    aFailedToStartT// "Failed to start the installer finalizer"
0x827f  stloc.2
0x8280  ldarg.0
0x8281  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x8286  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x828b  dup
0x828c  brtrue.s loc_8291
0x828e  pop
0x828f  br.s     loc_829C
0x8291  ldloc.2
0x8292  call     T0x2B000010
0x8297  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x829c  ldloc.2
0x829d  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x82a2  throw
0x82a3  ldloc.0
0x82a4  ret
```
