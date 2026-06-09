# TimeZoneSyncTask.Utils.Helper::FromBaseToString

- ea: `0xeaf0`
- end: `0xeb21`
- name: `TimeZoneSyncTask.Utils.Helper::FromBaseToString`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xed10`
- `0xf690`

## callees

- `0xce30`

## pseudocode

```c

```

## disassembly

```asm
0xeaf0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype TimeZoneSyncTask.Data.TimeBase, string> TimeZoneSyncTask.Utils.Helper::mapBaseToString
0xeaf5  ldarg.0
0xeaf6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype TimeZoneSyncTask.Data.TimeBase, string>::ContainsKey(var<u1>)
0xeafb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeb00  ldstr    aExpectingValid_3// "expecting valid TimeBase, got {0}"
0xeb05  ldarg.0
0xeb06  box      TimeZoneSyncTask.Data.TimeBase
0xeb0b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xeb10  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xeb15  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype TimeZoneSyncTask.Data.TimeBase, string> TimeZoneSyncTask.Utils.Helper::mapBaseToString
0xeb1a  ldarg.0
0xeb1b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype TimeZoneSyncTask.Data.TimeBase, string>::get_Item(void)
0xeb20  ret
```
