# _SrSmapiCreateReplica_::_1_::dtor$5

- ea: `0x18002a8d3`
- end: `0x18002a8df`
- name: `_SrSmapiCreateReplica_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplica_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18002a8d3  mov     rcx, [rdx+30h]
0x18002a8da  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
