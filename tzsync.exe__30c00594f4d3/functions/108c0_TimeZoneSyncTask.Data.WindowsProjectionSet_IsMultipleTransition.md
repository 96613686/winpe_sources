# TimeZoneSyncTask.Data.WindowsProjectionSet::IsMultipleTransition

- ea: `0x108c0`
- end: `0x108eb`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::IsMultipleTransition`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0xc6e0`

## callees

- `0x104d0`
- `0x10510`
- `0x10530`
- `0x108c0`

## pseudocode

```c

```

## disassembly

```asm
0x108c0  ldarg.0
0x108c1  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x108c6  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::get_Count()
0x108cb  ldc.i4.1
0x108cc  bne.un.s loc_108E9
0x108ce  ldarg.0
0x108cf  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x108d4  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x108d9  ldarg.0
0x108da  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x108df  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x108e4  mul
0x108e5  ldc.i4.1
0x108e6  cgt
0x108e8  ret
0x108e9  ldc.i4.0
0x108ea  ret
```
