# wvr::write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::write_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(mi::MiInstance &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002001c`
- end: `0x180020043`
- name: `??0?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEAA@AEAVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020cf0`

## callees

- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::write_property<std::wstring>::write_property<std::wstring>(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  srstor::read_property<std::wstring>::read_property<std::wstring>(a1, a2, a3);
  a1[5] = a2;
  return a1;
}

```

## disassembly

```asm
0x18002001c  mov     [rsp+arg_0], rbx
0x180020021  push    rdi
0x180020022  sub     rsp, 20h
0x180020026  mov     rbx, rdx
0x180020029  mov     rdi, rcx
0x18002002c  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020031  mov     [rdi+28h], rbx
0x180020035  mov     rax, rdi
0x180020038  mov     rbx, [rsp+28h+arg_0]
0x18002003d  add     rsp, 20h
0x180020041  pop     rdi
0x180020042  retn
```
