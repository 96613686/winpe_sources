# CFileScanRuntimeParams::AssembleConfigOptions(IMemObj *,IDataExtractionConfig const *,wchar_t *,wchar_t *,IExtractorLibraryBase const *,_GUID,CRowsetOptions const *)

- ea: `0x1010cdf60`
- end: `0x1010cee55`
- name: `?AssembleConfigOptions@CFileScanRuntimeParams@@CAPEAVIDataExtractionConfig@@PEAVIMemObj@@PEBV2@PEA_W2PEBVIExtractorLibraryBase@@U_GUID@@PEBVCRowsetOptions@@@Z`
- size: `3829`
- prototype: `struct IDataExtractionConfig *__fastcall(struct IMemObj *, const struct IDataExtractionConfig *, wchar_t *, wchar_t *, const struct IExtractorLibraryBase *, GUID *rguid, const struct CRowsetOptions *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1010cd820`

## callees

- `0x100401490`
- `0x1010cdf60`
- `0x10249a6c0`
- `0x10249abe0`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1010ceddd`
- `ole32!StringFromGUID2` at `0x1010ceddd`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1010cdfb1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1010ced50`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1010ced50`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce037`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce150`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce27d`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce353`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce429`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce519`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce5ce`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce6a5`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce817`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce8ed`
- `sqldk!SystemThread_TlsIndex` at `0x1010ce9c3`
- `sqldk!SystemThread_TlsIndex` at `0x1010cea99`
- `sqldk!SystemThread_TlsIndex` at `0x1010cebdd`
- `sqldk!SystemThread_TlsIndex` at `0x1010ced20`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce040`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce159`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce286`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce35c`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce432`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce522`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce5d7`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce6ae`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce820`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce8f6`
- `sqldk!SystemThread_TlsOffset` at `0x1010ce9cc`
- `sqldk!SystemThread_TlsOffset` at `0x1010ceaa2`
- `sqldk!SystemThread_TlsOffset` at `0x1010cebe6`
- `sqldk!SystemThread_TlsOffset` at `0x1010ced29`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce05b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce174`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce2a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce377`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce44d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce53d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce5f2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce6c9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce83b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce911`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce9e7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ceabd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010cec01`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce05b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce174`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce2a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce377`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce44d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce53d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce5f2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce6c9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce83b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce911`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ce9e7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010ceabd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1010cec01`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce0a0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce0c1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce0c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce1c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce2e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce307`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce30f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce3bc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce3dd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce3e5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce492`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce4b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce4bb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce582`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce5a2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce637`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce65c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce70c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce72b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce733`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce87e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce89d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce8a5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce954`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce973`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce97b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cea2a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cea49`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cea51`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceb00`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceb1f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceb27`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceba9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cec44`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cec63`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cec6b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce0a0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce0c1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce0c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce1c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce2e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce307`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce30f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce3bc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce3dd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce3e5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce492`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce4b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce4bb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce582`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce5a2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce637`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce65c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce70c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce72b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce733`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce87e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce89d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce8a5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce954`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce973`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ce97b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cea2a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cea49`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cea51`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceb00`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceb1f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceb27`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010ceba9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cec44`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cec63`
- `sqldk!??_V@YAXPEAX@Z` at `0x1010cec6b`
- `sqllang!?ExtractFromJSON@IDataExtractionConfig@@SAPEAV1@PEAVIMemObj@@PEB_W@Z` at `0x1010cdfd5`
- `sqllang!?ExtractFromJSON@IDataExtractionConfig@@SAPEAV1@PEAVIMemObj@@PEB_W@Z` at `0x1010cdfd5`

## string_xrefs

- `0x1010ce087`: `ExternalLibMaxConcurrentExtractorsPerThread`
- `0x1010ce93c`: `ExternalLibParquetNumChunksReadahead`
- `0x1010ce7b6`: `ReadPrefetch`
- `0x1010ce7dd`: `ReadPrefetch`
- `0x1010ce8c6`: `MaxNumChunkReadaheads`
- `0x1010ce989`: `MaxNumChunkReadaheads`
- `0x1010cdff8`: `ExternalLibMaxConcurrentExtractorsPerThread`
- `0x1010ce0d7`: `ExternalLibMaxConcurrentExtractorsPerThread`
- `0x1010ce0f7`: `ExternalLibMaxConcurrentExtractorsPerThread`
- `0x1010ce1ea`: `ReadPrefetchRelativeChunking`
- `0x1010ce211`: `ReadPrefetchRelativeChunking`
- `0x1010ce224`: `ReissueLongReadRequests`
- `0x1010ce242`: `ReissueLongReadRequests`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
struct IDataExtractionConfig *__fastcall CFileScanRuntimeParams::AssembleConfigOptions(
        struct IMemObj *a1,
        const struct IDataExtractionConfig *a2,
        wchar_t *a3,
        wchar_t *a4,
        const struct IExtractorLibraryBase *a5,
        GUID *rguid,
        const struct CRowsetOptions *a7)
{
  struct IDataExtractionConfig *v8; // rax
  struct IDataExtractionConfig *v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // rsi
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // rsi
  __int64 v18; // r9
  __int64 v19; // rsi
  __int64 v20; // r9
  __int64 v21; // rsi
  __int64 v22; // r9
  char v23; // al
  __int64 v24; // rsi
  __int64 v25; // r9
  __int64 v26; // rsi
  __int64 v27; // r9
  __int64 v28; // rsi
  __int64 v29; // r9
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v32; // rsi
  __int64 v33; // r9
  __int64 v34; // rsi
  __int64 v35; // r9
  __int64 v36; // rsi
  __int64 v37; // r9
  __int64 v38; // rsi
  __int64 v39; // r9
  __int64 v40; // rsi
  __int64 v41; // r9
  __int64 v42; // r9
  __int64 v43; // r9
  __int64 v44; // rax
  struct CSessionTraceFlags *v45; // rcx
  bool v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v49; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h] BYREF
  int v52; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v54; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v55; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v56; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v57; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v58; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v59; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v60; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v62; // [rsp+A8h] [rbp-58h] BYREF
  void *v63[2]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[40]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v65[4]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v66; // [rsp+150h] [rbp+50h]
  int v67; // [rsp+158h] [rbp+58h]
  __int16 v68; // [rsp+15Ch] [rbp+5Ch]

  v63[1] = (void *)-2LL;
  if ( a2 )
    v8 = (struct IDataExtractionConfig *)(*(__int64 (__fastcall **)(const struct IDataExtractionConfig *, struct IMemObj *))(*(_QWORD *)a2 + 8LL))(
                                           a2,
                                           a1);
  else
    v8 = IDataExtractionConfig::ExtractFromJSON(a1, L"{}");
  v9 = v8;
  if ( (**(unsigned __int8 (__fastcall ***)(const struct IExtractorLibraryBase *, __int64))a5)(a5, 7) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"ExternalLibMaxConcurrentExtractorsPerThread")
      && (**(unsigned __int8 (__fastcall ***)(const struct IExtractorLibraryBase *, __int64))a5)(a5, 5) )
    {
      v48 = 1;
      String = 0;
      v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v11 = *(_QWORD *)(v10 + 256);
      if ( !v11 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v11 = *(_QWORD *)(v10 + 256);
      }
      if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
              + 3))(
             *((_QWORD *)s_pServerConf + 3),
             L"ExternalLibraries",
             L"ExternalLibMaxConcurrentExtractorsPerThread",
             *(_QWORD *)(v11 + 1000),
             &String,
             0) )
      {
        if ( DynamicInt64SettingConverter(String, &v48) )
        {
          operator delete[](String);
          (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
            v9,
            a1,
            L"ExternalLibMaxConcurrentExtractorsPerThread",
            (unsigned int)v48);
        }
        else
        {
          operator delete[](String);
        }
      }
      else
      {
        operator delete[](String);
      }
    }
    v52 = 1;
    (*(void (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *, int *))(*(_QWORD *)v9 + 40LL))(
      v9,
      L"ExternalLibMaxConcurrentExtractorsPerThread",
      &v52);
    if ( v52 > 1 )
    {
      LOBYTE(v12) = 1;
      (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, __int64))(*(_QWORD *)v9 + 72LL))(
        v9,
        a1,
        L"UseAsyncInit",
        v12);
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"PrefetchMemoryLimitForAdditionalExtractorsInMB") )
  {
    v48 = 256;
    v54 = 0;
    v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v14 = *(_QWORD *)(v13 + 256);
    if ( !v14 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v14 = *(_QWORD *)(v13 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
            + 3))(
           *((_QWORD *)s_pServerConf + 3),
           L"ExternalLibraries",
           L"ExternalLibPrefetchMemoryLimitForAdditionalExtractorsInMB",
           *(_QWORD *)(v14 + 1000),
           &v54,
           0) )
    {
      DynamicInt64SettingConverter(v54, &v48);
    }
    operator delete[](v54);
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
      v9,
      a1,
      L"PrefetchMemoryLimitForAdditionalExtractorsInMB",
      (unsigned int)v48);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"ReadPrefetchRelativeChunking")
    && !byte_10317AB00
    && byte_10316E899 )
  {
    LOBYTE(v15) = 1;
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, __int64))(*(_QWORD *)v9 + 72LL))(
      v9,
      a1,
      L"ReadPrefetchRelativeChunking",
      v15);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"ReissueLongReadRequests") )
  {
    LOBYTE(v16) = byte_10316EA83 != 0;
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, __int64))(*(_QWORD *)v9 + 72LL))(
      v9,
      a1,
      L"ReissueLongReadRequests",
      v16);
  }
  v51 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"MaxNumberOfRequests") )
  {
    v55 = 0;
    v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v18 = *(_QWORD *)(v17 + 256);
    if ( !v18 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v18 = *(_QWORD *)(v17 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
            + 3))(
           *((_QWORD *)s_pServerConf + 3),
           L"ReissueRequests",
           L"MaxNumberOfRequests",
           *(_QWORD *)(v18 + 1000),
           &v55,
           0)
      && DynamicInt64SettingConverter(v55, &v51) )
    {
      operator delete[](v55);
      (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
        v9,
        a1,
        L"MaxNumberOfRequests",
        (unsigned int)v51);
    }
    else
    {
      operator delete[](v55);
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"BackoffCoefficient") )
  {
    v56 = 0;
    v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v20 = *(_QWORD *)(v19 + 256);
    if ( !v20 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v20 = *(_QWORD *)(v19 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
            + 3))(
           *((_QWORD *)s_pServerConf + 3),
           L"ReissueRequests",
           L"BackoffCoeficient",
           *(_QWORD *)(v20 + 1000),
           &v56,
           0)
      && DynamicInt64SettingConverter(v56, &v51) )
    {
      operator delete[](v56);
      (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
        v9,
        a1,
        L"BackoffCoefficient",
        (unsigned int)v51);
    }
    else
    {
      operator delete[](v56);
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"WaitMsWhenReissuingRequests") )
  {
    v50 = 0;
    v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v22 = *(_QWORD *)(v21 + 256);
    if ( !v22 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v22 = *(_QWORD *)(v21 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
            + 3))(
           *((_QWORD *)s_pServerConf + 3),
           L"ReissueRequests",
           L"WaitMsWhenReissuingRequests",
           *(_QWORD *)(v22 + 1000),
           &v50,
           0)
      && DynamicInt64SettingConverter(v50, &v51) )
    {
      operator delete[](v50);
      (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
        v9,
        a1,
        L"WaitMsWhenReissuingRequests",
        (unsigned int)v51);
    }
    else
    {
      operator delete[](v50);
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"ExternalLibBufferSize") )
  {
    v50 = 0;
    v23 = (**(__int64 (__fastcall ***)(const struct IExtractorLibraryBase *, __int64))a5)(a5, 1001);
    v49 = 0;
    if ( v23 )
    {
      v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v25 = *(_QWORD *)(v24 + 256);
      if ( !v25 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v25 = *(_QWORD *)(v24 + 256);
      }
      if ( !(***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
               + 3))(
              *((_QWORD *)s_pServerConf + 3),
              L"ExternalLibraries",
              L"ExternalLibMisonFileStreamBufferSizeBytes",
              *(_QWORD *)(v25 + 1000),
              &v49,
              0) )
        goto LABEL_61;
    }
    else
    {
      v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v27 = *(_QWORD *)(v26 + 256);
      if ( !v27 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v27 = *(_QWORD *)(v26 + 256);
      }
      if ( !(***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
               + 3))(
              *((_QWORD *)s_pServerConf + 3),
              L"ExternalLibraries",
              L"ExternalLibBufferSizeBytes",
              *(_QWORD *)(v27 + 1000),
              &v49,
              0) )
        goto LABEL_61;
    }
    if ( !DynamicInt64SettingConverter(v49, (__int64 *)&v50) )
    {
LABEL_61:
      operator delete[](v49);
      goto LABEL_62;
    }
    operator delete[](v49);
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
      v9,
      a1,
      L"ExternalLibBufferSize",
      (unsigned int)v50);
  }
LABEL_62:
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"ExternalLibMisonChunkSize")
    && (**(unsigned __int8 (__fastcall ***)(const struct IExtractorLibraryBase *, __int64))a5)(a5, 1001) )
  {
    v48 = 0;
    v57 = 0;
    v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v29 = *(_QWORD *)(v28 + 256);
    if ( !v29 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v29 = *(_QWORD *)(v28 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
            + 3))(
           *((_QWORD *)s_pServerConf + 3),
           L"ExternalLibraries",
           L"ExternalLibMisonChunkSizeBytes",
           *(_QWORD *)(v29 + 1000),
           &v57,
           0)
      && DynamicInt64SettingConverter(v57, &v48) )
    {
      operator delete[](v57);
      (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
        v9,
        a1,
        L"ExternalLibMisonChunkSize",
        (unsigned int)v48);
    }
    else
    {
      operator delete[](v57);
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"ExternalLibMisonEnableRowRejecting")
    && (**(unsigned __int8 (__fastcall ***)(const struct IExtractorLibraryBase *, __int64))a5)(a5, 1001)
    && byte_10316E998
    && byte_10316E896 )
  {
    LOBYTE(v30) = 1;
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, __int64))(*(_QWORD *)v9 + 72LL))(
      v9,
      a1,
      L"ExternalLibMisonEnableRowRejecting",
      v30);
  }
  if ( (**(unsigned __int8 (__fastcall ***)(const struct IExtractorLibraryBase *, __int64))a5)(a5, 5) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"ReadPrefetch")
      && byte_10316E897
      && !byte_10317AB00 )
    {
      LOBYTE(v31) = 1;
      (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, __int64))(*(_QWORD *)v9 + 72LL))(
        v9,
        a1,
        L"ReadPrefetch",
        v31);
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"MaxNumChunkPrefetches") )
    {
      v48 = 0;
      v58 = 0;
      v32 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v33 = *(_QWORD *)(v32 + 256);
      if ( !v33 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v33 = *(_QWORD *)(v32 + 256);
      }
      if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
              + 3))(
             *((_QWORD *)s_pServerConf + 3),
             L"ExternalLibraries",
             L"ExternalLibParquetNumChunksPrefetch",
             *(_QWORD *)(v33 + 1000),
             &v58,
             0)
        && DynamicInt64SettingConverter(v58, &v48) )
      {
        operator delete[](v58);
        (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
          v9,
          a1,
          L"MaxNumChunkPrefetches",
          (unsigned int)v48);
      }
      else
      {
        operator delete[](v58);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"MaxNumChunkReadaheads") )
    {
      v48 = 0;
      v59 = 0;
      v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v35 = *(_QWORD *)(v34 + 256);
      if ( !v35 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v35 = *(_QWORD *)(v34 + 256);
      }
      if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
              + 3))(
             *((_QWORD *)s_pServerConf + 3),
             L"ExternalLibraries",
             L"ExternalLibParquetNumChunksReadahead",
             *(_QWORD *)(v35 + 1000),
             &v59,
             0)
        && DynamicInt64SettingConverter(v59, &v48) )
      {
        operator delete[](v59);
        (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
          v9,
          a1,
          L"MaxNumChunkReadaheads",
          (unsigned int)v48);
      }
      else
      {
        operator delete[](v59);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"PrefetchChunkSize") )
    {
      v48 = 0;
      v60 = 0;
      v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v37 = *(_QWORD *)(v36 + 256);
      if ( !v37 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v37 = *(_QWORD *)(v36 + 256);
      }
      if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
              + 3))(
             *((_QWORD *)s_pServerConf + 3),
             L"ExternalLibraries",
             L"ExternalLibParquetPrefetchChunkSize",
             *(_QWORD *)(v37 + 1000),
             &v60,
             0)
        && DynamicInt64SettingConverter(v60, &v48) )
      {
        operator delete[](v60);
        (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
          v9,
          a1,
          L"PrefetchChunkSize",
          (unsigned int)v48);
      }
      else
      {
        operator delete[](v60);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"ExternalLibParquetUseDynamicPolicyRowGroupsToPrefetch") )
    {
      v47 = 1;
      String1 = 0;
      v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v39 = *(_QWORD *)(v38 + 256);
      if ( !v39 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v39 = *(_QWORD *)(v38 + 256);
      }
      if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
              + 3))(
             *((_QWORD *)s_pServerConf + 3),
             L"ExternalLibraries",
             L"ExternalLibParquetUseDynamicPolicyRowGroupsToPrefetch",
             *(_QWORD *)(v39 + 1000),
             &String1,
             0) )
      {
        if ( DynamicBoolSettingConverter(String1, &v47) )
        {
          operator delete[](String1);
          (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, bool))(*(_QWORD *)v9 + 72LL))(
            v9,
            a1,
            L"ExternalLibParquetUseDynamicPolicyRowGroupsToPrefetch",
            v47);
        }
        else
        {
          operator delete[](String1);
        }
      }
      else
      {
        operator delete[](String1);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"ExternalLibParquetDynamicPolicyRowGroupsToPrefetchThresholds") )
    {
      v63[0] = 0;
      if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, void **, _QWORD))(*(_QWORD *)s_pServerConf + 528LL))(
             s_pServerConf,
             L"ExternalLibraries",
             L"ExternalLibParquetDynamicPolicyRowGroupsToPrefetchThresholds",
             a1,
             v63,
             0) )
      {
        (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, void *))(*(_QWORD *)v9 + 88LL))(
          v9,
          a1,
          L"ExternalLibParquetDynamicPolicyRowGroupsToPrefetchThresholds",
          v63[0]);
      }
      operator delete[](v63[0]);
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
            v9,
            L"ExternalLibParquetRowGroupsToPrefetchNum") )
    {
      v48 = 2;
      v62 = 0;
      v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v41 = *(_QWORD *)(v40 + 256);
      if ( !v41 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v41 = *(_QWORD *)(v40 + 256);
      }
      if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))s_pServerConf
              + 3))(
             *((_QWORD *)s_pServerConf + 3),
             L"ExternalLibraries",
             L"ExternalLibParquetRowGroupsToPrefetchNum",
             *(_QWORD *)(v41 + 1000),
             &v62,
             0)
        && DynamicInt64SettingConverter(v62, &v48) )
      {
        operator delete[](v62);
        (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 80LL))(
          v9,
          a1,
          L"ExternalLibParquetRowGroupsToPrefetchNum",
          (unsigned int)v48);
      }
      else
      {
        operator delete[](v62);
      }
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"GroupSmallIORequestsInExtractors") )
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 72LL))(
      v9,
      a1,
      L"GroupSmallIORequestsInExtractors",
      (unsigned __int8)byte_10316E8D6);
  if ( a7
    && !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"ExternalLibSStreamBlockHashPartitionEliminationOnString") )
  {
    LOBYTE(v42) = *((_DWORD *)a7 + 5) == 1;
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, __int64))(*(_QWORD *)v9 + 72LL))(
      v9,
      a1,
      L"ExternalLibSStreamBlockHashPartitionEliminationOnString",
      v42);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"EnableCaching")
    && (byte_10316EA26
     || (byte_10317B1CC & 0x40) != 0
     || (v44 = *(_QWORD *)(SystemThread_TlsOffset
                         + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
     && (v45 = **(struct CSessionTraceFlags ***)(v44 + 56)) != 0
     && CSessionTraceFlags::CheckSessionTraceInternal(v45, 0x3266u)
     || dword_103172528 && dword_1031864F4) )
  {
    LOBYTE(v43) = 1;
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, __int64))(*(_QWORD *)v9 + 72LL))(
      v9,
      a1,
      L"EnableCaching",
      v43);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDataExtractionConfig *, const wchar_t *))(*(_QWORD *)v9 + 32LL))(
          v9,
          L"XStoreClientRequestId")
    && (*(_QWORD *)&rguid->Data1 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)rguid->Data4 != *(_QWORD *)GUID_NULL.Data4) )
  {
    memset(sz, 0, sizeof(sz));
    StringFromGUID2(rguid, sz, 40);
    v67 = 0;
    v68 = 0;
    v65[0] = *(_OWORD *)&sz[1];
    v65[1] = *(_OWORD *)&sz[9];
    v65[2] = *(_OWORD *)&sz[17];
    v65[3] = *(_OWORD *)&sz[25];
    v66 = *(_QWORD *)&sz[33];
    (*(void (__fastcall **)(struct IDataExtractionConfig *, struct IMemObj *, const wchar_t *, _OWORD *))(*(_QWORD *)v9 + 88LL))(
      v9,
      a1,
      L"XStoreClientRequestId",
      v65);
  }
  return v9;
}

```

