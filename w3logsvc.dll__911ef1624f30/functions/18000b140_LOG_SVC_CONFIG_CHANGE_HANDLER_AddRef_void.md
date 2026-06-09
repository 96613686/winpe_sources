# LOG_SVC_CONFIG_CHANGE_HANDLER::AddRef(void)

- ea: `0x18000b140`
- end: `0x18000b14d`
- name: `?AddRef@LOG_SVC_CONFIG_CHANGE_HANDLER@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(LOG_SVC_CONFIG_CHANGE_HANDLER *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## pseudocode

```c
__int64 __fastcall LOG_SVC_CONFIG_CHANGE_HANDLER::AddRef(LOG_SVC_CONFIG_CHANGE_HANDLER *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x18000b140  mov     eax, 1
0x18000b145  lock xadd [rcx+8], eax
0x18000b14a  inc     eax
0x18000b14c  retn
```
