# _std::_Hash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CaseInsensitiveStringHash_CaseInsensitiveStringEquality_::operator()_::_1_::dtor$0

- ea: `0x18001d8a2`
- end: `0x18001d8ae`
- name: `_std::_Hash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CaseInsensitiveStringHash_CaseInsensitiveStringEquality_::operator()_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010914`

## pseudocode

```c
__int64 __fastcall std::_Hash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CaseInsensitiveStringHash_CaseInsensitiveStringEquality_::operator()_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 128));
}

```

## disassembly

```asm
0x18001d8a2  mov     rcx, [rdx+80h]
0x18001d8a9  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
