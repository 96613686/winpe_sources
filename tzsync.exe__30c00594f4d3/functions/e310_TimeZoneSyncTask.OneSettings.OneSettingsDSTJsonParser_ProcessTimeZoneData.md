# TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ProcessTimeZoneData

- ea: `0xe310`
- end: `0xe409`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ProcessTimeZoneData`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0xe210`

## callees

- `0xdc10`
- `0xdc30`
- `0xdc50`
- `0xdc70`
- `0xdc90`
- `0xdcf0`
- `0xdd10`
- `0xdd20`
- `0xe310`
- `0xe410`
- `0xe600`
- `0xfdf0`

## pseudocode

```c

```

## disassembly

```asm
0xe310  newobj   instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::.ctor()
0xe315  stloc.0
0xe316  ldloc.0
0xe317  ldarg.2
0xe318  callvirt instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_zoneID(string value)
0xe31d  ldloc.0
0xe31e  ldarg.1
0xe31f  callvirt instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_tzVersion(unsigned int32 value)
0xe324  ldloc.0
0xe325  ldarg.3
0xe326  ldstr    aFirstentry// "FirstEntry"
0xe32b  callvirt instance string [Windows]Windows.Data.Json.JsonObject::GetNamedString(string)
0xe330  callvirt instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_minYear(string value)
0xe335  ldloc.0
0xe336  ldarg.3
0xe337  ldstr    aLastentry// "LastEntry"
0xe33c  callvirt instance string [Windows]Windows.Data.Json.JsonObject::GetNamedString(string)
0xe341  callvirt instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_maxYear(string value)
0xe346  ldarg.0
0xe347  ldarg.3
0xe348  ldstr    aTzi// "TZI"
0xe34d  callvirt instance string [Windows]Windows.Data.Json.JsonObject::GetNamedString(string)
0xe352  call     instance unsigned int8[] TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::StringToByteArray(string hex)
0xe357  stloc.1
0xe358  ldloc.0
0xe359  ldloc.1
0xe35a  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob(unsigned int8[] blob)
0xe35f  callvirt instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_tzi(valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData value)
0xe364  ldarg.3
0xe365  ldstr    aDynamicdst// "DynamicDST"
0xe36a  callvirt instance class [Windows]Windows.Data.Json.JsonObject [Windows]Windows.Data.Json.JsonObject::GetNamedObject(string)
0xe36f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>>::GetEnumerator()
0xe374  stloc.2
0xe375  br.s     loc_E3CB
0xe377  ldloc.2
0xe378  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>>::get_Current()
0xe37d  stloc.3
0xe37e  ldloca.s 3
0xe380  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>::get_Key()
0xe385  stloc.s  4
0xe387  ldloca.s 3
0xe389  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>::get_Value()
0xe38e  stloc.s  5
0xe390  ldarg.0
0xe391  ldloc.s  5
0xe393  callvirt instance string [Windows]Windows.Data.Json.IJsonValue::GetString()
0xe398  call     instance unsigned int8[] TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::StringToByteArray(string hex)
0xe39d  stloc.s  6
0xe39f  ldloc.0
0xe3a0  ldloc.s  4
0xe3a2  ldloc.s  6
0xe3a4  call     valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob(unsigned int8[] blob)
0xe3a9  callvirt instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::AddDSTRule(string year, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData data)
0xe3ae  ldstr    aYear// "Year "
0xe3b3  ldloc.s  4
0xe3b5  ldstr    aData_0// " data "
0xe3ba  ldloc.s  5
0xe3bc  callvirt instance string [Windows]Windows.Data.Json.IJsonValue::GetString()
0xe3c1  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xe3c6  call     void [System]System.Diagnostics.Trace::TraceInformation(string)
0xe3cb  ldloc.2
0xe3cc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe3d1  brtrue.s loc_E377
0xe3d3  leave.s  loc_E3DF
0xe3d5  ldloc.2
0xe3d6  brfalse.s loc_E3DE
0xe3d8  ldloc.2
0xe3d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe3de  endfinally
0xe3df  ldloc.0
0xe3e0  callvirt instance bool TimeZoneSyncTask.OneSettings.DynamicDSTRules::IsValid()
0xe3e5  brfalse.s loc_E3F4
0xe3e7  ldarg.0
0xe3e8  ldfld    class TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::timeZoneDSTSettings
0xe3ed  ldloc.0
0xe3ee  callvirt instance void TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::AddDynamicDSTRules(class TimeZoneSyncTask.OneSettings.DynamicDSTRules rule)
0xe3f3  ret
0xe3f4  ldstr    aInvalidDstRule// "Invalid DST Rule for {0}"
0xe3f9  ldc.i4.1
0xe3fa  newarr   [mscorlib]System.Object
0xe3ff  dup
0xe400  ldc.i4.0
0xe401  ldarg.2
0xe402  stelem.ref
0xe403  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xe408  ret
```
