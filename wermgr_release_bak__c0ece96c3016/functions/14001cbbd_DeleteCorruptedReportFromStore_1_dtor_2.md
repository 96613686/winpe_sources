# _DeleteCorruptedReportFromStore_::_1_::dtor$2

- ea: `0x14001cbbd`
- end: `0x14001cbc9`
- name: `_DeleteCorruptedReportFromStore_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400048c8`

## pseudocode

```c
__int64 __fastcall DeleteCorruptedReportFromStore_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a2 + 128);
}

```

## disassembly

```asm
0x14001cbbd  lea     rcx, [rdx+80h]
0x14001cbc4  jmp     ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
```
