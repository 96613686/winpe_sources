# ATL::CComObject<CWdsTransportMulticastSessionPolicy>::CreateInstance(ATL::CComObject<CWdsTransportMulticastSessionPolicy> * *)

- ea: `0x1800174c4`
- end: `0x180017601`
- name: `?CreateInstance@?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@SAJPEAPEAV12@@Z`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017608`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x1800174c4`
- `0x180018310`
- `0x180018348`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180017533`
- `KERNEL32!InitializeCriticalSection` at `0x180017533`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportMulticastSessionPolicy>::CreateInstance(
        struct _RTL_CRITICAL_SECTION **a1)
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
    v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x98u);
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
      LODWORD(v5[3].DebugInfo) = 0;
      HIDWORD(v5[3].DebugInfo) = 0;
      v5[3].LockCount = 0;
      v5[3].RecursionCount = 0;
      LODWORD(v5[3].OwningThread) = 0;
      HIDWORD(v5[3].OwningThread) = 0;
      LODWORD(v5[3].LockSemaphore) = 0;
      v5->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CWdsTransportMulticastSessionPolicy>::`vftable';
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
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v5->DebugInfo[3].CriticalSection)(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x1800174c4  mov     [rsp+arg_18], rbx
0x1800174c9  mov     [rsp+arg_0], rcx
0x1800174ce  push    rdi
0x1800174cf  push    r14
0x1800174d1  push    r15
0x1800174d3  sub     rsp, 20h
0x1800174d7  mov     r15, rcx
0x1800174da  test    rcx, rcx
0x1800174dd  jnz     short loc_1800174E9
0x1800174df  mov     eax, 80004003h
0x1800174e4  jmp     loc_1800175F1
0x1800174e9  and     qword ptr [rcx], 0
0x1800174ed  mov     r14d, 8007000Eh
0x1800174f3  mov     [rsp+38h+arg_8], r14d
0x1800174f8  and     [rsp+38h+arg_10], 0
0x1800174fe  mov     ecx, 98h; Size
0x180017503  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017508  mov     rdi, rax
0x18001750b  test    rdi, rdi
0x18001750e  jz      short loc_180017587
0x180017510  and     dword ptr [rax+8], 0
0x180017514  xorps   xmm0, xmm0
0x180017517  xor     eax, eax
0x180017519  movups  xmmword ptr [rdi+10h], xmm0
0x18001751d  movups  xmmword ptr [rdi+20h], xmm0
0x180017521  mov     [rdi+30h], rax
0x180017525  mov     [rdi+38h], al
0x180017528  and     [rdi+40h], rax
0x18001752c  and     [rdi+48h], eax
0x18001752f  lea     rcx, [rdi+50h]; lpCriticalSection
0x180017533  call    cs:__imp_InitializeCriticalSection
0x18001753a  nop     dword ptr [rax+rax+00h]
0x18001753f  and     dword ptr [rdi+78h], 0
0x180017543  and     dword ptr [rdi+7Ch], 0
0x180017547  and     dword ptr [rdi+80h], 0
0x18001754e  and     dword ptr [rdi+84h], 0
0x180017555  and     dword ptr [rdi+88h], 0
0x18001755c  and     dword ptr [rdi+8Ch], 0
0x180017563  and     dword ptr [rdi+90h], 0
0x18001756a  lea     rax, ??_7?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@6B@; const ATL::CComObject<CWdsTransportMulticastSessionPolicy>::`vftable'
0x180017571  mov     [rdi], rax
0x180017574  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001757b  mov     rax, [rcx]
0x18001757e  mov     rax, [rax+8]
0x180017582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017587  mov     [rsp+38h+arg_10], rdi
0x18001758c  jmp     short loc_18001759D
0x18001758e  mov     r15, [rsp+38h+arg_0]
0x180017593  mov     r14d, [rsp+38h+arg_8]
0x180017598  mov     rdi, [rsp+38h+arg_10]
0x18001759d  test    rdi, rdi
0x1800175a0  jz      short loc_1800175EB
0x1800175a2  lea     rcx, [rdi+8]; this
0x1800175a6  call    ?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalAddRef(void)
0x1800175ab  lea     rcx, [rdi+10h]; this
0x1800175af  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800175b4  xor     edx, edx
0x1800175b6  test    eax, eax
0x1800175b8  cmovs   edx, eax
0x1800175bb  xor     r14d, r14d
0x1800175be  test    edx, edx
0x1800175c0  cmovs   r14d, edx
0x1800175c4  lea     rcx, [rdi+8]; this
0x1800175c8  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x1800175cd  test    r14d, r14d
0x1800175d0  jz      short loc_1800175EB
0x1800175d2  mov     rdx, [rdi]
0x1800175d5  mov     rax, [rdx+98h]
0x1800175dc  mov     edx, 1
0x1800175e1  mov     rcx, rdi
0x1800175e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175e9  xor     edi, edi
0x1800175eb  mov     [r15], rdi
0x1800175ee  mov     eax, r14d
0x1800175f1  mov     rbx, [rsp+38h+arg_18]
0x1800175f6  add     rsp, 20h
0x1800175fa  pop     r15
0x1800175fc  pop     r14
0x1800175fe  pop     rdi
0x1800175ff  retn
```
