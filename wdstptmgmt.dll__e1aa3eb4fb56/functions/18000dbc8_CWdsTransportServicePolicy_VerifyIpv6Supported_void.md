# CWdsTransportServicePolicy::VerifyIpv6Supported(void)

- ea: `0x18000dbc8`
- end: `0x18000dc5f`
- name: `?VerifyIpv6Supported@CWdsTransportServicePolicy@@QEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d2c0`
- `0x18000df40`
- `0x18000e090`
- `0x18000e1e0`
- `0x18000e4f0`
- `0x18000e6d0`
- `0x18000e850`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009360`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dbfa`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dc3a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dbfa`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dc3a`

## string_xrefs

- `0x18000dbe7`: `-> CWdsTransportServicePolicy::VerifyIpv6Supported(0x%p)`
- `0x18000dc27`: `<- CWdsTransportServicePolicy::VerifyIpv6Supported(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportServicePolicy::VerifyIpv6Supported(CWdsTransportServicePolicy *this)
{
  unsigned int v2; // edx
  unsigned int v3; // ebx
  __int64 v5; // [rsp+20h] [rbp-28h]
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v6, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServicePolicy::VerifyIpv6Supported(0x%p)", this);
  v3 = CWdsTransportServer::VerifyServerVersionForFeature(*((CWdsTransportServer **)this + 8), v2, 1u, 0, -1055915751);
  LODWORD(v5) = v3;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServicePolicy::VerifyIpv6Supported(0x%p) =%x",
    this,
    v5);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v6);
  return v3;
}

```

## disassembly

```asm
0x18000dbc8  mov     [rsp+arg_0], rbx
0x18000dbcd  push    rdi
0x18000dbce  sub     rsp, 40h
0x18000dbd2  mov     rdi, rcx
0x18000dbd5  lea     rdx, [rcx+50h]
0x18000dbd9  lea     rcx, [rsp+48h+var_18]
0x18000dbde  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000dbe3  nop
0x18000dbe4  mov     r9, rdi
0x18000dbe7  lea     r8, aCwdstransports_19; "-> CWdsTransportServicePolicy::VerifyIp"...
0x18000dbee  mov     edx, 10000h
0x18000dbf3  lea     rcx, qword_18003B770
0x18000dbfa  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000dc01  nop     dword ptr [rax+rax+00h]
0x18000dc06  mov     [rsp+48h+var_28], 0C1100119h; int
0x18000dc0e  xor     r9d, r9d; int
0x18000dc11  lea     r8d, [r9+1]; unsigned int
0x18000dc15  mov     rcx, [rdi+40h]; this
0x18000dc19  call    ?VerifyServerVersionForFeature@CWdsTransportServer@@QEAAJKKHJ@Z; CWdsTransportServer::VerifyServerVersionForFeature(ulong,ulong,int,long)
0x18000dc1e  mov     ebx, eax
0x18000dc20  mov     [rsp+48h+var_28], eax
0x18000dc24  mov     r9, rdi
0x18000dc27  lea     r8, aCwdstransports_55; "<- CWdsTransportServicePolicy::VerifyIp"...
0x18000dc2e  mov     edx, 10000h
0x18000dc33  lea     rcx, qword_18003B770
0x18000dc3a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000dc41  nop     dword ptr [rax+rax+00h]
0x18000dc46  nop
0x18000dc47  lea     rcx, [rsp+48h+var_18]
0x18000dc4c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000dc51  mov     eax, ebx
0x18000dc53  mov     rbx, [rsp+48h+arg_0]
0x18000dc58  add     rsp, 40h
0x18000dc5c  pop     rdi
0x18000dc5d  retn
```
