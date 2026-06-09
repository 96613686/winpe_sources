# ATL::CComCreator<ATL::CComAggObject<CPXWizardTypeRegistration>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800040ac`
- end: `0x1800041c8`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003e50`

## callees

- `0x1800011dc`
- `0x1800040ac`
- `0x180004a90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CPXWizardTypeRegistration>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // edi
  char *v8; // rax
  char *v9; // rbx
  int v10; // eax
  int v11; // ecx
  int v12; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x58u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CPXWizardTypeRegistration>::`vftable';
    *(_OWORD *)(v8 + 40) = 0;
    *(_OWORD *)(v8 + 56) = 0;
    *((_QWORD *)v8 + 9) = 0;
    v8[80] = 0;
    *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CPXWizardTypeRegistration>::`vftable';
    *((_QWORD *)v8 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 40));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x1800040ac  mov     [rsp+arg_10], r8
0x1800040b1  mov     [rsp+arg_8], rdx
0x1800040b6  push    rbx
0x1800040b7  push    rsi
0x1800040b8  push    rdi
0x1800040b9  push    r14
0x1800040bb  push    r15
0x1800040bd  sub     rsp, 30h
0x1800040c1  mov     rsi, r8
0x1800040c4  mov     r14, rdx
0x1800040c7  mov     r15, rcx
0x1800040ca  test    r8, r8
0x1800040cd  jnz     short loc_1800040D9
0x1800040cf  mov     eax, 80004003h
0x1800040d4  jmp     loc_1800041BC
0x1800040d9  mov     qword ptr [r8], 0
0x1800040e0  mov     edi, 8007000Eh
0x1800040e5  mov     [rsp+58h+arg_18], edi
0x1800040e9  mov     [rsp+58h+var_38], 0
0x1800040f2  mov     ecx, 58h ; 'X'; Size
0x1800040f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800040fc  mov     rbx, rax
0x1800040ff  test    rbx, rbx
0x180004102  jz      short loc_18000414B
0x180004104  mov     dword ptr [rax+8], 0
0x18000410b  lea     rax, ??_7?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@6B@; const ATL::CComAggObject<CPXWizardTypeRegistration>::`vftable'
0x180004112  mov     [rbx], rax
0x180004115  xorps   xmm0, xmm0
0x180004118  xor     eax, eax
0x18000411a  movups  xmmword ptr [rbx+28h], xmm0
0x18000411e  movups  xmmword ptr [rbx+38h], xmm0
0x180004122  mov     [rbx+48h], rax
0x180004126  mov     [rbx+50h], al
0x180004129  lea     rax, ??_7?$CComContainedObject@VCPXWizardTypeRegistration@@@ATL@@6B@; const ATL::CComContainedObject<CPXWizardTypeRegistration>::`vftable'
0x180004130  mov     [rbx+18h], rax
0x180004134  mov     [rbx+20h], r15
0x180004138  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000413f  mov     rax, [rcx]
0x180004142  mov     rax, [rax+8]
0x180004146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414b  mov     [rsp+58h+var_38], rbx
0x180004150  jmp     short loc_180004165
0x180004152  mov     rsi, [rsp+58h+arg_10]
0x180004157  mov     r14, [rsp+58h+arg_8]
0x18000415c  mov     edi, [rsp+58h+arg_18]
0x180004160  mov     rbx, [rsp+58h+var_38]
0x180004165  test    rbx, rbx
0x180004168  jz      short loc_1800041BA
0x18000416a  lea     rcx, [rbx+28h]; this
0x18000416e  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180004173  xor     ecx, ecx
0x180004175  test    eax, eax
0x180004177  cmovs   ecx, eax
0x18000417a  xor     eax, eax
0x18000417c  test    ecx, ecx
0x18000417e  cmovs   eax, ecx
0x180004181  xor     edi, edi
0x180004183  test    eax, eax
0x180004185  cmovs   edi, eax
0x180004188  test    edi, edi
0x18000418a  jnz     short loc_1800041A6
0x18000418c  mov     rax, [rbx]
0x18000418f  mov     r8, rsi
0x180004192  mov     rdx, r14
0x180004195  mov     rcx, rbx
0x180004198  mov     rax, [rax]
0x18000419b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a0  mov     edi, eax
0x1800041a2  test    eax, eax
0x1800041a4  jz      short loc_1800041BA
0x1800041a6  mov     rdx, [rbx]
0x1800041a9  mov     rax, [rdx+18h]
0x1800041ad  mov     edx, 1
0x1800041b2  mov     rcx, rbx
0x1800041b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ba  mov     eax, edi
0x1800041bc  add     rsp, 30h
0x1800041c0  pop     r15
0x1800041c2  pop     r14
0x1800041c4  pop     rdi
0x1800041c5  pop     rsi
0x1800041c6  pop     rbx
0x1800041c7  retn
```
