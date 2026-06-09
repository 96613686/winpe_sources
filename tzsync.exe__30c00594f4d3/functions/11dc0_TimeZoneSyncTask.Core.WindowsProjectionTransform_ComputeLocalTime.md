# TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeLocalTime

- ea: `0x11dc0`
- end: `0x11eea`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeLocalTime`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f40`

## callees

- `0x102e0`
- `0x10300`
- `0x10320`
- `0x10340`
- `0x11dc0`

## pseudocode

```c

```

## disassembly

```asm
0x11dc0  ldc.i4.0
0x11dc1  stloc.0
0x11dc2  ldarga.s 1
0x11dc4  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x11dc9  stloc.1
0x11dca  ldloca.s 1
0x11dcc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x11dd1  brfalse  loc_11E76
0x11dd6  ldarga.s 1
0x11dd8  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11ddd  stloc.1
0x11dde  ldloca.s 1
0x11de0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x11de5  brfalse  loc_11E76
0x11dea  ldarga.s 1
0x11dec  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x11df1  stloc.1
0x11df2  ldloca.s 1
0x11df4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11df9  ldarga.s 1
0x11dfb  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11e00  stloc.1
0x11e01  ldloca.s 1
0x11e03  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11e08  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11e0d  brfalse.s loc_11E44
0x11e0f  ldarg.0
0x11e10  ldarga.s 1
0x11e12  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x11e17  stloc.1
0x11e18  ldloca.s 1
0x11e1a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11e1f  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11e24  brtrue.s loc_11E3D
0x11e26  ldarg.0
0x11e27  ldarga.s 1
0x11e29  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11e2e  stloc.1
0x11e2f  ldloca.s 1
0x11e31  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11e36  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11e3b  br.s     loc_11E3E
0x11e3d  ldc.i4.1
0x11e3e  stloc.0
0x11e3f  br       loc_11EC6
0x11e44  ldarg.0
0x11e45  ldarga.s 1
0x11e47  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11e4c  stloc.1
0x11e4d  ldloca.s 1
0x11e4f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11e54  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11e59  brfalse.s loc_11E72
0x11e5b  ldarg.0
0x11e5c  ldarga.s 1
0x11e5e  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x11e63  stloc.1
0x11e64  ldloca.s 1
0x11e66  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11e6b  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11e70  br.s     loc_11E73
0x11e72  ldc.i4.0
0x11e73  stloc.0
0x11e74  br.s     loc_11EC6
0x11e76  ldarga.s 1
0x11e78  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x11e7d  stloc.1
0x11e7e  ldloca.s 1
0x11e80  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x11e85  brfalse.s loc_11E9F
0x11e87  ldarg.0
0x11e88  ldarga.s 1
0x11e8a  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x11e8f  stloc.1
0x11e90  ldloca.s 1
0x11e92  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11e97  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11e9c  stloc.0
0x11e9d  br.s     loc_11EC6
0x11e9f  ldarga.s 1
0x11ea1  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11ea6  stloc.1
0x11ea7  ldloca.s 1
0x11ea9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x11eae  brfalse.s loc_11EC6
0x11eb0  ldarg.0
0x11eb1  ldarga.s 1
0x11eb3  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11eb8  stloc.1
0x11eb9  ldloca.s 1
0x11ebb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11ec0  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11ec5  stloc.0
0x11ec6  ldarg.0
0x11ec7  ldarga.s 1
0x11ec9  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0x11ece  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x11ed3  ldloc.0
0x11ed4  brtrue.s loc_11EDD
0x11ed6  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x11edb  br.s     loc_11EE4
0x11edd  ldarga.s 1
0x11edf  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0x11ee4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x11ee9  ret
```
