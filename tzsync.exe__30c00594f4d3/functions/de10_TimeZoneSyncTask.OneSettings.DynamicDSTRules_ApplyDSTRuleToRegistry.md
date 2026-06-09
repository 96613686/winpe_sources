# TimeZoneSyncTask.OneSettings.DynamicDSTRules::ApplyDSTRuleToRegistry

- ea: `0xde10`
- end: `0xe04c`
- name: `TimeZoneSyncTask.OneSettings.DynamicDSTRules::ApplyDSTRuleToRegistry`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe6e0`

## callees

- `0xdc00`
- `0xdc20`
- `0xdc40`
- `0xdc60`
- `0xdc80`
- `0xdd20`
- `0xde10`
- `0xe050`
- `0xfdf0`
- `0x10160`

## string_xrefs

- `0xde33`: `Applying DST Rule to Registry for {0}`
- `0xde72`: `Deleted TZVersion for {0}`

## pseudocode

```c

```

## disassembly

```asm
0xde10  ldarg.0
0xde11  call     instance bool TimeZoneSyncTask.OneSettings.DynamicDSTRules::IsValid()
0xde16  brtrue.s loc_DE33
0xde18  ldstr    aInvalidDstRule// "Invalid DST Rule for {0}"
0xde1d  ldc.i4.1
0xde1e  newarr   [mscorlib]System.Object
0xde23  dup
0xde24  ldc.i4.0
0xde25  ldarg.0
0xde26  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xde2b  stelem.ref
0xde2c  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xde31  ldc.i4.0
0xde32  ret
0xde33  ldstr    aApplyingDstRul// "Applying DST Rule to Registry for {0}"
0xde38  ldc.i4.1
0xde39  newarr   [mscorlib]System.Object
0xde3e  dup
0xde3f  ldc.i4.0
0xde40  ldarg.0
0xde41  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xde46  stelem.ref
0xde47  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xde4c  ldarg.1
0xde4d  ldarg.0
0xde4e  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xde53  ldc.i4.1
0xde54  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xde59  stloc.0
0xde5a  ldloc.0
0xde5b  ldstr    aOnesettingstzv// "OneSettingsTzVersion"
0xde60  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xde65  brfalse.s loc_DE8B
0xde67  ldloc.0
0xde68  ldstr    aOnesettingstzv// "OneSettingsTzVersion"
0xde6d  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string)
0xde72  ldstr    aDeletedTzversi// "Deleted TZVersion for {0}"
0xde77  ldc.i4.1
0xde78  newarr   [mscorlib]System.Object
0xde7d  dup
0xde7e  ldc.i4.0
0xde7f  ldarg.0
0xde80  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xde85  stelem.ref
0xde86  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xde8b  ldloc.0
0xde8c  ldstr    aDynamicDst_0// "Dynamic DST"
0xde91  ldc.i4.1
0xde92  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xde97  stloc.1
0xde98  ldloc.1
0xde99  brtrue.s loc_DEBC
0xde9b  ldstr    aErrorDynamicDs// "Error Dynamic DST key for {0}"
0xdea0  ldc.i4.1
0xdea1  newarr   [mscorlib]System.Object
0xdea6  dup
0xdea7  ldc.i4.0
0xdea8  ldarg.0
0xdea9  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xdeae  stelem.ref
0xdeaf  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xdeb4  ldc.i4.0
0xdeb5  stloc.s  6
0xdeb7  leave    loc_E049
0xdebc  ldarg.0
0xdebd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData> TimeZoneSyncTask.OneSettings.DynamicDSTRules::DSTRules
0xdec2  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::GetEnumerator()
0xdec7  stloc.s  7
0xdec9  br.s     loc_DF4A
0xdecb  ldloca.s 7
0xdecd  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Current()
0xded2  stloc.s  8
0xded4  ldloc.1
0xded5  ldloca.s 8
0xded7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Key()
0xdedc  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xdee1  castclass unsigned int8[]
0xdee6  stloc.s  9
0xdee8  ldloc.s  9
0xdeea  brfalse.s loc_DF2C
0xdeec  ldloc.s  9
0xdeee  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob(unsigned int8[] blob)
0xdef3  stloc.s  0xA
0xdef5  ldloca.s 0xA
0xdef7  ldloca.s 8
0xdef9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Value()
0xdefe  box      TimeZoneSyncTask.Data.RegistryTimeZoneData
0xdf03  constrained. TimeZoneSyncTask.Data.RegistryTimeZoneData
0xdf09  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xdf0e  brfalse.s loc_DF2C
0xdf10  ldstr    aDataExists0// " Data Exists: {0}"
0xdf15  ldc.i4.1
0xdf16  newarr   [mscorlib]System.Object
0xdf1b  dup
0xdf1c  ldc.i4.0
0xdf1d  ldloca.s 8
0xdf1f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Key()
0xdf24  stelem.ref
0xdf25  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xdf2a  br.s     loc_DF4A
0xdf2c  ldloc.1
0xdf2d  ldloca.s 8
0xdf2f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Key()
0xdf34  ldloca.s 8
0xdf36  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::get_Value()
0xdf3b  stloc.s  0xB
0xdf3d  ldloca.s 0xB
0xdf3f  call     instance unsigned int8[] TimeZoneSyncTask.Data.RegistryTimeZoneData::ToBlob()
0xdf44  ldc.i4.3
0xdf45  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0xdf4a  ldloca.s 7
0xdf4c  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::MoveNext()
0xdf51  brtrue   loc_DECB
0xdf56  leave.s  loc_DF66
0xdf58  ldloca.s 7
0xdf5a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>
0xdf60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdf65  endfinally
0xdf66  ldloc.1
0xdf67  ldstr    aFirstentry// "FirstEntry"
0xdf6c  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xdf71  callvirt instance string [mscorlib]System.Object::ToString()
0xdf76  call     int32 [mscorlib]System.Int32::Parse(string)
0xdf7b  stloc.2
0xdf7c  ldarg.0
0xdf7d  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_minYear()
0xdf82  call     int32 [mscorlib]System.Int32::Parse(string)
0xdf87  stloc.3
0xdf88  ldloc.2
0xdf89  ldloc.3
0xdf8a  beq.s    loc_DFAD
0xdf8c  ldloc.1
0xdf8d  ldstr    aFirstentry// "FirstEntry"
0xdf92  ldloc.3
0xdf93  box      [mscorlib]System.Int32
0xdf98  ldc.i4.4
0xdf99  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0xdf9e  ldloc.2
0xdf9f  ldloc.3
0xdfa0  bge.s    loc_DFAD
0xdfa2  ldarg.0
0xdfa3  ldloc.1
0xdfa4  ldloc.2
0xdfa5  ldloc.3
0xdfa6  ldc.i4.1
0xdfa7  sub
0xdfa8  call     instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::RemoveDSTRulesInRange(class [mscorlib]Microsoft.Win32.RegistryKey rkDynamicDST, int32 startYear, int32 endYear)
0xdfad  ldloc.1
0xdfae  ldstr    aLastentry// "LastEntry"
0xdfb3  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xdfb8  callvirt instance string [mscorlib]System.Object::ToString()
0xdfbd  call     int32 [mscorlib]System.Int32::Parse(string)
0xdfc2  stloc.s  4
0xdfc4  ldarg.0
0xdfc5  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_maxYear()
0xdfca  call     int32 [mscorlib]System.Int32::Parse(string)
0xdfcf  stloc.s  5
0xdfd1  ldloc.s  4
0xdfd3  ldloc.s  5
0xdfd5  beq.s    loc_DFFD
0xdfd7  ldloc.1
0xdfd8  ldstr    aLastentry// "LastEntry"
0xdfdd  ldloc.s  5
0xdfdf  box      [mscorlib]System.Int32
0xdfe4  ldc.i4.4
0xdfe5  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0xdfea  ldloc.s  4
0xdfec  ldloc.s  5
0xdfee  ble.s    loc_DFFD
0xdff0  ldarg.0
0xdff1  ldloc.1
0xdff2  ldloc.s  5
0xdff4  ldc.i4.1
0xdff5  add
0xdff6  ldloc.s  4
0xdff8  call     instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::RemoveDSTRulesInRange(class [mscorlib]Microsoft.Win32.RegistryKey rkDynamicDST, int32 startYear, int32 endYear)
0xdffd  leave.s  loc_E009
0xdfff  ldloc.1
0xe000  brfalse.s loc_E008
0xe002  ldloc.1
0xe003  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe008  endfinally
0xe009  ldloc.0
0xe00a  ldstr    aTzi// "TZI"
0xe00f  ldarg.0
0xe010  call     instance valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_tzi()
0xe015  stloc.s  0xB
0xe017  ldloca.s 0xB
0xe019  call     instance unsigned int8[] TimeZoneSyncTask.Data.RegistryTimeZoneData::ToBlob()
0xe01e  ldc.i4.3
0xe01f  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0xe024  ldloc.0
0xe025  ldstr    aOnesettingstzv// "OneSettingsTzVersion"
0xe02a  ldarg.0
0xe02b  call     instance unsigned int32 TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_tzVersion()
0xe030  box      [mscorlib]System.UInt32
0xe035  ldc.i4.4
0xe036  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0xe03b  leave.s  loc_E047
0xe03d  ldloc.0
0xe03e  brfalse.s loc_E046
0xe040  ldloc.0
0xe041  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe046  endfinally
0xe047  ldc.i4.1
0xe048  ret
0xe049  ldloc.s  6
0xe04b  ret
```
