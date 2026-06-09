# TimeZoneSyncTask.Core.WindowsProjectionTransform::IsNextTransitionAccurate

- ea: `0x12080`
- end: `0x120c1`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::IsNextTransitionAccurate`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14690`

## callees

- `0x11f60`
- `0x11ff0`
- `0x12080`

## pseudocode

```c

```

## disassembly

```asm
0x12080  ldarg.0
0x12081  ldarg.1
0x12082  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeNextTransition(valuetype [mscorlib]System.DateTime dtCurrent, valuetype TimeZoneSyncTask.Data.WindowsProjection projection)
0x12087  stloc.0
0x12088  ldarg.0
0x12089  ldarg.2
0x1208a  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeNextTransition(valuetype [mscorlib]System.DateTime dtCurrent, class TimeZoneSyncTask.Data.WindowsProjectionSet projectionSet)
0x1208f  stloc.1
0x12090  ldloca.s 0
0x12092  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x12097  ldloca.s 1
0x12099  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1209e  beq.s    loc_120A2
0x120a0  ldc.i4.0
0x120a1  ret
0x120a2  ldloca.s 0
0x120a4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x120a9  brtrue.s loc_120AD
0x120ab  ldc.i4.1
0x120ac  ret
0x120ad  ldloca.s 0
0x120af  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x120b4  ldloca.s 1
0x120b6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x120bb  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x120c0  ret
```
