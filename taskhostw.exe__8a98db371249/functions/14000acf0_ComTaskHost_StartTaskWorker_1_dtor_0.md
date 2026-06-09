# _ComTaskHost::StartTaskWorker_::_1_::dtor$0

- ea: `0x14000acf0`
- end: `0x14000acfc`
- name: `_ComTaskHost::StartTaskWorker_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006cd0`

## pseudocode

```c
__int64 __fastcall ComTaskHost::StartTaskWorker_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wmi::AutoRef<IUnknown>::~AutoRef<IUnknown>(a2 + 136);
}

```

## disassembly

```asm
0x14000acf0  lea     rcx, [rdx+88h]
0x14000acf7  jmp     ??1?$AutoRef@UIUnknown@@@wmi@@QEAA@XZ; wmi::AutoRef<IUnknown>::~AutoRef<IUnknown>(void)
```
