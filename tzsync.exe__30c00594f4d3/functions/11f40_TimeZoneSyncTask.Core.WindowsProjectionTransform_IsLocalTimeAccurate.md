# TimeZoneSyncTask.Core.WindowsProjectionTransform::IsLocalTimeAccurate

- ea: `0x11f40`
- end: `0x11f54`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::IsLocalTimeAccurate`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x11c70`
- `0x14660`

## callees

- `0x11dc0`
- `0x11ef0`

## pseudocode

```c

```

## disassembly

```asm
0x11f40  ldarg.0
0x11f41  ldarg.1
0x11f42  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeLocalTime(valuetype [mscorlib]System.DateTime dtCurrent, valuetype TimeZoneSyncTask.Data.WindowsProjection projection)
0x11f47  ldarg.0
0x11f48  ldarg.2
0x11f49  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeLocalTime(valuetype [mscorlib]System.DateTime dtCurrent, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions)
0x11f4e  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11f53  ret
```
