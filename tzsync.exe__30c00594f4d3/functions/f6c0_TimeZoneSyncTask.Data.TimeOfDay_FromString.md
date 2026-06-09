# TimeZoneSyncTask.Data.TimeOfDay::FromString

- ea: `0xf6c0`
- end: `0xf70a`
- name: `TimeZoneSyncTask.Data.TimeOfDay::FromString`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x12530`

## callees

- `0xeab0`
- `0xeb30`
- `0xf5f0`
- `0xf610`

## pseudocode

```c

```

## disassembly

```asm
0xf6c0  ldarg.0
0xf6c1  ldsfld   string TimeZoneSyncTask.Utils.Helper::TimeBaseSuffixes
0xf6c6  ldftn    T0x2B00001D
0xf6cc  newobj   instance void class [mscorlib]System.Func`2<char, bool>::.ctor(object, native int)
0xf6d1  call     T0x2B00001E
0xf6d6  stloc.0
0xf6d7  ldloca.s 1
0xf6d9  initobj  TimeZoneSyncTask.Data.TimeOfDay
0xf6df  ldloca.s 1
0xf6e1  ldarg.0
0xf6e2  ldsfld   string TimeZoneSyncTask.Utils.Helper::TimeBaseSuffixes
0xf6e7  call     T0x2B00001F
0xf6ec  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xf6f1  call     valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Utils.Helper::ParseTimeSpan(string ts)
0xf6f6  call     instance void TimeZoneSyncTask.Data.TimeOfDay::set_Duration(valuetype [mscorlib]System.TimeSpan value)
0xf6fb  ldloca.s 1
0xf6fd  ldloc.0
0xf6fe  call     valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Utils.Helper::FromSuffixToBase(char c)
0xf703  call     instance void TimeZoneSyncTask.Data.TimeOfDay::set_Base(valuetype TimeZoneSyncTask.Data.TimeBase value)
0xf708  ldloc.1
0xf709  ret
```
