# CWdsTransportConfigurationManager::get_ServicePolicy(IWdsTransportServicePolicy * *)

- ea: `0x18000c240`
- end: `0x18000c311`
- name: `?get_ServicePolicy@CWdsTransportConfigurationManager@@UEAAJPEAPEAUIWdsTransportServicePolicy@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this, struct IWdsTransportServicePolicy **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000c240`
- `0x18000c478`
- `0x18000cef4`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c279`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c2e8`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c279`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c2e8`

## string_xrefs

- `0x18000c266`: `-> CWdsTransportConfigurationManager::get_ServicePolicy(0x%p)`
- `0x18000c2d5`: `<- CWdsTransportConfigurationManager::get_ServicePolicy(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::get_ServicePolicy(
        CWdsTransportConfigurationManager *this,
        struct IWdsTransportServicePolicy **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::get_ServicePolicy(0x%p)",
    this);
  if ( a2 )
  {
    v4 = (unsigned int)CWdsTransportServicePolicy::DelayInitialize(*((CWdsTransportServicePolicy **)this + 17));
    if ( (int)ElValidateHr_3(v4, v5, v6, 347) >= 0 )
      LODWORD(v4) = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IWdsTransportServicePolicy **))this + 17))(
                      *((_QWORD *)this + 17),
                      &IID_IWdsTransportServicePolicy,
                      a2);
  }
  else
  {
    LODWORD(v4) = -2147024809;
  }
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::get_ServicePolicy(0x%p) =%x",
    this,
    v4);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c240  mov     [rsp+arg_0], rbx
0x18000c245  mov     [rsp+arg_8], rsi
0x18000c24a  push    rdi
0x18000c24b  sub     rsp, 40h
0x18000c24f  mov     rsi, rdx
0x18000c252  mov     rdi, rcx
0x18000c255  lea     rdx, [rcx+50h]
0x18000c259  lea     rcx, [rsp+48h+var_18]
0x18000c25e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000c263  mov     r9, rdi
0x18000c266  lea     r8, aCwdstransportc_32; "-> CWdsTransportConfigurationManager::g"...
0x18000c26d  mov     edx, 10000h
0x18000c272  lea     rcx, qword_18003B770
0x18000c279  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c280  nop     dword ptr [rax+rax+00h]
0x18000c285  test    rsi, rsi
0x18000c288  jnz     short loc_18000C291
0x18000c28a  mov     ebx, 80070057h
0x18000c28f  jmp     short loc_18000C2CE
0x18000c291  mov     rcx, [rdi+88h]; this
0x18000c298  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000c29d  mov     r9d, 15Bh
0x18000c2a3  mov     ecx, eax
0x18000c2a5  mov     ebx, eax
0x18000c2a7  call    ElValidateHr_3
0x18000c2ac  test    eax, eax
0x18000c2ae  js      short loc_18000C2CE
0x18000c2b0  mov     rcx, [rdi+88h]
0x18000c2b7  lea     rdx, IID_IWdsTransportServicePolicy
0x18000c2be  mov     r8, rsi
0x18000c2c1  mov     rax, [rcx]
0x18000c2c4  mov     rax, [rax]
0x18000c2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2cc  mov     ebx, eax
0x18000c2ce  mov     r9, rdi
0x18000c2d1  mov     [rsp+48h+var_28], ebx
0x18000c2d5  lea     r8, aCwdstransportc_17; "<- CWdsTransportConfigurationManager::g"...
0x18000c2dc  mov     edx, 10000h
0x18000c2e1  lea     rcx, qword_18003B770
0x18000c2e8  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c2ef  nop     dword ptr [rax+rax+00h]
0x18000c2f4  lea     rcx, [rsp+48h+var_18]
0x18000c2f9  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000c2fe  mov     rsi, [rsp+48h+arg_8]
0x18000c303  mov     eax, ebx
0x18000c305  mov     rbx, [rsp+48h+arg_0]
0x18000c30a  add     rsp, 40h
0x18000c30e  pop     rdi
0x18000c30f  retn
```
