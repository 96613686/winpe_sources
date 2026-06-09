# TimeZoneSyncTask.Utils.Helper::GetMonthAbbreviation

- ea: `0xe940`
- end: `0xe971`
- name: `TimeZoneSyncTask.Utils.Helper::GetMonthAbbreviation`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xf1f0`
- `0xfc30`

## callees

- `0xce30`

## pseudocode

```c

```

## disassembly

```asm
0xe940  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> TimeZoneSyncTask.Utils.Helper::mapMonthAbbreviations
0xe945  ldarg.0
0xe946  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsKey(var<u1>)
0xe94b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe950  ldstr    aExpectingValid_1// "expecting valid month, got {0}"
0xe955  ldarg.0
0xe956  box      [mscorlib]System.Int32
0xe95b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xe960  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xe965  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> TimeZoneSyncTask.Utils.Helper::mapMonthAbbreviations
0xe96a  ldarg.0
0xe96b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0xe970  ret
```
