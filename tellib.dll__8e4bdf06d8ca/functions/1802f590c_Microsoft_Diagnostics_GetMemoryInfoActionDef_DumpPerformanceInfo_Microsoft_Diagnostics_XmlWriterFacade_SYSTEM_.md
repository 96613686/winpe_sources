# Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpPerformanceInfo(Microsoft::Diagnostics::XmlWriterFacade &,_SYSTEM_PERFORMANCE_INFORMATION const &,_PERFORMANCE_INFORMATION const &,_EDP_ENFORCEMENT_LEVEL)

- ea: `0x1802f590c`
- end: `0x1802f6f9e`
- name: `?DumpPerformanceInfo@GetMemoryInfoActionDef@Diagnostics@Microsoft@@CAXAEAVXmlWriterFacade@23@AEBU_SYSTEM_PERFORMANCE_INFORMATION@@AEBU_PERFORMANCE_INFORMATION@@W4_EDP_ENFORCEMENT_LEVEL@@@Z`
- size: `5778`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802f7410`

## callees

- `0x1800b2d34`
- `0x1800daaac`
- `0x1802e50d0`
- `0x1802e5560`
- `0x1802e5670`

## string_xrefs

- `0x1802f592c`: `systemperformanceinfo`
- `0x1802f5a69`: `IoWriteOperationCount`
- `0x1802f5b1e`: `CommittedPages`
- `0x1802f59be`: `IoWriteTransferCount`
- `0x1802f5988`: `IoReadTransferCount`
- `0x1802f5a2e`: `IoReadOperationCount`
- `0x1802f5c94`: `CacheTransitionCount`
- `0x1802f5d49`: `PageReadIoCount`
- `0x1802f5d0a`: `PageReadCount`
- `0x1802f5b9c`: `PeakCommitment`
- `0x1802f5b5d`: `CommitLimit`
- `0x1802f6cb4`: `CommitLimit`
- `0x1802f5c1a`: `CopyOnWriteCount`
- `0x1802f5eba`: `MappedWriteIoCount`
- `0x1802f5e7f`: `MappedPagesWriteCount`
- `0x1802f5dc6`: `CacheIoCount`
- `0x1802f5d87`: `CacheReadCount`
- `0x1802f5e40`: `DirtyWriteIoCount`
- `0x1802f5e05`: `DirtyPagesWriteCount`
- `0x1802f60aa`: `ResidentSystemCodePage`
- `0x1802f606c`: `FreeSystemPtes`
- `0x1802f62a6`: `ResidentSystemDriverPage`
- `0x1802f626c`: `ResidentPagedPoolPage`
- `0x1802f632a`: `CcFastReadWait`
- `0x1802f62e8`: `CcFastReadNoWait`
- `0x1802f61ae`: `PagedPoolLookasideHits`
- `0x1802f616c`: `NonPagedPoolLookasideHits`
- `0x1802f622e`: `ResidentSystemCachePage`
- `0x1802f64ac`: `CcFastMdlReadNotPossible`
- `0x1802f646e`: `CcFastMdlReadResourceMiss`
- `0x1802f63ae`: `CcFastReadNotPossible`
- `0x1802f636c`: `CcFastReadResourceMiss`
- `0x1802f642b`: `CcFastMdlReadWait`
- `0x1802f63ed`: `CcFastMdlReadNoWait`
- `0x1802f66ab`: `CcPinReadNoWaitMiss`
- `0x1802f666d`: `CcPinReadWait`
- `0x1802f6722`: `CcCopyReadNoWait`
- `0x1802f66e8`: `CcPinReadWaitMiss`
- `0x1802f662b`: `CcPinReadNoWait`
- `0x1802f68ae`: `CcMdlReadNoWaitMiss`
- `0x1802f686c`: `CcMdlReadWait`
- `0x1802f692e`: `CcReadAheadIos`
- `0x1802f68f0`: `CcMdlReadWaitMiss`
- `0x1802f67a6`: `CcCopyReadNoWaitMiss`
- `0x1802f6764`: `CcCopyReadWait`
- `0x1802f682a`: `CcMdlReadNoWait`
- `0x1802f67e8`: `CcCopyReadWaitMiss`
- `0x1802f69b2`: `CcLazyWritePages`
- `0x1802f6970`: `CcLazyWriteIos`
- `0x1802f6cef`: `CommitPeak`
- `0x1802f6da0`: `SystemCache`
- `0x1802f6bf7`: `ResidentAvailablePages`
- `0x1802f6c75`: `CommitTotal`
- `0x1802f6c34`: `SharedCommittedPages`
- `0x1802f6f18`: `ThreadCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpPerformanceInfo(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  const wchar_t *v8; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+38h] [rbp-30h]
  const wchar_t *v10; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h]
  _BYTE v12[24]; // [rsp+50h] [rbp-18h] BYREF
  int v13; // [rsp+C8h] [rbp+60h] BYREF

  v8 = L"systemperformanceinfo";
  v9 = 21;
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a1, v12, &v8);
  v8 = L"IdleProcessTime";
  v9 = 15;
  v10 = L"info";
  v11 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v10, &v8, a2);
  v10 = L"IoReadTransferCount";
  v11 = 19;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 8);
  v10 = L"IoWriteTransferCount";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 16);
  v10 = L"IoOtherTransferCount";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 24);
  v10 = L"IoReadOperationCount";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 32,
    0);
  v10 = L"IoWriteOperationCount";
  v11 = 21;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 36,
    0);
  v10 = L"IoOtherOperationCount";
  v11 = 21;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 40,
    0);
  v10 = L"AvailablePages";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 44,
    0);
  v10 = L"CommittedPages";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 48,
    0);
  v10 = L"CommitLimit";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 52,
    0);
  v10 = L"PeakCommitment";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 56,
    0);
  v10 = L"PageFaultCount";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 60,
    0);
  v10 = L"CopyOnWriteCount";
  v11 = 16;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 64,
    0);
  v10 = L"TransitionCount";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 68,
    0);
  v10 = L"CacheTransitionCount";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 72,
    0);
  v10 = L"DemandZeroCount";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 76,
    0);
  v10 = L"PageReadCount";
  v11 = 13;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 80,
    0);
  v10 = L"PageReadIoCount";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 84,
    0);
  v10 = L"CacheReadCount";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 88,
    0);
  v10 = L"CacheIoCount";
  v11 = 12;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 92,
    0);
  v10 = L"DirtyPagesWriteCount";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 96,
    0);
  v10 = L"DirtyWriteIoCount";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 100,
    0);
  v10 = L"MappedPagesWriteCount";
  v11 = 21;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 104,
    0);
  v10 = L"MappedWriteIoCount";
  v11 = 18;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 108,
    0);
  v10 = L"PagedPoolPages";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 112,
    0);
  v10 = L"NonPagedPoolPages";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 116,
    0);
  v10 = L"PagedPoolAllocs";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 120,
    0);
  v10 = L"PagedPoolFrees";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 124,
    0);
  v10 = L"NonPagedPoolAllocs";
  v11 = 18;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 128,
    0);
  v10 = L"NonPagedPoolFrees";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 132,
    0);
  v10 = L"FreeSystemPtes";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 136,
    0);
  v10 = L"ResidentSystemCodePage";
  v11 = 22;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 140,
    0);
  v10 = L"TotalSystemDriverPages";
  v11 = 22;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 144,
    0);
  v10 = L"TotalSystemCodePages";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 148,
    0);
  v10 = L"NonPagedPoolLookasideHits";
  v11 = 25;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 152,
    0);
  v10 = L"PagedPoolLookasideHits";
  v11 = 22;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 156,
    0);
  v10 = L"AvailablePagedPoolPages";
  v11 = 23;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 160,
    0);
  v10 = L"ResidentSystemCachePage";
  v11 = 23;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 164,
    0);
  v10 = L"ResidentPagedPoolPage";
  v11 = 21;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 168,
    0);
  v10 = L"ResidentSystemDriverPage";
  v11 = 24;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 172,
    0);
  v10 = L"CcFastReadNoWait";
  v11 = 16;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 176,
    0);
  v10 = L"CcFastReadWait";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 180,
    0);
  v10 = L"CcFastReadResourceMiss";
  v11 = 22;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 184,
    0);
  v10 = L"CcFastReadNotPossible";
  v11 = 21;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 188,
    0);
  v10 = L"CcFastMdlReadNoWait";
  v11 = 19;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 192,
    0);
  v10 = L"CcFastMdlReadWait";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 196,
    0);
  v10 = L"CcFastMdlReadResourceMiss";
  v11 = 25;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 200,
    0);
  v10 = L"CcFastMdlReadNotPossible";
  v11 = 24;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 204,
    0);
  v10 = L"CcMapDataNoWait";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 208,
    0);
  v10 = L"CcMapDataWait";
  v11 = 13;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 212,
    0);
  v10 = L"CcMapDataNoWaitMiss";
  v11 = 19;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 216,
    0);
  v10 = L"CcMapDataWaitMiss";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 220,
    0);
  v10 = L"CcPinMappedDataCount";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 224,
    0);
  v10 = L"CcPinReadNoWait";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 228,
    0);
  v10 = L"CcPinReadWait";
  v11 = 13;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 232,
    0);
  v10 = L"CcPinReadNoWaitMiss";
  v11 = 19;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 236,
    0);
  v10 = L"CcPinReadWaitMiss";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 240,
    0);
  v10 = L"CcCopyReadNoWait";
  v11 = 16;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 244,
    0);
  v10 = L"CcCopyReadWait";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 248,
    0);
  v10 = L"CcCopyReadNoWaitMiss";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 252,
    0);
  v10 = L"CcCopyReadWaitMiss";
  v11 = 18;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 256,
    0);
  v10 = L"CcMdlReadNoWait";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 260,
    0);
  v10 = L"CcMdlReadWait";
  v11 = 13;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 264,
    0);
  v10 = L"CcMdlReadNoWaitMiss";
  v11 = 19;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 268,
    0);
  v10 = L"CcMdlReadWaitMiss";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 272,
    0);
  v10 = L"CcReadAheadIos";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 276,
    0);
  v10 = L"CcLazyWriteIos";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 280,
    0);
  v10 = L"CcLazyWritePages";
  v11 = 16;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 284,
    0);
  v10 = L"CcDataFlushes";
  v11 = 13;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 288,
    0);
  v10 = L"CcDataPages";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 292,
    0);
  v10 = L"ContextSwitches";
  v11 = 15;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 296,
    0);
  v10 = L"FirstLevelTbFills";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 300,
    0);
  v10 = L"SecondLevelTbFills";
  v11 = 18;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 304,
    0);
  v10 = L"SystemCalls";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 308,
    0);
  v10 = L"CcTotalDirtyPages";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 312,
    0);
  v10 = L"CcDirtyPageThreshold";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 320,
    0);
  v10 = L"ResidentAvailablePages";
  v11 = 22;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 328);
  v10 = L"SharedCommittedPages";
  v11 = 20;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 336,
    0);
  v10 = L"CommitTotal";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 8,
    0);
  v10 = L"CommitLimit";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 16,
    0);
  v10 = L"CommitPeak";
  v11 = 10;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 24,
    0);
  v10 = L"PhysicalTotal";
  v11 = 13;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 32,
    0);
  v10 = L"PhysicalAvailable";
  v11 = 17;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 40,
    0);
  v10 = L"SystemCache";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 48,
    0);
  v10 = L"KernelTotal";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 56,
    0);
  v10 = L"KernelPaged";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 64,
    0);
  v10 = L"KernelNonpaged";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 72,
    0);
  v10 = L"PageSize";
  v11 = 8;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 80,
    0);
  v10 = L"HandleCount";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 88,
    0);
  v10 = L"ProcessCount";
  v11 = 12;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 92,
    0);
  v10 = L"ThreadCount";
  v11 = 11;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 96,
    0);
  v13 = a4;
  v10 = L"EdpEnforcement";
  v11 = 14;
  v8 = L"info";
  v9 = 4;
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    (unsigned int)&v13,
    0);
  Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v12);
}

