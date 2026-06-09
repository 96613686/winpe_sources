# ATL::CComObject<CWdsTransportCollection>::~CComObject<CWdsTransportCollection>(void)

- ea: `0x180006938`
- end: `0x1800069d4`
- name: `??1?$CComObject@VCWdsTransportCollection@@@ATL@@UEAA@XZ`
- size: `156`
- prototype: `__int64 __fastcall(CWdsTransportCollection *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006a80`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x1800069e8`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006976`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000699e`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006976`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000699e`

## pseudocode

```c
void __fastcall ATL::CComObject<CWdsTransportCollection>::~CComObject<CWdsTransportCollection>(
        CWdsTransportCollection *this)
{
  _BYTE v2[24]; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)this = &ATL::CComObject<CWdsTransportCollection>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v2, (char *)this + 64);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportCollection::FinalRelease(0x%p)", this);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportCollection::FinalRelease(0x%p) =%x", this, 0);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v2);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWdsTransportCollection::~CWdsTransportCollection(this);
}

```

## disassembly

```asm
0x180006938  push    rbx
0x18000693a  sub     rsp, 40h
0x18000693e  mov     rbx, rcx
0x180006941  lea     rax, ??_7?$CComObject@VCWdsTransportCollection@@@ATL@@6B@; const ATL::CComObject<CWdsTransportCollection>::`vftable'
0x180006948  mov     [rcx], rax
0x18000694b  mov     dword ptr [rcx+8], 0C0000001h
0x180006952  lea     rdx, [rcx+40h]
0x180006956  lea     rcx, [rsp+48h+var_18]
0x18000695b  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180006960  mov     r9, rbx
0x180006963  lea     r8, aCwdstransportc_16; "-> CWdsTransportCollection::FinalReleas"...
0x18000696a  mov     edx, 10000h
0x18000696f  lea     rcx, qword_18003B770
0x180006976  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000697d  nop     dword ptr [rax+rax+00h]
0x180006982  and     [rsp+48h+var_28], 0
0x180006988  mov     r9, rbx
0x18000698b  lea     r8, aCwdstransportc_1; "<- CWdsTransportCollection::FinalReleas"...
0x180006992  mov     edx, 10000h
0x180006997  lea     rcx, qword_18003B770
0x18000699e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800069a5  nop     dword ptr [rax+rax+00h]
0x1800069aa  lea     rcx, [rsp+48h+var_18]
0x1800069af  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800069b4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800069bb  mov     rax, [rcx]
0x1800069be  mov     rax, [rax+10h]
0x1800069c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c7  mov     rcx, rbx; this
0x1800069ca  add     rsp, 40h
0x1800069ce  pop     rbx
0x1800069cf  jmp     ??1CWdsTransportCollection@@QEAA@XZ; CWdsTransportCollection::~CWdsTransportCollection(void)
```
