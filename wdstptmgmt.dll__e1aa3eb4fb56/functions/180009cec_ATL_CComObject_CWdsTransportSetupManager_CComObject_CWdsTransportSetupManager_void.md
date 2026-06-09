# ATL::CComObject<CWdsTransportSetupManager>::~CComObject<CWdsTransportSetupManager>(void)

- ea: `0x180009cec`
- end: `0x180009d88`
- name: `??1?$CComObject@VCWdsTransportSetupManager@@@ATL@@UEAA@XZ`
- size: `156`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009dd0`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009d9c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009d2a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009d52`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009d2a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009d52`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportSetupManager>::~CComObject<CWdsTransportSetupManager>(
        CWdsTransportConfigurationManager *this)
{
  _BYTE v2[24]; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)this = &ATL::CComObject<CWdsTransportSetupManager>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v2, (char *)this + 80);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportSetupManager::FinalRelease(0x%p)", this);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportSetupManager::FinalRelease(0x%p) =%x", this, 0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v2);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x180009cec  push    rbx
0x180009cee  sub     rsp, 40h
0x180009cf2  mov     rbx, rcx
0x180009cf5  lea     rax, ??_7?$CComObject@VCWdsTransportSetupManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportSetupManager>::`vftable'
0x180009cfc  mov     [rcx], rax
0x180009cff  mov     dword ptr [rcx+8], 0C0000001h
0x180009d06  lea     rdx, [rcx+50h]
0x180009d0a  lea     rcx, [rsp+48h+var_18]
0x180009d0f  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180009d14  mov     r9, rbx
0x180009d17  lea     r8, aCwdstransports_45; "-> CWdsTransportSetupManager::FinalRele"...
0x180009d1e  mov     edx, 10000h
0x180009d23  lea     rcx, qword_18003B770
0x180009d2a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180009d31  nop     dword ptr [rax+rax+00h]
0x180009d36  and     [rsp+48h+var_28], 0
0x180009d3c  mov     r9, rbx
0x180009d3f  lea     r8, aCwdstransports_38; "<- CWdsTransportSetupManager::FinalRele"...
0x180009d46  mov     edx, 10000h
0x180009d4b  lea     rcx, qword_18003B770
0x180009d52  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180009d59  nop     dword ptr [rax+rax+00h]
0x180009d5e  lea     rcx, [rsp+48h+var_18]
0x180009d63  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180009d68  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009d6f  mov     rax, [rcx]
0x180009d72  mov     rax, [rax+10h]
0x180009d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d7b  mov     rcx, rbx; this
0x180009d7e  add     rsp, 40h
0x180009d82  pop     rbx
0x180009d83  jmp     ??1CWdsTransportConfigurationManager@@QEAA@XZ; CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)
```
