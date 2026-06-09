# TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates

- ea: `0x10530`
- end: `0x10537`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates`
- size: `7`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x105b0`
- `0x10610`
- `0x10700`
- `0x107d0`
- `0x108c0`
- `0x10910`
- `0x11790`
- `0x11ff0`

## pseudocode

```c

```

## disassembly

```asm
0x10530  ldarg.0
0x10531  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::<SetDaylightDates>k__BackingField
0x10536  ret
```
