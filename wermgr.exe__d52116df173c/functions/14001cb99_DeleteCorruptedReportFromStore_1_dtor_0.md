# _DeleteCorruptedReportFromStore_::_1_::dtor$0

- ea: `0x14001cb99`
- end: `0x14001cba5`
- name: `_DeleteCorruptedReportFromStore_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400048c8`

## pseudocode

```c
void __fastcall DeleteCorruptedReportFromStore_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((void **)(a2 + 192));
}

```

## disassembly

```asm
0x14001cb99  lea     rcx, [rdx+0C0h]
0x14001cba0  jmp     ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
```
