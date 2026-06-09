# <InvokeAsync>d__15::MoveNext

- ea: `0x62d70`
- end: `0x6302b`
- name: `<InvokeAsync>d__15::MoveNext`
- size: `699`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x7570`
- `0x75d0`
- `0x7630`
- `0x8620`
- `0x8890`
- `0x62d70`

## string_xrefs

- `0x62d91`: `The installer has not been extracted successfully`
- `0x62db4`: `Directory not found: `

## pseudocode

```c

```

## disassembly

```asm
0x62d70  ldarg.0
0x62d71  ldfld    int32 <InvokeAsync>d__15::<>1__state
0x62d76  stloc.0
0x62d77  ldarg.0
0x62d78  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <InvokeAsync>d__15::<>4__this
0x62d7d  stloc.1
0x62d7e  ldloc.0
0x62d7f  brfalse  loc_62F2F
0x62d84  ldloc.1
0x62d85  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x62d8a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62d8f  brfalse.s loc_62D9C
0x62d91  ldstr    aTheInstallerHa// "The installer has not been extracted su"...
0x62d96  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x62d9b  throw
0x62d9c  ldloc.1
0x62d9d  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62da2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x62da7  ldloc.1
0x62da8  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x62dad  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x62db2  brtrue.s loc_62DCA
0x62db4  ldstr    aDirectoryNotFo// "Directory not found: "
0x62db9  ldloc.1
0x62dba  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x62dbf  call     string [mscorlib]System.String::Concat(string, string)
0x62dc4  newobj   instance void [mscorlib]System.IO.DirectoryNotFoundException::.ctor(string)
0x62dc9  throw
0x62dca  ldarg.0
0x62dcb  ldloc.1
0x62dcc  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::GetTemporaryInstallerPath()
0x62dd1  stfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62dd6  ldloc.1
0x62dd7  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62ddc  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x62de1  ldarg.0
0x62de2  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62de7  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x62dec  brtrue.s loc_62E0A
0x62dee  ldstr    aFileNotFound// "File not found: "
0x62df3  ldarg.0
0x62df4  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62df9  call     string [mscorlib]System.String::Concat(string, string)
0x62dfe  ldarg.0
0x62dff  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62e04  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x62e09  throw
0x62e0a  ldloc.1
0x62e0b  ldarg.0
0x62e0c  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62e11  call     instance void Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::ValidateMicrosoftSignature(string path)
0x62e16  ldloc.1
0x62e17  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62e1c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_ProcessService()
0x62e21  stloc.3
0x62e22  ldarg.0
0x62e23  ldloc.3
0x62e24  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::CreateProcess()
0x62e29  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62e2e  ldarg.0
0x62e2f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62e34  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x62e39  ldarg.0
0x62e3a  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62e3f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_FileName(string)
0x62e44  ldarg.0
0x62e45  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62e4a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x62e4f  ldarg.0
0x62e50  ldfld    string <InvokeAsync>d__15::commandLine
0x62e55  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Arguments(string)
0x62e5a  ldarg.0
0x62e5b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62e60  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x62e65  ldc.i4.1
0x62e66  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_UseShellExecute(bool)
0x62e6b  ldarg.0
0x62e6c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62e71  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x62e76  ldstr    aRunas// "runas"
0x62e7b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Verb(string)
0x62e80  ldarg.0
0x62e81  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62e86  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x62e8b  ldarg.0
0x62e8c  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62e91  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x62e96  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_WorkingDirectory(string)
0x62e9b  ldarg.0
0x62e9c  ldc.i4.2
0x62e9d  stfld    int32 <InvokeAsync>d__15::<retries>5__4
0x62ea2  ldarg.0
0x62ea3  ldc.i4.0
0x62ea4  stfld    bool <InvokeAsync>d__15::<retrySucceeded>5__5
0x62ea9  ldloc.1
0x62eaa  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62eaf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62eb4  dup
0x62eb5  brtrue.s loc_62EBA
0x62eb7  pop
0x62eb8  br.s     loc_62EDC
0x62eba  ldstr    aStartingProces// "Starting process: {0}, arguments: {1}"
0x62ebf  ldc.i4.2
0x62ec0  newarr   [mscorlib]System.Object
0x62ec5  dup
0x62ec6  ldc.i4.0
0x62ec7  ldarg.0
0x62ec8  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62ecd  stelem.ref
0x62ece  dup
0x62ecf  ldc.i4.1
0x62ed0  ldarg.0
0x62ed1  ldfld    string <InvokeAsync>d__15::commandLine
0x62ed6  stelem.ref
0x62ed7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x62edc  ldarg.0
0x62edd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62ee2  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0x62ee7  brtrue   loc_62FD8
0x62eec  br       loc_62FAE
0x62ef1  ldc.i4   0xBB8
0x62ef6  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Delay(int32)
0x62efb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x62f00  stloc.s  4
0x62f02  ldloca.s 4
0x62f04  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x62f09  brtrue.s loc_62F4C
0x62f0b  ldarg.0
0x62f0c  ldc.i4.0
0x62f0d  dup
0x62f0e  stloc.0
0x62f0f  stfld    int32 <InvokeAsync>d__15::<>1__state
0x62f14  ldarg.0
0x62f15  ldloc.s  4
0x62f17  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__15::<>u__1
0x62f1c  ldarg.0
0x62f1d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess> <InvokeAsync>d__15::<>t__builder
0x62f22  ldloca.s 4
0x62f24  ldarg.0
0x62f25  call     T0x2B000408
0x62f2a  leave    loc_6302A
0x62f2f  ldarg.0
0x62f30  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__15::<>u__1
0x62f35  stloc.s  4
0x62f37  ldarg.0
0x62f38  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__15::<>u__1
0x62f3d  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x62f43  ldarg.0
0x62f44  ldc.i4.m1
0x62f45  dup
0x62f46  stloc.0
0x62f47  stfld    int32 <InvokeAsync>d__15::<>1__state
0x62f4c  ldloca.s 4
0x62f4e  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x62f53  ldloc.1
0x62f54  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62f59  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62f5e  dup
0x62f5f  brtrue.s loc_62F64
0x62f61  pop
0x62f62  br.s     loc_62F86
0x62f64  ldstr    aFailedToStartP// "Failed to start process: {0}, arguments"...
0x62f69  ldc.i4.2
0x62f6a  newarr   [mscorlib]System.Object
0x62f6f  dup
0x62f70  ldc.i4.0
0x62f71  ldarg.0
0x62f72  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62f77  stelem.ref
0x62f78  dup
0x62f79  ldc.i4.1
0x62f7a  ldarg.0
0x62f7b  ldfld    string <InvokeAsync>d__15::commandLine
0x62f80  stelem.ref
0x62f81  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x62f86  ldarg.0
0x62f87  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62f8c  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0x62f91  brfalse.s loc_62F9C
0x62f93  ldarg.0
0x62f94  ldc.i4.1
0x62f95  stfld    bool <InvokeAsync>d__15::<retrySucceeded>5__5
0x62f9a  br.s     loc_62FBA
0x62f9c  ldarg.0
0x62f9d  ldfld    int32 <InvokeAsync>d__15::<retries>5__4
0x62fa2  stloc.s  5
0x62fa4  ldarg.0
0x62fa5  ldloc.s  5
0x62fa7  ldc.i4.1
0x62fa8  sub
0x62fa9  stfld    int32 <InvokeAsync>d__15::<retries>5__4
0x62fae  ldarg.0
0x62faf  ldfld    int32 <InvokeAsync>d__15::<retries>5__4
0x62fb4  ldc.i4.0
0x62fb5  bgt      loc_62EF1
0x62fba  ldarg.0
0x62fbb  ldfld    bool <InvokeAsync>d__15::<retrySucceeded>5__5
0x62fc0  brtrue.s loc_62FD8
0x62fc2  ldstr    aTheProcessWasN// "The process was not started: "
0x62fc7  ldarg.0
0x62fc8  ldfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62fcd  call     string [mscorlib]System.String::Concat(string, string)
0x62fd2  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x62fd7  throw
0x62fd8  ldarg.0
0x62fd9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62fde  stloc.2
0x62fdf  leave.s  loc_63008
0x62fe1  stloc.s  6
0x62fe3  ldarg.0
0x62fe4  ldc.i4.s 0xFE
0x62fe6  stfld    int32 <InvokeAsync>d__15::<>1__state
0x62feb  ldarg.0
0x62fec  ldnull
0x62fed  stfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x62ff2  ldarg.0
0x62ff3  ldnull
0x62ff4  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x62ff9  ldarg.0
0x62ffa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess> <InvokeAsync>d__15::<>t__builder
0x62fff  ldloc.s  6
0x63001  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess>::SetException(class [mscorlib]System.Exception)
0x63006  leave.s  loc_6302A
0x63008  ldarg.0
0x63009  ldc.i4.s 0xFE
0x6300b  stfld    int32 <InvokeAsync>d__15::<>1__state
0x63010  ldarg.0
0x63011  ldnull
0x63012  stfld    string <InvokeAsync>d__15::<installerFilePath>5__2
0x63017  ldarg.0
0x63018  ldnull
0x63019  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess <InvokeAsync>d__15::<process>5__3
0x6301e  ldarg.0
0x6301f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess> <InvokeAsync>d__15::<>t__builder
0x63024  ldloc.2
0x63025  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess>::SetResult(var<u1>)
0x6302a  ret
```
