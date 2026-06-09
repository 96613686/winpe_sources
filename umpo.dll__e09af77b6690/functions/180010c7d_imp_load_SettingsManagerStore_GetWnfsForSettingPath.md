# __imp_load_SettingsManagerStore_GetWnfsForSettingPath

- ea: `0x180010c7d`
- end: `0x180010c89`
- name: `__imp_load_SettingsManagerStore_GetWnfsForSettingPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180010bec`

## import_xrefs

- `policymanager!SettingsManagerStore_GetWnfsForSettingPath` at `0x180010c7d`

## pseudocode

```c
__int64 load_SettingsManagerStore_GetWnfsForSettingPath()
{
  return _tailMerge_policymanager_dll();
}

```

## disassembly

```asm
0x180010c7d  lea     rax, __imp_SettingsManagerStore_GetWnfsForSettingPath
0x180010c84  jmp     __tailMerge_policymanager_dll
```
