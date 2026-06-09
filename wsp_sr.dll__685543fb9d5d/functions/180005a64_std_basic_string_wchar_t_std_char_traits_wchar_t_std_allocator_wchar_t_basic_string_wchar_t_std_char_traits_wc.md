# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180005a64`
- end: `0x180005a69`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `82`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a376`
- `0x18002a39e`
- `0x18002a3c2`
- `0x18002a441`
- `0x18002a489`
- `0x18002a4ad`
- `0x18002a52a`
- `0x18002a6d5`
- `0x18002a735`
- `0x18002a798`
- `0x18002a80d`
- `0x18002a81f`
- `0x18002a831`
- `0x18002a855`
- `0x18002a89d`
- `0x18002a8af`
- `0x18002a8c1`
- `0x18002a8d3`
- `0x18002a8e5`
- `0x18002a909`
- `0x18002a92d`
- `0x18002a951`
- `0x18002a987`
- `0x18002aa28`
- `0x18002aa3a`
- `0x18002aa4c`
- `0x18002aa92`
- `0x18002aad8`
- `0x18002aaea`
- `0x18002aafc`
- `0x18002ab0e`
- `0x18002ab78`
- `0x18002ad04`
- `0x18002ad28`
- `0x18002ad4c`
- `0x18002ad5e`
- `0x18002ad82`
- `0x18002adb8`
- `0x18002adca`
- `0x18002adee`
- `0x18002aea0`
- `0x18002aedf`
- `0x18002aef1`
- `0x18002af15`
- `0x18002af39`
- `0x18002af4b`
- `0x18002af5d`
- `0x18002af6f`
- `0x18002afa5`
- `0x18002afb7`

## callees

- `0x180006724`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  return std::wstring::_Tidy_deallocate(a1);
}

```

## disassembly

```asm
0x180005a64  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
