# TimeZoneSyncTask.Data.Rule::get_LocalStandardOffset

- ea: `0xf500`
- end: `0xf507`
- name: `TimeZoneSyncTask.Data.Rule::get_LocalStandardOffset`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task`

## callers

- `0xf540`
- `0xf590`
- `0x10970`

## pseudocode

```c

```

## disassembly

```asm
0xf500  ldarg.0
0xf501  ldfld    valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Rule::<LocalStandardOffset>k__BackingField
0xf506  ret
```
