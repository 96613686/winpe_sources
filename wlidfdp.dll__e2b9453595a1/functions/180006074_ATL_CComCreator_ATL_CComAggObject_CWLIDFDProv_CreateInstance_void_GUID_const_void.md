# ATL::CComCreator<ATL::CComAggObject<CWLIDFDProv>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006074`
- end: `0x180006183`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCWLIDFDProv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `271`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006060`

## callees

- `0x180002c20`
- `0x18000424c`
- `0x1800051b0`
- `0x180006074`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CWLIDFDProv>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  _DWORD *v7; // rbx
  int v8; // edi
  _DWORD *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0xA8u);
    v7[2] = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CWLIDFDProv>::`vftable';
    CWLIDFDProv::CWLIDFDProv((CWLIDFDProv *)(v7 + 6));
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CWLIDFDProv>::`vftable';
    *((_QWORD *)v7 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 10));
    if ( v8 < 0
      || (*((_BYTE *)v7 + 80) = 1, (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006074  mov     [rsp+arg_0], rbx
0x180006079  mov     [rsp+arg_10], r8
0x18000607e  mov     [rsp+arg_8], rdx
0x180006083  push    rsi
0x180006084  push    rdi
0x180006085  push    r12
0x180006087  push    r14
0x180006089  push    r15
0x18000608b  sub     rsp, 30h
0x18000608f  mov     rsi, r8
0x180006092  mov     r14, rdx
0x180006095  mov     r12, rcx
0x180006098  test    r8, r8
0x18000609b  jnz     short loc_1800060A7
0x18000609d  mov     eax, 80004003h
0x1800060a2  jmp     loc_180006171
0x1800060a7  mov     qword ptr [r8], 0
0x1800060ae  mov     edi, 8007000Eh
0x1800060b3  mov     [rsp+58h+arg_18], edi
0x1800060b7  mov     [rsp+58h+var_38], 0
0x1800060c0  mov     ecx, 0A8h; Size
0x1800060c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800060ca  mov     rbx, rax
0x1800060cd  mov     [rsp+58h+var_30], rax
0x1800060d2  mov     dword ptr [rax+8], 0
0x1800060d9  lea     rax, ??_7?$CComAggObject@VCWLIDFDProv@@@ATL@@6B@; const ATL::CComAggObject<CWLIDFDProv>::`vftable'
0x1800060e0  mov     [rbx], rax
0x1800060e3  lea     rcx, [rbx+18h]; this
0x1800060e7  call    ??0CWLIDFDProv@@QEAA@XZ; CWLIDFDProv::CWLIDFDProv(void)
0x1800060ec  lea     rax, ??_7?$CComContainedObject@VCWLIDFDProv@@@ATL@@6B@; const ATL::CComContainedObject<CWLIDFDProv>::`vftable'
0x1800060f3  mov     [rbx+18h], rax
0x1800060f7  mov     [rbx+20h], r12
0x1800060fb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006102  mov     rax, [rcx]
0x180006105  mov     rax, [rax+8]
0x180006109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610e  nop
0x18000610f  mov     [rsp+58h+var_38], rbx
0x180006114  jmp     short loc_180006129
0x180006116  mov     rsi, [rsp+58h+arg_10]
0x18000611b  mov     r14, [rsp+58h+arg_8]
0x180006120  mov     edi, [rsp+58h+arg_18]
0x180006124  mov     rbx, [rsp+58h+var_38]
0x180006129  test    rbx, rbx
0x18000612c  jz      short loc_18000616F
0x18000612e  lea     rcx, [rbx+28h]; this
0x180006132  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006137  mov     edi, eax
0x180006139  test    eax, eax
0x18000613b  js      short loc_18000615B
0x18000613d  mov     byte ptr [rbx+50h], 1
0x180006141  mov     rax, [rbx]
0x180006144  mov     r8, rsi
0x180006147  mov     rdx, r14
0x18000614a  mov     rcx, rbx
0x18000614d  mov     rax, [rax]
0x180006150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006155  mov     edi, eax
0x180006157  test    eax, eax
0x180006159  jz      short loc_18000616F
0x18000615b  mov     rax, [rbx]
0x18000615e  mov     edx, 1
0x180006163  mov     rcx, rbx
0x180006166  mov     rax, [rax+18h]
0x18000616a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616f  mov     eax, edi
0x180006171  mov     rbx, [rsp+58h+arg_0]
0x180006176  add     rsp, 30h
0x18000617a  pop     r15
0x18000617c  pop     r14
0x18000617e  pop     r12
0x180006180  pop     rdi
0x180006181  pop     rsi
0x180006182  retn
```
