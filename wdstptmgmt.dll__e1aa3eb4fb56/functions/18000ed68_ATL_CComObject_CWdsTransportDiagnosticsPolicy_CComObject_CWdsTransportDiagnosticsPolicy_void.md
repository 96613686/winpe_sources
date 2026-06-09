# ATL::CComObject<CWdsTransportDiagnosticsPolicy>::~CComObject<CWdsTransportDiagnosticsPolicy>(void)

- ea: `0x18000ed68`
- end: `0x18000ee04`
- name: `??1?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@UEAA@XZ`
- size: `156`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee10`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009d9c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000eda6`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000edce`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000eda6`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000edce`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportDiagnosticsPolicy>::~CComObject<CWdsTransportDiagnosticsPolicy>(
        CWdsTransportConfigurationManager *this)
{
  _BYTE v2[24]; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)this = &ATL::CComObject<CWdsTransportDiagnosticsPolicy>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v2, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportDiagnosticsPolicy::FinalRelease(0x%p)", this);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportDiagnosticsPolicy::FinalRelease(0x%p) =%x",
    this,
    0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v2);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x18000ed68  push    rbx
0x18000ed6a  sub     rsp, 40h
0x18000ed6e  mov     rbx, rcx
0x18000ed71  lea     rax, ??_7?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@6B@; const ATL::CComObject<CWdsTransportDiagnosticsPolicy>::`vftable'
0x18000ed78  mov     [rcx], rax
0x18000ed7b  mov     dword ptr [rcx+8], 0C0000001h
0x18000ed82  lea     rdx, [rcx+50h]
0x18000ed86  lea     rcx, [rsp+48h+var_18]
0x18000ed8b  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000ed90  mov     r9, rbx
0x18000ed93  lea     r8, aCwdstransportd; "-> CWdsTransportDiagnosticsPolicy::Fina"...
0x18000ed9a  mov     edx, 10000h
0x18000ed9f  lea     rcx, qword_18003B770
0x18000eda6  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000edad  nop     dword ptr [rax+rax+00h]
0x18000edb2  and     [rsp+48h+var_28], 0
0x18000edb8  mov     r9, rbx
0x18000edbb  lea     r8, aCwdstransportd_4; "<- CWdsTransportDiagnosticsPolicy::Fina"...
0x18000edc2  mov     edx, 10000h
0x18000edc7  lea     rcx, qword_18003B770
0x18000edce  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000edd5  nop     dword ptr [rax+rax+00h]
0x18000edda  lea     rcx, [rsp+48h+var_18]
0x18000eddf  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000ede4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000edeb  mov     rax, [rcx]
0x18000edee  mov     rax, [rax+10h]
0x18000edf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edf7  mov     rcx, rbx; this
0x18000edfa  add     rsp, 40h
0x18000edfe  pop     rbx
0x18000edff  jmp     ??1CWdsTransportConfigurationManager@@QEAA@XZ; CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)
```
