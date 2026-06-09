# ATL::CComObject<CWdsTransportConfigurationManager>::CreateInstance(ATL::CComObject<CWdsTransportConfigurationManager> * *)

- ea: `0x18000b2d0`
- end: `0x18000b409`
- name: `?CreateInstance@?$CComObject@VCWdsTransportConfigurationManager@@@ATL@@SAJPEAPEAV12@@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b410`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x18000b2d0`
- `0x180018310`
- `0x180018348`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000b33f`
- `KERNEL32!InitializeCriticalSection` at `0x18000b33f`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportConfigurationManager>::CreateInstance(
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
    v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0xA0u);
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
      v5[3].OwningThread = 0;
      v5[3].LockSemaphore = 0;
      v5[3].SpinCount = 0;
      v5->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CWdsTransportConfigurationManager>::`vftable';
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
      (*(void (__fastcall **)(struct _RTL_CRITICAL_SECTION *, __int64))&v5->DebugInfo[2].Flags)(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000b2d0  mov     [rsp+arg_18], rbx
0x18000b2d5  mov     [rsp+arg_0], rcx
0x18000b2da  push    rdi
0x18000b2db  push    r14
0x18000b2dd  push    r15
0x18000b2df  sub     rsp, 20h
0x18000b2e3  mov     r15, rcx
0x18000b2e6  test    rcx, rcx
0x18000b2e9  jnz     short loc_18000B2F5
0x18000b2eb  mov     eax, 80004003h
0x18000b2f0  jmp     loc_18000B3F9
0x18000b2f5  and     qword ptr [rcx], 0
0x18000b2f9  mov     r14d, 8007000Eh
0x18000b2ff  mov     [rsp+38h+arg_8], r14d
0x18000b304  and     [rsp+38h+arg_10], 0
0x18000b30a  mov     ecx, 0A0h; Size
0x18000b30f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b314  mov     rdi, rax
0x18000b317  test    rdi, rdi
0x18000b31a  jz      short loc_18000B38F
0x18000b31c  and     dword ptr [rax+8], 0
0x18000b320  xorps   xmm0, xmm0
0x18000b323  xor     eax, eax
0x18000b325  movups  xmmword ptr [rdi+10h], xmm0
0x18000b329  movups  xmmword ptr [rdi+20h], xmm0
0x18000b32d  mov     [rdi+30h], rax
0x18000b331  mov     [rdi+38h], al
0x18000b334  and     [rdi+40h], rax
0x18000b338  and     [rdi+48h], eax
0x18000b33b  lea     rcx, [rdi+50h]; lpCriticalSection
0x18000b33f  call    cs:__imp_InitializeCriticalSection
0x18000b346  nop     dword ptr [rax+rax+00h]
0x18000b34b  and     dword ptr [rdi+78h], 0
0x18000b34f  and     dword ptr [rdi+7Ch], 0
0x18000b353  and     dword ptr [rdi+80h], 0
0x18000b35a  and     qword ptr [rdi+88h], 0
0x18000b362  and     qword ptr [rdi+90h], 0
0x18000b36a  and     qword ptr [rdi+98h], 0
0x18000b372  lea     rax, ??_7?$CComObject@VCWdsTransportConfigurationManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportConfigurationManager>::`vftable'
0x18000b379  mov     [rdi], rax
0x18000b37c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b383  mov     rax, [rcx]
0x18000b386  mov     rax, [rax+8]
0x18000b38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b38f  mov     [rsp+38h+arg_10], rdi
0x18000b394  jmp     short loc_18000B3A5
0x18000b396  mov     r15, [rsp+38h+arg_0]
0x18000b39b  mov     r14d, [rsp+38h+arg_8]
0x18000b3a0  mov     rdi, [rsp+38h+arg_10]
0x18000b3a5  test    rdi, rdi
0x18000b3a8  jz      short loc_18000B3F3
0x18000b3aa  lea     rcx, [rdi+8]; this
0x18000b3ae  call    ?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalAddRef(void)
0x18000b3b3  lea     rcx, [rdi+10h]; this
0x18000b3b7  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000b3bc  xor     edx, edx
0x18000b3be  test    eax, eax
0x18000b3c0  cmovs   edx, eax
0x18000b3c3  xor     r14d, r14d
0x18000b3c6  test    edx, edx
0x18000b3c8  cmovs   r14d, edx
0x18000b3cc  lea     rcx, [rdi+8]; this
0x18000b3d0  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x18000b3d5  test    r14d, r14d
0x18000b3d8  jz      short loc_18000B3F3
0x18000b3da  mov     rdx, [rdi]
0x18000b3dd  mov     rax, [rdx+88h]
0x18000b3e4  mov     edx, 1
0x18000b3e9  mov     rcx, rdi
0x18000b3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3f1  xor     edi, edi
0x18000b3f3  mov     [r15], rdi
0x18000b3f6  mov     eax, r14d
0x18000b3f9  mov     rbx, [rsp+38h+arg_18]
0x18000b3fe  add     rsp, 20h
0x18000b402  pop     r15
0x18000b404  pop     r14
0x18000b406  pop     rdi
0x18000b407  retn
```
