# TimeZoneSyncTask.OneSettings.DynamicDSTRules::CompareTo

- ea: `0xe0b0`
- end: `0xe0ea`
- name: `TimeZoneSyncTask.OneSettings.DynamicDSTRules::CompareTo`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xdb90`
- `0xdbb0`
- `0xdc00`
- `0xdc60`
- `0xe0b0`

## pseudocode

```c

```

## disassembly

```asm
0xe0b0  ldarg.0
0xe0b1  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xe0b6  ldarg.1
0xe0b7  callvirt instance string TimeZoneSyncTask.OneSettings.IDynamicDSTRules::get_zoneID()
0xe0bc  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xe0c1  brfalse.s loc_E0D5
0xe0c3  ldarg.0
0xe0c4  call     instance string TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_zoneID()
0xe0c9  ldarg.1
0xe0ca  callvirt instance string TimeZoneSyncTask.OneSettings.IDynamicDSTRules::get_zoneID()
0xe0cf  callvirt instance int32 [mscorlib]System.String::CompareTo(string)
0xe0d4  ret
0xe0d5  ldarg.0
0xe0d6  call     instance unsigned int32 TimeZoneSyncTask.OneSettings.DynamicDSTRules::get_tzVersion()
0xe0db  stloc.0
0xe0dc  ldloca.s 0
0xe0de  ldarg.1
0xe0df  callvirt instance unsigned int32 TimeZoneSyncTask.OneSettings.IDynamicDSTRules::get_tzVersion()
0xe0e4  call     instance int32 [mscorlib]System.UInt32::CompareTo(unsigned int32)
0xe0e9  ret
```
