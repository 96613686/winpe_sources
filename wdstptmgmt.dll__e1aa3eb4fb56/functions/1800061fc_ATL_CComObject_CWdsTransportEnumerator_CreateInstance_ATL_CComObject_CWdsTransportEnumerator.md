# ATL::CComObject<CWdsTransportEnumerator>::CreateInstance(ATL::CComObject<CWdsTransportEnumerator> * *)

- ea: `0x1800061fc`
- end: `0x180006311`
- name: `?CreateInstance@?$CComObject@VCWdsTransportEnumerator@@@ATL@@SAJPEAPEAV12@@Z`
- size: `277`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006110`
- `0x180007a30`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x1800061fc`
- `0x180006654`
- `0x180006680`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006264`
- `KERNEL32!InitializeCriticalSection` at `0x180006264`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportEnumerator>::CreateInstance(char **a1)
{
  char **v1; // r15
  unsigned int v3; // r14d
  char *v4; // rax
  char *v5; // rdi
  int v6; // eax
  int v7; // edx
  char *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (char *)operator new(0x78u);
    v5 = v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 2) = 0;
      *((_OWORD *)v4 + 1) = 0;
      *((_OWORD *)v4 + 2) = 0;
      *((_QWORD *)v4 + 6) = 0;
      v4[56] = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 64));
      *((_QWORD *)v5 + 13) = 0;
      *((_DWORD *)v5 + 28) = 0;
      *((_DWORD *)v5 + 29) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportEnumerator>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v5 + 2);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v5 + 16));
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v5 + 2);
    if ( v3 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x1800061fc  mov     [rsp+arg_18], rbx
0x180006201  mov     [rsp+arg_0], rcx
0x180006206  push    rdi
0x180006207  push    r14
0x180006209  push    r15
0x18000620b  sub     rsp, 20h
0x18000620f  mov     r15, rcx
0x180006212  test    rcx, rcx
0x180006215  jnz     short loc_180006221
0x180006217  mov     eax, 80004003h
0x18000621c  jmp     loc_180006301
0x180006221  and     qword ptr [rcx], 0
0x180006225  mov     r14d, 8007000Eh
0x18000622b  mov     [rsp+38h+arg_8], r14d
0x180006230  and     [rsp+38h+arg_10], 0
0x180006236  mov     ecx, 78h ; 'x'; Size
0x18000623b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006240  mov     rdi, rax
0x180006243  test    rdi, rdi
0x180006246  jz      short loc_18000629A
0x180006248  and     dword ptr [rax+8], 0
0x18000624c  xorps   xmm0, xmm0
0x18000624f  xor     eax, eax
0x180006251  movups  xmmword ptr [rdi+10h], xmm0
0x180006255  movups  xmmword ptr [rdi+20h], xmm0
0x180006259  mov     [rdi+30h], rax
0x18000625d  mov     [rdi+38h], al
0x180006260  lea     rcx, [rdi+40h]; lpCriticalSection
0x180006264  call    cs:__imp_InitializeCriticalSection
0x18000626b  nop     dword ptr [rax+rax+00h]
0x180006270  and     qword ptr [rdi+68h], 0
0x180006275  and     dword ptr [rdi+70h], 0
0x180006279  and     dword ptr [rdi+74h], 0
0x18000627d  lea     rax, ??_7?$CComObject@VCWdsTransportEnumerator@@@ATL@@6B@; const ATL::CComObject<CWdsTransportEnumerator>::`vftable'
0x180006284  mov     [rdi], rax
0x180006287  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000628e  mov     rax, [rcx]
0x180006291  mov     rax, [rax+8]
0x180006295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000629a  mov     [rsp+38h+arg_10], rdi
0x18000629f  jmp     short loc_1800062B0
0x1800062a1  mov     r15, [rsp+38h+arg_0]
0x1800062a6  mov     r14d, [rsp+38h+arg_8]
0x1800062ab  mov     rdi, [rsp+38h+arg_10]
0x1800062b0  test    rdi, rdi
0x1800062b3  jz      short loc_1800062FB
0x1800062b5  lea     rcx, [rdi+8]; volatile int *
0x1800062b9  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800062be  lea     rcx, [rdi+10h]; this
0x1800062c2  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800062c7  xor     edx, edx
0x1800062c9  test    eax, eax
0x1800062cb  cmovs   edx, eax
0x1800062ce  xor     r14d, r14d
0x1800062d1  test    edx, edx
0x1800062d3  cmovs   r14d, edx
0x1800062d7  lea     rcx, [rdi+8]; volatile int *
0x1800062db  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800062e0  test    r14d, r14d
0x1800062e3  jz      short loc_1800062FB
0x1800062e5  mov     rdx, [rdi]
0x1800062e8  mov     rax, [rdx+38h]
0x1800062ec  mov     edx, 1
0x1800062f1  mov     rcx, rdi
0x1800062f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f9  xor     edi, edi
0x1800062fb  mov     [r15], rdi
0x1800062fe  mov     eax, r14d
0x180006301  mov     rbx, [rsp+38h+arg_18]
0x180006306  add     rsp, 20h
0x18000630a  pop     r15
0x18000630c  pop     r14
0x18000630e  pop     rdi
0x18000630f  retn
```
