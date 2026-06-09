# _ComTaskHost::StopTaskWorker_::_1_::dtor$0

- ea: `0x14000ad90`
- end: `0x14000ad9c`
- name: `_ComTaskHost::StopTaskWorker_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006dc0`

## pseudocode

```c
void __fastcall ComTaskHost::StopTaskWorker_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)(a2 + 112));
}

```

## disassembly

```asm
0x14000ad90  lea     rcx, [rdx+70h]; this
0x14000ad97  jmp     ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
```
