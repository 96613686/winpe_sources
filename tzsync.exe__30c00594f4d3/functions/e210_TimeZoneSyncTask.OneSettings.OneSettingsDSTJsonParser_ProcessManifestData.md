# TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ProcessManifestData

- ea: `0xe210`
- end: `0xe302`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ProcessManifestData`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0xe1b0`

## callees

- `0xe210`
- `0xe310`

## pseudocode

```c

```

## disassembly

```asm
0xe210  ldarg.1
0xe211  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>>::GetEnumerator()
0xe216  stloc.0
0xe217  br       loc_E2EA
0xe21c  ldloc.0
0xe21d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>>::get_Current()
0xe222  stloc.1
0xe223  ldloca.s 1
0xe225  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>::get_Key()
0xe22a  stloc.2
0xe22b  ldloca.s 1
0xe22d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>::get_Value()
0xe232  stloc.3
0xe233  ldstr    aVersion0// "Version : {0} "
0xe238  ldc.i4.1
0xe239  newarr   [mscorlib]System.Object
0xe23e  dup
0xe23f  ldc.i4.0
0xe240  ldloc.2
0xe241  stelem.ref
0xe242  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xe247  ldloc.2
0xe248  ldc.i4.s 0x10
0xe24a  call     unsigned int32 [mscorlib]System.Convert::ToUInt32(string, int32)
0xe24f  stloc.s  4
0xe251  ldstr    aSystemVal0Vers// "System Val : {0}  Version Val : {1}  "
0xe256  ldc.i4.2
0xe257  newarr   [mscorlib]System.Object
0xe25c  dup
0xe25d  ldc.i4.0
0xe25e  ldarg.0
0xe25f  ldfld    unsigned int32 TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::systemTzversion
0xe264  box      [mscorlib]System.UInt32
0xe269  stelem.ref
0xe26a  dup
0xe26b  ldc.i4.1
0xe26c  ldloc.s  4
0xe26e  box      [mscorlib]System.UInt32
0xe273  stelem.ref
0xe274  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xe279  ldloc.s  4
0xe27b  ldarg.0
0xe27c  ldfld    unsigned int32 TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::systemTzversion
0xe281  blt.un.s loc_E2EA
0xe283  ldloc.3
0xe284  callvirt instance class [Windows]Windows.Data.Json.JsonObject [Windows]Windows.Data.Json.IJsonValue::GetObject()
0xe289  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>>::GetEnumerator()
0xe28e  stloc.s  5
0xe290  br.s     loc_E2D3
0xe292  ldloc.s  5
0xe294  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>>::get_Current()
0xe299  stloc.s  6
0xe29b  ldloca.s 6
0xe29d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>::get_Key()
0xe2a2  stloc.s  7
0xe2a4  ldloca.s 6
0xe2a6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Windows]Windows.Data.Json.IJsonValue>::get_Value()
0xe2ab  stloc.s  8
0xe2ad  ldstr    aTimezone0// "TimeZone : {0}"
0xe2b2  ldc.i4.1
0xe2b3  newarr   [mscorlib]System.Object
0xe2b8  dup
0xe2b9  ldc.i4.0
0xe2ba  ldloc.s  7
0xe2bc  stelem.ref
0xe2bd  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xe2c2  ldarg.0
0xe2c3  ldloc.s  4
0xe2c5  ldloc.s  7
0xe2c7  ldloc.s  8
0xe2c9  callvirt instance class [Windows]Windows.Data.Json.JsonObject [Windows]Windows.Data.Json.IJsonValue::GetObject()
0xe2ce  call     instance void TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ProcessTimeZoneData(unsigned int32 tzVersion, string zoneID, class [Windows]Windows.Data.Json.JsonObject dstData)
0xe2d3  ldloc.s  5
0xe2d5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe2da  brtrue.s loc_E292
0xe2dc  leave.s  loc_E2EA
0xe2de  ldloc.s  5
0xe2e0  brfalse.s loc_E2E9
0xe2e2  ldloc.s  5
0xe2e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe2e9  endfinally
0xe2ea  ldloc.0
0xe2eb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe2f0  brtrue   loc_E21C
0xe2f5  leave.s  loc_E301
0xe2f7  ldloc.0
0xe2f8  brfalse.s loc_E300
0xe2fa  ldloc.0
0xe2fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe300  endfinally
0xe301  ret
```
