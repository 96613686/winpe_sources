# TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset

- ea: `0xf740`
- end: `0xf747`
- name: `TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset`
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
0xf740  ldarg.0
0xf741  ldfld    valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::<LocalStandardOffset>k__BackingField
0xf746  ret
```
