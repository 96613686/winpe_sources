# ATL::CComObject<CWdsTransportContentProvider>::CreateInstance(ATL::CComObject<CWdsTransportContentProvider> * *)

- ea: `0x180018410`
- end: `0x18001852f`
- name: `?CreateInstance@?$CComObject@VCWdsTransportContentProvider@@@ATL@@SAJPEAPEAV12@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018538`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180006654`
- `0x180006680`
- `0x180018410`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180018478`
- `KERNEL32!InitializeCriticalSection` at `0x180018478`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportContentProvider>::CreateInstance(char **a1)
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
    v4 = (char *)operator new(0x88u);
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
      *((_QWORD *)v5 + 15) = 0;
      *((_QWORD *)v5 + 16) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportContentProvider>::`vftable';
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
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 88LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180018410  mov     [rsp+arg_18], rbx
0x180018415  mov     [rsp+arg_0], rcx
0x18001841a  push    rdi
0x18001841b  push    r14
0x18001841d  push    r15
0x18001841f  sub     rsp, 20h
0x180018423  mov     r15, rcx
0x180018426  test    rcx, rcx
0x180018429  jnz     short loc_180018435
0x18001842b  mov     eax, 80004003h
0x180018430  jmp     loc_18001851F
0x180018435  and     qword ptr [rcx], 0
0x180018439  mov     r14d, 8007000Eh
0x18001843f  mov     [rsp+38h+arg_8], r14d
0x180018444  and     [rsp+38h+arg_10], 0
0x18001844a  mov     ecx, 88h; Size
0x18001844f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018454  mov     rdi, rax
0x180018457  test    rdi, rdi
0x18001845a  jz      short loc_1800184B8
0x18001845c  and     dword ptr [rax+8], 0
0x180018460  xorps   xmm0, xmm0
0x180018463  xor     eax, eax
0x180018465  movups  xmmword ptr [rdi+10h], xmm0
0x180018469  movups  xmmword ptr [rdi+20h], xmm0
0x18001846d  mov     [rdi+30h], rax
0x180018471  mov     [rdi+38h], al
0x180018474  lea     rcx, [rdi+40h]; lpCriticalSection
0x180018478  call    cs:__imp_InitializeCriticalSection
0x18001847f  nop     dword ptr [rax+rax+00h]
0x180018484  and     qword ptr [rdi+68h], 0
0x180018489  and     qword ptr [rdi+70h], 0
0x18001848e  and     qword ptr [rdi+78h], 0
0x180018493  and     qword ptr [rdi+80h], 0
0x18001849b  lea     rax, ??_7?$CComObject@VCWdsTransportContentProvider@@@ATL@@6B@; const ATL::CComObject<CWdsTransportContentProvider>::`vftable'
0x1800184a2  mov     [rdi], rax
0x1800184a5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800184ac  mov     rax, [rcx]
0x1800184af  mov     rax, [rax+8]
0x1800184b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184b8  mov     [rsp+38h+arg_10], rdi
0x1800184bd  jmp     short loc_1800184CE
0x1800184bf  mov     r15, [rsp+38h+arg_0]
0x1800184c4  mov     r14d, [rsp+38h+arg_8]
0x1800184c9  mov     rdi, [rsp+38h+arg_10]
0x1800184ce  test    rdi, rdi
0x1800184d1  jz      short loc_180018519
0x1800184d3  lea     rcx, [rdi+8]; volatile int *
0x1800184d7  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800184dc  lea     rcx, [rdi+10h]; this
0x1800184e0  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800184e5  xor     edx, edx
0x1800184e7  test    eax, eax
0x1800184e9  cmovs   edx, eax
0x1800184ec  xor     r14d, r14d
0x1800184ef  test    edx, edx
0x1800184f1  cmovs   r14d, edx
0x1800184f5  lea     rcx, [rdi+8]; volatile int *
0x1800184f9  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800184fe  test    r14d, r14d
0x180018501  jz      short loc_180018519
0x180018503  mov     rdx, [rdi]
0x180018506  mov     rax, [rdx+58h]
0x18001850a  mov     edx, 1
0x18001850f  mov     rcx, rdi
0x180018512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018517  xor     edi, edi
0x180018519  mov     [r15], rdi
0x18001851c  mov     eax, r14d
0x18001851f  mov     rbx, [rsp+38h+arg_18]
0x180018524  add     rsp, 20h
0x180018528  pop     r15
0x18001852a  pop     r14
0x18001852c  pop     rdi
0x18001852d  retn
```
