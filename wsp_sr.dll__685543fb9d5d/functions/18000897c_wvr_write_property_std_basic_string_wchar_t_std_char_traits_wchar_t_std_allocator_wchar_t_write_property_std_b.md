# wvr::write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::~write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(void)

- ea: `0x18000897c`
- end: `0x180008985`
- name: `??1?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEAA@XZ`
- size: `9`
- prototype: ``
- caller_count: `62`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a5dc`
- `0x18002a5ee`
- `0x18002a61b`
- `0x18002a648`
- `0x18002a675`
- `0x18002a6a5`
- `0x18002a705`
- `0x18002a765`
- `0x18002a7c8`
- `0x18002ace0`
- `0x18002acf2`
- `0x18002ad16`
- `0x18002ad3a`
- `0x18002ad70`
- `0x18002ae36`
- `0x18002b12e`
- `0x18002b15e`
- `0x18002b18e`
- `0x18002b1a0`
- `0x18002b3a2`
- `0x18002b3d2`
- `0x18002b402`
- `0x18002b432`
- `0x18002b462`
- `0x18002b474`
- `0x18002b498`
- `0x18002b4bc`
- `0x18002b4ce`
- `0x18002b529`
- `0x18002b5f8`
- `0x18002b628`
- `0x18002b655`
- `0x18002b667`
- `0x18002b679`
- `0x18002b749`
- `0x18002b776`
- `0x18002b7a6`
- `0x18002b7d3`
- `0x18002b803`
- `0x18002b815`
- `0x18002b897`
- `0x18002b8a9`
- `0x18002b8d6`
- `0x18002b903`
- `0x18002b9ed`
- `0x18002b9ff`
- `0x18002ba2f`
- `0x18002ba5c`
- `0x18002ba8c`
- `0x18002babc`

## callees

- `0x180006724`

## pseudocode

```c
__int64 __fastcall wvr::write_property<std::wstring>::~write_property<std::wstring>(__int64 a1)
{
  return std::wstring::_Tidy_deallocate(a1 + 8);
}

```

## disassembly

```asm
0x18000897c  add     rcx, 8
0x180008980  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
