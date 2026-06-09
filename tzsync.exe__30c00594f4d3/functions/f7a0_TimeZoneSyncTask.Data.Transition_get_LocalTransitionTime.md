# TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime

- ea: `0xf7a0`
- end: `0xf7bd`
- name: `TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x11790`
- `0x145b0`

## callees

- `0xf720`
- `0xf740`
- `0xf760`

## pseudocode

```c

```

## disassembly

```asm
0xf7a0  ldarg.0
0xf7a1  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0xf7a6  ldarg.0
0xf7a7  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0xf7ac  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xf7b1  ldarg.0
0xf7b2  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_UtcOffset()
0xf7b7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xf7bc  ret
```
