# TimeZoneSyncTask.DynamicDstTransform::GetDynamicDstRange

- ea: `0xd2c0`
- end: `0xd6bd`
- name: `TimeZoneSyncTask.DynamicDstTransform::GetDynamicDstRange`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc6e0`

## callees

- `0x1050`
- `0x1200`
- `0xce40`
- `0xcfd0`
- `0xd2c0`
- `0xd6c0`

## string_xrefs

- `0xd2d7`: `Registry`
- `0xd3a2`: `Registry`
- `0xd3c0`: `Registry`
- `0xd411`: `Registry`
- `0xd467`: `Registry`
- `0xd2fa`: `Error querying registry data for TzVersion : {0} `
- `0xd316`: `Error querying registry data for TzVersion : {0} `
- `0xd495`: `Error querying {0} registry data for {1} : {2} `
- `0xd4c0`: `Error querying {0} registry data for {1} : {2} `
- `0xd5fe`: `Deleted OneSettings TZVersion as there is missing data`
- `0xd651`: `error querying registry data for {0}: {1}`
- `0xd672`: `error querying registry data for {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xd2c0  ldc.i4.0
0xd2c1  stloc.0
0xd2c2  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xd2c7  brfalse.s loc_D331
0xd2c9  ldarg.0
0xd2ca  ldstr    aTzversion// "TzVersion"
0xd2cf  callvirt instance valuetype [mscorlib]Microsoft.Win32.RegistryValueKind [mscorlib]Microsoft.Win32.RegistryKey::GetValueKind(string)
0xd2d4  ldc.i4.4
0xd2d5  ceq
0xd2d7  ldstr    aRegistry// "Registry"
0xd2dc  ldstr    aExpectingDword// "expecting DWORD for TzVersion"
0xd2e1  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xd2e6  ldarg.0
0xd2e7  ldstr    aTzversion// "TzVersion"
0xd2ec  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xd2f1  call     unsigned int32 [mscorlib]System.Convert::ToUInt32(object)
0xd2f6  stloc.0
0xd2f7  leave.s  loc_D331
0xd2f9  stloc.2
0xd2fa  ldstr    aErrorQueryingR// "Error querying registry data for TzVers"...
0xd2ff  ldc.i4.1
0xd300  newarr   [mscorlib]System.Object
0xd305  dup
0xd306  ldc.i4.0
0xd307  ldloc.2
0xd308  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd30d  stelem.ref
0xd30e  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xd313  leave.s  loc_D331
0xd315  stloc.3
0xd316  ldstr    aErrorQueryingR// "Error querying registry data for TzVers"...
0xd31b  ldc.i4.1
0xd31c  newarr   [mscorlib]System.Object
0xd321  dup
0xd322  ldc.i4.0
0xd323  ldloc.3
0xd324  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd329  stelem.ref
0xd32a  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xd32f  leave.s  loc_D331
0xd331  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::.ctor()
0xd336  stloc.1
0xd337  ldarg.0
0xd338  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetSubKeyNames()
0xd33d  ldarg.1
0xd33e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0xd343  call     T0x2B000010
0xd348  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xd34d  stloc.s  4
0xd34f  br       loc_D6A1
0xd354  ldloc.s  4
0xd356  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xd35b  stloc.s  5
0xd35d  ldc.i4.0
0xd35e  stloc.s  6
0xd360  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xd365  brfalse.s loc_D375
0xd367  ldloc.0
0xd368  brfalse.s loc_D375
0xd36a  ldarg.0
0xd36b  ldloc.s  5
0xd36d  ldloc.0
0xd36e  call     bool TimeZoneSyncTask.DynamicDstTransform::IsManagedByOneSettings(class [mscorlib]Microsoft.Win32.RegistryKey timeZoneyKey, string winTz, unsigned int32 tzVersion)
0xd373  stloc.s  6
0xd375  ldc.i4.0
0xd376  stloc.s  7
0xd378  ldarg.0
0xd379  ldloc.s  5
0xd37b  ldstr    aDynamicDst_0// "Dynamic DST"
0xd380  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xd385  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xd38a  stloc.s  8
0xd38c  ldloc.s  8
0xd38e  brfalse  loc_D693
0xd393  ldloc.s  8
0xd395  ldstr    aFirstentry// "FirstEntry"
0xd39a  callvirt instance valuetype [mscorlib]Microsoft.Win32.RegistryValueKind [mscorlib]Microsoft.Win32.RegistryKey::GetValueKind(string)
0xd39f  ldc.i4.4
0xd3a0  ceq
0xd3a2  ldstr    aRegistry// "Registry"
0xd3a7  ldstr    aExpectingDword_0// "expecting DWORD for FirstEntry"
0xd3ac  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xd3b1  ldloc.s  8
0xd3b3  ldstr    aLastentry// "LastEntry"
0xd3b8  callvirt instance valuetype [mscorlib]Microsoft.Win32.RegistryValueKind [mscorlib]Microsoft.Win32.RegistryKey::GetValueKind(string)
0xd3bd  ldc.i4.4
0xd3be  ceq
0xd3c0  ldstr    aRegistry// "Registry"
0xd3c5  ldstr    aExpectingDword_1// "expecting DWORD for LastEntry"
0xd3ca  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xd3cf  ldloc.s  8
0xd3d1  ldstr    aFirstentry// "FirstEntry"
0xd3d6  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xd3db  unbox.any [mscorlib]System.Int32
0xd3e0  stloc.s  9
0xd3e2  ldloc.s  8
0xd3e4  ldstr    aLastentry// "LastEntry"
0xd3e9  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xd3ee  unbox.any [mscorlib]System.Int32
0xd3f3  stloc.s  0xA
0xd3f5  ldloc.s  9
0xd3f7  ldloc.s  0xA
0xd3f9  bge.s    loc_D410
0xd3fb  ldloc.s  9
0xd3fd  ldc.i4.0
0xd3fe  ble.s    loc_D410
0xd400  ldloc.s  0xA
0xd402  ldsflda  valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MaxValue
0xd407  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xd40c  clt
0xd40e  br.s     loc_D411
0xd410  ldc.i4.0
0xd411  ldstr    aRegistry// "Registry"
0xd416  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd41b  ldstr    aExpecting01001// "expecting {0} < {1} && {0} > 0 && {1} <"...
0xd420  ldloc.s  9
0xd422  box      [mscorlib]System.Int32
0xd427  ldloc.s  0xA
0xd429  box      [mscorlib]System.Int32
0xd42e  ldsflda  valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MaxValue
0xd433  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xd438  box      [mscorlib]System.Int32
0xd43d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0xd442  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xd447  ldloc.s  9
0xd449  stloc.s  0xB
0xd44b  br       loc_D5C7
0xd450  nop
0xd451  ldloc.s  8
0xd453  ldloca.s 0xB
0xd455  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd45a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xd45f  callvirt instance valuetype [mscorlib]Microsoft.Win32.RegistryValueKind [mscorlib]Microsoft.Win32.RegistryKey::GetValueKind(string)
0xd464  ldc.i4.3
0xd465  ceq
0xd467  ldstr    aRegistry// "Registry"
0xd46c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd471  ldstr    aExpectingBinar// "expecting binary data for year {0}"
0xd476  ldloc.s  0xB
0xd478  box      [mscorlib]System.Int32
0xd47d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xd482  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xd487  leave    loc_D5C1
0xd48c  stloc.s  0xC
0xd48e  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0xd493  brfalse.s loc_D4C0
0xd495  ldstr    aErrorQuerying0// "Error querying {0} registry data for {1"...
0xd49a  ldc.i4.3
0xd49b  newarr   [mscorlib]System.Object
0xd4a0  dup
0xd4a1  ldc.i4.0
0xd4a2  ldloc.s  0xB
0xd4a4  box      [mscorlib]System.Int32
0xd4a9  stelem.ref
0xd4aa  dup
0xd4ab  ldc.i4.1
0xd4ac  ldloc.s  5
0xd4ae  stelem.ref
0xd4af  dup
0xd4b0  ldc.i4.2
0xd4b1  ldloc.s  0xC
0xd4b3  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd4b8  stelem.ref
0xd4b9  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceError(string format, object[] args)
0xd4be  br.s     loc_D4E9
0xd4c0  ldstr    aErrorQuerying0// "Error querying {0} registry data for {1"...
0xd4c5  ldc.i4.3
0xd4c6  newarr   [mscorlib]System.Object
0xd4cb  dup
0xd4cc  ldc.i4.0
0xd4cd  ldloc.s  0xB
0xd4cf  box      [mscorlib]System.Int32
0xd4d4  stelem.ref
0xd4d5  dup
0xd4d6  ldc.i4.1
0xd4d7  ldloc.s  5
0xd4d9  stelem.ref
0xd4da  dup
0xd4db  ldc.i4.2
0xd4dc  ldloc.s  0xC
0xd4de  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd4e3  stelem.ref
0xd4e4  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xd4e9  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xd4ee  brfalse.s loc_D4F3
0xd4f0  ldc.i4.1
0xd4f1  stloc.s  7
0xd4f3  ldnull
0xd4f4  stloc.s  0xD
0xd4f6  ldarg.0
0xd4f7  ldloc.s  5
0xd4f9  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xd4fe  stloc.s  0xE
0xd500  ldloc.s  0xE
0xd502  brfalse.s loc_D521
0xd504  ldloc.s  0xE
0xd506  ldstr    aTzi// "TZI"
0xd50b  call     T0x2B00000F
0xd510  call     string [mscorlib]System.String::Format(string, object[])
0xd515  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xd51a  castclass unsigned int8[]
0xd51f  stloc.s  0xD
0xd521  leave.s  loc_D52F
0xd523  ldloc.s  0xE
0xd525  brfalse.s loc_D52E
0xd527  ldloc.s  0xE
0xd529  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd52e  endfinally
0xd52f  ldloc.s  0xD
0xd531  brtrue.s loc_D539
0xd533  ldc.i4.m1
0xd534  call     void [mscorlib]System.Environment::Exit(int32)
0xd539  ldarg.0
0xd53a  ldloc.s  5
0xd53c  ldstr    aDynamicDst_0// "Dynamic DST"
0xd541  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xd546  ldc.i4.1
0xd547  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xd54c  stloc.s  0xF
0xd54e  ldloc.s  9
0xd550  ldc.i4   0x7E0
0xd555  blt.s    loc_D55B
0xd557  ldloc.s  9
0xd559  br.s     loc_D560
0xd55b  ldc.i4   0x7E0
0xd560  stloc.s  0x10
0xd562  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xd567  stloc.s  0x12
0xd569  ldloca.s 0x12
0xd56b  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xd570  ldc.i4.1
0xd571  add
0xd572  ldloc.s  0xA
0xd574  bgt.s    loc_D588
0xd576  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xd57b  stloc.s  0x12
0xd57d  ldloca.s 0x12
0xd57f  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xd584  ldc.i4.1
0xd585  add
0xd586  br.s     loc_D58A
0xd588  ldloc.s  0xA
0xd58a  stloc.s  0x11
0xd58c  ldloc.s  0xF
0xd58e  brfalse.s loc_D5B1
0xd590  ldloc.s  0xB
0xd592  ldloc.s  0x10
0xd594  blt.s    loc_D5B1
0xd596  ldloc.s  0xB
0xd598  ldloc.s  0x11
0xd59a  bgt.s    loc_D5B1
0xd59c  ldloc.s  0xF
0xd59e  ldloca.s 0xB
0xd5a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5a5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xd5aa  ldloc.s  0xD
0xd5ac  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0xd5b1  leave.s  loc_D5BF
0xd5b3  ldloc.s  0xF
0xd5b5  brfalse.s loc_D5BE
0xd5b7  ldloc.s  0xF
0xd5b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd5be  endfinally
0xd5bf  leave.s  loc_D5C1
0xd5c1  ldloc.s  0xB
0xd5c3  ldc.i4.1
0xd5c4  add
0xd5c5  stloc.s  0xB
0xd5c7  ldloc.s  0xB
0xd5c9  ldloc.s  0xA
0xd5cb  ble      loc_D450
0xd5d0  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xd5d5  brfalse.s loc_D62F
0xd5d7  ldloc.s  7
0xd5d9  brtrue.s loc_D5DF
0xd5db  ldloc.s  6
0xd5dd  brtrue.s loc_D646
0xd5df  ldloc.s  6
0xd5e1  brfalse.s loc_D616
0xd5e3  ldarg.0
0xd5e4  ldloc.s  5
0xd5e6  ldc.i4.1
0xd5e7  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xd5ec  stloc.s  0x13
0xd5ee  ldloc.s  0x13
0xd5f0  brfalse.s loc_D608
0xd5f2  ldloc.s  0x13
0xd5f4  ldstr    aOnesettingstzv// "OneSettingsTzVersion"
0xd5f9  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string)
0xd5fe  ldstr    aDeletedOnesett// "Deleted OneSettings TZVersion as there "...
0xd603  call     void [System]System.Diagnostics.Trace::TraceInformation(string)
0xd608  leave.s  loc_D616
0xd60a  ldloc.s  0x13
0xd60c  brfalse.s loc_D615
0xd60e  ldloc.s  0x13
0xd610  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd615  endfinally
0xd616  ldloc.1
0xd617  ldarg.1
0xd618  ldloc.s  5
  ... truncated ...
```
