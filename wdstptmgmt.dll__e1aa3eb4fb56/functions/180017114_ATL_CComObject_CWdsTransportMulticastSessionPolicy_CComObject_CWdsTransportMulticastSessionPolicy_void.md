# ATL::CComObject<CWdsTransportMulticastSessionPolicy>::~CComObject<CWdsTransportMulticastSessionPolicy>(void)

- ea: `0x180017114`
- end: `0x1800171b0`
- name: `??1?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@UEAA@XZ`
- size: `156`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800171c0`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009d9c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017152`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001717a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017152`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001717a`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportMulticastSessionPolicy>::~CComObject<CWdsTransportMulticastSessionPolicy>(
        CWdsTransportConfigurationManager *this)
{
  _BYTE v2[24]; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)this = &ATL::CComObject<CWdsTransportMulticastSessionPolicy>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v2, (char *)this + 80);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportMulticastSessionPolicy::FinalRelease(0x%p)",
    this);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportMulticastSessionPolicy::FinalRelease(0x%p) =%x",
    this,
    0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v2);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x180017114  push    rbx
0x180017116  sub     rsp, 40h
0x18001711a  mov     rbx, rcx
0x18001711d  lea     rax, ??_7?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@6B@; const ATL::CComObject<CWdsTransportMulticastSessionPolicy>::`vftable'
0x180017124  mov     [rcx], rax
0x180017127  mov     dword ptr [rcx+8], 0C0000001h
0x18001712e  lea     rdx, [rcx+50h]
0x180017132  lea     rcx, [rsp+48h+var_18]
0x180017137  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18001713c  mov     r9, rbx
0x18001713f  lea     r8, aCwdstransportm_15; "-> CWdsTransportMulticastSessionPolicy:"...
0x180017146  mov     edx, 10000h
0x18001714b  lea     rcx, qword_18003B770
0x180017152  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017159  nop     dword ptr [rax+rax+00h]
0x18001715e  and     [rsp+48h+var_28], 0
0x180017164  mov     r9, rbx
0x180017167  lea     r8, aCwdstransportm_4; "<- CWdsTransportMulticastSessionPolicy:"...
0x18001716e  mov     edx, 10000h
0x180017173  lea     rcx, qword_18003B770
0x18001717a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017181  nop     dword ptr [rax+rax+00h]
0x180017186  lea     rcx, [rsp+48h+var_18]
0x18001718b  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180017190  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180017197  mov     rax, [rcx]
0x18001719a  mov     rax, [rax+10h]
0x18001719e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171a3  mov     rcx, rbx; this
0x1800171a6  add     rsp, 40h
0x1800171aa  pop     rbx
0x1800171ab  jmp     ??1CWdsTransportConfigurationManager@@QEAA@XZ; CWdsTransportConfigurationManager::~CWdsTransportConfigurationManager(void)
```
