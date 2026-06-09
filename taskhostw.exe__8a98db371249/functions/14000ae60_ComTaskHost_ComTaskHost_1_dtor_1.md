# _ComTaskHost::ComTaskHost_::_1_::dtor$1

- ea: `0x14000ae60`
- end: `0x14000ae70`
- name: `_ComTaskHost::ComTaskHost_::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006060`

## pseudocode

```c
void __fastcall ComTaskHost::ComTaskHost_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(*(_QWORD *)(a2 + 96) + 56LL));
}

```

## disassembly

```asm
0x14000ae60  mov     rcx, [rdx+60h]
0x14000ae67  add     rcx, 38h ; '8'; this
0x14000ae6b  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
