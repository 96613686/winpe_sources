# _ComTaskHost::StartTaskWorker_::_1_::dtor$3

- ea: `0x14000ad50`
- end: `0x14000ad5c`
- name: `_ComTaskHost::StartTaskWorker_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400071d4`

## pseudocode

```c
void __fastcall ComTaskHost::StartTaskWorker_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ComCallAutoCancel::~ComCallAutoCancel((HANDLE *)(a2 + 64));
}

```

## disassembly

```asm
0x14000ad50  lea     rcx, [rdx+40h]; this
0x14000ad57  jmp     ??1ComCallAutoCancel@@QEAA@XZ; ComCallAutoCancel::~ComCallAutoCancel(void)
```
