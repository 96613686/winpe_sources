# TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets

- ea: `0x104d0`
- end: `0x104d7`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets`
- size: `7`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x105b0`
- `0x10610`
- `0x10700`
- `0x10770`
- `0x107d0`
- `0x108c0`
- `0x11790`

## pseudocode

```c

```

## disassembly

```asm
0x104d0  ldarg.0
0x104d1  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::<SetUtcOffsets>k__BackingField
0x104d6  ret
```
