# _ComTaskHost::StartTaskWorker_::_1_::dtor$2

- ea: `0x14000ad30`
- end: `0x14000ad3c`
- name: `_ComTaskHost::StartTaskWorker_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006cd0`

## pseudocode

```c
__int64 __fastcall ComTaskHost::StartTaskWorker_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wmi::AutoRef<IUnknown>::~AutoRef<IUnknown>(a2 + 144);
}

```

## disassembly

```asm
0x14000ad30  lea     rcx, [rdx+90h]
0x14000ad37  jmp     ??1?$AutoRef@UIUnknown@@@wmi@@QEAA@XZ; wmi::AutoRef<IUnknown>::~AutoRef<IUnknown>(void)
```
