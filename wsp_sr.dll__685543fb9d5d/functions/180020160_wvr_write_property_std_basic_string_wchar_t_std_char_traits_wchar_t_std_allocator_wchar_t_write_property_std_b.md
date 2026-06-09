# wvr::write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(mi::MiInstance &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180020160`
- end: `0x180020188`
- name: `??0?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEAA@AEAVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020e54`

## callees

- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::write_property<std::wstring>::write_property<std::wstring>(_QWORD *a1, __int64 a2, __int64 a3)
{
  srstor::read_property<std::wstring>::read_property<std::wstring>(a1, a2, a3);
  a1[5] = a2;
  return a1;
}

```

## disassembly

```asm
0x180020160  mov     [rsp+arg_0], rbx
0x180020165  push    rdi
0x180020166  sub     rsp, 20h
0x18002016a  mov     rbx, rdx
0x18002016d  mov     rdi, rcx
0x180020170  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020175  mov     [rdi+28h], rbx
0x180020179  mov     rax, rdi
0x18002017c  mov     rbx, [rsp+28h+arg_0]
0x180020181  add     rsp, 20h
0x180020185  pop     rdi
0x180020186  retn
```
