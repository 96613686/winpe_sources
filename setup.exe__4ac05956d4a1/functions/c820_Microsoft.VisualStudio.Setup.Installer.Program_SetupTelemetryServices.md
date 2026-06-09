# Microsoft.VisualStudio.Setup.Installer.Program::SetupTelemetryServices

- ea: `0xc820`
- end: `0xc88a`
- name: `Microsoft.VisualStudio.Setup.Installer.Program::SetupTelemetryServices`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xc5c0`

## callees

- `0xc820`
- `0xcab0`
- `0xcad0`
- `0x22d20`
- `0x230b0`

## string_xrefs

- `0xc82d`: `Setting the telemetry services`

## pseudocode

```c

```

## disassembly

```asm
0xc820  ldarg.0
0xc821  ldc.i4.0
0xc822  call     T0x2B00004E
0xc827  dup
0xc828  brtrue.s loc_C82D
0xc82a  pop
0xc82b  br.s     loc_C83C
0xc82d  ldstr    aSettingTheTele// "Setting the telemetry services"
0xc832  call     T0x2B000010
0xc837  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xc83c  ldarg.0
0xc83d  ldc.i4.0
0xc83e  call     T0x2B000065
0xc843  brfalse.s loc_C858
0xc845  ldarg.0
0xc846  ldc.i4.0
0xc847  call     T0x2B000066
0xc84c  brfalse.s loc_C858
0xc84e  ldarg.0
0xc84f  ldc.i4.0
0xc850  call     T0x2B000052
0xc855  brfalse.s loc_C858
0xc857  ret
0xc858  ldarg.1
0xc859  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.VisualStudio.Setup.Installer.Program::ApplicationStartTime
0xc85e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.LazyTelemetryProxy::.ctor(class Microsoft.VisualStudio.Setup.Installer.Services.ITelemetryFactory telemetryFactory, valuetype [mscorlib]System.DateTime startTime)
0xc863  stloc.0
0xc864  ldarg.0
0xc865  ldloc.0
0xc866  ldc.i4.0
0xc867  ldc.i4.0
0xc868  callvirt T0x2B000067
0xc86d  ldarg.1
0xc86e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.LazyTargetedNotificationsProxy::.ctor(class Microsoft.VisualStudio.Setup.Installer.Services.ITelemetryFactory telemetryFactory)
0xc873  stloc.1
0xc874  ldarg.0
0xc875  ldloc.1
0xc876  ldc.i4.0
0xc877  ldc.i4.0
0xc878  callvirt T0x2B000068
0xc87d  ldloc.0
0xc87e  call     void Microsoft.VisualStudio.Setup.Installer.Program::WriteAppInitializePreTelemetryEvent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry)
0xc883  ldloc.0
0xc884  call     void Microsoft.VisualStudio.Setup.Installer.Program::SendOptOutEvent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry)
0xc889  ret
```
