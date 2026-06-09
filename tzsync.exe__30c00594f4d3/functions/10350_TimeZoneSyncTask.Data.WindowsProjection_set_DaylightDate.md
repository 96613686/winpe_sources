# TimeZoneSyncTask.Data.WindowsProjection::set_DaylightDate

- ea: `0x10350`
- end: `0x10358`
- name: `TimeZoneSyncTask.Data.WindowsProjection::set_DaylightDate`
- size: `8`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x10020`
- `0x10920`
- `0x116d0`

## pseudocode

```c

```

## disassembly

```asm
0x10350  ldarg.0
0x10351  ldarg.1
0x10352  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::<DaylightDate>k__BackingField
0x10357  ret
```
