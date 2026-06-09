# ATL::CComObject<CWdsTransportContent>::CreateInstance(ATL::CComObject<CWdsTransportContent> * *)

- ea: `0x1800148c0`
- end: `0x1800149ee`
- name: `?CreateInstance@?$CComObject@VCWdsTransportContent@@@ATL@@SAJPEAPEAV12@@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800149f4`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180006654`
- `0x180006680`
- `0x1800148c0`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180014928`
- `KERNEL32!InitializeCriticalSection` at `0x180014928`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportContent>::CreateInstance(char **a1)
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
    v4 = (char *)operator new(0x98u);
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
      *((_QWORD *)v5 + 14) = 0;
      *((_DWORD *)v5 + 30) = 0;
      *((_QWORD *)v5 + 16) = 0;
      *((_QWORD *)v5 + 17) = 0;
      *((_QWORD *)v5 + 18) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportContent>::`vftable';
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
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 96LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x1800148c0  mov     [rsp+arg_18], rbx
0x1800148c5  mov     [rsp+arg_0], rcx
0x1800148ca  push    rdi
0x1800148cb  push    r14
0x1800148cd  push    r15
0x1800148cf  sub     rsp, 20h
0x1800148d3  mov     r15, rcx
0x1800148d6  test    rcx, rcx
0x1800148d9  jnz     short loc_1800148E5
0x1800148db  mov     eax, 80004003h
0x1800148e0  jmp     loc_1800149DE
0x1800148e5  and     qword ptr [rcx], 0
0x1800148e9  mov     r14d, 8007000Eh
0x1800148ef  mov     [rsp+38h+arg_8], r14d
0x1800148f4  and     [rsp+38h+arg_10], 0
0x1800148fa  mov     ecx, 98h; Size
0x1800148ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014904  mov     rdi, rax
0x180014907  test    rdi, rdi
0x18001490a  jz      short loc_180014977
0x18001490c  and     dword ptr [rax+8], 0
0x180014910  xorps   xmm0, xmm0
0x180014913  xor     eax, eax
0x180014915  movups  xmmword ptr [rdi+10h], xmm0
0x180014919  movups  xmmword ptr [rdi+20h], xmm0
0x18001491d  mov     [rdi+30h], rax
0x180014921  mov     [rdi+38h], al
0x180014924  lea     rcx, [rdi+40h]; lpCriticalSection
0x180014928  call    cs:__imp_InitializeCriticalSection
0x18001492f  nop     dword ptr [rax+rax+00h]
0x180014934  and     qword ptr [rdi+68h], 0
0x180014939  and     qword ptr [rdi+70h], 0
0x18001493e  and     dword ptr [rdi+78h], 0
0x180014942  and     qword ptr [rdi+80h], 0
0x18001494a  and     qword ptr [rdi+88h], 0
0x180014952  and     qword ptr [rdi+90h], 0
0x18001495a  lea     rax, ??_7?$CComObject@VCWdsTransportContent@@@ATL@@6B@; const ATL::CComObject<CWdsTransportContent>::`vftable'
0x180014961  mov     [rdi], rax
0x180014964  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001496b  mov     rax, [rcx]
0x18001496e  mov     rax, [rax+8]
0x180014972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014977  mov     [rsp+38h+arg_10], rdi
0x18001497c  jmp     short loc_18001498D
0x18001497e  mov     r15, [rsp+38h+arg_0]
0x180014983  mov     r14d, [rsp+38h+arg_8]
0x180014988  mov     rdi, [rsp+38h+arg_10]
0x18001498d  test    rdi, rdi
0x180014990  jz      short loc_1800149D8
0x180014992  lea     rcx, [rdi+8]; volatile int *
0x180014996  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18001499b  lea     rcx, [rdi+10h]; this
0x18001499f  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800149a4  xor     edx, edx
0x1800149a6  test    eax, eax
0x1800149a8  cmovs   edx, eax
0x1800149ab  xor     r14d, r14d
0x1800149ae  test    edx, edx
0x1800149b0  cmovs   r14d, edx
0x1800149b4  lea     rcx, [rdi+8]; volatile int *
0x1800149b8  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800149bd  test    r14d, r14d
0x1800149c0  jz      short loc_1800149D8
0x1800149c2  mov     rdx, [rdi]
0x1800149c5  mov     rax, [rdx+60h]
0x1800149c9  mov     edx, 1
0x1800149ce  mov     rcx, rdi
0x1800149d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149d6  xor     edi, edi
0x1800149d8  mov     [r15], rdi
0x1800149db  mov     eax, r14d
0x1800149de  mov     rbx, [rsp+38h+arg_18]
0x1800149e3  add     rsp, 20h
0x1800149e7  pop     r15
0x1800149e9  pop     r14
0x1800149eb  pop     rdi
0x1800149ec  retn
```
