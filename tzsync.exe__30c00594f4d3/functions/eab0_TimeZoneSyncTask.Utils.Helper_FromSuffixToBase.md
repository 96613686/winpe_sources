# TimeZoneSyncTask.Utils.Helper::FromSuffixToBase

- ea: `0xeab0`
- end: `0xeae1`
- name: `TimeZoneSyncTask.Utils.Helper::FromSuffixToBase`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xed40`
- `0xf6c0`

## callees

- `0xce30`

## pseudocode

```c

```

## disassembly

```asm
0xeab0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<char, valuetype TimeZoneSyncTask.Data.TimeBase> TimeZoneSyncTask.Utils.Helper::mapSuffixToBase
0xeab5  ldarg.0
0xeab6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<char, valuetype TimeZoneSyncTask.Data.TimeBase>::ContainsKey(var<u1>)
0xeabb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeac0  ldstr    aExpectingValid_2// "expecting valid TimeBase suffix, got {0"...
0xeac5  ldarg.0
0xeac6  box      [mscorlib]System.Char
0xeacb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xead0  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xead5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<char, valuetype TimeZoneSyncTask.Data.TimeBase> TimeZoneSyncTask.Utils.Helper::mapSuffixToBase
0xeada  ldarg.0
0xeadb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<char, valuetype TimeZoneSyncTask.Data.TimeBase>::get_Item(void)
0xeae0  ret
```
