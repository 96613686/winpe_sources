# ATL::CComObject<CWdsTransportTftpClient>::CreateInstance(ATL::CComObject<CWdsTransportTftpClient> * *)

- ea: `0x180018db0`
- end: `0x180018ec1`
- name: `?CreateInstance@?$CComObject@VCWdsTransportTftpClient@@@ATL@@SAJPEAPEAV12@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018ec8`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180006654`
- `0x180006680`
- `0x180018db0`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180018e18`
- `KERNEL32!InitializeCriticalSection` at `0x180018e18`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportTftpClient>::CreateInstance(char **a1)
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
    v4 = (char *)operator new(0xA8u);
    v5 = v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 2) = 0;
      *((_OWORD *)v4 + 1) = 0;
      *((_OWORD *)v4 + 2) = 0;
      *((_QWORD *)v4 + 6) = 0;
      v4[56] = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 64));
      *((_DWORD *)v5 + 26) = 0;
      *((_QWORD *)v5 + 14) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportTftpClient>::`vftable';
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
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 112LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180018db0  mov     [rsp+arg_18], rbx
0x180018db5  mov     [rsp+arg_0], rcx
0x180018dba  push    rdi
0x180018dbb  push    r14
0x180018dbd  push    r15
0x180018dbf  sub     rsp, 20h
0x180018dc3  mov     r15, rcx
0x180018dc6  test    rcx, rcx
0x180018dc9  jnz     short loc_180018DD5
0x180018dcb  mov     eax, 80004003h
0x180018dd0  jmp     loc_180018EB1
0x180018dd5  and     qword ptr [rcx], 0
0x180018dd9  mov     r14d, 8007000Eh
0x180018ddf  mov     [rsp+38h+arg_8], r14d
0x180018de4  and     [rsp+38h+arg_10], 0
0x180018dea  mov     ecx, 0A8h; Size
0x180018def  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018df4  mov     rdi, rax
0x180018df7  test    rdi, rdi
0x180018dfa  jz      short loc_180018E4A
0x180018dfc  and     dword ptr [rax+8], 0
0x180018e00  xorps   xmm0, xmm0
0x180018e03  xor     eax, eax
0x180018e05  movups  xmmword ptr [rdi+10h], xmm0
0x180018e09  movups  xmmword ptr [rdi+20h], xmm0
0x180018e0d  mov     [rdi+30h], rax
0x180018e11  mov     [rdi+38h], al
0x180018e14  lea     rcx, [rdi+40h]; lpCriticalSection
0x180018e18  call    cs:__imp_InitializeCriticalSection
0x180018e1f  nop     dword ptr [rax+rax+00h]
0x180018e24  and     dword ptr [rdi+68h], 0
0x180018e28  and     qword ptr [rdi+70h], 0
0x180018e2d  lea     rax, ??_7?$CComObject@VCWdsTransportTftpClient@@@ATL@@6B@; const ATL::CComObject<CWdsTransportTftpClient>::`vftable'
0x180018e34  mov     [rdi], rax
0x180018e37  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180018e3e  mov     rax, [rcx]
0x180018e41  mov     rax, [rax+8]
0x180018e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e4a  mov     [rsp+38h+arg_10], rdi
0x180018e4f  jmp     short loc_180018E60
0x180018e51  mov     r15, [rsp+38h+arg_0]
0x180018e56  mov     r14d, [rsp+38h+arg_8]
0x180018e5b  mov     rdi, [rsp+38h+arg_10]
0x180018e60  test    rdi, rdi
0x180018e63  jz      short loc_180018EAB
0x180018e65  lea     rcx, [rdi+8]; volatile int *
0x180018e69  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180018e6e  lea     rcx, [rdi+10h]; this
0x180018e72  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180018e77  xor     edx, edx
0x180018e79  test    eax, eax
0x180018e7b  cmovs   edx, eax
0x180018e7e  xor     r14d, r14d
0x180018e81  test    edx, edx
0x180018e83  cmovs   r14d, edx
0x180018e87  lea     rcx, [rdi+8]; volatile int *
0x180018e8b  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180018e90  test    r14d, r14d
0x180018e93  jz      short loc_180018EAB
0x180018e95  mov     rdx, [rdi]
0x180018e98  mov     rax, [rdx+70h]
0x180018e9c  mov     edx, 1
0x180018ea1  mov     rcx, rdi
0x180018ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ea9  xor     edi, edi
0x180018eab  mov     [r15], rdi
0x180018eae  mov     eax, r14d
0x180018eb1  mov     rbx, [rsp+38h+arg_18]
0x180018eb6  add     rsp, 20h
0x180018eba  pop     r15
0x180018ebc  pop     r14
0x180018ebe  pop     rdi
0x180018ebf  retn
```
