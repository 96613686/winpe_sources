# _ComTaskHost::StopTaskWorker_::_1_::dtor$1

- ea: `0x14000adb0`
- end: `0x14000adbc`
- name: `_ComTaskHost::StopTaskWorker_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400071d4`

## pseudocode

```c
void __fastcall ComTaskHost::StopTaskWorker_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ComCallAutoCancel::~ComCallAutoCancel((HANDLE *)(a2 + 48));
}

```

## disassembly

```asm
0x14000adb0  lea     rcx, [rdx+30h]; this
0x14000adb7  jmp     ??1ComCallAutoCancel@@QEAA@XZ; ComCallAutoCancel::~ComCallAutoCancel(void)
```
