# Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::CreateTelemetrySingleton

- ea: `0x27490`
- end: `0x275df`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::CreateTelemetrySingleton`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1a780`
- `0x27490`
- `0x27790`
- `0x2d6b0`
- `0x58e10`
- `0x592e0`

## string_xrefs

- `0x2749c`: `Creating a new telemetry service based on the previously serialized session.`
- `0x2752e`: `Creating a new telemetry service.`

## pseudocode

```c

```

## disassembly

```asm
0x27490  ldarg.0
0x27491  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::serviceOptions
0x27496  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x2749b  stloc.0
0x2749c  ldstr    aCreatingANewTe// "Creating a new telemetry service based "...
0x274a1  stloc.1
0x274a2  ldarg.0
0x274a3  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::commandLineOptions
0x274a8  stloc.s  7
0x274aa  ldloc.s  7
0x274ac  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ElevateOptions
0x274b1  stloc.s  5
0x274b3  ldloc.s  5
0x274b5  brtrue.s loc_274C6
0x274b7  ldloc.s  7
0x274b9  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase
0x274be  stloc.s  6
0x274c0  ldloc.s  6
0x274c2  brtrue.s loc_274F8
0x274c4  br.s     loc_2752A
0x274c6  ldloc.s  5
0x274c8  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ElevateOptions::get_SerializedSession()
0x274cd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x274d2  brtrue.s loc_2752A
0x274d4  ldloc.0
0x274d5  brfalse.s loc_274E3
0x274d7  ldloc.0
0x274d8  ldloc.1
0x274d9  call     T0x2B000010
0x274de  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x274e3  ldarg.0
0x274e4  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::GetServices()
0x274e9  ldloc.s  5
0x274eb  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ElevateOptions::get_SerializedSession()
0x274f0  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::.ctor(class [mscorlib]System.IServiceProvider, string)
0x274f5  stloc.2
0x274f6  br.s     loc_27549
0x274f8  ldloc.s  6
0x274fa  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_SerializedSession()
0x274ff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27504  brtrue.s loc_2752A
0x27506  ldloc.0
0x27507  brfalse.s loc_27515
0x27509  ldloc.0
0x2750a  ldloc.1
0x2750b  call     T0x2B000010
0x27510  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x27515  ldarg.0
0x27516  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::GetServices()
0x2751b  ldloc.s  6
0x2751d  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_SerializedSession()
0x27522  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::.ctor(class [mscorlib]System.IServiceProvider, string)
0x27527  stloc.2
0x27528  br.s     loc_27549
0x2752a  ldloc.0
0x2752b  brfalse.s loc_2753D
0x2752d  ldloc.0
0x2752e  ldstr    aCreatingANewTe_0// "Creating a new telemetry service."
0x27533  call     T0x2B000010
0x27538  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2753d  ldarg.0
0x2753e  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::GetServices()
0x27543  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::.ctor(class [mscorlib]System.IServiceProvider)
0x27548  stloc.2
0x27549  ldloc.0
0x2754a  brfalse.s loc_27566
0x2754c  ldloc.0
0x2754d  ldstr    aTelemetrySessi// "Telemetry session ID: {0}"
0x27552  ldc.i4.1
0x27553  newarr   [mscorlib]System.Object
0x27558  dup
0x27559  ldc.i4.0
0x2755a  ldloc.2
0x2755b  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySessionID()
0x27560  stelem.ref
0x27561  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x27566  ldloc.2
0x27567  callvirt instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x2756c  stloc.s  8
0x2756e  ldloc.s  8
0x27570  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.WindowsErrorReporting.BucketFilter> [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::get_BucketFiltersToEnableWatsonForFaults()
0x27575  brtrue.s loc_27586
0x27577  ldloc.s  8
0x27579  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.WindowsErrorReporting.BucketFilter>::.ctor()
0x2757e  dup
0x2757f  stloc.s  9
0x27581  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::set_BucketFiltersToEnableWatsonForFaults(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.WindowsErrorReporting.BucketFilter>)
0x27586  ldloc.2
0x27587  callvirt instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x2758c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.WindowsErrorReporting.BucketFilter> [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::get_BucketFiltersToEnableWatsonForFaults()
0x27591  call     void Microsoft.VisualStudio.Setup.Installer.Telemetry.BucketFilterManager::AddBucketFilters(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.WindowsErrorReporting.BucketFilter> bucketFilters)
0x27596  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2759b  ldarg.0
0x2759c  ldfld    valuetype [mscorlib]System.DateTime Microsoft.VisualStudio.Setup.Installer.Services.TelemetryFactory::applicationStartTime
0x275a1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x275a6  stloc.3
0x275a7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x275ac  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::TimeSinceAppStartProperty
0x275b1  stloc.s  0xA
0x275b3  dup
0x275b4  ldloc.s  0xA
0x275b6  ldloca.s 3
0x275b8  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x275bd  call     float64 [mscorlib]System.Math::Round(float64)
0x275c2  box      [mscorlib]System.Double
0x275c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x275cc  stloc.s  4
0x275ce  ldloc.2
0x275cf  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::TelemetryInitializedEvent
0x275d4  ldloc.s  4
0x275d6  ldnull
0x275d7  ldc.i4.0
0x275d8  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x275dd  ldloc.2
0x275de  ret
```
