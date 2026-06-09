# CSessionArbitrationHelperMgr::~CSessionArbitrationHelperMgr(void)

- ea: `0x18003256c`
- end: `0x180032662`
- name: `??1CSessionArbitrationHelperMgr@@UEAA@XZ`
- size: `246`
- prototype: `void __fastcall(CSessionArbitrationHelperMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18007a930`

## callees

- `0x180007f40`
- `0x1800095a0`
- `0x180012750`
- `0x18002ce5c`
- `0x18003256c`
- `0x180032668`
- `0x180032754`
- `0x1800327d0`
- `0x18004c270`

## import_xrefs

- `ntdll!RtlEnumerateGenericTable` at `0x1800325f8`
- `ntdll!RtlEnumerateGenericTable` at `0x1800325f8`
- `ntdll!RtlDeleteResource` at `0x1800325d9`
- `ntdll!RtlDeleteResource` at `0x180032627`
- `ntdll!RtlDeleteResource` at `0x1800325d9`
- `ntdll!RtlDeleteResource` at `0x180032627`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSessionArbitrationHelperMgr::~CSessionArbitrationHelperMgr(CSessionArbitrationHelperMgr *this)
{
  PVOID v2; // rbx
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)this = &CSessionArbitrationHelperMgr::`vftable';
  CSessionArbitrationHelperMgr::EmptySessionToArbitrationHelperList(this);
  CAutoExclusiveLock::CAutoExclusiveLock(
    (CAutoExclusiveLock *)v3,
    (CSessionArbitrationHelperMgr *)((char *)this + 1776));
  SmartArray<CTSTimerHandler,unsigned long>::Empty((char *)this + 1880);
  CAutoLock::Unlock((CAutoLock *)v3);
  SmartPtr<CDefaultSessionArbitrationHelper>::~SmartPtr<CDefaultSessionArbitrationHelper>((char *)this + 1904);
  SmartArray<CTSTimerHandler,unsigned long>::~SmartArray<CTSTimerHandler,unsigned long>((char *)this + 1880);
  if ( *((_DWORD *)this + 468) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1776));
  *((_DWORD *)this + 468) = 0;
  do
  {
    v2 = RtlEnumerateGenericTable((PRTL_GENERIC_TABLE)((char *)this + 1696), 1u);
    CListTree<CSessionToHelperItem>::ReleaseItemPtr((char *)this + 1696, v2);
  }
  while ( v2 );
  if ( *((_DWORD *)this + 422) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1592));
  *((_DWORD *)this + 422) = 0;
  *(_QWORD *)this = &CTSPrivateObject<IUnknown>::`vftable';
  RemoveTrackingObject((struct _LIST_ENTRY *)((char *)this + 1576));
}

```

## disassembly

```asm
0x18003256c  mov     [rsp+arg_0], rbx
0x180032571  mov     [rsp+arg_8], rsi
0x180032576  push    rdi
0x180032577  sub     rsp, 30h
0x18003257b  mov     rdi, rcx
0x18003257e  lea     rax, ??_7CSessionArbitrationHelperMgr@@6B@; const CSessionArbitrationHelperMgr::`vftable'
0x180032585  mov     [rcx], rax
0x180032588  call    ?EmptySessionToArbitrationHelperList@CSessionArbitrationHelperMgr@@AEAAJXZ; CSessionArbitrationHelperMgr::EmptySessionToArbitrationHelperList(void)
0x18003258d  lea     rsi, [rdi+6F0h]
0x180032594  mov     rdx, rsi; struct CResource *
0x180032597  lea     rcx, [rsp+38h+var_18]; this
0x18003259c  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800325a1  lea     rbx, [rdi+758h]
0x1800325a8  mov     rcx, rbx
0x1800325ab  call    ?Empty@?$SmartArray@VCTSTimerHandler@@K@@QEAAXXZ; SmartArray<CTSTimerHandler,ulong>::Empty(void)
0x1800325b0  nop
0x1800325b1  lea     rcx, [rsp+38h+var_18]; this
0x1800325b6  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800325bb  nop
0x1800325bc  lea     rcx, [rdi+770h]
0x1800325c3  call    ??1?$SmartPtr@VCDefaultSessionArbitrationHelper@@@@QEAA@XZ; SmartPtr<CDefaultSessionArbitrationHelper>::~SmartPtr<CDefaultSessionArbitrationHelper>(void)
0x1800325c8  mov     rcx, rbx
0x1800325cb  call    ??1?$SmartArray@VCTSTimerHandler@@K@@QEAA@XZ; SmartArray<CTSTimerHandler,ulong>::~SmartArray<CTSTimerHandler,ulong>(void)
0x1800325d0  cmp     dword ptr [rsi+60h], 0
0x1800325d4  jz      short loc_1800325E5
0x1800325d6  mov     rcx, rsi; Resource
0x1800325d9  call    cs:__imp_RtlDeleteResource
0x1800325e0  nop     dword ptr [rax+rax+00h]
0x1800325e5  mov     dword ptr [rsi+60h], 0
0x1800325ec  lea     rsi, [rdi+6A0h]
0x1800325f3  mov     dl, 1; Restart
0x1800325f5  mov     rcx, rsi; Table
0x1800325f8  call    cs:__imp_RtlEnumerateGenericTable
0x1800325ff  nop     dword ptr [rax+rax+00h]
0x180032604  mov     rbx, rax
0x180032607  mov     rdx, rax
0x18003260a  mov     rcx, rsi
0x18003260d  call    ?ReleaseItemPtr@?$CListTree@VCSessionToHelperItem@@@@IEAAHPEAPEAVCSessionToHelperItem@@@Z; CListTree<CSessionToHelperItem>::ReleaseItemPtr(CSessionToHelperItem * *)
0x180032612  test    rbx, rbx
0x180032615  jnz     short loc_1800325F3
0x180032617  lea     rbx, [rdi+638h]
0x18003261e  cmp     dword ptr [rbx+60h], 0
0x180032622  jz      short loc_180032633
0x180032624  mov     rcx, rbx; Resource
0x180032627  call    cs:__imp_RtlDeleteResource
0x18003262e  nop     dword ptr [rax+rax+00h]
0x180032633  mov     dword ptr [rbx+60h], 0
0x18003263a  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x180032641  mov     [rdi], rax
0x180032644  lea     rcx, [rdi+628h]; struct _LIST_ENTRY *
0x18003264b  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x180032650  nop
0x180032651  mov     rbx, [rsp+38h+arg_0]
0x180032656  mov     rsi, [rsp+38h+arg_8]
0x18003265b  add     rsp, 30h
0x18003265f  pop     rdi
0x180032660  retn
```
