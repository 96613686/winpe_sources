# _SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$2

- ea: `0x18002aa4c`
- end: `0x18002aa58`
- name: `_SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 120));
}

```

## disassembly

```asm
0x18002aa4c  mov     rcx, [rdx+78h]
0x18002aa53  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
