# TimeZoneSyncTask.Data.WindowsProjection::set_StandardDate

- ea: `0x10330`
- end: `0x10338`
- name: `TimeZoneSyncTask.Data.WindowsProjection::set_StandardDate`
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
0x10330  ldarg.0
0x10331  ldarg.1
0x10332  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::<StandardDate>k__BackingField
0x10337  ret
```
