# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800062b0`
- end: `0x180006398`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002c20`
- `0x18000424c`
- `0x18000592c`
- `0x1800062b0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 v5; // r14
  _BYTE *v7; // rbx
  int v8; // edi
  _BYTE *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x48u);
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v7[56] = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    *((_QWORD *)v7 + 8) = v5;
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 < 0 || (v7[56] = 1, (v8 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800062b0  mov     [rsp+arg_10], r8
0x1800062b5  mov     [rsp+arg_8], rdx
0x1800062ba  mov     [rsp+arg_0], rcx
0x1800062bf  push    rbx
0x1800062c0  push    rsi
0x1800062c1  push    rdi
0x1800062c2  push    r14
0x1800062c4  push    r15
0x1800062c6  sub     rsp, 30h
0x1800062ca  mov     rsi, r8
0x1800062cd  mov     r15, rdx
0x1800062d0  mov     r14, rcx
0x1800062d3  test    r8, r8
0x1800062d6  jnz     short loc_1800062E2
0x1800062d8  mov     eax, 80004003h
0x1800062dd  jmp     loc_18000638C
0x1800062e2  mov     qword ptr [r8], 0
0x1800062e9  mov     edi, 8007000Eh
0x1800062ee  mov     [rsp+58h+arg_18], edi
0x1800062f2  mov     [rsp+58h+var_38], 0
0x1800062fb  mov     ecx, 48h ; 'H'; Size
0x180006300  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006305  mov     rbx, rax
0x180006308  mov     dword ptr [rax+8], 0
0x18000630f  xorps   xmm0, xmm0
0x180006312  xor     eax, eax
0x180006314  movups  xmmword ptr [rbx+10h], xmm0
0x180006318  movups  xmmword ptr [rbx+20h], xmm0
0x18000631c  mov     [rbx+30h], rax
0x180006320  mov     [rbx+38h], al
0x180006323  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000632a  mov     [rbx], rax
0x18000632d  mov     [rsp+58h+var_38], rbx
0x180006332  jmp     short loc_18000634C
0x180006334  mov     rsi, [rsp+58h+arg_10]
0x180006339  mov     r15, [rsp+58h+arg_8]
0x18000633e  mov     r14, [rsp+58h+arg_0]
0x180006343  mov     edi, [rsp+58h+arg_18]
0x180006347  mov     rbx, [rsp+58h+var_38]
0x18000634c  test    rbx, rbx
0x18000634f  jz      short loc_18000638A
0x180006351  mov     [rbx+40h], r14
0x180006355  lea     rcx, [rbx+10h]; this
0x180006359  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000635e  mov     edi, eax
0x180006360  test    eax, eax
0x180006362  js      short loc_180006382
0x180006364  mov     byte ptr [rbx+38h], 1
0x180006368  mov     rax, [rbx]
0x18000636b  mov     r8, rsi
0x18000636e  mov     rdx, r15
0x180006371  mov     rcx, rbx
0x180006374  mov     rax, [rax]
0x180006377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637c  mov     edi, eax
0x18000637e  test    eax, eax
0x180006380  jz      short loc_18000638A
0x180006382  mov     rcx, rbx; Block
0x180006385  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000638a  mov     eax, edi
0x18000638c  add     rsp, 30h
0x180006390  pop     r15
0x180006392  pop     r14
0x180006394  pop     rdi
0x180006395  pop     rsi
0x180006396  pop     rbx
0x180006397  retn
```
