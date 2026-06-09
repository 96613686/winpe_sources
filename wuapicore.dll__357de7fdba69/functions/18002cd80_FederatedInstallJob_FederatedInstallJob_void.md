# FederatedInstallJob::~FederatedInstallJob(void)

- ea: `0x18002cd80`
- end: `0x18002cee9`
- name: `??1FederatedInstallJob@@UEAA@XZ`
- size: `361`
- prototype: `void __fastcall(FederatedInstallJob *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18002c9ac`
- `0x18002d0f0`

## callees

- `0x18001b6e4`
- `0x18002c5c0`
- `0x18002c6d0`
- `0x18002c790`
- `0x18002cd80`
- `0x180081a38`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cdc6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cdc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cdda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cdf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cdda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cdf3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce53`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce67`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce53`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce67`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FederatedInstallJob::~FederatedInstallJob(FederatedInstallJob *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx

  CSusArrayList<CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::_tagMapEntry,CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::_tagMapEntry,CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::CMapEntryOps>((char *)this + 928);
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,unsigned long,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned long>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,unsigned long,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned long>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,unsigned long,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned long>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,unsigned long,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned long>>::CMapEntryOps>((char *)this + 896);
  CSusArrayList<CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::_tagMapEntry,CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::_tagMapEntry,CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::CMapEntryOps>((char *)this + 864);
  *((_QWORD *)this + 102) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
  v2 = (void *)*((_QWORD *)this + 101);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 101) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 100);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 100) = 0;
  }
  v4 = *((_QWORD *)this + 99);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 98) = 0;
  v5 = *((_QWORD *)this + 96);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 95) = 0;
  SysFreeString(*((BSTR *)this + 91));
  *((_QWORD *)this + 91) = 0;
  SysFreeString(*((BSTR *)this + 90));
  *((_QWORD *)this + 90) = 0;
  SysFreeString(*((BSTR *)this + 89));
  *((_QWORD *)this + 89) = 0;
  v6 = (void *)*((_QWORD *)this + 88);
  if ( v6 )
  {
    SusFree(v6);
    *((_QWORD *)this + 88) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 87);
  if ( v7 )
  {
    SusFree(v7);
    *((_QWORD *)this + 87) = 0;
  }
  v8 = *((_QWORD *)this + 83);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 83) = 0;
  }
  CInstallationJob::~CInstallationJob(this);
}

```

## disassembly

```asm
0x18002cd80  mov     [rsp+arg_0], rbx
0x18002cd85  push    rdi
0x18002cd86  sub     rsp, 20h
0x18002cd8a  mov     rbx, rcx
0x18002cd8d  add     rcx, 3A0h
0x18002cd94  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAUInstallationJobSummary@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAUInstallationJobSummary@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::_tagMapEntry,CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::_tagMapEntry,CSusMap<_GUID,InstallationJobSummary *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<InstallationJobSummary *>>::CMapEntryOps>(void)
0x18002cd99  lea     rcx, [rbx+380h]
0x18002cda0  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@KV?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@V?$CSusArrayListItemOpNoop@K@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<tagDSGlobalUpdateId,ulong,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<ulong>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,ulong,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<ulong>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,ulong,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<ulong>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,ulong,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<ulong>>::CMapEntryOps>(void)
0x18002cda5  lea     rcx, [rbx+360h]
0x18002cdac  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@UPerServiceInstallData@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@VCSusArrayListItemOpPerServiceInstallDataFree@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::_tagMapEntry,CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::_tagMapEntry,CSusMap<_GUID,PerServiceInstallData,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpPerServiceInstallDataFree>::CMapEntryOps>(void)
0x18002cdb1  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x18002cdb8  mov     [rbx+330h], rax
0x18002cdbf  lea     rcx, [rbx+338h]; lpCriticalSection
0x18002cdc6  call    cs:__imp_DeleteCriticalSection
0x18002cdcc  mov     rcx, [rbx+328h]; hObject
0x18002cdd3  xor     edi, edi
0x18002cdd5  test    rcx, rcx
0x18002cdd8  jz      short loc_18002CDE7
0x18002cdda  call    cs:__imp_CloseHandle
0x18002cde0  mov     [rbx+328h], rdi
0x18002cde7  mov     rcx, [rbx+320h]; hObject
0x18002cdee  test    rcx, rcx
0x18002cdf1  jz      short loc_18002CE00
0x18002cdf3  call    cs:__imp_CloseHandle
0x18002cdf9  mov     [rbx+320h], rdi
0x18002ce00  mov     rcx, [rbx+318h]
0x18002ce07  test    rcx, rcx
0x18002ce0a  jz      short loc_18002CE18
0x18002ce0c  mov     rax, [rcx]
0x18002ce0f  mov     rax, [rax+10h]
0x18002ce13  call    _guard_dispatch_icall
0x18002ce18  mov     [rbx+318h], rdi
0x18002ce1f  mov     [rbx+310h], rdi
0x18002ce26  mov     rcx, [rbx+300h]
0x18002ce2d  test    rcx, rcx
0x18002ce30  jz      short loc_18002CE3E
0x18002ce32  mov     rax, [rcx]
0x18002ce35  mov     rax, [rax+10h]
0x18002ce39  call    _guard_dispatch_icall
0x18002ce3e  mov     [rbx+300h], rdi
0x18002ce45  mov     [rbx+2F8h], rdi
0x18002ce4c  mov     rcx, [rbx+2D8h]; bstrString
0x18002ce53  call    cs:__imp_SysFreeString
0x18002ce59  mov     [rbx+2D8h], rdi
0x18002ce60  mov     rcx, [rbx+2D0h]; bstrString
0x18002ce67  call    cs:__imp_SysFreeString
0x18002ce6d  mov     [rbx+2D0h], rdi
0x18002ce74  mov     rcx, [rbx+2C8h]; bstrString
0x18002ce7b  call    cs:__imp_SysFreeString
0x18002ce81  mov     [rbx+2C8h], rdi
0x18002ce88  mov     rcx, [rbx+2C0h]; lpMem
0x18002ce8f  test    rcx, rcx
0x18002ce92  jz      short loc_18002CEA0
0x18002ce94  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002ce99  mov     [rbx+2C0h], rdi
0x18002cea0  mov     rcx, [rbx+2B8h]; lpMem
0x18002cea7  test    rcx, rcx
0x18002ceaa  jz      short loc_18002CEB8
0x18002ceac  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002ceb1  mov     [rbx+2B8h], rdi
0x18002ceb8  mov     rcx, [rbx+298h]
0x18002cebf  test    rcx, rcx
0x18002cec2  jz      short loc_18002CED7
0x18002cec4  mov     rax, [rcx]
0x18002cec7  mov     rax, [rax+10h]
0x18002cecb  call    _guard_dispatch_icall
0x18002ced0  mov     [rbx+298h], rdi
0x18002ced7  mov     rcx, rbx; this
0x18002ceda  mov     rbx, [rsp+28h+arg_0]
0x18002cedf  add     rsp, 20h
0x18002cee3  pop     rdi
0x18002cee4  jmp     ??1CInstallationJob@@UEAA@XZ; CInstallationJob::~CInstallationJob(void)
```
