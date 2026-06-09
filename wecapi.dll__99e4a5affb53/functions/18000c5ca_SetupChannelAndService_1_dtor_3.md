# _SetupChannelAndService_::_1_::dtor$3

- ea: `0x18000c5ca`
- end: `0x18000c5d6`
- name: `_SetupChannelAndService_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x180006234`

## pseudocode

```c
__int64 __fastcall SetupChannelAndService_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wmi::ScopeGuardImpl1<int (*)(void *),void *>::~ScopeGuardImpl1<int (*)(void *),void *>(a2 + 256);
}

```

## disassembly

```asm
0x18000c5ca  lea     rcx, [rdx+100h]
0x18000c5d1  jmp     ??1?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<int (*)(void *),void *>::~ScopeGuardImpl1<int (*)(void *),void *>(void)
```
