# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTDCCtl>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180010c90`
- end: `0x180010d26`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCTDCCtl@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800011b8`
- `0x18000eec8`
- `0x180010c90`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTDCCtl>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  void *v6; // rax
  __int64 v7; // rax
  void (__fastcall ***v8)(_QWORD, __int64); // rsi

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x248u);
  if ( v6 )
  {
    v7 = ATL::CComObject<CTDCCtl>::CComObject<CTDCCtl>(v6);
    v8 = (void (__fastcall ***)(_QWORD, __int64))v7;
    if ( v7 )
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))(v7 + 176))(v7 + 176, a2, a3);
      if ( v5 )
        (**v8)(v8, 1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180010c90  push    rbx
0x180010c92  push    rbp
0x180010c93  push    rsi
0x180010c94  push    rdi
0x180010c95  sub     rsp, 28h
0x180010c99  mov     rdi, r8
0x180010c9c  mov     rbp, rdx
0x180010c9f  test    rcx, rcx
0x180010ca2  jnz     short loc_180010D03
0x180010ca4  test    r8, r8
0x180010ca7  jz      short loc_180010D08
0x180010ca9  mov     [r8], rcx
0x180010cac  mov     ebx, 8007000Eh
0x180010cb1  mov     ecx, 248h; Size
0x180010cb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010cbb  test    rax, rax
0x180010cbe  jz      short loc_180010D1B
0x180010cc0  mov     rcx, rax
0x180010cc3  call    ??0?$CComObject@VCTDCCtl@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CTDCCtl>::CComObject<CTDCCtl>(void *)
0x180010cc8  mov     rsi, rax
0x180010ccb  test    rax, rax
0x180010cce  jz      short loc_180010D1B
0x180010cd0  lea     rcx, [rax+0B0h]
0x180010cd7  mov     r8, rdi
0x180010cda  mov     rdx, [rcx]
0x180010cdd  mov     rax, [rdx]
0x180010ce0  mov     rdx, rbp
0x180010ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce8  mov     ebx, eax
0x180010cea  test    eax, eax
0x180010cec  jz      short loc_180010D1B
0x180010cee  mov     rcx, [rsi]
0x180010cf1  mov     edx, 1
0x180010cf6  mov     rax, [rcx]
0x180010cf9  mov     rcx, rsi
0x180010cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d01  jmp     short loc_180010D1B
0x180010d03  test    rdi, rdi
0x180010d06  jnz     short loc_180010D0F
0x180010d08  mov     ebx, 80004003h
0x180010d0d  jmp     short loc_180010D1B
0x180010d0f  mov     qword ptr [r8], 0
0x180010d16  mov     ebx, 80040110h
0x180010d1b  mov     eax, ebx
0x180010d1d  add     rsp, 28h
0x180010d21  pop     rdi
0x180010d22  pop     rsi
0x180010d23  pop     rbp
0x180010d24  pop     rbx
0x180010d25  retn
```
