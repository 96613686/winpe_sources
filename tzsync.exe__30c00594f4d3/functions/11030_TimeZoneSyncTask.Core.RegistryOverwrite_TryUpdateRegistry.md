# TimeZoneSyncTask.Core.RegistryOverwrite::TryUpdateRegistry

- ea: `0x11030`
- end: `0x11183`
- name: `TimeZoneSyncTask.Core.RegistryOverwrite::TryUpdateRegistry`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0xc6e0`

## callees

- `0x1050`
- `0xcfb0`
- `0xfdf0`
- `0xfeb0`
- `0x10020`
- `0x10160`
- `0x11030`
- `0x11190`
- `0x112f0`
- `0x116d0`

## pseudocode

```c

```

## disassembly

```asm
0x11030  ldarg.1
0x11031  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11036  ldstr    a0// "{0}"
0x1103b  ldarg.3
0x1103c  box      [mscorlib]System.Int32
0x11041  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x11046  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1104b  castclass unsigned int8[]
0x11050  stloc.0
0x11051  ldloc.0
0x11052  brtrue.s loc_11068
0x11054  ldarg.0
0x11055  ldarg.1
0x11056  ldarg.2
0x11057  ldarg.3
0x11058  ldarg.s  4
0x1105a  ldarg.s  5
0x1105c  ldarg.s  6
0x1105e  ldarg.s  7
0x11060  ldarg.s  8
0x11062  call     bool TimeZoneSyncTask.Core.RegistryOverwrite::AddRegistry(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot, class [mscorlib]Microsoft.Win32.RegistryKey rkDynamicDST, string winTz, int32 year, valuetype TimeZoneSyncTask.Data.WindowsProjection projection, valuetype [mscorlib]System.DateTime dtSync, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection> mapYearToProjection, bool isMultipleTransition)
0x11067  ret
0x11068  ldloc.0
0x11069  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob(unsigned int8[] blob)
0x1106e  stloc.2
0x1106f  ldloca.s 2
0x11071  ldarg.3
0x11072  call     instance valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Data.RegistryTimeZoneData::ToWindowsProjection(int32 year)
0x11077  stloc.1
0x11078  ldloca.s 1
0x1107a  ldarg.s  4
0x1107c  box      TimeZoneSyncTask.Data.WindowsProjection
0x11081  constrained. TimeZoneSyncTask.Data.WindowsProjection
0x11087  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1108c  brtrue   loc_11181
0x11091  ldarg.s  4
0x11093  ldarg.s  6
0x11095  call     valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Core.RegistryOverwrite::AdjustProjectionForMidnightTransition(valuetype TimeZoneSyncTask.Data.WindowsProjection projection, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions)
0x1109a  starg.s  4
0x1109c  ldarg.s  4
0x1109e  ldarg.3
0x1109f  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromWindowsProjection(valuetype TimeZoneSyncTask.Data.WindowsProjection projection, int32 year)
0x110a4  stloc.3
0x110a5  ldloca.s 3
0x110a7  call     instance unsigned int8[] TimeZoneSyncTask.Data.RegistryTimeZoneData::ToBlob()
0x110ac  stloc.s  4
0x110ae  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x110b3  brfalse.s loc_11107
0x110b5  ldstr    aChangingTziFor// "changing TZI for {0} in year {1}"
0x110ba  ldc.i4.2
0x110bb  newarr   [mscorlib]System.Object
0x110c0  dup
0x110c1  ldc.i4.0
0x110c2  ldarg.2
0x110c3  stelem.ref
0x110c4  dup
0x110c5  ldc.i4.1
0x110c6  ldarg.3
0x110c7  box      [mscorlib]System.Int32
0x110cc  stelem.ref
0x110cd  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x110d2  ldstr    aFromIana0// "from iana: {0}"
0x110d7  ldc.i4.1
0x110d8  newarr   [mscorlib]System.Object
0x110dd  dup
0x110de  ldc.i4.0
0x110df  ldarg.s  4
0x110e1  box      TimeZoneSyncTask.Data.WindowsProjection
0x110e6  stelem.ref
0x110e7  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x110ec  ldstr    aFromReg0// "from reg: {0}"
0x110f1  ldc.i4.1
0x110f2  newarr   [mscorlib]System.Object
0x110f7  dup
0x110f8  ldc.i4.0
0x110f9  ldloc.1
0x110fa  box      TimeZoneSyncTask.Data.WindowsProjection
0x110ff  stelem.ref
0x11100  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x11105  br.s     loc_11157
0x11107  ldstr    aChangingTziFor// "changing TZI for {0} in year {1}"
0x1110c  ldc.i4.2
0x1110d  newarr   [mscorlib]System.Object
0x11112  dup
0x11113  ldc.i4.0
0x11114  ldarg.2
0x11115  stelem.ref
0x11116  dup
0x11117  ldc.i4.1
0x11118  ldarg.3
0x11119  box      [mscorlib]System.Int32
0x1111e  stelem.ref
0x1111f  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x11124  ldstr    aFromIana0// "from iana: {0}"
0x11129  ldc.i4.1
0x1112a  newarr   [mscorlib]System.Object
0x1112f  dup
0x11130  ldc.i4.0
0x11131  ldarg.s  4
0x11133  box      TimeZoneSyncTask.Data.WindowsProjection
0x11138  stelem.ref
0x11139  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x1113e  ldstr    aFromReg0// "from reg: {0}"
0x11143  ldc.i4.1
0x11144  newarr   [mscorlib]System.Object
0x11149  dup
0x1114a  ldc.i4.0
0x1114b  ldloc.1
0x1114c  box      TimeZoneSyncTask.Data.WindowsProjection
0x11151  stelem.ref
0x11152  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x11157  ldarg.1
0x11158  ldarga.s 3
0x1115a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1115f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11164  ldloc.s  4
0x11166  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1116b  ldarga.s 5
0x1116d  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x11172  ldarg.3
0x11173  bne.un.s loc_1117F
0x11175  ldarg.0
0x11176  ldarg.2
0x11177  ldloc.s  4
0x11179  ldloc.3
0x1117a  call     void TimeZoneSyncTask.Core.RegistryOverwrite::UpdateRegCache(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot, string winTz, unsigned int8[] blobOut, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData dataRegTZ)
0x1117f  ldc.i4.1
0x11180  ret
0x11181  ldc.i4.0
0x11182  ret
```
