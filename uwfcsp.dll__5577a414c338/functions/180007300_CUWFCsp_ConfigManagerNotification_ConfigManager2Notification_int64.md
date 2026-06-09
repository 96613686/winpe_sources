# CUWFCsp::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x180007300`
- end: `0x180007305`
- name: `?ConfigManagerNotification@CUWFCsp@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `5`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x1800194e0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CUWFCsp::ConfigManagerNotification(__int64 a1, int a2, __int64 a3)
{
  return CConfigServiceProvider2Impl::ConfigManagerNotification(a1, a2, a3);
}

```

## disassembly

```asm
0x180007300  jmp     ?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z; CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)
```
