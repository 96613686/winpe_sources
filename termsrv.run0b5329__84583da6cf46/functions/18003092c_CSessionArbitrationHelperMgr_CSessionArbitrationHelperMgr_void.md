# CSessionArbitrationHelperMgr::~CSessionArbitrationHelperMgr(void)

- ea: `0x18003092c`
- end: `0x180030a0f`
- name: `??1CSessionArbitrationHelperMgr@@UEAA@XZ`
- size: `227`
- prototype: `void __fastcall(CSessionArbitrationHelperMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180077340`

## callees

- `0x180008980`
- `0x180009ee0`
- `0x180011f80`
- `0x18002b6ac`
- `0x18003092c`
- `0x180030a18`
- `0x180030af8`
- `0x180030b74`
- `0x180049d10`

## import_xrefs

- `ntdll!RtlEnumerateGenericTable` at `0x1800309b2`
- `ntdll!RtlEnumerateGenericTable` at `0x1800309b2`
- `ntdll!RtlDeleteResource` at `0x180030999`
- `ntdll!RtlDeleteResource` at `0x1800309db`
- `ntdll!RtlDeleteResource` at `0x180030999`
- `ntdll!RtlDeleteResource` at `0x1800309db`

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
0x18003092c  mov     [rsp+arg_0], rbx
0x180030931  mov     [rsp+arg_8], rsi
0x180030936  push    rdi
0x180030937  sub     rsp, 30h
0x18003093b  mov     rdi, rcx
0x18003093e  lea     rax, ??_7CSessionArbitrationHelperMgr@@6B@; const CSessionArbitrationHelperMgr::`vftable'
0x180030945  mov     [rcx], rax
0x180030948  call    ?EmptySessionToArbitrationHelperList@CSessionArbitrationHelperMgr@@AEAAJXZ; CSessionArbitrationHelperMgr::EmptySessionToArbitrationHelperList(void)
0x18003094d  lea     rsi, [rdi+6F0h]
0x180030954  mov     rdx, rsi; struct CResource *
0x180030957  lea     rcx, [rsp+38h+var_18]; this
0x18003095c  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180030961  lea     rbx, [rdi+758h]
0x180030968  mov     rcx, rbx
0x18003096b  call    ?Empty@?$SmartArray@VCTSTimerHandler@@K@@QEAAXXZ; SmartArray<CTSTimerHandler,ulong>::Empty(void)
0x180030970  nop
0x180030971  lea     rcx, [rsp+38h+var_18]; this
0x180030976  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18003097b  nop
0x18003097c  lea     rcx, [rdi+770h]
0x180030983  call    ??1?$SmartPtr@VCDefaultSessionArbitrationHelper@@@@QEAA@XZ; SmartPtr<CDefaultSessionArbitrationHelper>::~SmartPtr<CDefaultSessionArbitrationHelper>(void)
0x180030988  mov     rcx, rbx
0x18003098b  call    ??1?$SmartArray@VCTSTimerHandler@@K@@QEAA@XZ; SmartArray<CTSTimerHandler,ulong>::~SmartArray<CTSTimerHandler,ulong>(void)
0x180030990  cmp     dword ptr [rsi+60h], 0
0x180030994  jz      short loc_18003099F
0x180030996  mov     rcx, rsi; Resource
0x180030999  call    cs:__imp_RtlDeleteResource
0x18003099f  mov     dword ptr [rsi+60h], 0
0x1800309a6  lea     rsi, [rdi+6A0h]
0x1800309ad  mov     dl, 1; Restart
0x1800309af  mov     rcx, rsi; Table
0x1800309b2  call    cs:__imp_RtlEnumerateGenericTable
0x1800309b8  mov     rbx, rax
0x1800309bb  mov     rdx, rax
0x1800309be  mov     rcx, rsi
0x1800309c1  call    ?ReleaseItemPtr@?$CListTree@VCSessionToHelperItem@@@@IEAAHPEAPEAVCSessionToHelperItem@@@Z; CListTree<CSessionToHelperItem>::ReleaseItemPtr(CSessionToHelperItem * *)
0x1800309c6  test    rbx, rbx
0x1800309c9  jnz     short loc_1800309AD
0x1800309cb  lea     rbx, [rdi+638h]
0x1800309d2  cmp     dword ptr [rbx+60h], 0
0x1800309d6  jz      short loc_1800309E1
0x1800309d8  mov     rcx, rbx; Resource
0x1800309db  call    cs:__imp_RtlDeleteResource
0x1800309e1  mov     dword ptr [rbx+60h], 0
0x1800309e8  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x1800309ef  mov     [rdi], rax
0x1800309f2  lea     rcx, [rdi+628h]; struct _LIST_ENTRY *
0x1800309f9  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x1800309fe  nop
0x1800309ff  mov     rbx, [rsp+38h+arg_0]
0x180030a04  mov     rsi, [rsp+38h+arg_8]
0x180030a09  add     rsp, 30h
0x180030a0d  pop     rdi
0x180030a0e  retn
```
