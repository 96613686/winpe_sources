# mi::MiApplication::CreateInstance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180025f44`
- end: `0x180025f79`
- name: `?CreateInstance@MiApplication@mi@@QEAA?AVMiInstance@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006320`
- `0x180014050`
- `0x180016f84`
- `0x180019550`
- `0x18001a0c4`
- `0x18002095c`

## callees

- `0x1800065ec`
- `0x180025f44`
- `0x180025f80`

## pseudocode

```c
__int64 __fastcall mi::MiApplication::CreateInstance(__int64 a1, __int64 a2, __int64 a3)
{
  std::_Ref_count_base *v5[2]; // [rsp+28h] [rbp-20h] BYREF

  *(_OWORD *)v5 = 0;
  mi::MiApplication::CreateInstance(a1, a2, a3, v5);
  if ( v5[1] )
    std::_Ref_count_base::_Decref(v5[1]);
  return a2;
}

```

## disassembly

```asm
0x180025f44  push    rbx
0x180025f46  sub     rsp, 40h
0x180025f4a  mov     rbx, rdx
0x180025f4d  xorps   xmm0, xmm0
0x180025f50  movdqu  xmmword ptr [rsp+48h+var_20], xmm0
0x180025f56  lea     r9, [rsp+48h+var_20]
0x180025f5b  call    ?CreateInstance@MiApplication@mi@@QEAA?AVMiInstance@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@5@@Z; mi::MiApplication::CreateInstance(std::wstring const &,std::shared_ptr<mi::MiSession const> const &)
0x180025f60  nop
0x180025f61  mov     rcx, [rsp+48h+var_20+8]; this
0x180025f66  test    rcx, rcx
0x180025f69  jz      short loc_180025F70
0x180025f6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025f70  mov     rax, rbx
0x180025f73  add     rsp, 40h
0x180025f77  pop     rbx
0x180025f78  retn
```
