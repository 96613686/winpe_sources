# TimeZoneSyncTask.Utils.Helper::ParseInt32

- ea: `0xec20`
- end: `0xec3f`
- name: `TimeZoneSyncTask.Utils.Helper::ParseInt32`
- size: `31`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xeb30`
- `0xef60`
- `0x12530`

## callees

- `0xce30`
- `0xec40`

## pseudocode

```c

```

## disassembly

```asm
0xec20  ldarg.0
0xec21  ldloca.s 0
0xec23  call     bool TimeZoneSyncTask.Utils.Helper::TryParseInt32(string s, [out] int32& out)
0xec28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xec2d  ldstr    aExpectingInteg// "expecting integer, got {0}"
0xec32  ldarg.0
0xec33  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xec38  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xec3d  ldloc.0
0xec3e  ret
```
