# TimeZoneSyncTask.OneSettings.DynamicDSTRules::CompareZoneID

- ea: `0xe0f0`
- end: `0xe102`
- name: `TimeZoneSyncTask.OneSettings.DynamicDSTRules::CompareZoneID`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe640`

## callees

- `0xdb90`
- `0xdc00`

## pseudocode

```c

```

## disassembly

```asm
0xe0f0  ldarg.0
0xe0f1  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xe0f6  ldarg.1
0xe0f7  callvirt instance string TimeZoneSyncTask.OneSettings.IDynamicDSTRules::get_zoneID()
0xe0fc  callvirt instance int32 [mscorlib]System.String::CompareTo(string)
0xe101  ret
```
