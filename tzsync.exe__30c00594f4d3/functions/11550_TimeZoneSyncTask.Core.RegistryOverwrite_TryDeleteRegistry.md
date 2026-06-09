# TimeZoneSyncTask.Core.RegistryOverwrite::TryDeleteRegistry

- ea: `0x11550`
- end: `0x1165b`
- name: `TimeZoneSyncTask.Core.RegistryOverwrite::TryDeleteRegistry`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0xc6e0`

## callees

- `0x1050`
- `0xcfb0`
- `0xcfd0`
- `0xfeb0`
- `0x10160`
- `0x11190`
- `0x11550`
- `0x116d0`

## string_xrefs

- `0x1158a`: `Error deleting registry data for {0}: {1}`
- `0x115ae`: `Error deleting registry data for {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x11550  ldarg.1
0x11551  ldstr    aLastentry// "LastEntry"
0x11556  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1155b  unbox.any [mscorlib]System.Int32
0x11560  stloc.0
0x11561  ldarg.2
0x11562  ldloc.0
0x11563  ble.s    loc_11567
0x11565  ldc.i4.0
0x11566  ret
0x11567  ldarg.2
0x11568  ldc.i4.1
0x11569  add
0x1156a  stloc.1
0x1156b  br.s     loc_115D6
0x1156d  nop
0x1156e  ldarg.1
0x1156f  ldloca.s 1
0x11571  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11576  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1157b  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string)
0x11580  leave.s  loc_115D2
0x11582  stloc.2
0x11583  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x11588  brfalse.s loc_115AE
0x1158a  ldstr    aErrorDeletingR// "Error deleting registry data for {0}: {"...
0x1158f  ldc.i4.2
0x11590  newarr   [mscorlib]System.Object
0x11595  dup
0x11596  ldc.i4.0
0x11597  ldloc.1
0x11598  box      [mscorlib]System.Int32
0x1159d  stelem.ref
0x1159e  dup
0x1159f  ldc.i4.1
0x115a0  ldloc.2
0x115a1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x115a6  stelem.ref
0x115a7  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceError(string format, object[] args)
0x115ac  br.s     loc_115D0
0x115ae  ldstr    aErrorDeletingR// "Error deleting registry data for {0}: {"...
0x115b3  ldc.i4.2
0x115b4  newarr   [mscorlib]System.Object
0x115b9  dup
0x115ba  ldc.i4.0
0x115bb  ldloc.1
0x115bc  box      [mscorlib]System.Int32
0x115c1  stelem.ref
0x115c2  dup
0x115c3  ldc.i4.1
0x115c4  ldloc.2
0x115c5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x115ca  stelem.ref
0x115cb  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0x115d0  leave.s  loc_115D2
0x115d2  ldloc.1
0x115d3  ldc.i4.1
0x115d4  add
0x115d5  stloc.1
0x115d6  ldloc.1
0x115d7  ldloc.0
0x115d8  ble.s    loc_1156D
0x115da  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x115df  brfalse.s loc_115FC
0x115e1  ldstr    aUpdatingLasten// "Updating LastEntry to year {0}"
0x115e6  ldc.i4.1
0x115e7  newarr   [mscorlib]System.Object
0x115ec  dup
0x115ed  ldc.i4.0
0x115ee  ldarg.2
0x115ef  box      [mscorlib]System.Int32
0x115f4  stelem.ref
0x115f5  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x115fa  br.s     loc_11615
0x115fc  ldstr    aUpdatingLasten// "Updating LastEntry to year {0}"
0x11601  ldc.i4.1
0x11602  newarr   [mscorlib]System.Object
0x11607  dup
0x11608  ldc.i4.0
0x11609  ldarg.2
0x1160a  box      [mscorlib]System.Int32
0x1160f  stelem.ref
0x11610  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x11615  ldarg.1
0x11616  ldstr    aLastentry// "LastEntry"
0x1161b  ldarg.2
0x1161c  box      [mscorlib]System.Int32
0x11621  ldc.i4.4
0x11622  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0x11627  ldarga.s 3
0x11629  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x1162e  ldarg.2
0x1162f  bne.un.s loc_11659
0x11631  ldarg.s  5
0x11633  ldarg.s  6
0x11635  call     valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Core.RegistryOverwrite::AdjustProjectionForMidnightTransition(valuetype TimeZoneSyncTask.Data.WindowsProjection projection, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions)
0x1163a  starg.s  5
0x1163c  ldarg.s  5
0x1163e  ldarg.2
0x1163f  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromWindowsProjection(valuetype TimeZoneSyncTask.Data.WindowsProjection projection, int32 year)
0x11644  stloc.3
0x11645  ldloca.s 3
0x11647  call     instance unsigned int8[] TimeZoneSyncTask.Data.RegistryTimeZoneData::ToBlob()
0x1164c  stloc.s  4
0x1164e  ldarg.0
0x1164f  ldarg.s  4
0x11651  ldloc.s  4
0x11653  ldloc.3
0x11654  call     void TimeZoneSyncTask.Core.RegistryOverwrite::UpdateRegCache(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot, string winTz, unsigned int8[] blobOut, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData dataRegTZ)
0x11659  ldc.i4.1
0x1165a  ret
```
