# srstor::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(mi::MiInstance const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180020138`
- end: `0x18002015a`
- name: `??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `34`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1800169ec`
- `0x180020160`
- `0x1800208ec`
- `0x180020960`
- `0x180020c80`
- `0x180020cf4`
- `0x180020de0`
- `0x180020ec8`
- `0x180020f3c`
- `0x180020fb0`
- `0x180021024`
- `0x1800212cc`
- `0x180021340`
- `0x18002156c`
- `0x1800215e0`
- `0x180029970`
- `0x180029ef0`
- `0x18002a050`

## callees

- `0x180005884`

## pseudocode

```c
_QWORD *__fastcall srstor::read_property<std::wstring>::read_property<std::wstring>(_QWORD *a1, __int64 a2, __int64 a3)
{
  *a1 = a2;
  std::wstring::wstring(a1 + 1, a3);
  return a1;
}

```

## disassembly

```asm
0x180020138  push    rbx
0x18002013a  sub     rsp, 20h
0x18002013e  mov     [rcx], rdx
0x180020141  mov     rbx, rcx
0x180020144  add     rcx, 8
0x180020148  mov     rdx, r8
0x18002014b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180020150  mov     rax, rbx
0x180020153  add     rsp, 20h
0x180020157  pop     rbx
0x180020158  retn
```
