# _ComTaskHost::StartTaskWorker_::_1_::dtor$1

- ea: `0x14000ad10`
- end: `0x14000ad1c`
- name: `_ComTaskHost::StartTaskWorker_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006dc0`

## pseudocode

```c
void __fastcall ComTaskHost::StartTaskWorker_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)(a2 + 128));
}

```

## disassembly

```asm
0x14000ad10  lea     rcx, [rdx+80h]; this
0x14000ad17  jmp     ??1AutoThreadPriority@@QEAA@XZ; AutoThreadPriority::~AutoThreadPriority(void)
```
