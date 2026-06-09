# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004500`
- end: `0x1800045f5`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800011dc`
- `0x180002f98`
- `0x180004500`
- `0x180004a90`
- `0x180013010`

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
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // ecx
  _DWORD *v12; // [rsp+20h] [rbp-38h]

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
      v8[2] = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *((_BYTE *)v8 + 56) = 0;
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
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 4));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180004500  mov     [rsp+arg_10], r8
0x180004505  mov     [rsp+arg_8], rdx
0x18000450a  mov     [rsp+arg_0], rcx
0x18000450f  push    rbx
0x180004510  push    rsi
0x180004511  push    rdi
0x180004512  push    r14
0x180004514  push    r15
0x180004516  sub     rsp, 30h
0x18000451a  mov     rsi, r8
0x18000451d  mov     r15, rdx
0x180004520  mov     r14, rcx
0x180004523  test    r8, r8
0x180004526  jnz     short loc_180004532
0x180004528  mov     eax, 80004003h
0x18000452d  jmp     loc_1800045E9
0x180004532  mov     qword ptr [r8], 0
0x180004539  mov     edi, 8007000Eh
0x18000453e  mov     [rsp+58h+arg_18], edi
0x180004542  mov     [rsp+58h+var_38], 0
0x18000454b  mov     ecx, 48h ; 'H'; Size
0x180004550  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004555  mov     rbx, rax
0x180004558  test    rbx, rbx
0x18000455b  jz      short loc_180004582
0x18000455d  mov     dword ptr [rax+8], 0
0x180004564  xorps   xmm0, xmm0
0x180004567  xor     eax, eax
0x180004569  movups  xmmword ptr [rbx+10h], xmm0
0x18000456d  movups  xmmword ptr [rbx+20h], xmm0
0x180004571  mov     [rbx+30h], rax
0x180004575  mov     [rbx+38h], al
0x180004578  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000457f  mov     [rbx], rax
0x180004582  mov     [rsp+58h+var_38], rbx
0x180004587  jmp     short loc_1800045A1
0x180004589  mov     rsi, [rsp+58h+arg_10]
0x18000458e  mov     r15, [rsp+58h+arg_8]
0x180004593  mov     r14, [rsp+58h+arg_0]
0x180004598  mov     edi, [rsp+58h+arg_18]
0x18000459c  mov     rbx, [rsp+58h+var_38]
0x1800045a1  test    rbx, rbx
0x1800045a4  jz      short loc_1800045E7
0x1800045a6  mov     [rbx+40h], r14
0x1800045aa  lea     rcx, [rbx+10h]; this
0x1800045ae  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800045b3  xor     ecx, ecx
0x1800045b5  test    eax, eax
0x1800045b7  cmovs   ecx, eax
0x1800045ba  xor     edi, edi
0x1800045bc  test    ecx, ecx
0x1800045be  cmovs   edi, ecx
0x1800045c1  test    edi, edi
0x1800045c3  jnz     short loc_1800045DF
0x1800045c5  mov     rax, [rbx]
0x1800045c8  mov     r8, rsi
0x1800045cb  mov     rdx, r15
0x1800045ce  mov     rcx, rbx
0x1800045d1  mov     rax, [rax]
0x1800045d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d9  mov     edi, eax
0x1800045db  test    eax, eax
0x1800045dd  jz      short loc_1800045E7
0x1800045df  mov     rcx, rbx
0x1800045e2  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x1800045e7  mov     eax, edi
0x1800045e9  add     rsp, 30h
0x1800045ed  pop     r15
0x1800045ef  pop     r14
0x1800045f1  pop     rdi
0x1800045f2  pop     rsi
0x1800045f3  pop     rbx
0x1800045f4  retn
```
