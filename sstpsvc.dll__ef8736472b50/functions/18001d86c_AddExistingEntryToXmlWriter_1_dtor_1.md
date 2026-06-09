# _AddExistingEntryToXmlWriter_::_1_::dtor$1

- ea: `0x18001d86c`
- end: `0x18001d878`
- name: `_AddExistingEntryToXmlWriter_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001093c`

## pseudocode

```c
__int64 __fastcall AddExistingEntryToXmlWriter_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(a2 + 48);
}

```

## disassembly

```asm
0x18001d86c  lea     rcx, [rdx+30h]
0x18001d873  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
