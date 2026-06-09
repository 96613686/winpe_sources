# mi::MiApplication::CreateInstance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002627c`
- end: `0x1800262b2`
- name: `?CreateInstance@MiApplication@mi@@QEAA?AVMiInstance@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006360`
- `0x180013f60`
- `0x180016e4c`
- `0x180019584`
- `0x18001a0fc`
- `0x180020ac0`

## callees

- `0x180006630`
- `0x18002627c`
- `0x1800262b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall mi::MiApplication::CreateInstance(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  std::_Ref_count_base *v5[2]; // [rsp+28h] [rbp-20h] BYREF

  *(_OWORD *)v5 = 0;
  mi::MiApplication::CreateInstance(a1, a2, a3, (__int64)v5);
  if ( v5[1] )
    std::_Ref_count_base::_Decref(v5[1]);
  return a2;
}

```

## disassembly

```asm
0x18002627c  push    rbx
0x18002627e  sub     rsp, 40h
0x180026282  mov     rbx, rdx
0x180026285  xorps   xmm0, xmm0
0x180026288  movdqu  xmmword ptr [rsp+48h+var_20], xmm0
0x18002628e  lea     r9, [rsp+48h+var_20]
0x180026293  call    ?CreateInstance@MiApplication@mi@@QEAA?AVMiInstance@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@5@@Z; mi::MiApplication::CreateInstance(std::wstring const &,std::shared_ptr<mi::MiSession const> const &)
0x180026298  nop
0x180026299  mov     rcx, [rsp+48h+var_20+8]; this
0x18002629e  test    rcx, rcx
0x1800262a1  jz      short loc_1800262A8
0x1800262a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800262a8  mov     rax, rbx
0x1800262ab  add     rsp, 40h
0x1800262af  pop     rbx
0x1800262b0  retn
```
