# _ComTaskHost::Stop_::_1_::dtor$0

- ea: `0x14000ad70`
- end: `0x14000ad7c`
- name: `_ComTaskHost::Stop_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007078`

## pseudocode

```c
void __fastcall ComTaskHost::Stop_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)(a2 + 96));
}

```

## disassembly

```asm
0x14000ad70  lea     rcx, [rdx+60h]; this
0x14000ad77  jmp     ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
```
