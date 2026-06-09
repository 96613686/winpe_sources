# CWdsTransportConfigurationManager::get_MulticastSessionPolicy(IWdsTransportMulticastSessionPolicy * *)

- ea: `0x18000c160`
- end: `0x18000c231`
- name: `?get_MulticastSessionPolicy@CWdsTransportConfigurationManager@@UEAAJPEAPEAUIWdsTransportMulticastSessionPolicy@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this, struct IWdsTransportMulticastSessionPolicy **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000c160`
- `0x18000c478`
- `0x18001770c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c199`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c208`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c199`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c208`

## string_xrefs

- `0x18000c186`: `-> CWdsTransportConfigurationManager::get_MulticastSessionPolicy(0x%p)`
- `0x18000c1f5`: `<- CWdsTransportConfigurationManager::get_MulticastSessionPolicy(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::get_MulticastSessionPolicy(
        CWdsTransportConfigurationManager *this,
        struct IWdsTransportMulticastSessionPolicy **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::get_MulticastSessionPolicy(0x%p)",
    this);
  if ( a2 )
  {
    v4 = (unsigned int)CWdsTransportMulticastSessionPolicy::DelayInitialize(*((CWdsTransportMulticastSessionPolicy **)this
                                                                            + 19));
    if ( (int)ElValidateHr_3(v4, v5, v6, 459) >= 0 )
      LODWORD(v4) = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IWdsTransportMulticastSessionPolicy **))this
                       + 19))(
                      *((_QWORD *)this + 19),
                      &IID_IWdsTransportMulticastSessionPolicy,
                      a2);
  }
  else
  {
    LODWORD(v4) = -2147024809;
  }
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::get_MulticastSessionPolicy(0x%p) =%x",
    this,
    v4);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c160  mov     [rsp+arg_0], rbx
0x18000c165  mov     [rsp+arg_8], rsi
0x18000c16a  push    rdi
0x18000c16b  sub     rsp, 40h
0x18000c16f  mov     rsi, rdx
0x18000c172  mov     rdi, rcx
0x18000c175  lea     rdx, [rcx+50h]
0x18000c179  lea     rcx, [rsp+48h+var_18]
0x18000c17e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000c183  mov     r9, rdi
0x18000c186  lea     r8, aCwdstransportc_4; "-> CWdsTransportConfigurationManager::g"...
0x18000c18d  mov     edx, 10000h
0x18000c192  lea     rcx, qword_18003B770
0x18000c199  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c1a0  nop     dword ptr [rax+rax+00h]
0x18000c1a5  test    rsi, rsi
0x18000c1a8  jnz     short loc_18000C1B1
0x18000c1aa  mov     ebx, 80070057h
0x18000c1af  jmp     short loc_18000C1EE
0x18000c1b1  mov     rcx, [rdi+98h]; this
0x18000c1b8  call    ?DelayInitialize@CWdsTransportMulticastSessionPolicy@@QEAAJXZ; CWdsTransportMulticastSessionPolicy::DelayInitialize(void)
0x18000c1bd  mov     r9d, 1CBh
0x18000c1c3  mov     ecx, eax
0x18000c1c5  mov     ebx, eax
0x18000c1c7  call    ElValidateHr_3
0x18000c1cc  test    eax, eax
0x18000c1ce  js      short loc_18000C1EE
0x18000c1d0  mov     rcx, [rdi+98h]
0x18000c1d7  lea     rdx, IID_IWdsTransportMulticastSessionPolicy
0x18000c1de  mov     r8, rsi
0x18000c1e1  mov     rax, [rcx]
0x18000c1e4  mov     rax, [rax]
0x18000c1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ec  mov     ebx, eax
0x18000c1ee  mov     r9, rdi
0x18000c1f1  mov     [rsp+48h+var_28], ebx
0x18000c1f5  lea     r8, aCwdstransportc_2; "<- CWdsTransportConfigurationManager::g"...
0x18000c1fc  mov     edx, 10000h
0x18000c201  lea     rcx, qword_18003B770
0x18000c208  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c20f  nop     dword ptr [rax+rax+00h]
0x18000c214  lea     rcx, [rsp+48h+var_18]
0x18000c219  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000c21e  mov     rsi, [rsp+48h+arg_8]
0x18000c223  mov     eax, ebx
0x18000c225  mov     rbx, [rsp+48h+arg_0]
0x18000c22a  add     rsp, 40h
0x18000c22e  pop     rdi
0x18000c22f  retn
```
