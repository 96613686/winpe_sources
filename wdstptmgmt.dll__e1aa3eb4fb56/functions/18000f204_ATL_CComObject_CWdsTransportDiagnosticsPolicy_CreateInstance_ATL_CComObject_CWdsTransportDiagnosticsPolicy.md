# ATL::CComObject<CWdsTransportDiagnosticsPolicy>::CreateInstance(ATL::CComObject<CWdsTransportDiagnosticsPolicy> * *)

- ea: `0x18000f204`
- end: `0x18000f330`
- name: `?CreateInstance@?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@SAJPEAPEAV12@@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f338`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x18000f204`
- `0x180018310`
- `0x180018348`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000f273`
- `KERNEL32!InitializeCriticalSection` at `0x18000f273`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportDiagnosticsPolicy>::CreateInstance(struct _RTL_CRITICAL_SECTION **a1)
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
    v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x90u);
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
      v5->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CWdsTransportDiagnosticsPolicy>::`vftable';
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
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v5->DebugInfo[2].ProcessLocksList.Blink)(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000f204  mov     [rsp+arg_18], rbx
0x18000f209  mov     [rsp+arg_0], rcx
0x18000f20e  push    rdi
0x18000f20f  push    r14
0x18000f211  push    r15
0x18000f213  sub     rsp, 20h
0x18000f217  mov     r15, rcx
0x18000f21a  test    rcx, rcx
0x18000f21d  jnz     short loc_18000F229
0x18000f21f  mov     eax, 80004003h
0x18000f224  jmp     loc_18000F320
0x18000f229  and     qword ptr [rcx], 0
0x18000f22d  mov     r14d, 8007000Eh
0x18000f233  mov     [rsp+38h+arg_8], r14d
0x18000f238  and     [rsp+38h+arg_10], 0
0x18000f23e  mov     ecx, 90h; Size
0x18000f243  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f248  mov     rdi, rax
0x18000f24b  test    rdi, rdi
0x18000f24e  jz      short loc_18000F2B9
0x18000f250  and     dword ptr [rax+8], 0
0x18000f254  xorps   xmm0, xmm0
0x18000f257  xor     eax, eax
0x18000f259  movups  xmmword ptr [rdi+10h], xmm0
0x18000f25d  movups  xmmword ptr [rdi+20h], xmm0
0x18000f261  mov     [rdi+30h], rax
0x18000f265  mov     [rdi+38h], al
0x18000f268  and     [rdi+40h], rax
0x18000f26c  and     [rdi+48h], eax
0x18000f26f  lea     rcx, [rdi+50h]; lpCriticalSection
0x18000f273  call    cs:__imp_InitializeCriticalSection
0x18000f27a  nop     dword ptr [rax+rax+00h]
0x18000f27f  and     dword ptr [rdi+78h], 0
0x18000f283  and     dword ptr [rdi+7Ch], 0
0x18000f287  and     dword ptr [rdi+80h], 0
0x18000f28e  and     dword ptr [rdi+84h], 0
0x18000f295  and     dword ptr [rdi+88h], 0
0x18000f29c  lea     rax, ??_7?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@6B@; const ATL::CComObject<CWdsTransportDiagnosticsPolicy>::`vftable'
0x18000f2a3  mov     [rdi], rax
0x18000f2a6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f2ad  mov     rax, [rcx]
0x18000f2b0  mov     rax, [rax+8]
0x18000f2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b9  mov     [rsp+38h+arg_10], rdi
0x18000f2be  jmp     short loc_18000F2CF
0x18000f2c0  mov     r15, [rsp+38h+arg_0]
0x18000f2c5  mov     r14d, [rsp+38h+arg_8]
0x18000f2ca  mov     rdi, [rsp+38h+arg_10]
0x18000f2cf  test    rdi, rdi
0x18000f2d2  jz      short loc_18000F31A
0x18000f2d4  lea     rcx, [rdi+8]; this
0x18000f2d8  call    ?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalAddRef(void)
0x18000f2dd  lea     rcx, [rdi+10h]; this
0x18000f2e1  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000f2e6  xor     edx, edx
0x18000f2e8  test    eax, eax
0x18000f2ea  cmovs   edx, eax
0x18000f2ed  xor     r14d, r14d
0x18000f2f0  test    edx, edx
0x18000f2f2  cmovs   r14d, edx
0x18000f2f6  lea     rcx, [rdi+8]; this
0x18000f2fa  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x18000f2ff  test    r14d, r14d
0x18000f302  jz      short loc_18000F31A
0x18000f304  mov     rdx, [rdi]
0x18000f307  mov     rax, [rdx+78h]
0x18000f30b  mov     edx, 1
0x18000f310  mov     rcx, rdi
0x18000f313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f318  xor     edi, edi
0x18000f31a  mov     [r15], rdi
0x18000f31d  mov     eax, r14d
0x18000f320  mov     rbx, [rsp+38h+arg_18]
0x18000f325  add     rsp, 20h
0x18000f329  pop     r15
0x18000f32b  pop     r14
0x18000f32d  pop     rdi
0x18000f32e  retn
```
