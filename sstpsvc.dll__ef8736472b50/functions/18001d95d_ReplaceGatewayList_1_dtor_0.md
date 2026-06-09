# _ReplaceGatewayList_::_1_::dtor$0

- ea: `0x18001d95d`
- end: `0x18001d969`
- name: `_ReplaceGatewayList_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001093c`

## pseudocode

```c
__int64 __fastcall ReplaceGatewayList_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(*(_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x18001d95d  mov     rcx, [rdx+40h]
0x18001d964  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
