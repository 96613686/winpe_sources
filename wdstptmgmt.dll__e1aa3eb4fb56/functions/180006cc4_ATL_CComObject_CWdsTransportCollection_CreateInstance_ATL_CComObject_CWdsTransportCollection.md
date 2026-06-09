# ATL::CComObject<CWdsTransportCollection>::CreateInstance(ATL::CComObject<CWdsTransportCollection> * *)

- ea: `0x180006cc4`
- end: `0x180006dd9`
- name: `?CreateInstance@?$CComObject@VCWdsTransportCollection@@@ATL@@SAJPEAPEAV12@@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006de0`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180006654`
- `0x180006680`
- `0x180006cc4`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006d2c`
- `KERNEL32!InitializeCriticalSection` at `0x180006d2c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportCollection>::CreateInstance(char **a1)
{
  unsigned int v3; // r14d
  char *v4; // rax
  char *v5; // rdi
  int v6; // eax
  int v7; // edx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  v4 = (char *)operator new(0x90u);
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
    *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportCollection>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 80LL))(v5, 1);
      v5 = 0;
    }
  }
  *a1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180006cc4  mov     [rsp+arg_18], rbx
0x180006cc9  mov     [rsp+arg_0], rcx
0x180006cce  push    rdi
0x180006ccf  push    r14
0x180006cd1  push    r15
0x180006cd3  sub     rsp, 20h
0x180006cd7  mov     r15, rcx
0x180006cda  test    rcx, rcx
0x180006cdd  jnz     short loc_180006CE9
0x180006cdf  mov     eax, 80004003h
0x180006ce4  jmp     loc_180006DC9
0x180006ce9  and     qword ptr [rcx], 0
0x180006ced  mov     r14d, 8007000Eh
0x180006cf3  mov     [rsp+38h+arg_8], r14d
0x180006cf8  and     [rsp+38h+arg_10], 0
0x180006cfe  mov     ecx, 90h; Size
0x180006d03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d08  mov     rdi, rax
0x180006d0b  test    rdi, rdi
0x180006d0e  jz      short loc_180006D62
0x180006d10  and     dword ptr [rax+8], 0
0x180006d14  xorps   xmm0, xmm0
0x180006d17  xor     eax, eax
0x180006d19  movups  xmmword ptr [rdi+10h], xmm0
0x180006d1d  movups  xmmword ptr [rdi+20h], xmm0
0x180006d21  mov     [rdi+30h], rax
0x180006d25  mov     [rdi+38h], al
0x180006d28  lea     rcx, [rdi+40h]; lpCriticalSection
0x180006d2c  call    cs:__imp_InitializeCriticalSection
0x180006d33  nop     dword ptr [rax+rax+00h]
0x180006d38  and     qword ptr [rdi+68h], 0
0x180006d3d  and     dword ptr [rdi+70h], 0
0x180006d41  and     dword ptr [rdi+74h], 0
0x180006d45  lea     rax, ??_7?$CComObject@VCWdsTransportCollection@@@ATL@@6B@; const ATL::CComObject<CWdsTransportCollection>::`vftable'
0x180006d4c  mov     [rdi], rax
0x180006d4f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006d56  mov     rax, [rcx]
0x180006d59  mov     rax, [rax+8]
0x180006d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d62  mov     [rsp+38h+arg_10], rdi
0x180006d67  jmp     short loc_180006D78
0x180006d69  mov     r15, [rsp+38h+arg_0]
0x180006d6e  mov     r14d, [rsp+38h+arg_8]
0x180006d73  mov     rdi, [rsp+38h+arg_10]
0x180006d78  test    rdi, rdi
0x180006d7b  jz      short loc_180006DC3
0x180006d7d  lea     rcx, [rdi+8]; volatile int *
0x180006d81  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180006d86  lea     rcx, [rdi+10h]; this
0x180006d8a  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006d8f  xor     edx, edx
0x180006d91  test    eax, eax
0x180006d93  cmovs   edx, eax
0x180006d96  xor     r14d, r14d
0x180006d99  test    edx, edx
0x180006d9b  cmovs   r14d, edx
0x180006d9f  lea     rcx, [rdi+8]; volatile int *
0x180006da3  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180006da8  test    r14d, r14d
0x180006dab  jz      short loc_180006DC3
0x180006dad  mov     rdx, [rdi]
0x180006db0  mov     rax, [rdx+50h]
0x180006db4  mov     edx, 1
0x180006db9  mov     rcx, rdi
0x180006dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc1  xor     edi, edi
0x180006dc3  mov     [r15], rdi
0x180006dc6  mov     eax, r14d
0x180006dc9  mov     rbx, [rsp+38h+arg_18]
0x180006dce  add     rsp, 20h
0x180006dd2  pop     r15
0x180006dd4  pop     r14
0x180006dd6  pop     rdi
0x180006dd7  retn
```
