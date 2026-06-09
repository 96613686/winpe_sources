# _SrSmapiInvokeDeleteReplicationGroup_::_1_::dtor$0

- ea: `0x18002aa92`
- end: `0x18002aa9e`
- name: `_SrSmapiInvokeDeleteReplicationGroup_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeDeleteReplicationGroup_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 104));
}

```

## disassembly

```asm
0x18002aa92  mov     rcx, [rdx+68h]
0x18002aa99  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
