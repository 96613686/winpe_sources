# _SetupChannelAndService_::_1_::dtor$1

- ea: `0x18000c5a6`
- end: `0x18000c5b2`
- name: `_SetupChannelAndService_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x180006234`

## pseudocode

```c
__int64 __fastcall SetupChannelAndService_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wmi::ScopeGuardImpl1<int (*)(void *),void *>::~ScopeGuardImpl1<int (*)(void *),void *>(a2 + 208);
}

```

## disassembly

```asm
0x18000c5a6  lea     rcx, [rdx+0D0h]
0x18000c5ad  jmp     ??1?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<int (*)(void *),void *>::~ScopeGuardImpl1<int (*)(void *),void *>(void)
```
