# Microsoft.VisualStudio.Setup.Installer.Program::ExecuteInternal

- ea: `0xc1b0`
- end: `0xc3d1`
- name: `Microsoft.VisualStudio.Setup.Installer.Program::ExecuteInternal`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc0f0`

## callees

- `0xb090`
- `0xc1b0`
- `0xc940`
- `0xcb40`
- `0xcc60`
- `0xd4c0`
- `0x22d00`
- `0x27380`
- `0x28f30`
- `0x2b6b0`
- `0x2d730`
- `0x59ad0`
- `0x5f760`
- `0x60460`

## string_xrefs

- `0xc1fa`: `Closing the installer with exit code {0}`
- `0xc269`: `Closing the installer with exit code {0}`
- `0xc2d6`: `Cannot start a new instance of the installer while another instance is running.`

## pseudocode

```c

```

## disassembly

```asm
0xc1b0  ldarg.1
0xc1b1  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::GetAppRunProperties(class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> parserResult)
0xc1b6  stloc.0
0xc1b7  ldarg.2
0xc1b8  brtrue.s loc_C1BD
0xc1ba  ldnull
0xc1bb  br.s     loc_C1CB
0xc1bd  ldarg.2
0xc1be  ldsfld   string AppRun::AppRunEvent
0xc1c3  ldloc.0
0xc1c4  ldc.i4.0
0xc1c5  ldc.i4.0
0xc1c6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0xc1cb  stloc.1
0xc1cc  ldarg.1
0xc1cd  brfalse.s loc_C215
0xc1cf  ldarg.1
0xc1d0  callvirt instance bool class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_HasErrors()
0xc1d5  brfalse.s loc_C215
0xc1d7  ldarg.2
0xc1d8  brfalse.s loc_C1E8
0xc1da  ldarg.2
0xc1db  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ParseCommandlineEvent
0xc1e0  ldnull
0xc1e1  ldnull
0xc1e2  ldc.i4.0
0xc1e3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0xc1e8  ldloc.1
0xc1e9  brfalse.s loc_C1F6
0xc1eb  ldloc.1
0xc1ec  ldstr    aInvalidArgumen// "Invalid Argument"
0xc1f1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0xc1f6  ldarg.3
0xc1f7  brfalse.s loc_C215
0xc1f9  ldarg.3
0xc1fa  ldstr    aClosingTheInst// "Closing the installer with exit code {0"...
0xc1ff  ldc.i4.s 0x57
0xc201  box      [mscorlib]System.Int32
0xc206  call     string [mscorlib]System.String::Format(string, object)
0xc20b  call     T0x2B000010
0xc210  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0xc215  ldarg.0
0xc216  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0xc21b  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.VisualStudio.Setup.Installer.Program::ApplicationStartTime
0xc220  ldarg.1
0xc221  brtrue.s loc_C226
0xc223  ldnull
0xc224  br.s     loc_C22C
0xc226  ldarg.1
0xc227  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_Options()
0xc22c  call     class Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::GetInstance(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions serviceOptions, valuetype [mscorlib]System.DateTime applicationStartTime, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions commandLineOptions)
0xc231  stloc.2
0xc232  ldarg.0
0xc233  ldc.i4.0
0xc234  call     T0x2B000055
0xc239  dup
0xc23a  brtrue.s loc_C244
0xc23c  pop
0xc23d  ldarg.0
0xc23e  ldloc.2
0xc23f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Application.ApplicationFactory::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer services, class Microsoft.VisualStudio.Setup.Installer.Services.ITelemetryFactory telemetryFactory)
0xc244  ldarg.1
0xc245  callvirt instance class Microsoft.VisualStudio.Setup.Installer.IApplication Microsoft.VisualStudio.Setup.Installer.Application.IApplicationFactory::Create(class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> commandLineOptions)
0xc24a  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.IApplication::Run()
0xc24f  stloc.3
0xc250  ldarg.0
0xc251  ldarg.2
0xc252  ldloc.1
0xc253  ldloc.3
0xc254  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Program::CloseWindow
0xc259  call     void Microsoft.VisualStudio.Setup.Installer.Program::WriteAppRunEndProperties(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer services, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, int32 returnCode, string resultDetails)
0xc25e  ldloc.1
0xc25f  ldloc.3
0xc260  call     void Microsoft.VisualStudio.Setup.Installer.Program::RecordSuccessOrFailure(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, int32 exitCode)
0xc265  ldarg.3
0xc266  brfalse.s loc_C282
0xc268  ldarg.3
0xc269  ldstr    aClosingTheInst// "Closing the installer with exit code {0"...
0xc26e  ldc.i4.1
0xc26f  newarr   [mscorlib]System.Object
0xc274  dup
0xc275  ldc.i4.0
0xc276  ldloc.3
0xc277  box      [mscorlib]System.Int32
0xc27c  stelem.ref
0xc27d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0xc282  ldloc.3
0xc283  stloc.s  4
0xc285  leave    loc_C3CE
0xc28a  stloc.s  5
0xc28c  ldc.i4   0x138F
0xc291  stloc.s  6
0xc293  ldarg.3
0xc294  brfalse.s loc_C2A8
0xc296  ldarg.3
0xc297  ldloc.s  5
0xc299  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc29e  call     T0x2B000010
0xc2a3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xc2a8  ldarg.0
0xc2a9  ldarg.2
0xc2aa  ldloc.1
0xc2ab  ldloc.s  6
0xc2ad  ldloc.s  5
0xc2af  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc2b4  call     void Microsoft.VisualStudio.Setup.Installer.Program::WriteAppRunEndProperties(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer services, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, int32 returnCode, string resultDetails)
0xc2b9  ldloc.1
0xc2ba  brfalse.s loc_C2C9
0xc2bc  ldloc.1
0xc2bd  ldloc.s  5
0xc2bf  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc2c4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0xc2c9  ldloc.s  6
0xc2cb  stloc.s  4
0xc2cd  leave    loc_C3CE
0xc2d2  pop
0xc2d3  ldc.i4.0
0xc2d4  stloc.s  7
0xc2d6  ldstr    aCannotStartANe// "Cannot start a new instance of the inst"...
0xc2db  stloc.s  8
0xc2dd  ldarg.1
0xc2de  brtrue.s loc_C2E3
0xc2e0  ldnull
0xc2e1  br.s     loc_C2E9
0xc2e3  ldarg.1
0xc2e4  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_Options()
0xc2e9  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions
0xc2ee  stloc.s  0xA
0xc2f0  ldloc.s  0xA
0xc2f2  brtrue.s loc_C2F7
0xc2f4  ldnull
0xc2f5  br.s     loc_C2FE
0xc2f7  ldloc.s  0xA
0xc2f9  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_PipeName()
0xc2fe  stloc.s  9
0xc300  ldarg.0
0xc301  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.WindowSignalServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0xc306  ldloc.s  9
0xc308  call     class Microsoft.VisualStudio.Setup.Installer.Services.IWindowSignalService Microsoft.VisualStudio.Setup.Installer.Services.WindowSignalService::CreateDefault(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.WindowSignalServiceOptions serviceOptions, string pipeName)
0xc30d  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IWindowSignalService::Signal()
0xc312  ldarg.3
0xc313  brfalse.s loc_C322
0xc315  ldarg.3
0xc316  ldloc.s  8
0xc318  call     T0x2B000010
0xc31d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xc322  ldarg.0
0xc323  ldarg.2
0xc324  ldloc.1
0xc325  ldloc.s  7
0xc327  ldloc.s  8
0xc329  call     void Microsoft.VisualStudio.Setup.Installer.Program::WriteAppRunEndProperties(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer services, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, int32 returnCode, string resultDetails)
0xc32e  ldloc.1
0xc32f  brfalse.s loc_C339
0xc331  ldloc.1
0xc332  ldloc.s  8
0xc334  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0xc339  ldloc.s  7
0xc33b  stloc.s  4
0xc33d  leave    loc_C3CE
0xc342  stloc.s  0xB
0xc344  ldstr    aApplicationFai// "Application failed with an uncaught exc"...
0xc349  ldloc.s  0xB
0xc34b  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc350  call     string [mscorlib]System.String::Concat(string, string)
0xc355  stloc.s  0xC
0xc357  ldarg.3
0xc358  brfalse.s loc_C369
0xc35a  ldarg.3
0xc35b  ldloc.s  0xB
0xc35d  ldloc.s  0xC
0xc35f  call     T0x2B000010
0xc364  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0xc369  ldarg.0
0xc36a  ldarg.2
0xc36b  ldloc.1
0xc36c  ldloc.s  0xB
0xc36e  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0xc373  ldloc.s  0xB
0xc375  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc37a  call     void Microsoft.VisualStudio.Setup.Installer.Program::WriteAppRunEndProperties(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer services, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, int32 returnCode, string resultDetails)
0xc37f  ldloc.1
0xc380  brfalse.s loc_C394
0xc382  ldloc.1
0xc383  ldloc.s  0xC
0xc385  ldloc.s  0xB
0xc387  ldloc.s  0xB
0xc389  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc38e  ldc.i4.0
0xc38f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0xc394  ldarg.0
0xc395  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Program::GetLogFiles(class [mscorlib]System.IServiceProvider services)
0xc39a  stloc.s  0xD
0xc39c  ldarg.2
0xc39d  brfalse.s loc_C3B9
0xc39f  ldarg.2
0xc3a0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ApplicationFaultEvent
0xc3a5  ldstr    aTheApplication// "The application caught an unexpected ex"...
0xc3aa  ldnull
0xc3ab  ldloc.s  0xB
0xc3ad  ldnull
0xc3ae  ldc.i4.0
0xc3af  ldnull
0xc3b0  ldc.i4.1
0xc3b1  ldloc.s  0xD
0xc3b3  ldc.i4.0
0xc3b4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0xc3b9  ldloc.s  0xB
0xc3bb  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0xc3c0  stloc.s  4
0xc3c2  leave.s  loc_C3CE
0xc3c4  ldloc.1
0xc3c5  brfalse.s loc_C3CD
0xc3c7  ldloc.1
0xc3c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc3cd  endfinally
0xc3ce  ldloc.s  4
0xc3d0  ret
```
