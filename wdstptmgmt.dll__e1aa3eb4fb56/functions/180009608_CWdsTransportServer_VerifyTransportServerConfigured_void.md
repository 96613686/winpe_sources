# CWdsTransportServer::VerifyTransportServerConfigured(void)

- ea: `0x180009608`
- end: `0x18000970e`
- name: `?VerifyTransportServerConfigured@CWdsTransportServer@@QEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(CWdsTransportServer *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b514`
- `0x18001028c`
- `0x180019974`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009608`
- `0x180009af8`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009645`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800096e9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009645`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800096e9`

## string_xrefs

- `0x180009632`: `-> CWdsTransportServer::VerifyTransportServerConfigured(0x%p)`
- `0x1800096d6`: `<- CWdsTransportServer::VerifyTransportServerConfigured(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportServer::VerifyTransportServerConfigured(CWdsTransportServer *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-28h]
  _BYTE v9[24]; // [rsp+30h] [rbp-18h] BYREF
  int v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v9, (char *)this + 72);
  v11 = 0;
  v10 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportServer::VerifyTransportServerConfigured(0x%p)",
    this);
  v2 = (*(unsigned int (__fastcall **)(CWdsTransportServer *, __int64 *))(*(_QWORD *)this + 64LL))(this, &v11);
  if ( (int)ElValidateHr_1(v2, v3, v4, 359) >= 0 )
  {
    v2 = (*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 64LL))(v11, &v10);
    if ( (int)ElValidateHr_1(v2, v5, v6, 367) >= 0 )
      LODWORD(v2) = (v10 & 2) == 0 ? 0xC1100106 : 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  v8 = v2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServer::VerifyTransportServerConfigured(0x%p) =%x",
    this,
    v8);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180009608  mov     [rsp+arg_10], rbx
0x18000960d  push    rdi
0x18000960e  sub     rsp, 40h
0x180009612  mov     rdi, rcx
0x180009615  lea     rdx, [rcx+48h]
0x180009619  lea     rcx, [rsp+48h+var_18]
0x18000961e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180009623  nop
0x180009624  and     [rsp+48h+arg_8], 0
0x18000962a  and     [rsp+48h+arg_0], 0
0x18000962f  mov     r9, rdi
0x180009632  lea     r8, aCwdstransports_24; "-> CWdsTransportServer::VerifyTransport"...
0x180009639  mov     edx, 10000h
0x18000963e  lea     rcx, qword_18003B770
0x180009645  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000964c  nop     dword ptr [rax+rax+00h]
0x180009651  mov     rax, [rdi]
0x180009654  lea     rdx, [rsp+48h+arg_8]
0x180009659  mov     rcx, rdi
0x18000965c  mov     rax, [rax+40h]
0x180009660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009665  mov     ebx, eax
0x180009667  mov     r9d, 167h
0x18000966d  mov     ecx, eax
0x18000966f  call    ElValidateHr_1
0x180009674  test    eax, eax
0x180009676  js      short loc_1800096B3
0x180009678  mov     rcx, [rsp+48h+arg_8]
0x18000967d  mov     rax, [rcx]
0x180009680  lea     rdx, [rsp+48h+arg_0]
0x180009685  mov     rax, [rax+40h]
0x180009689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000968e  mov     ebx, eax
0x180009690  mov     r9d, 16Fh
0x180009696  mov     ecx, eax
0x180009698  call    ElValidateHr_1
0x18000969d  test    eax, eax
0x18000969f  js      short loc_1800096B3
0x1800096a1  mov     eax, [rsp+48h+arg_0]
0x1800096a5  and     al, 2
0x1800096a7  neg     al
0x1800096a9  sbb     ebx, ebx
0x1800096ab  not     ebx
0x1800096ad  and     ebx, 0C1100106h
0x1800096b3  mov     rcx, [rsp+48h+arg_8]
0x1800096b8  test    rcx, rcx
0x1800096bb  jz      short loc_1800096CF
0x1800096bd  mov     rax, [rcx]
0x1800096c0  mov     rax, [rax+10h]
0x1800096c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c9  and     [rsp+48h+arg_8], 0
0x1800096cf  mov     [rsp+48h+var_28], ebx
0x1800096d3  mov     r9, rdi
0x1800096d6  lea     r8, aCwdstransports_26; "<- CWdsTransportServer::VerifyTransport"...
0x1800096dd  mov     edx, 10000h
0x1800096e2  lea     rcx, qword_18003B770
0x1800096e9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800096f0  nop     dword ptr [rax+rax+00h]
0x1800096f5  nop
0x1800096f6  lea     rcx, [rsp+48h+var_18]
0x1800096fb  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180009700  mov     eax, ebx
0x180009702  mov     rbx, [rsp+48h+arg_10]
0x180009707  add     rsp, 40h
0x18000970b  pop     rdi
0x18000970c  retn
```
