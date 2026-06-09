# CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(void)

- ea: `0x18000dd98`
- end: `0x18000de2f`
- name: `?VerifyUdpPortPolicySupported@CWdsTransportServicePolicy@@QEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d2c0`
- `0x18000e3c0`
- `0x18000eae0`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009360`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ddca`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000de0a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ddca`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000de0a`

## string_xrefs

- `0x18000ddb7`: `-> CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(0x%p)`
- `0x18000ddf7`: `<- CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(CWdsTransportServicePolicy *this)
{
  unsigned int v2; // edx
  unsigned int v3; // ebx
  __int64 v5; // [rsp+20h] [rbp-28h]
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v6, (char *)this + 80);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(0x%p)",
    this);
  v3 = CWdsTransportServer::VerifyServerVersionForFeature(*((CWdsTransportServer **)this + 8), v2, 1u, 0, -1055915744);
  LODWORD(v5) = v3;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(0x%p) =%x",
    this,
    v5);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v6);
  return v3;
}

```

## disassembly

```asm
0x18000dd98  mov     [rsp+arg_0], rbx
0x18000dd9d  push    rdi
0x18000dd9e  sub     rsp, 40h
0x18000dda2  mov     rdi, rcx
0x18000dda5  lea     rdx, [rcx+50h]
0x18000dda9  lea     rcx, [rsp+48h+var_18]
0x18000ddae  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000ddb3  nop
0x18000ddb4  mov     r9, rdi
0x18000ddb7  lea     r8, aCwdstransports_22; "-> CWdsTransportServicePolicy::VerifyUd"...
0x18000ddbe  mov     edx, 10000h
0x18000ddc3  lea     rcx, qword_18003B770
0x18000ddca  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ddd1  nop     dword ptr [rax+rax+00h]
0x18000ddd6  mov     [rsp+48h+var_28], 0C1100120h; int
0x18000ddde  xor     r9d, r9d; int
0x18000dde1  lea     r8d, [r9+1]; unsigned int
0x18000dde5  mov     rcx, [rdi+40h]; this
0x18000dde9  call    ?VerifyServerVersionForFeature@CWdsTransportServer@@QEAAJKKHJ@Z; CWdsTransportServer::VerifyServerVersionForFeature(ulong,ulong,int,long)
0x18000ddee  mov     ebx, eax
0x18000ddf0  mov     [rsp+48h+var_28], eax
0x18000ddf4  mov     r9, rdi
0x18000ddf7  lea     r8, aCwdstransports_34; "<- CWdsTransportServicePolicy::VerifyUd"...
0x18000ddfe  mov     edx, 10000h
0x18000de03  lea     rcx, qword_18003B770
0x18000de0a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000de11  nop     dword ptr [rax+rax+00h]
0x18000de16  nop
0x18000de17  lea     rcx, [rsp+48h+var_18]
0x18000de1c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000de21  mov     eax, ebx
0x18000de23  mov     rbx, [rsp+48h+arg_0]
0x18000de28  add     rsp, 40h
0x18000de2c  pop     rdi
0x18000de2d  retn
```
