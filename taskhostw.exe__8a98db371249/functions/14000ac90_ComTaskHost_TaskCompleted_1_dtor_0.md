# _ComTaskHost::TaskCompleted_::_1_::dtor$0

- ea: `0x14000ac90`
- end: `0x14000ac9c`
- name: `_ComTaskHost::TaskCompleted_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006f60`

## pseudocode

```c
void __fastcall ComTaskHost::TaskCompleted_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ShutdownGuard::~ShutdownGuard((ShutdownGuard *)(a2 + 144));
}

```

## disassembly

```asm
0x14000ac90  lea     rcx, [rdx+90h]; this
0x14000ac97  jmp     ??1ShutdownGuard@@QEAA@XZ; ShutdownGuard::~ShutdownGuard(void)
```
