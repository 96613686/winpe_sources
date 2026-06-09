# CWdsTransportServicePolicy::VerifyNetworkProfileSupported(void)

- ea: `0x18000dc68`
- end: `0x18000dd01`
- name: `?VerifyNetworkProfileSupported@CWdsTransportServicePolicy@@QEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d2c0`
- `0x18000e150`
- `0x18000e7b0`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009360`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dc9a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dcdc`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dc9a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000dcdc`

## string_xrefs

- `0x18000dc87`: `-> CWdsTransportServicePolicy::VerifyNetworkProfileSupported(0x%p)`
- `0x18000dcc9`: `<- CWdsTransportServicePolicy::VerifyNetworkProfileSupported(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportServicePolicy::VerifyNetworkProfileSupported(CWdsTransportServicePolicy *this)
{
  unsigned int v2; // edx
  unsigned int v3; // ebx
  __int64 v5; // [rsp+20h] [rbp-28h]
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v6, (char *)this + 80);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportServicePolicy::VerifyNetworkProfileSupported(0x%p)",
    this);
  v3 = CWdsTransportServer::VerifyServerVersionForFeature(*((CWdsTransportServer **)this + 8), v2, 0, 1, -1055915745);
  LODWORD(v5) = v3;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServicePolicy::VerifyNetworkProfileSupported(0x%p) =%x",
    this,
    v5);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v6);
  return v3;
}

```

## disassembly

```asm
0x18000dc68  mov     [rsp+arg_0], rbx
0x18000dc6d  push    rdi
0x18000dc6e  sub     rsp, 40h
0x18000dc72  mov     rdi, rcx
0x18000dc75  lea     rdx, [rcx+50h]
0x18000dc79  lea     rcx, [rsp+48h+var_18]
0x18000dc7e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000dc83  nop
0x18000dc84  mov     r9, rdi
0x18000dc87  lea     r8, aCwdstransports_41; "-> CWdsTransportServicePolicy::VerifyNe"...
0x18000dc8e  mov     edx, 10000h
0x18000dc93  lea     rcx, qword_18003B770
0x18000dc9a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000dca1  nop     dword ptr [rax+rax+00h]
0x18000dca6  mov     [rsp+48h+var_28], 0C110011Fh; int
0x18000dcae  mov     r9d, 1; int
0x18000dcb4  xor     r8d, r8d; unsigned int
0x18000dcb7  mov     rcx, [rdi+40h]; this
0x18000dcbb  call    ?VerifyServerVersionForFeature@CWdsTransportServer@@QEAAJKKHJ@Z; CWdsTransportServer::VerifyServerVersionForFeature(ulong,ulong,int,long)
0x18000dcc0  mov     ebx, eax
0x18000dcc2  mov     [rsp+48h+var_28], eax
0x18000dcc6  mov     r9, rdi
0x18000dcc9  lea     r8, aCwdstransports_8; "<- CWdsTransportServicePolicy::VerifyNe"...
0x18000dcd0  mov     edx, 10000h
0x18000dcd5  lea     rcx, qword_18003B770
0x18000dcdc  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000dce3  nop     dword ptr [rax+rax+00h]
0x18000dce8  nop
0x18000dce9  lea     rcx, [rsp+48h+var_18]
0x18000dcee  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000dcf3  mov     eax, ebx
0x18000dcf5  mov     rbx, [rsp+48h+arg_0]
0x18000dcfa  add     rsp, 40h
0x18000dcfe  pop     rdi
0x18000dcff  retn
```
