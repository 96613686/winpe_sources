# TimeZoneSyncTask.Core.RegistryOverwrite::AddRegistry

- ea: `0x112f0`
- end: `0x11541`
- name: `TimeZoneSyncTask.Core.RegistryOverwrite::AddRegistry`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x11030`

## callees

- `0x1050`
- `0xcfb0`
- `0xfdf0`
- `0xfeb0`
- `0x10020`
- `0x10160`
- `0x11190`
- `0x112f0`
- `0x116d0`

## pseudocode

```c

```

## disassembly

```asm
0x112f0  ldarg.1
0x112f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x112f6  ldstr    a0// "{0}"
0x112fb  ldarg.1
0x112fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11301  ldstr    aLastentry// "LastEntry"
0x11306  call     T0x2B00000F
0x1130b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11310  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x11315  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1131a  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1131f  castclass unsigned int8[]
0x11324  stloc.0
0x11325  ldarg.1
0x11326  ldstr    aLastentry// "LastEntry"
0x1132b  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x11330  unbox.any [mscorlib]System.Int32
0x11335  stloc.1
0x11336  ldloc.0
0x11337  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob(unsigned int8[] blob)
0x1133c  stloc.3
0x1133d  ldloca.s 3
0x1133f  ldarg.3
0x11340  call     instance valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Data.RegistryTimeZoneData::ToWindowsProjection(int32 year)
0x11345  stloc.2
0x11346  ldloca.s 2
0x11348  ldarg.s  4
0x1134a  box      TimeZoneSyncTask.Data.WindowsProjection
0x1134f  constrained. TimeZoneSyncTask.Data.WindowsProjection
0x11355  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1135a  ldc.i4.0
0x1135b  ceq
0x1135d  ldarg.s  8
0x1135f  or
0x11360  brfalse  loc_1153F
0x11365  ldarg.s  4
0x11367  ldarg.s  6
0x11369  call     valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Core.RegistryOverwrite::AdjustProjectionForMidnightTransition(valuetype TimeZoneSyncTask.Data.WindowsProjection projection, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions)
0x1136e  starg.s  4
0x11370  ldarg.s  4
0x11372  ldarg.3
0x11373  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromWindowsProjection(valuetype TimeZoneSyncTask.Data.WindowsProjection projection, int32 year)
0x11378  stloc.s  4
0x1137a  ldloca.s 4
0x1137c  call     instance unsigned int8[] TimeZoneSyncTask.Data.RegistryTimeZoneData::ToBlob()
0x11381  stloc.s  5
0x11383  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x11388  brfalse.s loc_113C3
0x1138a  ldstr    aCreatingTziFor// "Creating TZI for {0} in year {1}"
0x1138f  ldc.i4.2
0x11390  newarr   [mscorlib]System.Object
0x11395  dup
0x11396  ldc.i4.0
0x11397  ldarg.2
0x11398  stelem.ref
0x11399  dup
0x1139a  ldc.i4.1
0x1139b  ldarg.3
0x1139c  box      [mscorlib]System.Int32
0x113a1  stelem.ref
0x113a2  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x113a7  ldstr    aFromIana0// "from iana: {0}"
0x113ac  ldc.i4.1
0x113ad  newarr   [mscorlib]System.Object
0x113b2  dup
0x113b3  ldc.i4.0
0x113b4  ldarg.s  4
0x113b6  box      TimeZoneSyncTask.Data.WindowsProjection
0x113bb  stelem.ref
0x113bc  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x113c1  br.s     loc_113FA
0x113c3  ldstr    aCreatingTziFor// "Creating TZI for {0} in year {1}"
0x113c8  ldc.i4.2
0x113c9  newarr   [mscorlib]System.Object
0x113ce  dup
0x113cf  ldc.i4.0
0x113d0  ldarg.2
0x113d1  stelem.ref
0x113d2  dup
0x113d3  ldc.i4.1
0x113d4  ldarg.3
0x113d5  box      [mscorlib]System.Int32
0x113da  stelem.ref
0x113db  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x113e0  ldstr    aFromIana0// "from iana: {0}"
0x113e5  ldc.i4.1
0x113e6  newarr   [mscorlib]System.Object
0x113eb  dup
0x113ec  ldc.i4.0
0x113ed  ldarg.s  4
0x113ef  box      TimeZoneSyncTask.Data.WindowsProjection
0x113f4  stelem.ref
0x113f5  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x113fa  ldarg.1
0x113fb  ldarga.s 3
0x113fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11402  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11407  ldloc.s  5
0x11409  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1140e  ldarg.3
0x1140f  ldloc.1
0x11410  ldc.i4.1
0x11411  add
0x11412  ble      loc_114DB
0x11417  ldloc.1
0x11418  ldc.i4.1
0x11419  add
0x1141a  stloc.s  6
0x1141c  ldloc.0
0x1141d  stloc.s  7
0x1141f  br       loc_114D3
0x11424  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x11429  brfalse.s loc_11473
0x1142b  ldstr    aCreatingTziFor// "Creating TZI for {0} in year {1}"
0x11430  ldc.i4.2
0x11431  newarr   [mscorlib]System.Object
0x11436  dup
0x11437  ldc.i4.0
0x11438  ldarg.2
0x11439  stelem.ref
0x1143a  dup
0x1143b  ldc.i4.1
0x1143c  ldloc.s  6
0x1143e  box      [mscorlib]System.Int32
0x11443  stelem.ref
0x11444  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x11449  ldstr    aUpdatingFromRe// "Updating from reg: {0}"
0x1144e  ldc.i4.1
0x1144f  newarr   [mscorlib]System.Object
0x11454  dup
0x11455  ldc.i4.0
0x11456  ldloc.s  7
0x11458  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob(unsigned int8[] blob)
0x1145d  stloc.3
0x1145e  ldloca.s 3
0x11460  ldloc.1
0x11461  call     instance valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Data.RegistryTimeZoneData::ToWindowsProjection(int32 year)
0x11466  box      TimeZoneSyncTask.Data.WindowsProjection
0x1146b  stelem.ref
0x1146c  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x11471  br.s     loc_114B9
0x11473  ldstr    aCreatingTziFor// "Creating TZI for {0} in year {1}"
0x11478  ldc.i4.2
0x11479  newarr   [mscorlib]System.Object
0x1147e  dup
0x1147f  ldc.i4.0
0x11480  ldarg.2
0x11481  stelem.ref
0x11482  dup
0x11483  ldc.i4.1
0x11484  ldloc.s  6
0x11486  box      [mscorlib]System.Int32
0x1148b  stelem.ref
0x1148c  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x11491  ldstr    aUpdatingFromRe// "Updating from reg: {0}"
0x11496  ldc.i4.1
0x11497  newarr   [mscorlib]System.Object
0x1149c  dup
0x1149d  ldc.i4.0
0x1149e  ldloc.s  7
0x114a0  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob(unsigned int8[] blob)
0x114a5  stloc.3
0x114a6  ldloca.s 3
0x114a8  ldloc.1
0x114a9  call     instance valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Data.RegistryTimeZoneData::ToWindowsProjection(int32 year)
0x114ae  box      TimeZoneSyncTask.Data.WindowsProjection
0x114b3  stelem.ref
0x114b4  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x114b9  ldarg.1
0x114ba  ldloca.s 6
0x114bc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x114c1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x114c6  ldloc.s  7
0x114c8  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x114cd  ldloc.s  6
0x114cf  ldc.i4.1
0x114d0  add
0x114d1  stloc.s  6
0x114d3  ldloc.s  6
0x114d5  ldarg.3
0x114d6  blt      loc_11424
0x114db  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x114e0  brfalse.s loc_114FD
0x114e2  ldstr    aUpdatingLasten// "Updating LastEntry to year {0}"
0x114e7  ldc.i4.1
0x114e8  newarr   [mscorlib]System.Object
0x114ed  dup
0x114ee  ldc.i4.0
0x114ef  ldarg.3
0x114f0  box      [mscorlib]System.Int32
0x114f5  stelem.ref
0x114f6  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x114fb  br.s     loc_11516
0x114fd  ldstr    aUpdatingLasten// "Updating LastEntry to year {0}"
0x11502  ldc.i4.1
0x11503  newarr   [mscorlib]System.Object
0x11508  dup
0x11509  ldc.i4.0
0x1150a  ldarg.3
0x1150b  box      [mscorlib]System.Int32
0x11510  stelem.ref
0x11511  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x11516  ldarg.1
0x11517  ldstr    aLastentry// "LastEntry"
0x1151c  ldarg.3
0x1151d  box      [mscorlib]System.Int32
0x11522  ldc.i4.4
0x11523  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0x11528  ldarga.s 5
0x1152a  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x1152f  ldarg.3
0x11530  bne.un.s loc_1153D
0x11532  ldarg.0
0x11533  ldarg.2
0x11534  ldloc.s  5
0x11536  ldloc.s  4
0x11538  call     void TimeZoneSyncTask.Core.RegistryOverwrite::UpdateRegCache(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot, string winTz, unsigned int8[] blobOut, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData dataRegTZ)
0x1153d  ldc.i4.1
0x1153e  ret
0x1153f  ldc.i4.0
0x11540  ret
```
