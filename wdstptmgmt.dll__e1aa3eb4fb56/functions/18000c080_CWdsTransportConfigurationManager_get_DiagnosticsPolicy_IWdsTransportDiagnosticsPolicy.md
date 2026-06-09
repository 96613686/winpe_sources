# CWdsTransportConfigurationManager::get_DiagnosticsPolicy(IWdsTransportDiagnosticsPolicy * *)

- ea: `0x18000c080`
- end: `0x18000c151`
- name: `?get_DiagnosticsPolicy@CWdsTransportConfigurationManager@@UEAAJPEAPEAUIWdsTransportDiagnosticsPolicy@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this, struct IWdsTransportDiagnosticsPolicy **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000c080`
- `0x18000c478`
- `0x18000f43c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c0b9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c128`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c0b9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c128`

## string_xrefs

- `0x18000c0a6`: `-> CWdsTransportConfigurationManager::get_DiagnosticsPolicy(0x%p)`
- `0x18000c115`: `<- CWdsTransportConfigurationManager::get_DiagnosticsPolicy(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::get_DiagnosticsPolicy(
        CWdsTransportConfigurationManager *this,
        struct IWdsTransportDiagnosticsPolicy **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::get_DiagnosticsPolicy(0x%p)",
    this);
  if ( a2 )
  {
    v4 = (unsigned int)CWdsTransportDiagnosticsPolicy::DelayInitialize(*((CWdsTransportDiagnosticsPolicy **)this + 18));
    if ( (int)ElValidateHr_3(v4, v5, v6, 403) >= 0 )
      LODWORD(v4) = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IWdsTransportDiagnosticsPolicy **))this + 18))(
                      *((_QWORD *)this + 18),
                      &IID_IWdsTransportDiagnosticsPolicy,
                      a2);
  }
  else
  {
    LODWORD(v4) = -2147024809;
  }
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::get_DiagnosticsPolicy(0x%p) =%x",
    this,
    v4);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c080  mov     [rsp+arg_0], rbx
0x18000c085  mov     [rsp+arg_8], rsi
0x18000c08a  push    rdi
0x18000c08b  sub     rsp, 40h
0x18000c08f  mov     rsi, rdx
0x18000c092  mov     rdi, rcx
0x18000c095  lea     rdx, [rcx+50h]
0x18000c099  lea     rcx, [rsp+48h+var_18]
0x18000c09e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000c0a3  mov     r9, rdi
0x18000c0a6  lea     r8, aCwdstransportc_35; "-> CWdsTransportConfigurationManager::g"...
0x18000c0ad  mov     edx, 10000h
0x18000c0b2  lea     rcx, qword_18003B770
0x18000c0b9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c0c0  nop     dword ptr [rax+rax+00h]
0x18000c0c5  test    rsi, rsi
0x18000c0c8  jnz     short loc_18000C0D1
0x18000c0ca  mov     ebx, 80070057h
0x18000c0cf  jmp     short loc_18000C10E
0x18000c0d1  mov     rcx, [rdi+90h]; this
0x18000c0d8  call    ?DelayInitialize@CWdsTransportDiagnosticsPolicy@@QEAAJXZ; CWdsTransportDiagnosticsPolicy::DelayInitialize(void)
0x18000c0dd  mov     r9d, 193h
0x18000c0e3  mov     ecx, eax
0x18000c0e5  mov     ebx, eax
0x18000c0e7  call    ElValidateHr_3
0x18000c0ec  test    eax, eax
0x18000c0ee  js      short loc_18000C10E
0x18000c0f0  mov     rcx, [rdi+90h]
0x18000c0f7  lea     rdx, IID_IWdsTransportDiagnosticsPolicy
0x18000c0fe  mov     r8, rsi
0x18000c101  mov     rax, [rcx]
0x18000c104  mov     rax, [rax]
0x18000c107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c10c  mov     ebx, eax
0x18000c10e  mov     r9, rdi
0x18000c111  mov     [rsp+48h+var_28], ebx
0x18000c115  lea     r8, aCwdstransportc_33; "<- CWdsTransportConfigurationManager::g"...
0x18000c11c  mov     edx, 10000h
0x18000c121  lea     rcx, qword_18003B770
0x18000c128  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c12f  nop     dword ptr [rax+rax+00h]
0x18000c134  lea     rcx, [rsp+48h+var_18]
0x18000c139  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000c13e  mov     rsi, [rsp+48h+arg_8]
0x18000c143  mov     eax, ebx
0x18000c145  mov     rbx, [rsp+48h+arg_0]
0x18000c14a  add     rsp, 40h
0x18000c14e  pop     rdi
0x18000c14f  retn
```
