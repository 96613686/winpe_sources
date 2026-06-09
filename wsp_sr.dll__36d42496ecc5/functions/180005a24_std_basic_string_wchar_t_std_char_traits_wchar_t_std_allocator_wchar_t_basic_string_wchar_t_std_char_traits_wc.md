# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180005a24`
- end: `0x180005a29`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `82`
- callee_count: `1`
- tags: ``

## callers

- `0x180029ec6`
- `0x180029eee`
- `0x180029f12`
- `0x180029f91`
- `0x180029fd9`
- `0x180029ffd`
- `0x18002a074`
- `0x18002a20e`
- `0x18002a26c`
- `0x18002a2cd`
- `0x18002a340`
- `0x18002a352`
- `0x18002a364`
- `0x18002a388`
- `0x18002a3d0`
- `0x18002a3e2`
- `0x18002a3f4`
- `0x18002a406`
- `0x18002a418`
- `0x18002a43c`
- `0x18002a460`
- `0x18002a484`
- `0x18002a4ba`
- `0x18002a55b`
- `0x18002a56d`
- `0x18002a57f`
- `0x18002a5c5`
- `0x18002a60b`
- `0x18002a61d`
- `0x18002a62f`
- `0x18002a641`
- `0x18002a6ab`
- `0x18002a837`
- `0x18002a85b`
- `0x18002a87f`
- `0x18002a891`
- `0x18002a8b5`
- `0x18002a8eb`
- `0x18002a8fd`
- `0x18002a921`
- `0x18002a9d3`
- `0x18002aa11`
- `0x18002aa23`
- `0x18002aa47`
- `0x18002aa6b`
- `0x18002aa7d`
- `0x18002aa8f`
- `0x18002aaa1`
- `0x18002aad7`
- `0x18002aae9`

## callees

- `0x1800066d8`

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
0x180005a24  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
