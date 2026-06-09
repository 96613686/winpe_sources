# ATL::CComObject<CWdsTransportNamespaceManager>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceManager> * *)

- ea: `0x18000ff30`
- end: `0x180010052`
- name: `?CreateInstance@?$CComObject@VCWdsTransportNamespaceManager@@@ATL@@SAJPEAPEAV12@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010058`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x18000ff30`
- `0x180018310`
- `0x180018348`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000ff9f`
- `KERNEL32!InitializeCriticalSection` at `0x18000ff9f`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportNamespaceManager>::CreateInstance(struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v1; // r15
  unsigned int v3; // r14d
  struct _RTL_CRITICAL_SECTION *v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int v6; // eax
  int v7; // edx
  struct _RTL_CRITICAL_SECTION *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x88u);
    v5 = v4;
    if ( v4 )
    {
      v4->LockCount = 0;
      *(_OWORD *)&v4->OwningThread = 0;
      *(_OWORD *)&v4->SpinCount = 0;
      *(_QWORD *)&v4[1].LockCount = 0;
      LOBYTE(v4[1].OwningThread) = 0;
      v4[1].LockSemaphore = 0;
      LODWORD(v4[1].SpinCount) = 0;
      InitializeCriticalSection(v4 + 2);
      v5[3].DebugInfo = 0;
      v5[3].LockCount = 0;
      v5[3].RecursionCount = 0;
      v5->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CWdsTransportNamespaceManager>::`vftable';
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
    CWdsTransportServerComObjectRoot::InternalAddRef((CWdsTransportServerComObjectRoot *)&v5->LockCount);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)&v5->OwningThread);
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServerComObjectRoot *)&v5->LockCount);
    if ( v3 )
    {
      (*(void (__fastcall **)(struct _RTL_CRITICAL_SECTION *, __int64))&v5->DebugInfo[1].EntryCount)(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000ff30  mov     [rsp+arg_18], rbx
0x18000ff35  mov     [rsp+arg_0], rcx
0x18000ff3a  push    rdi
0x18000ff3b  push    r14
0x18000ff3d  push    r15
0x18000ff3f  sub     rsp, 20h
0x18000ff43  mov     r15, rcx
0x18000ff46  test    rcx, rcx
0x18000ff49  jnz     short loc_18000FF55
0x18000ff4b  mov     eax, 80004003h
0x18000ff50  jmp     loc_180010042
0x18000ff55  and     qword ptr [rcx], 0
0x18000ff59  mov     r14d, 8007000Eh
0x18000ff5f  mov     [rsp+38h+arg_8], r14d
0x18000ff64  and     [rsp+38h+arg_10], 0
0x18000ff6a  mov     ecx, 88h; Size
0x18000ff6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ff74  mov     rdi, rax
0x18000ff77  test    rdi, rdi
0x18000ff7a  jz      short loc_18000FFDB
0x18000ff7c  and     dword ptr [rax+8], 0
0x18000ff80  xorps   xmm0, xmm0
0x18000ff83  xor     eax, eax
0x18000ff85  movups  xmmword ptr [rdi+10h], xmm0
0x18000ff89  movups  xmmword ptr [rdi+20h], xmm0
0x18000ff8d  mov     [rdi+30h], rax
0x18000ff91  mov     [rdi+38h], al
0x18000ff94  and     [rdi+40h], rax
0x18000ff98  and     [rdi+48h], eax
0x18000ff9b  lea     rcx, [rdi+50h]; lpCriticalSection
0x18000ff9f  call    cs:__imp_InitializeCriticalSection
0x18000ffa6  nop     dword ptr [rax+rax+00h]
0x18000ffab  and     qword ptr [rdi+78h], 0
0x18000ffb0  and     dword ptr [rdi+80h], 0
0x18000ffb7  and     dword ptr [rdi+84h], 0
0x18000ffbe  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportNamespaceManager>::`vftable'
0x18000ffc5  mov     [rdi], rax
0x18000ffc8  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ffcf  mov     rax, [rcx]
0x18000ffd2  mov     rax, [rax+8]
0x18000ffd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffdb  mov     [rsp+38h+arg_10], rdi
0x18000ffe0  jmp     short loc_18000FFF1
0x18000ffe2  mov     r15, [rsp+38h+arg_0]
0x18000ffe7  mov     r14d, [rsp+38h+arg_8]
0x18000ffec  mov     rdi, [rsp+38h+arg_10]
0x18000fff1  test    rdi, rdi
0x18000fff4  jz      short loc_18001003C
0x18000fff6  lea     rcx, [rdi+8]; this
0x18000fffa  call    ?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalAddRef(void)
0x18000ffff  lea     rcx, [rdi+10h]; this
0x180010003  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180010008  xor     edx, edx
0x18001000a  test    eax, eax
0x18001000c  cmovs   edx, eax
0x18001000f  xor     r14d, r14d
0x180010012  test    edx, edx
0x180010014  cmovs   r14d, edx
0x180010018  lea     rcx, [rdi+8]; this
0x18001001c  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x180010021  test    r14d, r14d
0x180010024  jz      short loc_18001003C
0x180010026  mov     rdx, [rdi]
0x180010029  mov     rax, [rdx+50h]
0x18001002d  mov     edx, 1
0x180010032  mov     rcx, rdi
0x180010035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001003a  xor     edi, edi
0x18001003c  mov     [r15], rdi
0x18001003f  mov     eax, r14d
0x180010042  mov     rbx, [rsp+38h+arg_18]
0x180010047  add     rsp, 20h
0x18001004b  pop     r15
0x18001004d  pop     r14
0x18001004f  pop     rdi
0x180010050  retn
```
