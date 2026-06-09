# _SrSmapiInvokeCreateReplicationGroup_::_1_::dtor$0

- ea: `0x18002aafb`
- end: `0x18002ab07`
- name: `_SrSmapiInvokeCreateReplicationGroup_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a24`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeCreateReplicationGroup_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 224));
}

```

## disassembly

```asm
0x18002aafb  mov     rcx, [rdx+0E0h]
0x18002ab02  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
