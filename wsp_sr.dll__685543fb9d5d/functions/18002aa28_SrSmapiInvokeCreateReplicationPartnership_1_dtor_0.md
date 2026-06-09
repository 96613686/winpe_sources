# _SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$0

- ea: `0x18002aa28`
- end: `0x18002aa34`
- name: `_SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 136));
}

```

## disassembly

```asm
0x18002aa28  mov     rcx, [rdx+88h]
0x18002aa2f  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
