# _CommandImpl::ShowHelp_::_1_::dtor$2

- ea: `0x180015991`
- end: `0x18001599d`
- name: `_CommandImpl::ShowHelp_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d3b4`

## pseudocode

```c
__int64 __fastcall CommandImpl::ShowHelp_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 32);
}

```

## disassembly

```asm
0x180015991  lea     rcx, [rdx+20h]
0x180015998  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