## disassembly

```asm
0x1010cdf60  push    rbp
0x1010cdf62  push    rsi
0x1010cdf63  push    rdi
0x1010cdf64  push    r12
0x1010cdf66  push    r13
0x1010cdf68  push    r14
0x1010cdf6a  push    r15
0x1010cdf6c  lea     rbp, [rsp-70h]
0x1010cdf71  sub     rsp, 170h
0x1010cdf78  mov     [rbp+0A0h+var_E8], 0FFFFFFFFFFFFFFFEh
0x1010cdf80  mov     [rsp+1A0h+arg_10], rbx
0x1010cdf88  mov     rax, cs:__security_cookie
0x1010cdf8f  xor     rax, rsp
0x1010cdf92  mov     [rbp+0A0h+var_40], rax
0x1010cdf96  mov     r8, rdx
0x1010cdf99  mov     rdi, rcx
0x1010cdf9c  mov     r14, [rbp+0A0h+arg_20]
0x1010cdfa3  mov     r13, [rbp+0A0h+rguid]
0x1010cdfaa  mov     r12, [rbp+0A0h+arg_30]
0x1010cdfb1  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1010cdfb8  mov     r15, [rax]
0x1010cdfbb  test    rdx, rdx
0x1010cdfbe  jz      short loc_1010CDFCE
0x1010cdfc0  mov     rax, [rdx]
0x1010cdfc3  mov     rdx, rcx
0x1010cdfc6  mov     rcx, r8
0x1010cdfc9  call    qword ptr [rax+8]
0x1010cdfcc  jmp     short loc_1010CDFDB
0x1010cdfce  lea     rdx, asc_102A6A308; "{}"
0x1010cdfd5  call    cs:__imp_?ExtractFromJSON@IDataExtractionConfig@@SAPEAV1@PEAVIMemObj@@PEB_W@Z; IDataExtractionConfig::ExtractFromJSON(IMemObj *,wchar_t const *)
0x1010cdfdb  mov     rbx, rax
0x1010cdfde  mov     rax, [r14]
0x1010cdfe1  mov     edx, 7
0x1010cdfe6  mov     rcx, r14
0x1010cdfe9  call    qword ptr [rax]
0x1010cdfeb  xor     esi, esi
0x1010cdfed  test    al, al
0x1010cdfef  jz      loc_1010CE121
0x1010cdff5  mov     rax, [rbx]
0x1010cdff8  lea     rdx, ?x_wszPropMaxConcurrentExtractorsPerThread@IDataExtractionConfig@@2QB_WB; "ExternalLibMaxConcurrentExtractorsPerTh"...
0x1010cdfff  mov     rcx, rbx
0x1010ce002  call    qword ptr [rax+20h]
0x1010ce005  test    al, al
0x1010ce007  jnz     loc_1010CE0E7
0x1010ce00d  mov     rax, [r14]
0x1010ce010  lea     edx, [rsi+5]
0x1010ce013  mov     rcx, r14
0x1010ce016  call    qword ptr [rax]
0x1010ce018  test    al, al
0x1010ce01a  jz      loc_1010CE0E7
0x1010ce020  mov     [rsp+1A0h+var_168], 1
0x1010ce029  mov     [rsp+1A0h+String], rsi
0x1010ce02e  mov     rdx, gs:58h
0x1010ce037  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1010ce03e  mov     ecx, [rax]
0x1010ce040  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1010ce047  mov     esi, [rax]
0x1010ce049  add     rsi, [rdx+rcx*8]
0x1010ce04d  mov     r9, [rsi+100h]
0x1010ce054  test    r9, r9
0x1010ce057  jnz     short loc_1010CE068
0x1010ce059  xor     ecx, ecx
0x1010ce05b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1010ce061  mov     r9, [rsi+100h]
0x1010ce068  mov     rcx, [r15+18h]
0x1010ce06c  mov     rax, [rcx]
0x1010ce06f  xor     esi, esi
0x1010ce071  mov     [rsp+1A0h+var_178], rsi
0x1010ce076  lea     rdx, [rsp+1A0h+String]
0x1010ce07b  mov     [rsp+1A0h+var_180], rdx
0x1010ce080  mov     r9, [r9+3E8h]
0x1010ce087  lea     r8, aExternallibmax; "ExternalLibMaxConcurrentExtractorsPerTh"...
0x1010ce08e  lea     rdx, aExternallibrar; "ExternalLibraries"
0x1010ce095  call    qword ptr [rax]
0x1010ce097  test    al, al
0x1010ce099  jnz     short loc_1010CE0A8
0x1010ce09b  mov     rcx, [rsp+1A0h+String]
0x1010ce0a0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce0a6  jmp     short loc_1010CE0E7
0x1010ce0a8  lea     rdx, [rsp+1A0h+var_168]; __int64 *
0x1010ce0ad  mov     rcx, [rsp+1A0h+String]; String
0x1010ce0b2  call    ?DynamicInt64SettingConverter@@YA_NPEB_WPEA_J@Z; DynamicInt64SettingConverter(wchar_t const *,__int64 *)
0x1010ce0b7  nop
0x1010ce0b8  mov     rcx, [rsp+1A0h+String]
0x1010ce0bd  test    al, al
0x1010ce0bf  jnz     short loc_1010CE0C9
0x1010ce0c1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce0c7  jmp     short loc_1010CE0E7
0x1010ce0c9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce0cf  mov     rax, [rbx]
0x1010ce0d2  mov     r9d, dword ptr [rsp+1A0h+var_168]
0x1010ce0d7  lea     r8, ?x_wszPropMaxConcurrentExtractorsPerThread@IDataExtractionConfig@@2QB_WB; "ExternalLibMaxConcurrentExtractorsPerTh"...
0x1010ce0de  mov     rdx, rdi
0x1010ce0e1  mov     rcx, rbx
0x1010ce0e4  call    qword ptr [rax+50h]
0x1010ce0e7  mov     [rsp+1A0h+var_148], 1
0x1010ce0ef  mov     rax, [rbx]
0x1010ce0f2  lea     r8, [rsp+1A0h+var_148]
0x1010ce0f7  lea     rdx, ?x_wszPropMaxConcurrentExtractorsPerThread@IDataExtractionConfig@@2QB_WB; "ExternalLibMaxConcurrentExtractorsPerTh"...
0x1010ce0fe  mov     rcx, rbx
0x1010ce101  call    qword ptr [rax+28h]
0x1010ce104  cmp     [rsp+1A0h+var_148], 1
0x1010ce109  jle     short loc_1010CE121
0x1010ce10b  mov     rax, [rbx]
0x1010ce10e  mov     r9b, 1
0x1010ce111  lea     r8, ?x_wszPropUseAsyncInit@IDataExtractionConfig@@2QB_WB; "UseAsyncInit"
0x1010ce118  mov     rdx, rdi
0x1010ce11b  mov     rcx, rbx
0x1010ce11e  call    qword ptr [rax+48h]
0x1010ce121  mov     rax, [rbx]
0x1010ce124  lea     rdx, ?x_wszPropPrefetchMemoryLimitForAdditionalExtractorsInMB@IDataExtractionConfig@@2QB_WB; "PrefetchMemoryLimitForAdditionalExtract"...
0x1010ce12b  mov     rcx, rbx
0x1010ce12e  call    qword ptr [rax+20h]
0x1010ce131  test    al, al
0x1010ce133  jnz     loc_1010CE1E7
0x1010ce139  mov     [rsp+1A0h+var_168], 100h
0x1010ce142  mov     [rsp+1A0h+var_138], rsi
0x1010ce147  mov     rdx, gs:58h
0x1010ce150  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1010ce157  mov     ecx, [rax]
0x1010ce159  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1010ce160  mov     esi, [rax]
0x1010ce162  add     rsi, [rdx+rcx*8]
0x1010ce166  mov     r9, [rsi+100h]
0x1010ce16d  test    r9, r9
0x1010ce170  jnz     short loc_1010CE181
0x1010ce172  xor     ecx, ecx
0x1010ce174  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1010ce17a  mov     r9, [rsi+100h]
0x1010ce181  mov     rcx, [r15+18h]
0x1010ce185  mov     rax, [rcx]
0x1010ce188  xor     esi, esi
0x1010ce18a  mov     [rsp+1A0h+var_178], rsi
0x1010ce18f  lea     rdx, [rsp+1A0h+var_138]
0x1010ce194  mov     [rsp+1A0h+var_180], rdx
0x1010ce199  mov     r9, [r9+3E8h]
0x1010ce1a0  lea     r8, aExternallibpre; "ExternalLibPrefetchMemoryLimitForAdditi"...
0x1010ce1a7  lea     rdx, aExternallibrar; "ExternalLibraries"
0x1010ce1ae  call    qword ptr [rax]
0x1010ce1b0  test    al, al
0x1010ce1b2  jz      short loc_1010CE1C4
0x1010ce1b4  lea     rdx, [rsp+1A0h+var_168]; __int64 *
0x1010ce1b9  mov     rcx, [rsp+1A0h+var_138]; String
0x1010ce1be  call    ?DynamicInt64SettingConverter@@YA_NPEB_WPEA_J@Z; DynamicInt64SettingConverter(wchar_t const *,__int64 *)
0x1010ce1c3  nop
0x1010ce1c4  mov     rcx, [rsp+1A0h+var_138]
0x1010ce1c9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce1cf  mov     rax, [rbx]
0x1010ce1d2  mov     r9d, dword ptr [rsp+1A0h+var_168]
0x1010ce1d7  lea     r8, ?x_wszPropPrefetchMemoryLimitForAdditionalExtractorsInMB@IDataExtractionConfig@@2QB_WB; "PrefetchMemoryLimitForAdditionalExtract"...
0x1010ce1de  mov     rdx, rdi
0x1010ce1e1  mov     rcx, rbx
0x1010ce1e4  call    qword ptr [rax+50h]
0x1010ce1e7  mov     rax, [rbx]
0x1010ce1ea  lea     rdx, ?x_wszPropReadPrefetchRelativeChunking@IDataExtractionConfig@@2QB_WB; "ReadPrefetchRelativeChunking"
0x1010ce1f1  mov     rcx, rbx
0x1010ce1f4  call    qword ptr [rax+20h]
0x1010ce1f7  test    al, al
0x1010ce1f9  jnz     short loc_1010CE221
0x1010ce1fb  cmp     cs:byte_10317AB00, al
0x1010ce201  jnz     short loc_1010CE221
0x1010ce203  cmp     cs:byte_10316E899, al
0x1010ce209  jz      short loc_1010CE221
0x1010ce20b  mov     rax, [rbx]
0x1010ce20e  mov     r9b, 1
0x1010ce211  lea     r8, ?x_wszPropReadPrefetchRelativeChunking@IDataExtractionConfig@@2QB_WB; "ReadPrefetchRelativeChunking"
0x1010ce218  mov     rdx, rdi
0x1010ce21b  mov     rcx, rbx
0x1010ce21e  call    qword ptr [rax+48h]
0x1010ce221  mov     rax, [rbx]
0x1010ce224  lea     rdx, ?x_wszPropReissueLongReadRequests@IDataExtractionConfig@@2QB_WB; "ReissueLongReadRequests"
0x1010ce22b  mov     rcx, rbx
0x1010ce22e  call    qword ptr [rax+20h]
0x1010ce231  test    al, al
0x1010ce233  jnz     short loc_1010CE252
0x1010ce235  cmp     cs:byte_10316EA83, al
0x1010ce23b  setnz   r9b
0x1010ce23f  mov     rax, [rbx]
0x1010ce242  lea     r8, ?x_wszPropReissueLongReadRequests@IDataExtractionConfig@@2QB_WB; "ReissueLongReadRequests"
0x1010ce249  mov     rdx, rdi
0x1010ce24c  mov     rcx, rbx
0x1010ce24f  call    qword ptr [rax+48h]
0x1010ce252  mov     [rsp+1A0h+var_150], rsi
0x1010ce257  mov     rax, [rbx]
0x1010ce25a  lea     rdx, ?x_wszPropMaxNumberOfRequests@IDataExtractionConfig@@2QB_WB; "MaxNumberOfRequests"
0x1010ce261  mov     rcx, rbx
0x1010ce264  call    qword ptr [rax+20h]
0x1010ce267  test    al, al
0x1010ce269  jnz     loc_1010CE32D
0x1010ce26f  mov     [rsp+1A0h+var_130], rsi
0x1010ce274  mov     rdx, gs:58h
0x1010ce27d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1010ce284  mov     ecx, [rax]
0x1010ce286  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1010ce28d  mov     esi, [rax]
0x1010ce28f  add     rsi, [rdx+rcx*8]
0x1010ce293  mov     r9, [rsi+100h]
0x1010ce29a  test    r9, r9
0x1010ce29d  jnz     short loc_1010CE2AE
0x1010ce29f  xor     ecx, ecx
0x1010ce2a1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1010ce2a7  mov     r9, [rsi+100h]
0x1010ce2ae  mov     rcx, [r15+18h]
0x1010ce2b2  mov     rax, [rcx]
0x1010ce2b5  xor     esi, esi
0x1010ce2b7  mov     [rsp+1A0h+var_178], rsi
0x1010ce2bc  lea     rdx, [rsp+1A0h+var_130]
0x1010ce2c1  mov     [rsp+1A0h+var_180], rdx
0x1010ce2c6  mov     r9, [r9+3E8h]
0x1010ce2cd  lea     r8, aMaxnumberofreq; "MaxNumberOfRequests"
0x1010ce2d4  lea     rdx, aReissuerequest; "ReissueRequests"
0x1010ce2db  call    qword ptr [rax]
0x1010ce2dd  test    al, al
0x1010ce2df  jnz     short loc_1010CE2EE
0x1010ce2e1  mov     rcx, [rsp+1A0h+var_130]
0x1010ce2e6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce2ec  jmp     short loc_1010CE32D
0x1010ce2ee  lea     rdx, [rsp+1A0h+var_150]; __int64 *
0x1010ce2f3  mov     rcx, [rsp+1A0h+var_130]; String
0x1010ce2f8  call    ?DynamicInt64SettingConverter@@YA_NPEB_WPEA_J@Z; DynamicInt64SettingConverter(wchar_t const *,__int64 *)
0x1010ce2fd  nop
0x1010ce2fe  mov     rcx, [rsp+1A0h+var_130]
0x1010ce303  test    al, al
0x1010ce305  jnz     short loc_1010CE30F
0x1010ce307  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce30d  jmp     short loc_1010CE32D
0x1010ce30f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce315  mov     rax, [rbx]
0x1010ce318  mov     r9d, dword ptr [rsp+1A0h+var_150]
0x1010ce31d  lea     r8, ?x_wszPropMaxNumberOfRequests@IDataExtractionConfig@@2QB_WB; "MaxNumberOfRequests"
0x1010ce324  mov     rdx, rdi
0x1010ce327  mov     rcx, rbx
0x1010ce32a  call    qword ptr [rax+50h]
0x1010ce32d  mov     rax, [rbx]
0x1010ce330  lea     rdx, ?x_wszPropBackoffCoefficient@IDataExtractionConfig@@2QB_WB; "BackoffCoefficient"
0x1010ce337  mov     rcx, rbx
0x1010ce33a  call    qword ptr [rax+20h]
0x1010ce33d  test    al, al
0x1010ce33f  jnz     loc_1010CE403
0x1010ce345  mov     [rsp+1A0h+var_128], rsi
0x1010ce34a  mov     rdx, gs:58h
0x1010ce353  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1010ce35a  mov     ecx, [rax]
0x1010ce35c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1010ce363  mov     esi, [rax]
0x1010ce365  add     rsi, [rdx+rcx*8]
0x1010ce369  mov     r9, [rsi+100h]
0x1010ce370  test    r9, r9
0x1010ce373  jnz     short loc_1010CE384
0x1010ce375  xor     ecx, ecx
0x1010ce377  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1010ce37d  mov     r9, [rsi+100h]
0x1010ce384  mov     rcx, [r15+18h]
0x1010ce388  mov     rax, [rcx]
0x1010ce38b  xor     esi, esi
0x1010ce38d  mov     [rsp+1A0h+var_178], rsi
0x1010ce392  lea     rdx, [rsp+1A0h+var_128]
0x1010ce397  mov     [rsp+1A0h+var_180], rdx
0x1010ce39c  mov     r9, [r9+3E8h]
0x1010ce3a3  lea     r8, aBackoffcoefici; "BackoffCoeficient"
0x1010ce3aa  lea     rdx, aReissuerequest; "ReissueRequests"
0x1010ce3b1  call    qword ptr [rax]
0x1010ce3b3  test    al, al
0x1010ce3b5  jnz     short loc_1010CE3C4
0x1010ce3b7  mov     rcx, [rsp+1A0h+var_128]
0x1010ce3bc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce3c2  jmp     short loc_1010CE403
0x1010ce3c4  lea     rdx, [rsp+1A0h+var_150]; __int64 *
0x1010ce3c9  mov     rcx, [rsp+1A0h+var_128]; String
0x1010ce3ce  call    ?DynamicInt64SettingConverter@@YA_NPEB_WPEA_J@Z; DynamicInt64SettingConverter(wchar_t const *,__int64 *)
0x1010ce3d3  nop
0x1010ce3d4  mov     rcx, [rsp+1A0h+var_128]
0x1010ce3d9  test    al, al
0x1010ce3db  jnz     short loc_1010CE3E5
0x1010ce3dd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce3e3  jmp     short loc_1010CE403
0x1010ce3e5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1010ce3eb  mov     rax, [rbx]
0x1010ce3ee  mov     r9d, dword ptr [rsp+1A0h+var_150]
0x1010ce3f3  lea     r8, ?x_wszPropBackoffCoefficient@IDataExtractionConfig@@2QB_WB; "BackoffCoefficient"
0x1010ce3fa  mov     rdx, rdi
0x1010ce3fd  mov     rcx, rbx
0x1010ce400  call    qword ptr [rax+50h]
0x1010ce403  mov     rax, [rbx]
0x1010ce406  lea     rdx, ?x_wszPropWaitMsWhenReissuingRequests@IDataExtractionConfig@@2QB_WB; "WaitMsWhenReissuingRequests"
0x1010ce40d  mov     rcx, rbx
0x1010ce410  call    qword ptr [rax+20h]
0x1010ce413  test    al, al
0x1010ce415  jnz     loc_1010CE4D9
0x1010ce41b  mov     [rsp+1A0h+var_158], rsi
0x1010ce420  mov     rdx, gs:58h
0x1010ce429  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1010ce430  mov     ecx, [rax]
0x1010ce432  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1010ce439  mov     esi, [rax]
0x1010ce43b  add     rsi, [rdx+rcx*8]
0x1010ce43f  mov     r9, [rsi+100h]
0x1010ce446  test    r9, r9
0x1010ce449  jnz     short loc_1010CE45A
0x1010ce44b  xor     ecx, ecx
  ... truncated ...
```
