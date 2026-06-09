# _ComTaskMgrBase::StopComTask_::_1_::dtor$0

- ea: `0x14000b064`
- end: `0x14000b070`
- name: `_ComTaskMgrBase::StopComTask_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006f60`

## pseudocode

```c
void __fastcall ComTaskMgrBase::StopComTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ShutdownGuard::~ShutdownGuard((ShutdownGuard *)(a2 + 56));
}

```

## disassembly

```asm
0x14000b064  lea     rcx, [rdx+38h]; this
0x14000b06b  jmp     ??1ShutdownGuard@@QEAA@XZ; ShutdownGuard::~ShutdownGuard(void)
```
