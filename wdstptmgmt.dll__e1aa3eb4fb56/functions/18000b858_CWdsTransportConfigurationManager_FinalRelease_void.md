# CWdsTransportConfigurationManager::FinalRelease(void)

- ea: `0x18000b858`
- end: `0x18000b95c`
- name: `?FinalRelease@CWdsTransportConfigurationManager@@QEAAXXZ`
- size: `260`
- prototype: `void __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b23c`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000b858`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b886`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b93e`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b886`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b93e`

## string_xrefs

- `0x18000b873`: `-> CWdsTransportConfigurationManager::FinalRelease(0x%p)`
- `0x18000b92b`: `<- CWdsTransportConfigurationManager::FinalRelease(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWdsTransportConfigurationManager::FinalRelease(CWdsTransportConfigurationManager *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportConfigurationManager::FinalRelease(0x%p)", this);
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
    *(_DWORD *)(v2 + 72) = 0;
  v3 = *((_QWORD *)this + 18);
  if ( v3 )
    *(_DWORD *)(v3 + 72) = 0;
  v4 = *((_QWORD *)this + 19);
  if ( v4 )
    *(_DWORD *)(v4 + 72) = 0;
  v5 = *((_QWORD *)this + 17);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 17) = 0;
  }
  v6 = *((_QWORD *)this + 18);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 18) = 0;
  }
  v7 = *((_QWORD *)this + 19);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 19) = 0;
  }
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::FinalRelease(0x%p) =%x",
    this,
    0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
}

```

## disassembly

```asm
0x18000b858  push    rbx
0x18000b85a  sub     rsp, 40h
0x18000b85e  mov     rbx, rcx
0x18000b861  lea     rdx, [rcx+50h]
0x18000b865  lea     rcx, [rsp+48h+var_18]
0x18000b86a  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000b86f  nop
0x18000b870  mov     r9, rbx
0x18000b873  lea     r8, aCwdstransportc_46; "-> CWdsTransportConfigurationManager::F"...
0x18000b87a  mov     edx, 10000h
0x18000b87f  lea     rcx, qword_18003B770
0x18000b886  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b88d  nop     dword ptr [rax+rax+00h]
0x18000b892  mov     rax, [rbx+88h]
0x18000b899  test    rax, rax
0x18000b89c  jz      short loc_18000B8A2
0x18000b89e  and     dword ptr [rax+48h], 0
0x18000b8a2  mov     rax, [rbx+90h]
0x18000b8a9  test    rax, rax
0x18000b8ac  jz      short loc_18000B8B2
0x18000b8ae  and     dword ptr [rax+48h], 0
0x18000b8b2  mov     rax, [rbx+98h]
0x18000b8b9  test    rax, rax
0x18000b8bc  jz      short loc_18000B8C2
0x18000b8be  and     dword ptr [rax+48h], 0
0x18000b8c2  mov     rcx, [rbx+88h]
0x18000b8c9  test    rcx, rcx
0x18000b8cc  jz      short loc_18000B8E2
0x18000b8ce  mov     rax, [rcx]
0x18000b8d1  mov     rax, [rax+10h]
0x18000b8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8da  and     qword ptr [rbx+88h], 0
0x18000b8e2  mov     rcx, [rbx+90h]
0x18000b8e9  test    rcx, rcx
0x18000b8ec  jz      short loc_18000B902
0x18000b8ee  mov     rax, [rcx]
0x18000b8f1  mov     rax, [rax+10h]
0x18000b8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8fa  and     qword ptr [rbx+90h], 0
0x18000b902  mov     rcx, [rbx+98h]
0x18000b909  test    rcx, rcx
0x18000b90c  jz      short loc_18000B922
0x18000b90e  mov     rax, [rcx]
0x18000b911  mov     rax, [rax+10h]
0x18000b915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b91a  and     qword ptr [rbx+98h], 0
0x18000b922  and     [rsp+48h+var_28], 0
0x18000b928  mov     r9, rbx
0x18000b92b  lea     r8, aCwdstransportc_41; "<- CWdsTransportConfigurationManager::F"...
0x18000b932  mov     edx, 10000h
0x18000b937  lea     rcx, qword_18003B770
0x18000b93e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b945  nop     dword ptr [rax+rax+00h]
0x18000b94a  nop
0x18000b94b  lea     rcx, [rsp+48h+var_18]
0x18000b950  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000b955  add     rsp, 40h
0x18000b959  pop     rbx
0x18000b95a  retn
```
