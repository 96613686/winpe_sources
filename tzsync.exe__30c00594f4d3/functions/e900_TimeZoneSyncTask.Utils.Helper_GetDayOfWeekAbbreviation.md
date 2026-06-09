# TimeZoneSyncTask.Utils.Helper::GetDayOfWeekAbbreviation

- ea: `0xe900`
- end: `0xe93a`
- name: `TimeZoneSyncTask.Utils.Helper::GetDayOfWeekAbbreviation`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xee80`
- `0xfc30`

## callees

- `0xce30`
- `0xe900`

## pseudocode

```c

```

## disassembly

```asm
0xe900  ldarg.0
0xe901  ldc.i4.0
0xe902  blt.s    loc_E913
0xe904  ldarg.0
0xe905  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> TimeZoneSyncTask.Utils.Helper::rgDayOfWeekAbbreviations
0xe90a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0xe90f  clt
0xe911  br.s     loc_E914
0xe913  ldc.i4.0
0xe914  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe919  ldstr    aExpectingValid_0// "expecting valid DayOfWeek index, got {0"...
0xe91e  ldarg.0
0xe91f  box      [mscorlib]System.Int32
0xe924  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xe929  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xe92e  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> TimeZoneSyncTask.Utils.Helper::rgDayOfWeekAbbreviations
0xe933  ldarg.0
0xe934  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0xe939  ret
```
