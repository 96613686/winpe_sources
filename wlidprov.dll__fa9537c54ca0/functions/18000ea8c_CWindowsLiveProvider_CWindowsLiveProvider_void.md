# CWindowsLiveProvider::~CWindowsLiveProvider(void)

- ea: `0x18000ea8c`
- end: `0x18000ead1`
- name: `??1CWindowsLiveProvider@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CWindowsLiveProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ccac`

## callees

- `0x18000ea8c`
- `0x18000ebc4`
- `0x18000ec10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eaa8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eac5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eaa8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eac5`

## pseudocode

```c
void __fastcall CWindowsLiveProvider::~CWindowsLiveProvider(CWindowsLiveProvider *this)
{
  CAutoRefPtr<SmartWLIDHandle>::Deinit((char *)this + 224);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  ATL::CAtlMap<unsigned long,CWLIDNotifyItem *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CWLIDNotifyItem *>>::RemoveAll((char *)this + 104);
  if ( *((_BYTE *)this + 96) )
  {
    *((_BYTE *)this + 96) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  }
}

```

## disassembly

```asm
0x18000ea8c  push    rbx
0x18000ea8e  sub     rsp, 20h
0x18000ea92  mov     rbx, rcx
0x18000ea95  add     rcx, 0E0h
0x18000ea9c  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18000eaa1  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18000eaa8  call    cs:__imp_DeleteCriticalSection
0x18000eaae  lea     rcx, [rbx+68h]
0x18000eab2  call    ?RemoveAll@?$CAtlMap@KPEAVCWLIDNotifyItem@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCWLIDNotifyItem@@@3@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CWLIDNotifyItem *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CWLIDNotifyItem *>>::RemoveAll(void)
0x18000eab7  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000eabb  cmp     byte ptr [rcx+28h], 0
0x18000eabf  jz      short loc_18000EACB
0x18000eac1  mov     byte ptr [rcx+28h], 0
0x18000eac5  call    cs:__imp_DeleteCriticalSection
0x18000eacb  add     rsp, 20h
0x18000eacf  pop     rbx
0x18000ead0  retn
```
