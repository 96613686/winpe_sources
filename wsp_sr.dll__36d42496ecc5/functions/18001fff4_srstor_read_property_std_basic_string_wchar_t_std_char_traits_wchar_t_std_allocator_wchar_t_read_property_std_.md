# srstor::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(mi::MiInstance const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18001fff4`
- end: `0x180020015`
- name: `??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `33`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, _QWORD *)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180016b28`
- `0x18002001c`
- `0x18002078c`
- `0x180020800`
- `0x180020b1c`
- `0x180020b90`
- `0x180020c7c`
- `0x180020d64`
- `0x180020dd8`
- `0x180020e4c`
- `0x180020ec0`
- `0x180021138`
- `0x1800211ac`
- `0x1800213dc`
- `0x180021450`
- `0x1800294dc`
- `0x180029a44`
- `0x180029ba0`

## callees

- `0x18000584c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall srstor::read_property<std::wstring>::read_property<std::wstring>(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  *a1 = a2;
  std::wstring::wstring((__int64)(a1 + 1), a3);
  return a1;
}

```

## disassembly

```asm
0x18001fff4  push    rbx
0x18001fff6  sub     rsp, 20h
0x18001fffa  mov     [rcx], rdx
0x18001fffd  mov     rbx, rcx
0x180020000  add     rcx, 8
0x180020004  mov     rdx, r8
0x180020007  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002000c  mov     rax, rbx
0x18002000f  add     rsp, 20h
0x180020013  pop     rbx
0x180020014  retn
```
