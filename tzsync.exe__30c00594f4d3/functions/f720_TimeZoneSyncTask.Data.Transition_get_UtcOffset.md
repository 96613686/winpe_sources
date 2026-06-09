# TimeZoneSyncTask.Data.Transition::get_UtcOffset

- ea: `0xf720`
- end: `0xf727`
- name: `TimeZoneSyncTask.Data.Transition::get_UtcOffset`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task`

## callers

- `0xf7a0`
- `0xf7e0`
- `0xf840`
- `0x11790`
- `0x11ef0`

## pseudocode

```c

```

## disassembly

```asm
0xf720  ldarg.0
0xf721  ldfld    valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::<UtcOffset>k__BackingField
0xf726  ret
```
