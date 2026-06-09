# _AddExistingEntryToXmlWriter_::_1_::dtor$0

- ea: `0x18001d8b4`
- end: `0x18001d8c0`
- name: `_AddExistingEntryToXmlWriter_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180010930`

## pseudocode

```c
__int64 __fastcall AddExistingEntryToXmlWriter_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::~set<std::wstring,_lessstr,std::allocator<std::wstring>>(*(_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x18001d8b4  mov     rcx, [rdx+50h]
0x18001d8bb  jmp     ??1?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,_lessstr,std::allocator<std::wstring>>::~set<std::wstring,_lessstr,std::allocator<std::wstring>>(void)
```
