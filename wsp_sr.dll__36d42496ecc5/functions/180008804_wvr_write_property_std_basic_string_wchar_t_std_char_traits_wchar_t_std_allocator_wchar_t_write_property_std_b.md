# wvr::write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::~write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(void)

- ea: `0x180008804`
- end: `0x18000880d`
- name: `??1?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEAA@XZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `62`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a11a`
- `0x18002a12c`
- `0x18002a158`
- `0x18002a184`
- `0x18002a1b0`
- `0x18002a1df`
- `0x18002a23d`
- `0x18002a29b`
- `0x18002a2fc`
- `0x18002a813`
- `0x18002a825`
- `0x18002a849`
- `0x18002a86d`
- `0x18002a8a3`
- `0x18002a969`
- `0x18002ac60`
- `0x18002ac8f`
- `0x18002acbe`
- `0x18002acd0`
- `0x18002aed0`
- `0x18002aeff`
- `0x18002af2e`
- `0x18002af5d`
- `0x18002af8c`
- `0x18002af9e`
- `0x18002afc2`
- `0x18002afe6`
- `0x18002aff8`
- `0x18002b053`
- `0x18002b121`
- `0x18002b150`
- `0x18002b17c`
- `0x18002b18e`
- `0x18002b1a0`
- `0x18002b26f`
- `0x18002b29b`
- `0x18002b2ca`
- `0x18002b2f6`
- `0x18002b325`
- `0x18002b337`
- `0x18002b3b9`
- `0x18002b3cb`
- `0x18002b3f7`
- `0x18002b423`
- `0x18002b50d`
- `0x18002b51f`
- `0x18002b54e`
- `0x18002b57a`
- `0x18002b5a9`
- `0x18002b5d8`

## callees

- `0x1800066d8`

## pseudocode

```c
__int64 __fastcall wvr::write_property<std::wstring>::~write_property<std::wstring>(__int64 a1)
{
  return std::wstring::_Tidy_deallocate(a1 + 8);
}

```

## disassembly

```asm
0x180008804  add     rcx, 8
0x180008808  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
