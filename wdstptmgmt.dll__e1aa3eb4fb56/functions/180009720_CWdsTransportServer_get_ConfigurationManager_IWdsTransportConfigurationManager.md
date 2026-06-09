# CWdsTransportServer::get_ConfigurationManager(IWdsTransportConfigurationManager * *)

- ea: `0x180009720`
- end: `0x1800097f1`
- name: `?get_ConfigurationManager@CWdsTransportServer@@UEAAJPEAPEAUIWdsTransportConfigurationManager@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CWdsTransportServer *__hidden this, struct IWdsTransportConfigurationManager **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009720`
- `0x180009af8`
- `0x18000b514`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009759`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800097c8`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009759`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800097c8`

## string_xrefs

- `0x180009746`: `-> CWdsTransportServer::get_ConfigurationManager(0x%p)`
- `0x1800097b5`: `<- CWdsTransportServer::get_ConfigurationManager(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportServer::get_ConfigurationManager(
        CWdsTransportServer *this,
        struct IWdsTransportConfigurationManager **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 72);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServer::get_ConfigurationManager(0x%p)", this);
  if ( a2 )
  {
    v4 = (unsigned int)CWdsTransportConfigurationManager::DelayInitialize(*((CWdsTransportConfigurationManager **)this
                                                                          + 16));
    if ( (int)ElValidateHr_1(v4, v5, v6, 776) >= 0 )
      LODWORD(v4) = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IWdsTransportConfigurationManager **))this
                       + 16))(
                      *((_QWORD *)this + 16),
                      &IID_IWdsTransportConfigurationManager,
                      a2);
  }
  else
  {
    LODWORD(v4) = -2147024809;
  }
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServer::get_ConfigurationManager(0x%p) =%x",
    this,
    v4);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009720  mov     [rsp+arg_0], rbx
0x180009725  mov     [rsp+arg_8], rsi
0x18000972a  push    rdi
0x18000972b  sub     rsp, 40h
0x18000972f  mov     rsi, rdx
0x180009732  mov     rdi, rcx
0x180009735  lea     rdx, [rcx+48h]
0x180009739  lea     rcx, [rsp+48h+var_18]
0x18000973e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180009743  mov     r9, rdi
0x180009746  lea     r8, aCwdstransports_56; "-> CWdsTransportServer::get_Configurati"...
0x18000974d  mov     edx, 10000h
0x180009752  lea     rcx, qword_18003B770
0x180009759  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180009760  nop     dword ptr [rax+rax+00h]
0x180009765  test    rsi, rsi
0x180009768  jnz     short loc_180009771
0x18000976a  mov     ebx, 80070057h
0x18000976f  jmp     short loc_1800097AE
0x180009771  mov     rcx, [rdi+80h]; this
0x180009778  call    ?DelayInitialize@CWdsTransportConfigurationManager@@QEAAJXZ; CWdsTransportConfigurationManager::DelayInitialize(void)
0x18000977d  mov     r9d, 308h
0x180009783  mov     ecx, eax
0x180009785  mov     ebx, eax
0x180009787  call    ElValidateHr_1
0x18000978c  test    eax, eax
0x18000978e  js      short loc_1800097AE
0x180009790  mov     rcx, [rdi+80h]
0x180009797  lea     rdx, IID_IWdsTransportConfigurationManager
0x18000979e  mov     r8, rsi
0x1800097a1  mov     rax, [rcx]
0x1800097a4  mov     rax, [rax]
0x1800097a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ac  mov     ebx, eax
0x1800097ae  mov     r9, rdi
0x1800097b1  mov     [rsp+48h+var_28], ebx
0x1800097b5  lea     r8, aCwdstransports_52; "<- CWdsTransportServer::get_Configurati"...
0x1800097bc  mov     edx, 10000h
0x1800097c1  lea     rcx, qword_18003B770
0x1800097c8  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800097cf  nop     dword ptr [rax+rax+00h]
0x1800097d4  lea     rcx, [rsp+48h+var_18]
0x1800097d9  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800097de  mov     rsi, [rsp+48h+arg_8]
0x1800097e3  mov     eax, ebx
0x1800097e5  mov     rbx, [rsp+48h+arg_0]
0x1800097ea  add     rsp, 40h
0x1800097ee  pop     rdi
0x1800097ef  retn
```
