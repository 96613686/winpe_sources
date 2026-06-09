# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003960`
- end: `0x180003a5f`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001700`
- `0x180001c7c`
- `0x1800036c8`
- `0x180003960`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 (__fastcall **a1)(_QWORD, _QWORD, _QWORD),
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 (__fastcall **v5)(_QWORD, _QWORD, _QWORD); // r14
  unsigned int v7; // edi
  _BYTE *v8; // rax
  _BYTE *v9; // rbx
  int v10; // ecx
  int v11; // eax
  _BYTE *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    if ( v10 >= 0 )
      v9[56] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180003960  mov     [rsp+arg_10], r8
0x180003965  mov     [rsp+arg_8], rdx
0x18000396a  mov     [rsp+arg_0], rcx
0x18000396f  push    rbx
0x180003970  push    rsi
0x180003971  push    rdi
0x180003972  push    r14
0x180003974  push    r15
0x180003976  sub     rsp, 30h
0x18000397a  mov     rsi, r8
0x18000397d  mov     r15, rdx
0x180003980  mov     r14, rcx
0x180003983  test    r8, r8
0x180003986  jnz     short loc_180003992
0x180003988  mov     eax, 80004003h
0x18000398d  jmp     loc_180003A53
0x180003992  mov     qword ptr [r8], 0
0x180003999  mov     edi, 8007000Eh
0x18000399e  mov     [rsp+58h+arg_18], edi
0x1800039a2  mov     [rsp+58h+var_38], 0
0x1800039ab  mov     ecx, 48h ; 'H'; Size
0x1800039b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800039b5  mov     rbx, rax
0x1800039b8  test    rbx, rbx
0x1800039bb  jz      short loc_1800039E2
0x1800039bd  mov     dword ptr [rax+8], 0
0x1800039c4  xorps   xmm0, xmm0
0x1800039c7  xor     eax, eax
0x1800039c9  movups  xmmword ptr [rbx+10h], xmm0
0x1800039cd  movups  xmmword ptr [rbx+20h], xmm0
0x1800039d1  mov     [rbx+30h], rax
0x1800039d5  mov     [rbx+38h], al
0x1800039d8  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800039df  mov     [rbx], rax
0x1800039e2  mov     [rsp+58h+var_38], rbx
0x1800039e7  jmp     short loc_180003A01
0x1800039e9  mov     rsi, [rsp+58h+arg_10]
0x1800039ee  mov     r15, [rsp+58h+arg_8]
0x1800039f3  mov     r14, [rsp+58h+arg_0]
0x1800039f8  mov     edi, [rsp+58h+arg_18]
0x1800039fc  mov     rbx, [rsp+58h+var_38]
0x180003a01  test    rbx, rbx
0x180003a04  jz      short loc_180003A51
0x180003a06  mov     [rbx+40h], r14
0x180003a0a  lea     rcx, [rbx+10h]; this
0x180003a0e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003a13  mov     ecx, eax
0x180003a15  test    eax, eax
0x180003a17  js      short loc_180003A1D
0x180003a19  mov     byte ptr [rbx+38h], 1
0x180003a1d  xor     eax, eax
0x180003a1f  test    ecx, ecx
0x180003a21  cmovs   eax, ecx
0x180003a24  xor     edi, edi
0x180003a26  test    eax, eax
0x180003a28  cmovs   edi, eax
0x180003a2b  test    edi, edi
0x180003a2d  jnz     short loc_180003A49
0x180003a2f  mov     rax, [rbx]
0x180003a32  mov     r8, rsi
0x180003a35  mov     rdx, r15
0x180003a38  mov     rcx, rbx
0x180003a3b  mov     rax, [rax]
0x180003a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a43  mov     edi, eax
0x180003a45  test    eax, eax
0x180003a47  jz      short loc_180003A51
0x180003a49  mov     rcx, rbx; Block
0x180003a4c  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180003a51  mov     eax, edi
0x180003a53  add     rsp, 30h
0x180003a57  pop     r15
0x180003a59  pop     r14
0x180003a5b  pop     rdi
0x180003a5c  pop     rsi
0x180003a5d  pop     rbx
0x180003a5e  retn
```
