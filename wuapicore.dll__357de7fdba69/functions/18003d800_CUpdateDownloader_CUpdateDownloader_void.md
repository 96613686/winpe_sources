# CUpdateDownloader::~CUpdateDownloader(void)

- ea: `0x18003d800`
- end: `0x18003d929`
- name: `??1CUpdateDownloader@@UEAA@XZ`
- size: `297`
- prototype: `void __fastcall(CUpdateDownloader *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18003d6c4`

## callees

- `0x18001f9b8`
- `0x18003d800`
- `0x180081a38`
- `0x18009b0b8`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003d913`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003d913`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d842`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d85a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d872`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d88a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d85a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d872`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d88a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CUpdateDownloader::~CUpdateDownloader(CUpdateDownloader *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx

  CSusArrayList<CSusMap<_GUID,unsigned long,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<unsigned long>>::_tagMapEntry,CSusMap<_GUID,unsigned long,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<unsigned long>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,unsigned long,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<unsigned long>>::_tagMapEntry,CSusMap<_GUID,unsigned long,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<unsigned long>>::CMapEntryOps>((char *)this + 264);
  v2 = (void *)*((_QWORD *)this + 32);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 32) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 29);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 29) = 0;
  }
  SysFreeString(*((BSTR *)this + 28));
  *((_QWORD *)this + 28) = 0;
  SysFreeString(*((BSTR *)this + 27));
  *((_QWORD *)this + 27) = 0;
  SysFreeString(*((BSTR *)this + 26));
  *((_QWORD *)this + 26) = 0;
  v4 = (void *)*((_QWORD *)this + 25);
  if ( v4 )
  {
    SusFree(v4);
    *((_QWORD *)this + 25) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 24);
  if ( v5 )
  {
    SusFree(v5);
    *((_QWORD *)this + 24) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 23);
  if ( v6 )
  {
    SusFree(v6);
    *((_QWORD *)this + 23) = 0;
  }
  v7 = *((_QWORD *)this + 14);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( *((_BYTE *)this + 104) )
  {
    *((_BYTE *)this + 104) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  }
  *(_QWORD *)this = &CSusBaseAllocTag<1752326505>::`vftable';
}

```

## disassembly

```asm
0x18003d800  push    rbx
0x18003d802  sub     rsp, 20h
0x18003d806  mov     rbx, rcx
0x18003d809  add     rcx, 108h
0x18003d810  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@KV?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpNoop@K@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,ulong,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<ulong>>::_tagMapEntry,CSusMap<_GUID,ulong,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<ulong>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,ulong,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<ulong>>::_tagMapEntry,CSusMap<_GUID,ulong,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<ulong>>::CMapEntryOps>(void)
0x18003d815  mov     rcx, [rbx+100h]; Block
0x18003d81c  test    rcx, rcx
0x18003d81f  jz      short loc_18003D836
0x18003d821  mov     edx, 90h
0x18003d826  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003d82b  mov     qword ptr [rbx+100h], 0
0x18003d836  mov     rcx, [rbx+0E8h]; hObject
0x18003d83d  test    rcx, rcx
0x18003d840  jz      short loc_18003D853
0x18003d842  call    cs:__imp_CloseHandle
0x18003d848  mov     qword ptr [rbx+0E8h], 0
0x18003d853  mov     rcx, [rbx+0E0h]; bstrString
0x18003d85a  call    cs:__imp_SysFreeString
0x18003d860  mov     qword ptr [rbx+0E0h], 0
0x18003d86b  mov     rcx, [rbx+0D8h]; bstrString
0x18003d872  call    cs:__imp_SysFreeString
0x18003d878  mov     qword ptr [rbx+0D8h], 0
0x18003d883  mov     rcx, [rbx+0D0h]; bstrString
0x18003d88a  call    cs:__imp_SysFreeString
0x18003d890  mov     qword ptr [rbx+0D0h], 0
0x18003d89b  mov     rcx, [rbx+0C8h]; lpMem
0x18003d8a2  test    rcx, rcx
0x18003d8a5  jz      short loc_18003D8B7
0x18003d8a7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d8ac  mov     qword ptr [rbx+0C8h], 0
0x18003d8b7  mov     rcx, [rbx+0C0h]; lpMem
0x18003d8be  test    rcx, rcx
0x18003d8c1  jz      short loc_18003D8D3
0x18003d8c3  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d8c8  mov     qword ptr [rbx+0C0h], 0
0x18003d8d3  mov     rcx, [rbx+0B8h]; lpMem
0x18003d8da  test    rcx, rcx
0x18003d8dd  jz      short loc_18003D8EF
0x18003d8df  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d8e4  mov     qword ptr [rbx+0B8h], 0
0x18003d8ef  mov     rcx, [rbx+70h]
0x18003d8f3  test    rcx, rcx
0x18003d8f6  jz      short loc_18003D905
0x18003d8f8  mov     rax, [rcx]
0x18003d8fb  mov     rax, [rax+10h]
0x18003d8ff  call    _guard_dispatch_icall
0x18003d904  nop
0x18003d905  lea     rcx, [rbx+40h]; lpCriticalSection
0x18003d909  cmp     byte ptr [rcx+28h], 0
0x18003d90d  jz      short loc_18003D919
0x18003d90f  mov     byte ptr [rcx+28h], 0
0x18003d913  call    cs:__imp_DeleteCriticalSection
0x18003d919  lea     rax, ??_7?$CSusBaseAllocTag@$0GIHCGBGJ@@@6B@; const CSusBaseAllocTag<1752326505>::`vftable'
0x18003d920  mov     [rbx], rax
0x18003d923  add     rsp, 20h
0x18003d927  pop     rbx
0x18003d928  retn
```
