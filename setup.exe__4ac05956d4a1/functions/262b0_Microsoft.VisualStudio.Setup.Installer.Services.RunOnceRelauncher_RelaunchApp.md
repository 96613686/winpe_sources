# Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::RelaunchApp

- ea: `0x262b0`
- end: `0x2636e`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::RelaunchApp`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xbf50`

## callees

- `0x262b0`
- `0x59dc0`

## string_xrefs

- `0x26330`: `This process is created due to a Windows restart relaunching setup \n                                        via the runOnce registry key. It has launched another Visual Studio Installer instance, \n                                        without the runOnce parameter to complete the requested operation \n                                        and will return so that Windows can continue with boot-up. \n                                        The child Visual Studio Installer process has no`
- `0x2634f`: `Failed to relaunch installer without RunOnce parameter`

## pseudocode

```c

```

## disassembly

```asm
0x262b0  ldarg.0
0x262b1  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ResumeOptions Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::resumeOptions
0x262b6  ldc.i4.0
0x262b7  callvirt instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ResumeOptions::set_RunOnce(bool value)
0x262bc  ldarg.0
0x262bd  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ResumeOptions Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::resumeOptions
0x262c2  ldc.i4.1
0x262c3  call     T0x2B000173
0x262c8  stloc.0
0x262c9  ldarg.0
0x262ca  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::processService
0x262cf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::CreateProcess()
0x262d4  stloc.1
0x262d5  ldarg.0
0x262d6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::processService
0x262db  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::GetCurrentProcess()
0x262e0  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_MainModuleFileName()
0x262e5  stloc.2
0x262e6  ldloc.1
0x262e7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x262ec  ldloc.2
0x262ed  ldc.i4.0
0x262ee  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::QuotePath(string, bool)
0x262f3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_FileName(string)
0x262f8  ldloc.1
0x262f9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x262fe  ldloc.0
0x262ff  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Arguments(string)
0x26304  ldloc.1
0x26305  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x2630a  ldc.i4.0
0x2630b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_UseShellExecute(bool)
0x26310  ldloc.1
0x26311  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x26316  ldc.i4.1
0x26317  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_CreateNoWindow(bool)
0x2631c  ldloc.1
0x2631d  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0x26322  brfalse.s loc_26343
0x26324  ldarg.0
0x26325  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::logger
0x2632a  dup
0x2632b  brtrue.s loc_26330
0x2632d  pop
0x2632e  br.s     loc_2633F
0x26330  ldstr    aThisProcessIsC// "This process is created due to a Window"...
0x26335  call     T0x2B000010
0x2633a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2633f  ldc.i4.1
0x26340  stloc.3
0x26341  leave.s  loc_2636C
0x26343  ldarg.0
0x26344  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Services.RunOnceRelauncher::logger
0x26349  dup
0x2634a  brtrue.s loc_2634F
0x2634c  pop
0x2634d  br.s     loc_2635E
0x2634f  ldstr    aFailedToRelaun// "Failed to relaunch installer without Ru"...
0x26354  call     T0x2B000010
0x26359  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2635e  ldc.i4.0
0x2635f  stloc.3
0x26360  leave.s  loc_2636C
0x26362  ldloc.1
0x26363  brfalse.s loc_2636B
0x26365  ldloc.1
0x26366  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2636b  endfinally
0x2636c  ldloc.3
0x2636d  ret
```
