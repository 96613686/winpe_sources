# ATL::CComObject<CWdsTransportSetupManager>::CreateInstance(ATL::CComObject<CWdsTransportSetupManager> * *)

- ea: `0x180009e50`
- end: `0x180009f83`
- name: `?CreateInstance@?$CComObject@VCWdsTransportSetupManager@@@ATL@@SAJPEAPEAV12@@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009f8c`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180009e50`
- `0x180018310`
- `0x180018348`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180009ebf`
- `KERNEL32!InitializeCriticalSection` at `0x180009ebf`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportSetupManager>::CreateInstance(struct _RTL_CRITICAL_SECTION **a1)
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
      HIDWORD(v5[3].DebugInfo) = 0;
      v5[3].LockCount = 0;
      v5[3].RecursionCount = 0;
      LODWORD(v5[3].OwningThread) = 0;
      HIDWORD(v5[3].OwningThread) = 0;
      LODWORD(v5[3].DebugInfo) = 0;
      v5->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CWdsTransportSetupManager>::`vftable';
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
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v5->DebugInfo[2].ProcessLocksList.Flink)(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180009e50  mov     [rsp+arg_18], rbx
0x180009e55  mov     [rsp+arg_0], rcx
0x180009e5a  push    rdi
0x180009e5b  push    r14
0x180009e5d  push    r15
0x180009e5f  sub     rsp, 20h
0x180009e63  mov     r15, rcx
0x180009e66  test    rcx, rcx
0x180009e69  jnz     short loc_180009E75
0x180009e6b  mov     eax, 80004003h
0x180009e70  jmp     loc_180009F73
0x180009e75  and     qword ptr [rcx], 0
0x180009e79  mov     r14d, 8007000Eh
0x180009e7f  mov     [rsp+38h+arg_8], r14d
0x180009e84  and     [rsp+38h+arg_10], 0
0x180009e8a  mov     ecx, 90h; Size
0x180009e8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e94  mov     rdi, rax
0x180009e97  test    rdi, rdi
0x180009e9a  jz      short loc_180009F0C
0x180009e9c  and     dword ptr [rax+8], 0
0x180009ea0  xorps   xmm0, xmm0
0x180009ea3  xor     eax, eax
0x180009ea5  movups  xmmword ptr [rdi+10h], xmm0
0x180009ea9  movups  xmmword ptr [rdi+20h], xmm0
0x180009ead  mov     [rdi+30h], rax
0x180009eb1  mov     [rdi+38h], al
0x180009eb4  and     [rdi+40h], rax
0x180009eb8  and     [rdi+48h], eax
0x180009ebb  lea     rcx, [rdi+50h]; lpCriticalSection
0x180009ebf  call    cs:__imp_InitializeCriticalSection
0x180009ec6  nop     dword ptr [rax+rax+00h]
0x180009ecb  and     dword ptr [rdi+7Ch], 0
0x180009ecf  and     dword ptr [rdi+80h], 0
0x180009ed6  and     dword ptr [rdi+84h], 0
0x180009edd  and     dword ptr [rdi+88h], 0
0x180009ee4  and     dword ptr [rdi+8Ch], 0
0x180009eeb  and     dword ptr [rdi+78h], 0
0x180009eef  lea     rax, ??_7?$CComObject@VCWdsTransportSetupManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportSetupManager>::`vftable'
0x180009ef6  mov     [rdi], rax
0x180009ef9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009f00  mov     rax, [rcx]
0x180009f03  mov     rax, [rax+8]
0x180009f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f0c  mov     [rsp+38h+arg_10], rdi
0x180009f11  jmp     short loc_180009F22
0x180009f13  mov     r15, [rsp+38h+arg_0]
0x180009f18  mov     r14d, [rsp+38h+arg_8]
0x180009f1d  mov     rdi, [rsp+38h+arg_10]
0x180009f22  test    rdi, rdi
0x180009f25  jz      short loc_180009F6D
0x180009f27  lea     rcx, [rdi+8]; this
0x180009f2b  call    ?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalAddRef(void)
0x180009f30  lea     rcx, [rdi+10h]; this
0x180009f34  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009f39  xor     edx, edx
0x180009f3b  test    eax, eax
0x180009f3d  cmovs   edx, eax
0x180009f40  xor     r14d, r14d
0x180009f43  test    edx, edx
0x180009f45  cmovs   r14d, edx
0x180009f49  lea     rcx, [rdi+8]; this
0x180009f4d  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x180009f52  test    r14d, r14d
0x180009f55  jz      short loc_180009F6D
0x180009f57  mov     rdx, [rdi]
0x180009f5a  mov     rax, [rdx+70h]
0x180009f5e  mov     edx, 1
0x180009f63  mov     rcx, rdi
0x180009f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f6b  xor     edi, edi
0x180009f6d  mov     [r15], rdi
0x180009f70  mov     eax, r14d
0x180009f73  mov     rbx, [rsp+38h+arg_18]
0x180009f78  add     rsp, 20h
0x180009f7c  pop     r15
0x180009f7e  pop     r14
0x180009f80  pop     rdi
0x180009f81  retn
```
