# _SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$2

- ea: `0x18002a57f`
- end: `0x18002a58b`
- name: `_SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a24`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 120));
}

```

## disassembly

```asm
0x18002a57f  mov     rcx, [rdx+78h]
0x18002a586  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
