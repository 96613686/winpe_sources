# _dynamic_atexit_destructor_for__CWerCplSupportService::ms_instance__

- ea: `0x180012610`
- end: `0x18001261c`
- name: `_dynamic_atexit_destructor_for__CWerCplSupportService::ms_instance__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007694`

## pseudocode

```c
void dynamic_atexit_destructor_for__CWerCplSupportService::ms_instance__()
{
  CWerCplSupportService::~CWerCplSupportService(&CWerCplSupportService::ms_instance);
}

```

## disassembly

```asm
0x180012610  lea     rcx, ?ms_instance@CWerCplSupportService@@0V1@A; this
0x180012617  jmp     ??1CWerCplSupportService@@AEAA@XZ; CWerCplSupportService::~CWerCplSupportService(void)
```
