# TimeZoneSyncTask.Program::IsTzsyncElevated

- ea: `0xc620`
- end: `0xc66d`
- name: `TimeZoneSyncTask.Program::IsTzsyncElevated`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc470`

## callees

- `0xc620`
- `0xcff0`

## string_xrefs

- `0xc63b`: `Unauthorized Access Exception - Expected as running not Elevated -`

## pseudocode

```c

```

## disassembly

```asm
0xc620  ldc.i4.0
0xc621  stloc.0
0xc622  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0xc627  newobj   instance void [mscorlib]System.Security.Principal.WindowsPrincipal::.ctor(class [mscorlib]System.Security.Principal.WindowsIdentity)
0xc62c  ldc.i4   0x220
0xc631  callvirt instance bool [mscorlib]System.Security.Principal.WindowsPrincipal::IsInRole(valuetype [mscorlib]System.Security.Principal.WindowsBuiltInRole)
0xc636  stloc.0
0xc637  leave.s  loc_C66B
0xc639  stloc.1
0xc63a  ldc.i4.0
0xc63b  ldstr    aUnauthorizedAc// "Unauthorized Access Exception - Expecte"...
0xc640  ldloc.1
0xc641  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc646  call     string [mscorlib]System.String::Format(string, object)
0xc64b  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc650  leave.s  loc_C66B
0xc652  stloc.2
0xc653  ldc.i4.1
0xc654  ldstr    aException// "Exception -"
0xc659  ldloc.2
0xc65a  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc65f  call     string [mscorlib]System.String::Format(string, object)
0xc664  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc669  leave.s  loc_C66B
0xc66b  ldloc.0
0xc66c  ret
```
