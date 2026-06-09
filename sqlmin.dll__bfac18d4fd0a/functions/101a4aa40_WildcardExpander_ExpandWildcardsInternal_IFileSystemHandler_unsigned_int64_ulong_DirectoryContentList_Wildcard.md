# WildcardExpander::ExpandWildcardsInternal(IFileSystemHandler *,unsigned __int64,ulong,DirectoryContentList *,WildcardExpander::WildcardExpansionStatistics *,int,wchar_t const *,wchar_t const *,FCBDirectoryListingDirectives *)

- ea: `0x101a4aa40`
- end: `0x101a4be55`
- name: `?ExpandWildcardsInternal@WildcardExpander@@AEBAKPEAVIFileSystemHandler@@_KKPEAVDirectoryContentList@@PEAUWildcardExpansionStatistics@1@HPEB_W4PEAUFCBDirectoryListingDirectives@@@Z`
- size: `5141`
- prototype: `unsigned int __usercall@<eax>(WildcardExpander *__hidden this@<rcx>, struct IFileSystemHandler *@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, struct DirectoryContentList *, struct WildcardExpander::WildcardExpansionStatistics *, int, const wchar_t *, const wchar_t *, struct FCBDirectoryListingDirectives *)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x101a49d40`

## callees

- `0x100401010`
- `0x100401490`
- `0x100472800`
- `0x100553e20`
- `0x100553eb0`
- `0x1010b2210`
- `0x101667e10`
- `0x101668290`
- `0x101669c00`
- `0x101669d30`
- `0x10166a8b0`
- `0x1017af1b0`
- `0x101a48830`
- `0x101a48e50`
- `0x101a49270`
- `0x101a497b0`
- `0x101a4aa40`
- `0x101a4c410`
- `0x101a4c980`
- `0x101a4cad0`
- `0x101a4cc20`
- `0x101a4cc50`
- `0x101a4cd20`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101a4adf4`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4ae65`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b00a`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b205`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b2b4`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b4e3`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b621`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b6bd`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4adf4`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4ae65`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b00a`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b205`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b2b4`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b4e3`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b621`
- `KERNEL32!QueryPerformanceCounter` at `0x101a4b6bd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4ade4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4ae08`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4ae8e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4affa`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b033`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b1f5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b23b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b2a4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b2dd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b4d3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b611`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b64e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b6ad`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101a4b6ea`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101a4ae2a`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101a4ae9a`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101a4b03f`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101a4b258`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101a4b2e9`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101a4b65a`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101a4b6f6`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x101a4b55d`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x101a4b55d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4ad94`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4ba5a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4ad94`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4ba5a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4ab47`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4acf0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4bb26`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4ab47`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4acf0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101a4bb26`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101a4b59c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101a4b845`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101a4bd76`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101a4b59c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101a4b845`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101a4bd76`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4ac50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4aed7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4afe7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b07c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b31f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b733`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b9e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4bafa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4ac50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4aed7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4afe7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b07c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b31f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b733`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4b9e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101a4bafa`
- `sqldk!SystemThread_TlsIndex` at `0x101a4b32e`
- `sqldk!SystemThread_TlsIndex` at `0x101a4b375`
- `sqldk!SystemThread_TlsIndex` at `0x101a4b3d8`
- `sqldk!SystemThread_TlsIndex` at `0x101a4b416`
- `sqldk!SystemThread_TlsOffset` at `0x101a4b337`
- `sqldk!SystemThread_TlsOffset` at `0x101a4b37e`
- `sqldk!SystemThread_TlsOffset` at `0x101a4b3e1`
- `sqldk!SystemThread_TlsOffset` at `0x101a4b41f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b1a0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b800`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b8a0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b970`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bc5b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bd22`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bdad`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bdde`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4be1d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b1a0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b800`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b8a0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4b970`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bc5b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bd22`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bdad`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4bdde`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101a4be1d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b352`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b3a4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b43a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b519`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b352`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b3a4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b43a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101a4b519`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4ada4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b192`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b7f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b892`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b962`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b9f0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4ba81`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bab4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bb92`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bcc0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bd2d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bd9f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bdd0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4be0f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4ada4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b192`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b7f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b892`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b962`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4b9f0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4ba81`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bab4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bb92`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bcc0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bd2d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bd9f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4bdd0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101a4be0f`
- `VCRUNTIME140!wcschr` at `0x101a4ba14`
- `VCRUNTIME140!wcschr` at `0x101a4ba14`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x101a4ba74`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x101a4ba74`
- `sqllang!?IsDataVirtualizationFeatureSetLockdownEnabled@DataVirtualizationResource@@YA_NXZ` at `0x101a4aade`
- `sqllang!?IsDataVirtualizationFeatureSetLockdownEnabled@DataVirtualizationResource@@YA_NXZ` at `0x101a4b902`
- `sqllang!?IsDataVirtualizationFeatureSetLockdownEnabled@DataVirtualizationResource@@YA_NXZ` at `0x101a4aade`
- `sqllang!?IsDataVirtualizationFeatureSetLockdownEnabled@DataVirtualizationResource@@YA_NXZ` at `0x101a4b902`

## string_xrefs

- `0x101a4b839`: `itemTokenList.CLength() <= m_inputTokensList.CLength()`

## pseudocode

```c

```
