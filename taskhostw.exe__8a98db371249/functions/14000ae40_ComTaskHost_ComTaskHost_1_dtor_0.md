# _ComTaskHost::ComTaskHost_::_1_::dtor$0

- ea: `0x14000ae40`
- end: `0x14000ae50`
- name: `_ComTaskHost::ComTaskHost_::_1_::dtor$0`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006060`

## pseudocode

```c
void __fastcall ComTaskHost::ComTaskHost_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(*(_QWORD *)(a2 + 96) + 40LL));
}

```

## disassembly

```asm
0x14000ae40  mov     rcx, [rdx+60h]
0x14000ae47  add     rcx, 28h ; '('; this
0x14000ae4b  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
