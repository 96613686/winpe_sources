# _CPath::GetDirectorySizeRecursive_::_1_::dtor$2

- ea: `0x14001cf55`
- end: `0x14001cf61`
- name: `_CPath::GetDirectorySizeRecursive_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400048c8`

## pseudocode

```c
__int64 __fastcall CPath::GetDirectorySizeRecursive_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a2 + 72);
}

```

## disassembly

```asm
0x14001cf55  lea     rcx, [rdx+48h]
0x14001cf5c  jmp     ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
```