```

## disassembly

```asm
0x1802f590c  push    rbp
0x1802f590e  push    rbx
0x1802f590f  push    rsi
0x1802f5910  push    rdi
0x1802f5911  push    r12
0x1802f5913  push    r13
0x1802f5915  push    r14
0x1802f5917  push    r15
0x1802f5919  mov     rbp, rsp
0x1802f591c  sub     rsp, 68h
0x1802f5920  mov     esi, r9d
0x1802f5923  mov     rdi, r8
0x1802f5926  mov     rbx, rdx
0x1802f5929  mov     r14, rcx
0x1802f592c  lea     rax, aSystemperforma; "systemperformanceinfo"
0x1802f5933  mov     [rbp+var_38], rax
0x1802f5937  mov     r13d, 15h
0x1802f593d  mov     [rbp+var_30], r13
0x1802f5941  lea     r8, [rbp+var_38]
0x1802f5945  lea     rdx, [rbp+var_18]
0x1802f5949  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x1802f594e  nop
0x1802f594f  lea     rax, aIdleprocesstim; "IdleProcessTime"
0x1802f5956  mov     [rbp+var_38], rax
0x1802f595a  lea     r15d, [r13-6]
0x1802f595e  mov     [rbp+var_30], r15
0x1802f5962  lea     rax, aInfo_0; "info"
0x1802f5969  mov     [rbp+var_28], rax
0x1802f596d  lea     r12d, [r13-11h]
0x1802f5971  mov     [rbp+var_20], r12
0x1802f5975  mov     r9, rbx
0x1802f5978  lea     r8, [rbp+var_38]
0x1802f597c  lea     rdx, [rbp+var_28]
0x1802f5980  mov     rcx, r14
0x1802f5983  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1802f5988  lea     rax, aIoreadtransfer; "IoReadTransferCount"
0x1802f598f  mov     [rbp+var_28], rax
0x1802f5993  mov     [rbp+var_20], 13h
0x1802f599b  lea     rax, aInfo_0; "info"
0x1802f59a2  mov     [rbp+var_38], rax
0x1802f59a6  mov     [rbp+var_30], r12
0x1802f59aa  lea     r9, [rbx+8]
0x1802f59ae  lea     r8, [rbp+var_28]
0x1802f59b2  lea     rdx, [rbp+var_38]
0x1802f59b6  mov     rcx, r14
0x1802f59b9  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1802f59be  lea     rax, aIowritetransfe; "IoWriteTransferCount"
0x1802f59c5  mov     [rbp+var_28], rax
0x1802f59c9  lea     r12d, [r13-1]
0x1802f59cd  mov     [rbp+var_20], r12
0x1802f59d1  lea     rax, aInfo_0; "info"
0x1802f59d8  mov     [rbp+var_38], rax
0x1802f59dc  mov     [rbp+var_30], 4
0x1802f59e4  lea     r9, [rbx+10h]
0x1802f59e8  lea     r8, [rbp+var_28]
0x1802f59ec  lea     rdx, [rbp+var_38]
0x1802f59f0  mov     rcx, r14
0x1802f59f3  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1802f59f8  lea     rax, aIoothertransfe; "IoOtherTransferCount"
0x1802f59ff  mov     [rbp+var_28], rax
0x1802f5a03  mov     [rbp+var_20], r12
0x1802f5a07  lea     rax, aInfo_0; "info"
0x1802f5a0e  mov     [rbp+var_38], rax
0x1802f5a12  mov     [rbp+var_30], 4
0x1802f5a1a  lea     r9, [rbx+18h]
0x1802f5a1e  lea     r8, [rbp+var_28]
0x1802f5a22  lea     rdx, [rbp+var_38]
0x1802f5a26  mov     rcx, r14
0x1802f5a29  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1802f5a2e  lea     rax, aIoreadoperatio; "IoReadOperationCount"
0x1802f5a35  mov     [rbp+var_28], rax
0x1802f5a39  mov     [rbp+var_20], r12
0x1802f5a3d  lea     rax, aInfo_0; "info"
0x1802f5a44  mov     [rbp+var_38], rax
0x1802f5a48  mov     [rbp+var_30], 4
0x1802f5a50  lea     r9, [rbx+20h]
0x1802f5a54  mov     [rsp+68h+var_48], 0
0x1802f5a59  lea     r8, [rbp+var_28]
0x1802f5a5d  lea     rdx, [rbp+var_38]
0x1802f5a61  mov     rcx, r14
0x1802f5a64  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5a69  lea     rax, aIowriteoperati; "IoWriteOperationCount"
0x1802f5a70  mov     [rbp+var_28], rax
0x1802f5a74  mov     [rbp+var_20], r13
0x1802f5a78  lea     rax, aInfo_0; "info"
0x1802f5a7f  mov     [rbp+var_38], rax
0x1802f5a83  mov     [rbp+var_30], 4
0x1802f5a8b  lea     r9, [rbx+24h]
0x1802f5a8f  mov     [rsp+68h+var_48], 0
0x1802f5a94  lea     r8, [rbp+var_28]
0x1802f5a98  lea     rdx, [rbp+var_38]
0x1802f5a9c  mov     rcx, r14
0x1802f5a9f  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5aa4  lea     rax, aIootheroperati; "IoOtherOperationCount"
0x1802f5aab  mov     [rbp+var_28], rax
0x1802f5aaf  mov     [rbp+var_20], r13
0x1802f5ab3  lea     rax, aInfo_0; "info"
0x1802f5aba  mov     [rbp+var_38], rax
0x1802f5abe  mov     [rbp+var_30], 4
0x1802f5ac6  lea     r9, [rbx+28h]
0x1802f5aca  mov     [rsp+68h+var_48], 0
0x1802f5acf  lea     r8, [rbp+var_28]
0x1802f5ad3  lea     rdx, [rbp+var_38]
0x1802f5ad7  mov     rcx, r14
0x1802f5ada  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5adf  lea     rax, aAvailablepages; "AvailablePages"
0x1802f5ae6  mov     [rbp+var_28], rax
0x1802f5aea  mov     [rbp+var_20], 0Eh
0x1802f5af2  lea     rax, aInfo_0; "info"
0x1802f5af9  mov     [rbp+var_38], rax
0x1802f5afd  mov     [rbp+var_30], 4
0x1802f5b05  lea     r9, [rbx+2Ch]
0x1802f5b09  mov     [rsp+68h+var_48], 0
0x1802f5b0e  lea     r8, [rbp+var_28]
0x1802f5b12  lea     rdx, [rbp+var_38]
0x1802f5b16  mov     rcx, r14
0x1802f5b19  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5b1e  lea     rax, aCommittedpages; "CommittedPages"
0x1802f5b25  mov     [rbp+var_28], rax
0x1802f5b29  mov     [rbp+var_20], 0Eh
0x1802f5b31  lea     rax, aInfo_0; "info"
0x1802f5b38  mov     [rbp+var_38], rax
0x1802f5b3c  mov     [rbp+var_30], 4
0x1802f5b44  lea     r9, [rbx+30h]
0x1802f5b48  mov     [rsp+68h+var_48], 0
0x1802f5b4d  lea     r8, [rbp+var_28]
0x1802f5b51  lea     rdx, [rbp+var_38]
0x1802f5b55  mov     rcx, r14
0x1802f5b58  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5b5d  lea     rax, aCommitlimit; "CommitLimit"
0x1802f5b64  mov     [rbp+var_28], rax
0x1802f5b68  mov     [rbp+var_20], 0Bh
0x1802f5b70  lea     rax, aInfo_0; "info"
0x1802f5b77  mov     [rbp+var_38], rax
0x1802f5b7b  mov     [rbp+var_30], 4
0x1802f5b83  lea     r9, [rbx+34h]
0x1802f5b87  mov     [rsp+68h+var_48], 0
0x1802f5b8c  lea     r8, [rbp+var_28]
0x1802f5b90  lea     rdx, [rbp+var_38]
0x1802f5b94  mov     rcx, r14
0x1802f5b97  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5b9c  lea     rax, aPeakcommitment; "PeakCommitment"
0x1802f5ba3  mov     [rbp+var_28], rax
0x1802f5ba7  mov     [rbp+var_20], 0Eh
0x1802f5baf  lea     rax, aInfo_0; "info"
0x1802f5bb6  mov     [rbp+var_38], rax
0x1802f5bba  mov     [rbp+var_30], 4
0x1802f5bc2  lea     r9, [rbx+38h]
0x1802f5bc6  mov     [rsp+68h+var_48], 0
0x1802f5bcb  lea     r8, [rbp+var_28]
0x1802f5bcf  lea     rdx, [rbp+var_38]
0x1802f5bd3  mov     rcx, r14
0x1802f5bd6  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5bdb  lea     rax, aPagefaultcount; "PageFaultCount"
0x1802f5be2  mov     [rbp+var_28], rax
0x1802f5be6  mov     [rbp+var_20], 0Eh
0x1802f5bee  lea     rax, aInfo_0; "info"
0x1802f5bf5  mov     [rbp+var_38], rax
0x1802f5bf9  mov     [rbp+var_30], 4
0x1802f5c01  lea     r9, [rbx+3Ch]
0x1802f5c05  mov     [rsp+68h+var_48], 0
0x1802f5c0a  lea     r8, [rbp+var_28]
0x1802f5c0e  lea     rdx, [rbp+var_38]
0x1802f5c12  mov     rcx, r14
0x1802f5c15  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5c1a  lea     rax, aCopyonwritecou; "CopyOnWriteCount"
0x1802f5c21  mov     [rbp+var_28], rax
0x1802f5c25  mov     [rbp+var_20], 10h
0x1802f5c2d  lea     rax, aInfo_0; "info"
0x1802f5c34  mov     [rbp+var_38], rax
0x1802f5c38  mov     [rbp+var_30], 4
0x1802f5c40  lea     r9, [rbx+40h]
0x1802f5c44  mov     [rsp+68h+var_48], 0
0x1802f5c49  lea     r8, [rbp+var_28]
0x1802f5c4d  lea     rdx, [rbp+var_38]
0x1802f5c51  mov     rcx, r14
0x1802f5c54  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5c59  lea     rax, aTransitioncoun; "TransitionCount"
0x1802f5c60  mov     [rbp+var_28], rax
0x1802f5c64  mov     [rbp+var_20], r15
0x1802f5c68  lea     rax, aInfo_0; "info"
0x1802f5c6f  mov     [rbp+var_38], rax
0x1802f5c73  mov     [rbp+var_30], 4
0x1802f5c7b  lea     r9, [rbx+44h]
0x1802f5c7f  mov     [rsp+68h+var_48], 0
0x1802f5c84  lea     r8, [rbp+var_28]
0x1802f5c88  lea     rdx, [rbp+var_38]
0x1802f5c8c  mov     rcx, r14
0x1802f5c8f  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5c94  lea     rax, aCachetransitio; "CacheTransitionCount"
0x1802f5c9b  mov     [rbp+var_28], rax
0x1802f5c9f  mov     [rbp+var_20], r12
0x1802f5ca3  lea     rax, aInfo_0; "info"
0x1802f5caa  mov     [rbp+var_38], rax
0x1802f5cae  mov     [rbp+var_30], 4
0x1802f5cb6  lea     r9, [rbx+48h]
0x1802f5cba  mov     [rsp+68h+var_48], 0
0x1802f5cbf  lea     r8, [rbp+var_28]
0x1802f5cc3  lea     rdx, [rbp+var_38]
0x1802f5cc7  mov     rcx, r14
0x1802f5cca  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5ccf  lea     rax, aDemandzerocoun; "DemandZeroCount"
0x1802f5cd6  mov     [rbp+var_28], rax
0x1802f5cda  mov     [rbp+var_20], r15
0x1802f5cde  lea     rax, aInfo_0; "info"
0x1802f5ce5  mov     [rbp+var_38], rax
0x1802f5ce9  mov     [rbp+var_30], 4
0x1802f5cf1  lea     r9, [rbx+4Ch]
0x1802f5cf5  mov     [rsp+68h+var_48], 0
0x1802f5cfa  lea     r8, [rbp+var_28]
0x1802f5cfe  lea     rdx, [rbp+var_38]
0x1802f5d02  mov     rcx, r14
0x1802f5d05  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5d0a  lea     rax, aPagereadcount; "PageReadCount"
0x1802f5d11  mov     [rbp+var_28], rax
0x1802f5d15  mov     [rbp+var_20], 0Dh
0x1802f5d1d  lea     rax, aInfo_0; "info"
0x1802f5d24  mov     [rbp+var_38], rax
0x1802f5d28  mov     [rbp+var_30], 4
0x1802f5d30  lea     r9, [rbx+50h]
0x1802f5d34  mov     [rsp+68h+var_48], 0
0x1802f5d39  lea     r8, [rbp+var_28]
0x1802f5d3d  lea     rdx, [rbp+var_38]
0x1802f5d41  mov     rcx, r14
0x1802f5d44  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5d49  lea     rax, aPagereadiocoun; "PageReadIoCount"
0x1802f5d50  mov     [rbp+var_28], rax
0x1802f5d54  mov     [rbp+var_20], r15
0x1802f5d58  lea     rax, aInfo_0; "info"
0x1802f5d5f  mov     [rbp+var_38], rax
0x1802f5d63  mov     [rbp+var_30], 4
0x1802f5d6b  lea     r9, [rbx+54h]
0x1802f5d6f  xor     r15d, r15d
0x1802f5d72  mov     [rsp+68h+var_48], r15b
0x1802f5d77  lea     r8, [rbp+var_28]
0x1802f5d7b  lea     rdx, [rbp+var_38]
0x1802f5d7f  mov     rcx, r14
0x1802f5d82  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5d87  lea     rax, aCachereadcount; "CacheReadCount"
0x1802f5d8e  mov     [rbp+var_28], rax
0x1802f5d92  mov     [rbp+var_20], 0Eh
0x1802f5d9a  lea     rax, aInfo_0; "info"
0x1802f5da1  mov     [rbp+var_38], rax
0x1802f5da5  mov     [rbp+var_30], 4
0x1802f5dad  lea     r9, [rbx+58h]
0x1802f5db1  mov     [rsp+68h+var_48], r15b
0x1802f5db6  lea     r8, [rbp+var_28]
0x1802f5dba  lea     rdx, [rbp+var_38]
0x1802f5dbe  mov     rcx, r14
0x1802f5dc1  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5dc6  lea     rax, aCacheiocount; "CacheIoCount"
0x1802f5dcd  mov     [rbp+var_28], rax
0x1802f5dd1  mov     [rbp+var_20], 0Ch
0x1802f5dd9  lea     rax, aInfo_0; "info"
0x1802f5de0  mov     [rbp+var_38], rax
0x1802f5de4  mov     [rbp+var_30], 4
0x1802f5dec  lea     r9, [rbx+5Ch]
0x1802f5df0  mov     [rsp+68h+var_48], r15b
0x1802f5df5  lea     r8, [rbp+var_28]
0x1802f5df9  lea     rdx, [rbp+var_38]
0x1802f5dfd  mov     rcx, r14
0x1802f5e00  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5e05  lea     rax, aDirtypageswrit; "DirtyPagesWriteCount"
0x1802f5e0c  mov     [rbp+var_28], rax
0x1802f5e10  mov     [rbp+var_20], r12
0x1802f5e14  lea     rax, aInfo_0; "info"
0x1802f5e1b  mov     [rbp+var_38], rax
0x1802f5e1f  mov     [rbp+var_30], 4
0x1802f5e27  lea     r9, [rbx+60h]
0x1802f5e2b  mov     [rsp+68h+var_48], r15b
0x1802f5e30  lea     r8, [rbp+var_28]
0x1802f5e34  lea     rdx, [rbp+var_38]
0x1802f5e38  mov     rcx, r14
0x1802f5e3b  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5e40  lea     rax, aDirtywriteioco; "DirtyWriteIoCount"
0x1802f5e47  mov     [rbp+var_28], rax
0x1802f5e4b  lea     r12d, [r13-4]
0x1802f5e4f  mov     [rbp+var_20], r12
0x1802f5e53  lea     rax, aInfo_0; "info"
0x1802f5e5a  mov     [rbp+var_38], rax
0x1802f5e5e  mov     [rbp+var_30], 4
0x1802f5e66  lea     r9, [rbx+64h]
0x1802f5e6a  mov     [rsp+68h+var_48], r15b
0x1802f5e6f  lea     r8, [rbp+var_28]
0x1802f5e73  lea     rdx, [rbp+var_38]
0x1802f5e77  mov     rcx, r14
0x1802f5e7a  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5e7f  lea     rax, aMappedpageswri; "MappedPagesWriteCount"
0x1802f5e86  mov     [rbp+var_28], rax
0x1802f5e8a  mov     [rbp+var_20], r13
0x1802f5e8e  lea     rax, aInfo_0; "info"
0x1802f5e95  mov     [rbp+var_38], rax
0x1802f5e99  mov     [rbp+var_30], 4
0x1802f5ea1  lea     r9, [rbx+68h]
0x1802f5ea5  mov     [rsp+68h+var_48], r15b
0x1802f5eaa  lea     r8, [rbp+var_28]
0x1802f5eae  lea     rdx, [rbp+var_38]
0x1802f5eb2  mov     rcx, r14
0x1802f5eb5  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f5eba  lea     rax, aMappedwriteioc; "MappedWriteIoCount"
  ... truncated ...
```
