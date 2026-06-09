# TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ParseOneSettingsData

- ea: `0xe1b0`
- end: `0xe20c`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ParseOneSettingsData`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0xe1b0`
- `0xe210`
- `0xe640`

## pseudocode

```c

```

## disassembly

```asm
0xe1b0  ldarg.0
0xe1b1  ldfld    class [Windows]Windows.Data.Json.JsonObject TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::oneSettingsData
0xe1b6  ldstr    aSettings// "settings"
0xe1bb  ldnull
0xe1bc  callvirt instance class [Windows]Windows.Data.Json.JsonObject [Windows]Windows.Data.Json.JsonObject::GetNamedObject(string, class [Windows]Windows.Data.Json.JsonObject)
0xe1c1  stloc.0
0xe1c2  ldloc.0
0xe1c3  brtrue.s loc_E1D1
0xe1c5  ldstr    aDstSettingsNot// "DST settings not found in OneSettings"
0xe1ca  call     void [System]System.Diagnostics.Trace::TraceInformation(string)
0xe1cf  leave.s  loc_E20B
0xe1d1  ldloc.0
0xe1d2  ldstr    aDstData// "DST_DATA"
0xe1d7  ldnull
0xe1d8  callvirt instance class [Windows]Windows.Data.Json.JsonObject [Windows]Windows.Data.Json.JsonObject::GetNamedObject(string, class [Windows]Windows.Data.Json.JsonObject)
0xe1dd  stloc.1
0xe1de  ldloc.1
0xe1df  brtrue.s loc_E1ED
0xe1e1  ldstr    aDstSettingsNot// "DST settings not found in OneSettings"
0xe1e6  call     void [System]System.Diagnostics.Trace::TraceInformation(string)
0xe1eb  leave.s  loc_E20B
0xe1ed  ldarg.0
0xe1ee  ldloc.1
0xe1ef  call     instance void TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::ProcessManifestData(class [Windows]Windows.Data.Json.JsonObject manifestData)
0xe1f4  ldarg.0
0xe1f5  ldfld    class TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::timeZoneDSTSettings
0xe1fa  callvirt instance void TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::RemoveOlderVersions()
0xe1ff  leave.s  loc_E20B
0xe201  pop
0xe202  ldarg.0
0xe203  ldnull
0xe204  stfld    class TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::timeZoneDSTSettings
0xe209  rethrow
0xe20b  ret
```
