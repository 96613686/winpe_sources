# TimeZoneSyncTask.TimeZoneSync::Require_0

- ea: `0xce40`
- end: `0xce99`
- name: `TimeZoneSyncTask.TimeZoneSync::Require_0`
- size: `89`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0xc6e0`
- `0xce30`
- `0xcee0`
- `0xd2c0`
- `0xe120`
- `0xfdf0`
- `0x11190`

## callees

- `0xce40`
- `0xcff0`
- `0x14140`
- `0x14170`
- `0x141a0`

## string_xrefs

- `0xce51`: `Registry`

## pseudocode

```c

```

## disassembly

```asm
0xce40  ldarg.0
0xce41  brtrue.s loc_CE98
0xce43  ldarg.1
0xce44  ldstr    aData// "Data"
0xce49  call     bool [mscorlib]System.String::op_Equality(string, string)
0xce4e  brtrue.s loc_CE78
0xce50  ldarg.1
0xce51  ldstr    aRegistry// "Registry"
0xce56  call     bool [mscorlib]System.String::op_Equality(string, string)
0xce5b  brtrue.s loc_CE7F
0xce5d  ldarg.1
0xce5e  ldstr    aWnf// "WNF"
0xce63  call     bool [mscorlib]System.String::op_Equality(string, string)
0xce68  brtrue.s loc_CE86
0xce6a  ldarg.1
0xce6b  ldstr    aDefault// "default"
0xce70  call     bool [mscorlib]System.String::op_Equality(string, string)
0xce75  brtrue.s loc_CE8D
0xce77  ret
0xce78  ldarg.2
0xce79  newobj   instance void IANADataValidationException::.ctor(string msg)
0xce7e  throw
0xce7f  ldarg.2
0xce80  newobj   instance void RegistryException::.ctor(string msg)
0xce85  throw
0xce86  ldarg.2
0xce87  newobj   instance void WNFNotificationException::.ctor(string msg)
0xce8c  throw
0xce8d  ldc.i4.1
0xce8e  ldstr    aUnknownExcepti// "Unknown exception - needs to be defined"...
0xce93  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xce98  ret
```
