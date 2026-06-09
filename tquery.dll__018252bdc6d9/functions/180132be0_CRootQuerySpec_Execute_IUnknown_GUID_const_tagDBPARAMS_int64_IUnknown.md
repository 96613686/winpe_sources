# CRootQuerySpec::Execute(IUnknown *,_GUID const &,tagDBPARAMS *,__int64 *,IUnknown * *)

- ea: `0x180132be0`
- end: `0x180134e1f`
- name: `?Execute@CRootQuerySpec@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAUtagDBPARAMS@@PEA_JPEAPEAU2@@Z`
- size: `8767`
- prototype: `__int64 __fastcall(CRootQuerySpec *this, struct IUnknown *, struct _GUID *, struct tagDBPARAMS *, __int64 *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `92`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801c9390`

## callees

- `0x18002a3f8`
- `0x18002f1dc`
- `0x180036d60`
- `0x180038f08`
- `0x18005b8c8`
- `0x1800601c0`
- `0x18006380c`
- `0x1800670b4`
- `0x180068ce4`
- `0x180069160`
- `0x180069cf4`
- `0x18006a088`
- `0x18006a26c`
- `0x18006a95c`
- `0x180078410`
- `0x18008b084`
- `0x18008c088`
- `0x180090630`
- `0x180090930`
- `0x180091e08`
- `0x18009202c`
- `0x180093050`
- `0x180094a80`
- `0x1800deeec`
- `0x1800e613c`
- `0x1800e8ff8`
- `0x1800e938c`
- `0x1800ef5c8`
- `0x1800ef6bc`
- `0x1800f0d04`
- `0x1800f1ae0`
- `0x1800fb428`
- `0x1800fb7b0`
- `0x1800fecc4`
- `0x1800ff378`
- `0x18010135c`
- `0x18010221c`
- `0x180106038`
- `0x180108c88`
- `0x180109548`
- `0x18010a954`
- `0x1801185dc`
- `0x180132be0`
- `0x180135088`
- `0x18013cd74`
- `0x18014d7c0`
- `0x180153610`
- `0x18015aa68`
- `0x18015b194`
- `0x18015e264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180132d3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180132d3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013323e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133a9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133d36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134721`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134d3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013323e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133a9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133d36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134721`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134d3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18013356a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18013356a`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180133e2b`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180133e2b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180133261`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180134b07`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180133261`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180134b07`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180134bdb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180134bdb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180132c4d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180132c4d`

## string_xrefs

- `0x180132c9b`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1801331de`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1801338fe`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180133b99`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180133ecc`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x18013456a`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134cda`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134d69`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134d90`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134da5`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134dba`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134dce`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134de3`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134df7`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134e0c`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180132e23`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180132ea5`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x180134a8c`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`

## pseudocode

```c
__int64 __fastcall CRootQuerySpec::Execute(
        CRootQuerySpec *this,
        struct IUnknown *a2,
        struct _GUID *a3,
        struct tagDBPARAMS *a4,
        __int64 *a5,
        struct IUnknown **a6)
{
  int v10; // ebx
  __int64 v11; // rdx
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  int v14; // r13d
  bool v15; // al
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  const wchar_t *v18; // r9
  const wchar_t *v19; // r9
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  __int64 v23; // rax
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  __int64 v26; // rax
  volatile signed __int32 *v27; // rcx
  CRootQuerySpec *v28; // rbx
  wchar_t ***v29; // rdx
  unsigned int v30; // r8d
  wchar_t **v31; // rax
  int v32; // eax
  struct CColumnGroupArray *v33; // rbx
  unsigned int v34; // r8d
  int v35; // eax
  std::_Ref_count_base *v36; // r14
  wchar_t **v37; // rsi
  const wchar_t *const *v38; // rsi
  const wchar_t *v39; // rax
  const wchar_t *v40; // rdx
  const wchar_t *v41; // rsi
  unsigned int v42; // eax
  __int64 v43; // rdx
  int v44; // esi
  __int64 v45; // rcx
  const wchar_t *v46; // r8
  CUtlProps *v47; // rsi
  CUtlProps *v48; // rsi
  unsigned int v49; // edx
  unsigned int v50; // r8d
  __int64 v51; // rax
  void (__fastcall *v52)(__int64, struct IUnknown *, _BYTE *, _BYTE *); // r10
  __int64 v53; // r11
  __int64 v54; // rcx
  void (__fastcall *v55)(__int64, struct IUnknown *, _BYTE *, _BYTE *); // r10
  struct IUnknown *v56; // rbx
  int v57; // eax
  __int64 v58; // rcx
  BOOL v59; // esi
  int v60; // eax
  int v61; // eax
  __int64 v62; // rcx
  __int64 (*v63)(void); // rax
  int v64; // eax
  int v65; // eax
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  struct _GUID *v69; // rcx
  const wchar_t *v70; // r8
  int v71; // eax
  const wchar_t *v72; // r14
  char IsEnabled; // al
  __int64 v74; // rbx
  const char *v75; // r9
  int v76; // [rsp+20h] [rbp-CD8h]
  int v77; // [rsp+20h] [rbp-CD8h]
  int *v78; // [rsp+20h] [rbp-CD8h]
  bool v79; // [rsp+90h] [rbp-C68h]
  unsigned int v80; // [rsp+94h] [rbp-C64h] BYREF
  unsigned int *v81; // [rsp+98h] [rbp-C60h] BYREF
  CUtlProps *v82; // [rsp+A0h] [rbp-C58h] BYREF
  int v83; // [rsp+A8h] [rbp-C50h]
  wchar_t *v84; // [rsp+ACh] [rbp-C4Ch] BYREF
  struct IUnknown *v85; // [rsp+B8h] [rbp-C40h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-C38h] BYREF
  wchar_t **v87; // [rsp+C8h] [rbp-C30h] BYREF
  struct IUnknown *v88; // [rsp+D0h] [rbp-C28h] BYREF
  wchar_t **v89; // [rsp+D8h] [rbp-C20h]
  __int64 v90; // [rsp+E0h] [rbp-C18h]
  unsigned int v91; // [rsp+E8h] [rbp-C10h] BYREF
  struct CColumnGroupArray *v92; // [rsp+F0h] [rbp-C08h] BYREF
  void **v93; // [rsp+F8h] [rbp-C00h]
  std::_Ref_count_base *v94[2]; // [rsp+100h] [rbp-BF8h] BYREF
  struct _GUID *v95; // [rsp+110h] [rbp-BE8h]
  CRootQuerySpec *v96; // [rsp+118h] [rbp-BE0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+120h] [rbp-BD8h]
  CMRowsetProps *v98; // [rsp+128h] [rbp-BD0h] BYREF
  struct IUnknown **v99; // [rsp+130h] [rbp-BC8h] BYREF
  std::_Ref_count_base *v100; // [rsp+138h] [rbp-BC0h]
  int v101; // [rsp+140h] [rbp-BB8h] BYREF
  void *Block; // [rsp+148h] [rbp-BB0h]
  _BYTE v103[40]; // [rsp+150h] [rbp-BA8h] BYREF
  int v104; // [rsp+178h] [rbp-B80h] BYREF
  void *v105; // [rsp+180h] [rbp-B78h]
  _BYTE v106[40]; // [rsp+188h] [rbp-B70h] BYREF
  int v107; // [rsp+1B0h] [rbp-B48h] BYREF
  void *v108; // [rsp+1B8h] [rbp-B40h]
  _BYTE v109[40]; // [rsp+1C0h] [rbp-B38h] BYREF
  tagDBPROPSET v110; // [rsp+1E8h] [rbp-B10h] BYREF
  wchar_t ***v111; // [rsp+208h] [rbp-AF0h]
  CRootQuerySpec *v112; // [rsp+210h] [rbp-AE8h]
  struct _GUID *v113; // [rsp+218h] [rbp-AE0h]
  struct IUnknown *v114; // [rsp+220h] [rbp-AD8h]
  unsigned __int64 CurrentTimestamp; // [rsp+228h] [rbp-AD0h]
  struct _GUID v116; // [rsp+230h] [rbp-AC8h] BYREF
  _DWORD *v117; // [rsp+240h] [rbp-AB8h]
  _DWORD *v118; // [rsp+248h] [rbp-AB0h]
  struct _GUID v119; // [rsp+250h] [rbp-AA8h] BYREF
  GUID pguid; // [rsp+260h] [rbp-A98h] BYREF
  struct _GUID Buf1; // [rsp+270h] [rbp-A88h] BYREF
  int v122; // [rsp+280h] [rbp-A78h] BYREF
  void *v123; // [rsp+288h] [rbp-A70h]
  _BYTE v124[24]; // [rsp+290h] [rbp-A68h] BYREF
  wchar_t *v125[3]; // [rsp+2A8h] [rbp-A50h] BYREF
  unsigned __int64 v126; // [rsp+2C0h] [rbp-A38h]
  struct _GUID v127; // [rsp+2E8h] [rbp-A10h] BYREF
  _BYTE v128[88]; // [rsp+300h] [rbp-9F8h] BYREF
  __int64 v129; // [rsp+358h] [rbp-9A0h]
  _BYTE v130[16]; // [rsp+360h] [rbp-998h] BYREF
  _BYTE v131[176]; // [rsp+370h] [rbp-988h] BYREF
  int v132; // [rsp+420h] [rbp-8D8h]
  int v133; // [rsp+424h] [rbp-8D4h]
  int v134[4]; // [rsp+428h] [rbp-8D0h] BYREF
  int v135; // [rsp+470h] [rbp-888h]
  _BYTE v136[344]; // [rsp+478h] [rbp-880h] BYREF
  _QWORD v137[42]; // [rsp+5D0h] [rbp-728h] BYREF
  _QWORD v138[42]; // [rsp+720h] [rbp-5D8h] BYREF
  _QWORD v139[42]; // [rsp+870h] [rbp-488h] BYREF
  _QWORD v140[42]; // [rsp+9C0h] [rbp-338h] BYREF
  _BYTE v141[336]; // [rsp+B10h] [rbp-1E8h] BYREF
  OLECHAR sz[2]; // [rsp+C60h] [rbp-98h] BYREF
  int v143; // [rsp+C64h] [rbp-94h]
  __int16 v144; // [rsp+C90h] [rbp-68h]
  __int16 v145; // [rsp+C98h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+CF8h] [rbp+0h]

  v95 = a3;
  v85 = a2;
  v96 = this;
  v114 = a2;
  v113 = a3;
  v93 = (void **)a6;
  SetErrorInfo(0, 0);
  v116 = IID_ICommand;
  if ( !a6 )
  {
    v10 = CCIOleDBError::PostHResult((CRootQuerySpec *)((char *)this + 128), -2147024809, &v116);
    if ( v10 >= 0 )
      return (unsigned int)v10;
    v11 = 728;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)(unsigned int)v10,
      v76);
    return (unsigned int)v10;
  }
  if ( a2
    && (*(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_IUnknown.Data1 || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_IUnknown.Data4) )
  {
    v10 = CCIOleDBError::PostHResult((CRootQuerySpec *)((char *)this + 128), -2147217886, &v116);
    if ( v10 >= 0 )
      return (unsigned int)v10;
    v11 = 733;
    goto LABEL_4;
  }
  if ( a4 )
  {
    v10 = CCIOleDBError::PostHResult((CRootQuerySpec *)((char *)this + 128), -2147024809, &v116);
    if ( v10 >= 0 )
      return (unsigned int)v10;
    v11 = 738;
    goto LABEL_4;
  }
  v112 = this;
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 80);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v83 = 0;
  HIDWORD(v84) = 0;
  v118 = (_DWORD *)((char *)this + 176);
  *((_DWORD *)this + 44) &= ~0x10000000u;
  v79 = 0;
  v14 = 0;
  v15 = IsRunningInContainer();
  SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::IndexerQueryExecutionClient(
    (SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient *)v128,
    v15);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) )
  {
    CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &Buf1, v16, 0xDu);
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      pguid = 0;
      if ( CoCreateGuid_0(&pguid) >= 0 )
      {
        if ( StringFromGUID2_0(&pguid, sz, 39) )
          CUtlProps::SetValString((CRootQuerySpec *)((char *)this + 416), 2u, 0xDu, sz);
        else
          SearchIndexerDebug::Error(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
            (const wchar_t *)0x304,
            (unsigned int)L"[Query] Failed to convert query GUID to string\n",
            v18);
      }
    }
    CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &Buf1, v17, 0xCu);
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      if ( StringFromGUID2_0(&rguid, sz, 39) )
        CUtlProps::SetValString((CRootQuerySpec *)((char *)this + 416), 2u, 0xCu, sz);
      else
        SearchIndexerDebug::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
          (const wchar_t *)0x316,
          (unsigned int)L"[Query] Failed to convert session GUID to string\n",
          v19);
    }
  }
  *(_OWORD *)v94 = 0;
  CurrentTimestamp = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60916561>::GetImpl'::`2'::impl) )
  {
    try
    {
      CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &Buf1, v20, 0xCu);
      if ( memcmp_0(&Buf1, &FE_SCOPE_QUERY, 0x10u) )
      {
        CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &Buf1, v21, 0xCu);
        CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &pguid, v22, 0xDu);
        v23 = std::make_shared<SearchIndexerTelemetryAggregatedNormal::WSearchQueryTelemetry,_GUID const,_GUID const>(
                &v99,
                &pguid,
                &Buf1);
        std::shared_ptr<inverted::CQueryOperator>::operator=<inverted::CNoneOperator,0>(v94, v23);
        if ( v100 )
          std::_Ref_count_base::_Decref(v100);
        CurrentTimestamp = SearchIndexerTelemetryAggregatedNormal::WSearchQueryTelemetry::GetCurrentTimestamp();
      }
    }
    catch ( ... )
    {
      pguid = 0;
      std::shared_ptr<inverted::CQueryOperator>::operator=<inverted::CNoneOperator,0>(v94, &pguid);
      if ( *(_QWORD *)pguid.Data4 )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)pguid.Data4);
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        823,
        "onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx");
    }
  }
  wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v138);
  v138[0] = &SearchIndexerTelemetry::QueryExecutionActivity::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
  {
    CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &Buf1, v24, 0xCu);
    CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &pguid, v25, 0xDu);
    v26 = SearchIndexerTelemetry::QueryExecutionActivity::Start<_GUID const,_GUID const>((SearchIndexerTelemetry::QueryExecutionActivity *)v137);
    SearchIndexerTelemetry::QueryExecutionActivity::operator=(v138, v26);
    SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity((SearchIndexerTelemetry::QueryExecutionActivity *)v137);
  }
  pv = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
  {
    v27 = *(volatile signed __int32 **)(tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>>((struct wil::details::IFailureCallback *)v125)
                                      + 56);
    pv = (LPVOID)v27;
    if ( v27 )
      _InterlockedAdd(v27 + 70, 1u);
    tip2::test_watcher<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>::~test_watcher<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>(v125);
  }
  v88 = 0;
  *v93 = 0;
  LODWORD(v90) = *(_QWORD *)&GUID_bedba8d9_c93a_4c0b_97ba_40bdb5a2b4c1.Data1 == *(_QWORD *)&v95->Data1
              && *(_QWORD *)GUID_bedba8d9_c93a_4c0b_97ba_40bdb5a2b4c1.Data4 == *(_QWORD *)v95->Data4
              || *(_QWORD *)&GUID_21c3f4c2_02df_404f_9d50_070cee79540f.Data1 == *(_QWORD *)&v95->Data1
              && *(_QWORD *)GUID_21c3f4c2_02df_404f_9d50_070cee79540f.Data4 == *(_QWORD *)v95->Data4;
  CRootQuerySpec::_EnsureStructuredQueryHelperExists(this);
  v28 = v112;
  v29 = (wchar_t ***)((char *)v112 + 184);
  v111 = (wchar_t ***)((char *)v112 + 184);
  if ( *((_QWORD *)this + 79) )
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, wchar_t **))(**((_QWORD **)this + 343) + 40LL))(
      *((_QWORD *)this + 343),
      L"SQL query: ",
      *v29);
  }
  else
  {
    if ( !*v29 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58638708>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58638708>::GetImpl'::`2'::impl)
        && *((_BYTE *)this + 2802) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60141615>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60141615>::GetImpl'::`2'::impl) )
          SearchIndexerTelemetryAggregatedHigh::QueryCancellationMetrics(2);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x360,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
          (const char *)0x80040E4ELL,
          v76);
        ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v88);
        wil::com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>(&pv);
        SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity((SearchIndexerTelemetry::QueryExecutionActivity *)v138);
        if ( v94[1] )
          std::_Ref_count_base::_Decref(v94[1]);
        SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient *)v128);
        LeaveCriticalSection(v13);
        return 2147749454LL;
      }
      CRootQuerySpec::_BuildSQL(this);
      v79 = lstrcmpW(*((LPCWSTR *)v28 + 29), L".") != 0;
      v29 = v111;
    }
    (*(void (__fastcall **)(_QWORD, const wchar_t *, wchar_t **))(**((_QWORD **)this + 343) + 40LL))(
      *((_QWORD *)this + 343),
      L"SQL query built: ",
      *v29);
    CRootQuerySpec::_BuildTree(this);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
  {
    v31 = (wchar_t **)L"Unknown SQL Query";
    if ( *v111 )
      v31 = *v111;
    v87 = v31;
    CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &Buf1, v30, 0xDu);
    SearchIndexerTelemetry::QueryExecutionActivity::QueryString<_GUID const,wchar_t const *>(v138, &Buf1, &v87);
  }
  if ( *((_BYTE *)this + 2800) )
  {
    memset_0(sz, 0, 0x48u);
    *(_DWORD *)sz = 15;
    v143 = 1;
    v144 = 11;
    v145 = -1;
    *(_QWORD *)&v110.guidPropertySet.Data4[4] = 629145848;
    v110.cProperties = 1;
    v110.guidPropertySet.Data1 = -1481869331;
    *(_DWORD *)&v110.guidPropertySet.Data2 = 298776791;
    *(_DWORD *)v110.guidPropertySet.Data4 = 536909991;
    v110.rgProperties = (DBPROP *)sz;
    v32 = CMRowsetProps::SetProperties((CRootQuerySpec *)((char *)this + 416), 1u, &v110);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x381,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
        (const char *)(unsigned int)v32,
        v76);
  }
  v92 = 0;
  v98 = (CMRowsetProps *)operator new(0x20u);
  v33 = CColumnGroupArray::CColumnGroupArray(v98);
  v92 = v33;
  wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v140);
  v140[0] = &SearchIndexerTelemetry::ParseTreeActivity::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
  {
    CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &Buf1, v34, 0xDu);
    wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v137);
    v137[0] = &SearchIndexerTelemetry::ParseTreeActivity::`vftable';
    v119 = Buf1;
    SearchIndexerTelemetry::ParseTreeActivity::StartActivity((SearchIndexerTelemetry::ParseTreeActivity *)v137, &v119);
    SearchIndexerTelemetry::ParseTreeActivity::operator=(v140, v137);
    SearchIndexerTelemetry::ParseTreeActivity::~ParseTreeActivity((SearchIndexerTelemetry::ParseTreeActivity *)v137);
  }
  CParseCommandTree::CParseCommandTree((CParseCommandTree *)v130, v33, *((_DWORD *)this + 156));
  CParseCommandTree::ParseTree((CParseCommandTree *)v130, *((struct CDbCmdTreeNode **)this + 79));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v140);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60916561>::GetImpl'::`2'::impl)
    && v94[0] )
  {
    v35 = v136[336] != 0;
    LODWORD(v89) = v35;
    if ( v136[337] )
    {
      LOBYTE(v35) = v35 | 2;
      LODWORD(v89) = v35;
    }
    v36 = v94[0];
    v37 = (wchar_t **)((char *)v94[0] + 144);
    AcquireSRWLockExclusive((PSRWLOCK)v94[0] + 18);
    v87 = v37;
    *((_BYTE *)v36 + 64) = (_BYTE)v89;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v87);
  }
  v107 = 5;
  v108 = v109;
  XGrowable<wchar_t const *,5>::SetSize(&v107, 5);
  v122 = 5;
  v123 = v124;
  XGrowable<unsigned long,5>::SetSize(&v122, 5);
  v104 = 5;
  v105 = v106;
  XGrowable<wchar_t const *,5>::SetSize(&v104, 5);
  v101 = 5;
  Block = v103;
  XGrowable<wchar_t const *,5>::SetSize(&v101, 5);
  v80 = 0;
  CParseCommandTree::GetScopes(
    (unsigned int)v130,
    (unsigned int)&v80,
    (unsigned int)&v107,
    (unsigned int)&v122,
    (__int64)&v104,
    (__int64)&v101);
  CreateScreenOnQueryEvent(&pguid);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pguid.Data1 + 8LL))(*(_QWORD *)&pguid.Data1);
  if ( v80 )
  {
    v38 = (const wchar_t *const *)Block;
    v87 = (wchar_t **)v105;
    v81 = (unsigned int *)v123;
    v89 = (wchar_t **)v108;
    v39 = (const wchar_t *)(*(__int64 (__fastcall **)(CRootQuerySpec *))(*(_QWORD *)this + 72LL))(this);
    SetScopeProperties(
      (struct ICommand *)this,
      v39,
      v80,
      (const wchar_t *const *)v89,
      v81,
      (const wchar_t *const *)v87,
      v38);
  }
  std::wstring::wstring(v125);
  v117 = (_DWORD *)((char *)this + 684);
  if ( *((_DWORD *)this + 171) )
    GetProtocolHelperWithQuote(*((_QWORD *)this + 84), v125);
  v40 = (const wchar_t *)v125;
  if ( v126 > 7 )
    v40 = v125[0];
  SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::Start(
    (SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient *)v128,
    v40);
  v41 = (const wchar_t *)v125;
  if ( v126 > 7 )
    v41 = v125[0];
  wil::ActivityBase<SearchIndexerDiagnosticsLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerDiagnosticsLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v139);
  v139[0] = &SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient::`vftable';
  SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient::StartActivity(
    (SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient *)v139,
    v41);
  if ( !v134[3] )
  {
    v75 = (const char *)(unsigned int)wil::verify_hresult<long>(2147749396LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      v75,
      v77);
  }
  LODWORD(v81) = v90;
  v80 = v135 + 1;
  XArray<XInterface<IUnknown>>::XArray<XInterface<IUnknown>>(&v99, (unsigned int)(v135 + 1));
  LODWORD(v89) = 1;
  v82 = 0;
  v98 = (CMRowsetProps *)operator new(0x80u);
  v82 = CMRowsetProps::CMRowsetProps(v98, (CRootQuerySpec *)((char *)this + 416));
  if ( (_DWORD)v90 )
    CMRowsetProps::SetImpliedProperties(v82, &IID_IRowset, v80);
  else
    CMRowsetProps::SetImpliedProperties(v82, v95, v80);
  v42 = CMRowsetProps::ArePropsInError(v82, (CRootQuerySpec *)((char *)this + 416));
  v44 = v42;
  v83 = v42;
  HIDWORD(v84) = v42;
  if ( v42 )
  {
    if ( (byte_180368441 & 1) != 0 )
    {
      v45 = *((_QWORD *)this + 23);
      v46 = L"Unknown";
      if ( v45 )
        v46 = (const wchar_t *)*((_QWORD *)this + 23);
      McTemplateU0zq_EventWriteTransfer(v45, v43, v46, v42);
    }
    if ( v44 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x406,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
        (const char *)(unsigned int)v44,
        v77);
    XPtr<CMRowsetProps>::~XPtr<CMRowsetProps>(&v82);
    XArray<XInterface<IUnknown>>::~XArray<XInterface<IUnknown>>(&v99);
    SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient *)v139);
    std::wstring::_Tidy_deallocate(v125);
    if ( *(_QWORD *)pguid.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)pguid.Data4);
    if ( Block != v103 )
    {
      operator delete(Block);
      Block = v103;
      v101 = 5;
    }
    if ( v105 != v106 )
    {
      operator delete(v105);
      v105 = v106;
      v104 = 5;
    }
    if ( v123 != v124 )
    {
      operator delete(v123);
      v123 = v124;
      v122 = 5;
    }
    if ( v108 != v109 )
    {
      operator delete(v108);
      v108 = v109;
      v107 = 5;
    }
    CParseCommandTree::~CParseCommandTree((CParseCommandTree *)v130);
    SearchIndexerTelemetry::ParseTreeActivity::~ParseTreeActivity((SearchIndexerTelemetry::ParseTreeActivity *)v140);
    XPtr<CColumnGroupArray>::~XPtr<CColumnGroupArray>(&v92);
    ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v88);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>(&pv);
    SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity((SearchIndexerTelemetry::QueryExecutionActivity *)v138);
    if ( v94[1] )
      std::_Ref_count_base::_Decref(v94[1]);
    SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient *)v128);
    LeaveCriticalSection(v13);
    return (unsigned int)v44;
  }
  if ( v132 )
    CUtlProps::SetValLong(v82, 0, 0xFu, v132);
  if ( v133 )
  {
    v47 = v82;
    CUtlProps::SetValLong(v82, 0, 0x10u, v133);
    *((_DWORD *)v47 + 29) |= 0x80u;
  }
  if ( *((_QWORD *)this + 345) )
  {
    v48 = v82;
    CUtlProps::SetValBool(v82, v43, 3u, -1);
    CUtlProps::SetValBool(v48, v49, 4u, -1);
    *((_DWORD *)v48 + 29) |= 2u;
  }
  if ( v79 )
    CUtlProps::SetValLong(v82, 3u, 0, 1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58638708>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58638708>::GetImpl'::`2'::impl)
    && *((_BYTE *)this + 2802) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60141615>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60141615>::GetImpl'::`2'::impl) )
      SearchIndexerTelemetryAggregatedHigh::QueryCancellationMetrics(2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)0x80040E4ELL,
      v77);
    XPtr<CMRowsetProps>::~XPtr<CMRowsetProps>(&v82);
    XArray<XInterface<IUnknown>>::~XArray<XInterface<IUnknown>>(&v99);
    SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient *)v139);
    std::wstring::_Tidy_deallocate(v125);
    if ( *(_QWORD *)pguid.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)pguid.Data4);
    if ( Block != v103 )
    {
      operator delete(Block);
      Block = v103;
      v101 = 5;
    }
    if ( v105 != v106 )
    {
      operator delete(v105);
      v105 = v106;
      v104 = 5;
    }
    if ( v123 != v124 )
    {
      operator delete(v123);
      v123 = v124;
      v122 = 5;
    }
    if ( v108 != v109 )
    {
      operator delete(v108);
      v108 = v109;
      v107 = 5;
    }
    CParseCommandTree::~CParseCommandTree((CParseCommandTree *)v130);
    SearchIndexerTelemetry::ParseTreeActivity::~ParseTreeActivity((SearchIndexerTelemetry::ParseTreeActivity *)v140);
    XPtr<CColumnGroupArray>::~XPtr<CColumnGroupArray>(&v92);
    ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v88);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>(&pv);
    SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity((SearchIndexerTelemetry::QueryExecutionActivity *)v138);
    if ( v94[1] )
      std::_Ref_count_base::_Decref(v94[1]);
LABEL_199:
    SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient *)v128);
    LeaveCriticalSection(v13);
    return 2147749454LL;
  }
  v98 = (CRootQuerySpec *)((char *)this + 216);
  if ( !*((_QWORD *)this + 27) )
  {
    wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v137);
    v137[0] = &SearchIndexerTelemetry::QueryInternalQueryActivity::`vftable';
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    {
      CUtlProps::GetValGuid((CRootQuerySpec *)((char *)this + 416), &v127, v50, 0xDu);
      v51 = SearchIndexerTelemetry::QueryInternalQueryActivity::Start<_GUID const>((SearchIndexerTelemetry::QueryInternalQueryActivity *)v141);
      SearchIndexerTelemetry::QueryInternalQueryActivity::operator=(v137, v51);
      SearchIndexerTelemetry::QueryInternalQueryActivity::~QueryInternalQueryActivity((SearchIndexerTelemetry::QueryInternalQueryActivity *)v141);
    }
    *((_QWORD *)this + 27) = (*(__int64 (__fastcall **)(CRootQuerySpec *))(*(_QWORD *)this + 88LL))(this);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
      wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v137);
    SearchIndexerTelemetry::QueryInternalQueryActivity::~QueryInternalQueryActivity((SearchIndexerTelemetry::QueryInternalQueryActivity *)v137);
  }
  v90 = *((_QWORD *)this + 73);
  GetUserDefaultLCID();
  v87 = 0;
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, wchar_t ***))this + 27))(
         *((_QWORD *)this + 27),
         &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352,
         &v87) >= 0 )
    (*((void (__fastcall **)(wchar_t **, _QWORD))*v87 + 3))(v87, *((_QWORD *)this + 349));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58638708>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58638708>::GetImpl'::`2'::impl)
    && *((_BYTE *)this + 2802) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60141615>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60141615>::GetImpl'::`2'::impl) )
      SearchIndexerTelemetryAggregatedHigh::QueryCancellationMetrics(2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x463,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)0x80040E4ELL,
      v77);
    ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v87);
    XPtr<CMRowsetProps>::~XPtr<CMRowsetProps>(&v82);
    XArray<XInterface<IUnknown>>::~XArray<XInterface<IUnknown>>(&v99);
    SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient *)v139);
    std::wstring::_Tidy_deallocate(v125);
    if ( *(_QWORD *)pguid.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)pguid.Data4);
    if ( Block != v103 )
    {
      operator delete(Block);
      Block = v103;
      v101 = 5;
    }
    if ( v105 != v106 )
    {
      operator delete(v105);
      v105 = v106;
      v104 = 5;
    }
    if ( v123 != v124 )
    {
      operator delete(v123);
      v123 = v124;
      v122 = 5;
    }
    if ( v108 != v109 )
    {
      operator delete(v108);
      v108 = v109;
      v107 = 5;
    }
    CParseCommandTree::~CParseCommandTree((CParseCommandTree *)v130);
    SearchIndexerTelemetry::ParseTreeActivity::~ParseTreeActivity((SearchIndexerTelemetry::ParseTreeActivity *)v140);
    XPtr<CColumnGroupArray>::~XPtr<CColumnGroupArray>(&v92);
    ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v88);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>(&pv);
    SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity((SearchIndexerTelemetry::QueryExecutionActivity *)v138);
    if ( v94[1] )
      std::_Ref_count_base::_Decref(v94[1]);
    goto LABEL_199;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60916561>::GetImpl'::`2'::impl) )
  {
    std::shared_ptr<inverted::IInvertedQueryProps>::shared_ptr<inverted::IInvertedQueryProps>(&v110, v94);
    v78 = v134;
    v52(v53, v85, v131, v136);
  }
  else
  {
    v54 = *((_QWORD *)this + 27);
    v55 = *(void (__fastcall **)(__int64, struct IUnknown *, _BYTE *, _BYTE *))(*(_QWORD *)v54 + 24LL);
    Buf1 = 0;
    v78 = v134;
    v55(v54, v85, v131, v136);
  }
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v87);
  v56 = *v99;
  *v99 = 0;
  v88 = v56;
  if ( *((_QWORD *)this + 80) )
  {
    v85 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v56->lpVtbl->QueryInterface)(
           v56,
           &GUID_dd7aa19c_dacf_4378_a0be_e58a18d08983,
           &v85) >= 0 )
    {
      v83 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v85->lpVtbl[1].QueryInterface)(
              v85,
              *((_QWORD *)this + 80));
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 40LL))(*((_QWORD *)this + 27)) == 265 )
      {
        HIDWORD(v84) = 0;
        v57 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 80) + 72LL))(
                *((_QWORD *)this + 80),
                (char *)&v84 + 4);
        v83 = v57;
        if ( v57 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B7,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
            (const char *)(unsigned int)v57,
            (int)v134);
        if ( HIDWORD(v84) )
          DrainRowset(v56);
      }
      v58 = *((_QWORD *)this + 80);
      if ( v58 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      *((_QWORD *)this + 80) = 0;
    }
    if ( v85 )
      ((void (__fastcall *)(struct IUnknown *))v85->lpVtbl->Release)(v85);
  }
  v91 = -1;
  v59 = *v117 != 0;
  if ( *((_QWORD *)this + 347) || *v117 )
  {
    v81 = 0;
    TComPointer<IReuseContext>::InitializeByCertainQI(&v81, v56);
    v60 = (*(__int64 (__fastcall **)(unsigned int *, BOOL))(*(_QWORD *)v81 + 64LL))(v81, v59);
    v14 = v60;
    if ( v60 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4CA,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
        (const char *)(unsigned int)v60,
        (int)v134);
    if ( *((_QWORD *)this + 347) )
    {
      v61 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v81 + 48LL))(v81);
      v14 = v61;
      if ( v61 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4CF,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
          (const char *)(unsigned int)v61,
          (int)v134);
      v62 = *((_QWORD *)this + 344);
      if ( v62 )
      {
        v85 = 0;
        (*(void (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v62 + 40LL))(v62, &v85);
        v63 = *(__int64 (**)(void))(*(_QWORD *)v81 + 32LL);
        if ( v85 )
        {
          v64 = v63();
          v14 = v64;
          if ( v64 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4D9,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
              (const char *)(unsigned int)v64,
              (int)v134);
        }
        else
        {
          v65 = ((__int64 (__fastcall *)(unsigned int *, _QWORD))v63)(v81, *((_QWORD *)this + 344));
          v14 = v65;
          if ( v65 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4DF,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
              (const char *)(unsigned int)v65,
              (int)v134);
        }
        if ( v85 )
          ((void (__fastcall *)(struct IUnknown *))v85->lpVtbl->Release)(v85);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
    {
      (*(void (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v81 + 80LL))(
        v81,
        (__int64)(*((_QWORD *)this + 352) - *((_QWORD *)this + 351)) >> 5);
      (*(void (__fastcall **)(unsigned int *, _QWORD))(*(_QWORD *)v81 + 88LL))(v81, *((_QWORD *)this + 348));
      v66 = *((_QWORD *)this + 348);
      if ( v66 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      *((_QWORD *)this + 348) = 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58638708>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58638708>::GetImpl'::`2'::impl)
      && *((_BYTE *)this + 2802) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60141615>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60141615>::GetImpl'::`2'::impl) )
        SearchIndexerTelemetryAggregatedHigh::QueryCancellationMetrics(2);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F4,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
        (const char *)0x80040E4ELL,
        (int)v134);
      if ( v81 )
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v81 + 16LL))(v81);
      XPtr<CMRowsetProps>::~XPtr<CMRowsetProps>(&v82);
      XArray<XInterface<IUnknown>>::~XArray<XInterface<IUnknown>>(&v99);
      SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient *)v139);
      std::wstring::_Tidy_deallocate(v125);
      if ( *(_QWORD *)pguid.Data4 )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)pguid.Data4);
      if ( Block != v103 )
      {
        operator delete(Block);
        Block = v103;
        v101 = 5;
      }
      if ( v105 != v106 )
      {
        operator delete(v105);
        v105 = v106;
        v104 = 5;
      }
      if ( v123 != v124 )
      {
        operator delete(v123);
        v123 = v124;
        v122 = 5;
      }
      if ( v108 != v109 )
      {
        operator delete(v108);
        v108 = v109;
        v107 = 5;
      }
      CParseCommandTree::~CParseCommandTree((CParseCommandTree *)v130);
      SearchIndexerTelemetry::ParseTreeActivity::~ParseTreeActivity((SearchIndexerTelemetry::ParseTreeActivity *)v140);
      XPtr<CColumnGroupArray>::~XPtr<CColumnGroupArray>(&v92);
      ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v88);
      wil::com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>(&pv);
      SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity((SearchIndexerTelemetry::QueryExecutionActivity *)v138);
      if ( v94[1] )
        std::_Ref_count_base::_Decref(v94[1]);
      goto LABEL_199;
    }
    (*(void (__fastcall **)(unsigned int *, unsigned int *))(*(_QWORD *)v81 + 24LL))(v81, &v91);
    if ( v81 )
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v81 + 16LL))(v81);
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 343) + 48LL))(*((_QWORD *)this + 343));
  v68 = *((_QWORD *)this + 344);
  if ( v68 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  *((_QWORD *)this + 344) = 0;
  v69 = v95;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&v95->Data1
    && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)v95->Data4 )
  {
    *v93 = v56;
    v88 = 0;
  }
  else
  {
    if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&v95->Data1 && *(_QWORD *)GUID_NULL.Data4 == *(_QWORD *)v95->Data4 )
      v71 = v83;
    else
      v71 = ((__int64 (__fastcall *)(struct IUnknown *, struct _GUID *, void **))v56->lpVtbl->QueryInterface)(
              v56,
              v95,
              v93);
    v69 = (struct _GUID *)retaddr;
    if ( v71 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
        (const char *)(unsigned int)v71,
        (int)v134);
  }
  *v118 &= ~0x10000000u;
  if ( (byte_180368441 & 1) != 0 )
  {
    v70 = L"Unknown";
    if ( *v111 )
      v70 = (const wchar_t *)*v111;
    McTemplateU0zq_EventWriteTransfer(v69, v67, v70, 0);
  }
  if ( (byte_180368442 & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(
      &Microsoft_Windows_Search_Core_Context,
      MSSearchTraceId_ClientQuery_Rowset_Reuse,
      v91);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pguid.Data1 + 16LL))(*(_QWORD *)&pguid.Data1);
  wil::ActivityBase<SearchIndexerDiagnosticsLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v139);
  XPtr<CMRowsetProps>::~XPtr<CMRowsetProps>(&v82);
  XArray<XInterface<IUnknown>>::~XArray<XInterface<IUnknown>>(&v99);
  SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionClient *)v139);
  std::wstring::_Tidy_deallocate(v125);
  if ( *(_QWORD *)pguid.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)pguid.Data4);
  if ( Block != v103 )
  {
    operator delete(Block);
    Block = v103;
    v101 = 5;
  }
  if ( v105 != v106 )
  {
    operator delete(v105);
    v105 = v106;
    v104 = 5;
  }
  if ( v123 != v124 )
  {
    operator delete(v123);
    v123 = v124;
    v122 = 5;
  }
  if ( v108 != v109 )
  {
    operator delete(v108);
    v108 = v109;
    v107 = 5;
  }
  CParseCommandTree::~CParseCommandTree((CParseCommandTree *)v130);
  SearchIndexerTelemetry::ParseTreeActivity::~ParseTreeActivity((SearchIndexerTelemetry::ParseTreeActivity *)v140);
  XPtr<CColumnGroupArray>::~XPtr<CColumnGroupArray>(&v92);
  v72 = &psz;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl);
  if ( IsEnabled && StrStrIW(*((PCWSTR *)this + 23), L"CONTAINSSEMANTIC") )
    v129 = 1;
  SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::Stop(
    (SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient *)v128,
    v14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v138);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
  {
    v74 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>::ensure_data(&pv);
    v98 = (CMRowsetProps *)v74;
    if ( v74 )
      _InterlockedIncrement((volatile signed __int32 *)(v74 + 280));
    tip2::details::shared_data<0,0,0>::begin_update(v74 + 8);
    *(_BYTE *)(v74 + 272) = 0;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>::~test_data_control<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>(&v98);
    if ( pv )
      tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60916561>::GetImpl'::`2'::impl)
    && v94[0] )
  {
    if ( *((_QWORD *)this + 23) )
      v72 = (const wchar_t *)*((_QWORD *)this + 23);
    SearchIndexerTelemetryAggregatedNormal::WSearchQueryTelemetry::AddExecutionParams(
      v94[0],
      CurrentTimestamp,
      v14,
      v79,
      v72);
  }
  if ( v14 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)(unsigned int)v14,
      (int)v78);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v88);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>,wil::err_returncode_policy>(&pv);
  SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity((SearchIndexerTelemetry::QueryExecutionActivity *)v138);
  if ( v94[1] )
    std::_Ref_count_base::_Decref(v94[1]);
  SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::~IndexerQueryExecutionClient((SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient *)v128);
  LeaveCriticalSection(v13);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180132be0  push    rbx
0x180132be2  push    rsi
0x180132be3  push    rdi
0x180132be4  push    r12
0x180132be6  push    r13
0x180132be8  push    r14
0x180132bea  push    r15
0x180132bec  sub     rsp, 0CC0h
0x180132bf3  mov     rax, cs:__security_cookie
0x180132bfa  xor     rax, rsp
0x180132bfd  mov     [rsp+0CF8h+var_48], rax
0x180132c05  mov     rbx, r9
0x180132c08  mov     rdi, r8
0x180132c0b  mov     [rsp+0CF8h+var_BE8], r8
0x180132c13  mov     rsi, rdx
0x180132c16  mov     [rsp+0CF8h+var_C40], rdx
0x180132c1e  mov     r12, rcx
0x180132c21  mov     [rsp+0CF8h+var_BE0], rcx
0x180132c29  mov     [rsp+0CF8h+var_AD8], rdx
0x180132c31  mov     [rsp+0CF8h+var_AE0], r8
0x180132c39  mov     r14, [rsp+0CF8h+arg_28]
0x180132c41  mov     [rsp+0CF8h+var_C00], r14
0x180132c49  xor     edx, edx; perrinfo
0x180132c4b  xor     ecx, ecx; dwReserved
0x180132c4d  call    cs:__imp_SetErrorInfo
0x180132c53  movups  xmm0, xmmword ptr cs:IID_ICommand.Data1
0x180132c5a  movdqu  xmmword ptr [rsp+0CF8h+var_AC8.Data1], xmm0
0x180132c63  xor     r15d, r15d
0x180132c66  test    r14, r14
0x180132c69  jnz     short loc_180132CAE
0x180132c6b  lea     rcx, [r12+80h]; this
0x180132c73  lea     r8, [rsp+0CF8h+var_AC8]; struct _GUID *
0x180132c7b  mov     edx, 80070057h; int
0x180132c80  call    ?PostHResult@CCIOleDBError@@QEAAJJAEBU_GUID@@@Z; CCIOleDBError::PostHResult(long,_GUID const &)
0x180132c85  mov     ebx, eax
0x180132c87  test    eax, eax
0x180132c89  jns     short loc_180132CA7
0x180132c8b  mov     edx, 2D8h; void *
0x180132c90  mov     rcx, [rsp+0CF8h]; this
0x180132c98  mov     r9d, ebx; char *
0x180132c9b  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180132ca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132ca7  mov     eax, ebx
0x180132ca9  jmp     loc_180134D43
0x180132cae  test    rsi, rsi
0x180132cb1  jz      short loc_180132CF3
0x180132cb3  mov     rax, [rdi]
0x180132cb6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180132cbd  jnz     short loc_180132CCC
0x180132cbf  mov     rax, [rdi+8]
0x180132cc3  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180132cca  jz      short loc_180132CF3
0x180132ccc  lea     rcx, [r12+80h]; this
0x180132cd4  lea     r8, [rsp+0CF8h+var_AC8]; struct _GUID *
0x180132cdc  mov     edx, 80040E22h; int
0x180132ce1  call    ?PostHResult@CCIOleDBError@@QEAAJJAEBU_GUID@@@Z; CCIOleDBError::PostHResult(long,_GUID const &)
0x180132ce6  mov     ebx, eax
0x180132ce8  test    eax, eax
0x180132cea  jns     short loc_180132CA7
0x180132cec  mov     edx, 2DDh
0x180132cf1  jmp     short loc_180132C90
0x180132cf3  test    rbx, rbx
0x180132cf6  jz      short loc_180132D22
0x180132cf8  lea     rcx, [r12+80h]; this
0x180132d00  lea     r8, [rsp+0CF8h+var_AC8]; struct _GUID *
0x180132d08  mov     edx, 80070057h; int
0x180132d0d  call    ?PostHResult@CCIOleDBError@@QEAAJJAEBU_GUID@@@Z; CCIOleDBError::PostHResult(long,_GUID const &)
0x180132d12  mov     ebx, eax
0x180132d14  test    eax, eax
0x180132d16  jns     short loc_180132CA7
0x180132d18  mov     edx, 2E2h
0x180132d1d  jmp     loc_180132C90
0x180132d22  mov     [rsp+0CF8h+var_AE8], r12
0x180132d2a  lea     rdi, [r12+50h]
0x180132d2f  mov     [rsp+0CF8h+lpCriticalSection], rdi
0x180132d37  mov     rcx, rdi; lpCriticalSection
0x180132d3a  call    cs:__imp_EnterCriticalSection
0x180132d40  nop
0x180132d41  mov     [rsp+0CF8h+var_C50], r15d
0x180132d49  mov     dword ptr [rsp+0CF8h+var_C4C+4], r15d
0x180132d51  lea     rax, [r12+0B0h]
0x180132d59  mov     [rsp+0CF8h+var_AB0], rax
0x180132d61  btr     dword ptr [rax], 1Ch
0x180132d65  mov     [rsp+0CF8h+var_C68], r15b
0x180132d6d  mov     [rsp+0CF8h+var_C67], r15b
0x180132d75  mov     r13d, r15d
0x180132d78  call    ?IsRunningInContainer@@YA_NXZ; IsRunningInContainer(void)
0x180132d7d  mov     dl, al; bool
0x180132d7f  lea     rcx, [rsp+0CF8h+var_9F8]; this
0x180132d87  call    ??0IndexerQueryExecutionClient@SearchIndexerTelemetryAggregatedNormal@@QEAA@_N@Z; SearchIndexerTelemetryAggregatedNormal::IndexerQueryExecutionClient::IndexerQueryExecutionClient(bool)
0x180132d8c  nop
0x180132d8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57994465@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465> `wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl(void)'::`2'::impl
0x180132d94  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(void)
0x180132d99  mov     r14d, 0Dh
0x180132d9f  test    al, al
0x180132da1  jz      loc_180132ECC
0x180132da7  lea     rbx, [r12+1A0h]
0x180132daf  mov     r9d, r14d; unsigned int
0x180132db2  lea     rdx, [rsp+0CF8h+Buf1]; retstr
0x180132dba  mov     rcx, rbx; this
0x180132dbd  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180132dc2  lea     r8d, [r14+3]; Size
0x180132dc6  lea     rdx, GUID_NULL; Buf2
0x180132dcd  lea     rcx, [rsp+0CF8h+Buf1]; Buf1
0x180132dd5  call    memcmp_0
0x180132dda  test    eax, eax
0x180132ddc  jnz     short loc_180132E49
0x180132dde  xorps   xmm0, xmm0
0x180132de1  movups  xmmword ptr [rsp+0CF8h+pguid.Data1], xmm0
0x180132de9  lea     rcx, [rsp+0CF8h+pguid]; pguid
0x180132df1  call    CoCreateGuid_0
0x180132df6  test    eax, eax
0x180132df8  js      short loc_180132E49
0x180132dfa  lea     r8d, [r14+1Ah]; cchMax
0x180132dfe  lea     rdx, [rsp+0CF8h+sz]; lpsz
0x180132e06  lea     rcx, [rsp+0CF8h+pguid]; rguid
0x180132e0e  call    StringFromGUID2_0
0x180132e13  test    eax, eax
0x180132e15  jnz     short loc_180132E31
0x180132e17  lea     r8, aQueryFailedToC; "[Query] Failed to convert query GUID to"...
0x180132e1e  mov     edx, 304h; wchar_t *
0x180132e23  lea     rcx, aOnecoreuapBase_122; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180132e2a  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180132e2f  jmp     short loc_180132E49
0x180132e31  lea     r9, [rsp+0CF8h+sz]; wchar_t *
0x180132e39  mov     r8d, r14d; unsigned int
0x180132e3c  mov     edx, 2; unsigned int
0x180132e41  mov     rcx, rbx; this
0x180132e44  call    ?SetValString@CUtlProps@@QEAAJKKPEB_W@Z; CUtlProps::SetValString(ulong,ulong,wchar_t const *)
0x180132e49  mov     r9d, 0Ch; unsigned int
0x180132e4f  lea     rdx, [rsp+0CF8h+Buf1]; retstr
0x180132e57  mov     rcx, rbx; this
0x180132e5a  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180132e5f  mov     r8d, 10h; Size
0x180132e65  lea     rdx, GUID_NULL; Buf2
0x180132e6c  lea     rcx, [rsp+0CF8h+Buf1]; Buf1
0x180132e74  call    memcmp_0
0x180132e79  test    eax, eax
0x180132e7b  jnz     short loc_180132ECC
0x180132e7d  lea     r8d, [rax+27h]; cchMax
0x180132e81  lea     rdx, [rsp+0CF8h+sz]; lpsz
0x180132e89  lea     rcx, rguid; rguid
0x180132e90  call    StringFromGUID2_0
0x180132e95  test    eax, eax
0x180132e97  jnz     short loc_180132EB3
0x180132e99  lea     r8, aQueryFailedToC_0; "[Query] Failed to convert session GUID "...
0x180132ea0  mov     edx, 316h; wchar_t *
0x180132ea5  lea     rcx, aOnecoreuapBase_122; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180132eac  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180132eb1  jmp     short loc_180132ECC
0x180132eb3  lea     r9, [rsp+0CF8h+sz]; wchar_t *
0x180132ebb  mov     edx, 2; unsigned int
0x180132ec0  lea     r8d, [rdx+0Ah]; unsigned int
0x180132ec4  mov     rcx, rbx; this
0x180132ec7  call    ?SetValString@CUtlProps@@QEAAJKKPEB_W@Z; CUtlProps::SetValString(ulong,ulong,wchar_t const *)
0x180132ecc  xorps   xmm0, xmm0
0x180132ecf  movdqu  xmmword ptr [rsp+0CF8h+var_BF8], xmm0
0x180132ed8  mov     [rsp+0CF8h+var_AD0], r15
0x180132ee0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60916561@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60916561@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561> `wil::Feature<__WilFeatureTraits_Feature_60916561>::GetImpl(void)'::`2'::impl
0x180132ee7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60916561@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561>::__private_IsEnabled(void)
0x180132eec  test    al, al
0x180132eee  jz      loc_180132FF2
0x180132ef4  lea     rbx, [r12+1A0h]
0x180132efc  mov     r9d, 0Ch; unsigned int
0x180132f02  lea     rdx, [rsp+0CF8h+Buf1]; retstr
0x180132f0a  mov     rcx, rbx; this
0x180132f0d  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180132f12  mov     r8d, 10h; Size
0x180132f18  lea     rdx, ?FE_SCOPE_QUERY@@3U_GUID@@B; Buf2
0x180132f1f  lea     rcx, [rsp+0CF8h+Buf1]; Buf1
0x180132f27  call    memcmp_0
0x180132f2c  test    eax, eax
0x180132f2e  jz      short loc_180132FA5
0x180132f30  mov     r9d, 0Ch; unsigned int
0x180132f36  lea     rdx, [rsp+0CF8h+Buf1]; retstr
0x180132f3e  mov     rcx, rbx; this
0x180132f41  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180132f46  mov     r9d, r14d; unsigned int
0x180132f49  lea     rdx, [rsp+0CF8h+pguid]; retstr
0x180132f51  mov     rcx, rbx; this
0x180132f54  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180132f59  lea     r8, [rsp+0CF8h+Buf1]
0x180132f61  lea     rdx, [rsp+0CF8h+pguid]
0x180132f69  lea     rcx, [rsp+0CF8h+var_BC8]
0x180132f71  call    ??$make_shared@VWSearchQueryTelemetry@SearchIndexerTelemetryAggregatedNormal@@$$CBU_GUID@@$$CBU3@@std@@YA?AV?$shared_ptr@VWSearchQueryTelemetry@SearchIndexerTelemetryAggregatedNormal@@@0@$$QEBU_GUID@@0@Z; std::make_shared<SearchIndexerTelemetryAggregatedNormal::WSearchQueryTelemetry,_GUID const,_GUID const>(_GUID const &&,_GUID const &&)
0x180132f76  mov     rdx, rax
0x180132f79  lea     rcx, [rsp+0CF8h+var_BF8]
0x180132f81  call    ??$?4VCNoneOperator@inverted@@$0A@@?$shared_ptr@VCQueryOperator@inverted@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@VCNoneOperator@inverted@@@1@@Z; std::shared_ptr<inverted::CQueryOperator>::operator=<inverted::CNoneOperator,0>(std::shared_ptr<inverted::CNoneOperator> &&)
0x180132f86  mov     rcx, [rsp+0CF8h+var_BC0]; this
0x180132f8e  test    rcx, rcx
0x180132f91  jz      short loc_180132F98
0x180132f93  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180132f98  call    ?GetCurrentTimestamp@WSearchQueryTelemetry@SearchIndexerTelemetryAggregatedNormal@@SA_KXZ; SearchIndexerTelemetryAggregatedNormal::WSearchQueryTelemetry::GetCurrentTimestamp(void)
0x180132f9d  mov     [rsp+0CF8h+var_AD0], rax
0x180132fa5  jmp     short loc_180132FF2
0x180132fa7  xor     r15d, r15d
0x180132faa  lea     r14d, [r15+0Dh]
0x180132fae  mov     rdi, [rsp+0CF8h+lpCriticalSection]
0x180132fb6  mov     eax, r15d
0x180132fb9  mov     [rsp+0CF8h+var_C50], eax
0x180132fc0  mov     [rsp+0CF8h+var_C68], al
0x180132fc7  mov     r13d, r15d
0x180132fca  mov     r12, [rsp+0CF8h+var_BE0]
0x180132fd2  mov     rax, [rsp+0CF8h+var_AD8]
0x180132fda  mov     [rsp+0CF8h+var_C40], rax
0x180132fe2  mov     rax, [rsp+0CF8h+var_AE0]
0x180132fea  mov     [rsp+0CF8h+var_BE8], rax
0x180132ff2  lea     rdx, aQueryexecution; "QueryExecutionActivity"
0x180132ff9  lea     rcx, [rsp+0CF8h+var_5D8]; struct wil::details::IFailureCallback *
0x180133001  call    ??0?$ActivityBase@VSearchIndexerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180133006  lea     rax, ??_7QueryExecutionActivity@SearchIndexerTelemetry@@6B@; const SearchIndexerTelemetry::QueryExecutionActivity::`vftable'
0x18013300d  mov     [rsp+0CF8h+var_5D8], rax
0x180133015  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59422362@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362> `wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl(void)'::`2'::impl
0x18013301c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(void)
0x180133021  test    al, al
0x180133023  jz      short loc_180133090
0x180133025  lea     rbx, [r12+1A0h]
0x18013302d  mov     r9d, 0Ch; unsigned int
0x180133033  lea     rdx, [rsp+0CF8h+Buf1]; retstr
0x18013303b  mov     rcx, rbx; this
0x18013303e  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180133043  mov     r9d, r14d; unsigned int
0x180133046  lea     rdx, [rsp+0CF8h+pguid]; retstr
0x18013304e  mov     rcx, rbx; this
0x180133051  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180133056  lea     r8, [rsp+0CF8h+Buf1]
0x18013305e  lea     rdx, [rsp+0CF8h+pguid]
0x180133066  lea     rcx, [rsp+0CF8h+var_728]; this
0x18013306e  call    ??$Start@$$CBU_GUID@@$$CBU1@@QueryExecutionActivity@SearchIndexerTelemetry@@SA?AV01@$$QEBU_GUID@@0@Z; SearchIndexerTelemetry::QueryExecutionActivity::Start<_GUID const,_GUID const>(_GUID const &&,_GUID const &&)
0x180133073  mov     rdx, rax
0x180133076  lea     rcx, [rsp+0CF8h+var_5D8]
0x18013307e  call    ??4QueryExecutionActivity@SearchIndexerTelemetry@@QEAAAEAV01@$$QEAV01@@Z; SearchIndexerTelemetry::QueryExecutionActivity::operator=(SearchIndexerTelemetry::QueryExecutionActivity &&)
0x180133083  lea     rcx, [rsp+0CF8h+var_728]; this
0x18013308b  call    ??1QueryExecutionActivity@SearchIndexerTelemetry@@QEAA@XZ; SearchIndexerTelemetry::QueryExecutionActivity::~QueryExecutionActivity(void)
0x180133090  mov     [rsp+0CF8h+pv], r15
0x180133098  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x18013309f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x1801330a4  test    al, al
0x1801330a6  jnz     short loc_1801330AF
0x1801330a8  mov     esi, 1
0x1801330ad  jmp     short loc_1801330FB
0x1801330af  lea     rcx, [rsp+0CF8h+var_A50]; struct wil::details::IFailureCallback *
0x1801330b7  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_PerfTotalTimeTakenByAllCursorTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1801330bc  mov     rcx, [rax+38h]
0x1801330c0  mov     rax, [rsp+0CF8h+pv]
0x1801330c8  mov     [rsp+0CF8h+pv], rcx
0x1801330d0  mov     esi, 1
0x1801330d5  test    rcx, rcx
0x1801330d8  jz      short loc_1801330E1
0x1801330da  lock add [rcx+118h], esi
0x1801330e1  test    rax, rax
0x1801330e4  jz      short loc_1801330EE
0x1801330e6  mov     rcx, rax; pv
0x1801330e9  call    ?Release@?$merged_data@U_tip_PerfTotalTimeTakenByAllCursorTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>::Release(void)
0x1801330ee  lea     rcx, [rsp+0CF8h+var_A50]
0x1801330f6  call    ??1?$test_watcher@V?$merged_data@U_tip_PerfTotalTimeTakenByAllCursorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>::~test_watcher<tip2::details::merged_data<_tip_PerfTotalTimeTakenByAllCursorTest,_tip_PerfTotalTimeTakenByAllCursorTest>>(void)
0x1801330fb  mov     [rsp+0CF8h+var_C28], r15
0x180133103  mov     rax, [rsp+0CF8h+var_C00]
0x18013310b  mov     [rax], r15
0x18013310e  mov     rax, qword ptr cs:_GUID_bedba8d9_c93a_4c0b_97ba_40bdb5a2b4c1.Data1
0x180133115  mov     rcx, [rsp+0CF8h+var_BE8]
0x18013311d  cmp     rax, [rcx]
0x180133120  jnz     short loc_18013312F
0x180133122  mov     rax, qword ptr cs:_GUID_bedba8d9_c93a_4c0b_97ba_40bdb5a2b4c1.Data4
0x180133129  cmp     rax, [rcx+8]
0x18013312d  jz      short loc_180133148
0x18013312f  mov     rax, qword ptr cs:_GUID_21c3f4c2_02df_404f_9d50_070cee79540f.Data1
0x180133136  cmp     rax, [rcx]
0x180133139  jnz     short loc_180133151
0x18013313b  mov     rax, qword ptr cs:_GUID_21c3f4c2_02df_404f_9d50_070cee79540f.Data4
0x180133142  cmp     rax, [rcx+8]
0x180133146  jnz     short loc_180133151
0x180133148  mov     dword ptr [rsp+0CF8h+var_C18], esi
0x18013314f  jmp     short loc_180133159
0x180133151  mov     dword ptr [rsp+0CF8h+var_C18], r15d
0x180133159  mov     rcx, r12; this
0x18013315c  call    ?_EnsureStructuredQueryHelperExists@CRootQuerySpec@@AEAAXXZ; CRootQuerySpec::_EnsureStructuredQueryHelperExists(void)
0x180133161  mov     rbx, [rsp+0CF8h+var_AE8]
0x180133169  lea     rdx, [rbx+0B8h]
0x180133170  mov     [rsp+0CF8h+var_AF0], rdx
0x180133178  cmp     [r12+278h], r15
0x180133180  jnz     loc_1801332AA
0x180133186  cmp     [rdx], r15
0x180133189  jnz     loc_180133282
0x18013318f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58638708@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58638708@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58638708> `wil::Feature<__WilFeatureTraits_Feature_58638708>::GetImpl(void)'::`2'::impl
0x180133196  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58638708@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58638708>::__private_IsEnabled(void)
0x18013319b  test    al, al
0x18013319d  jz      loc_18013324B
0x1801331a3  mov     al, [r12+0AF2h]
0x1801331ab  nop
0x1801331ac  test    al, al
0x1801331ae  jz      loc_18013324B
0x1801331b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60141615@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60141615@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60141615> `wil::Feature<__WilFeatureTraits_Feature_60141615>::GetImpl(void)'::`2'::impl
0x1801331bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60141615@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60141615>::__private_IsEnabled(void)
0x1801331c0  test    al, al
0x1801331c2  jz      short loc_1801331CE
0x1801331c4  mov     ecx, 2
0x1801331c9  call    ?QueryCancellationMetrics@SearchIndexerTelemetryAggregatedHigh@@SAXW4QueryCancellationEventInfo@@@Z; SearchIndexerTelemetryAggregatedHigh::QueryCancellationMetrics(QueryCancellationEventInfo)
0x1801331ce  mov     rcx, [rsp+0CF8h]; this
0x1801331d6  mov     ebx, 80040E4Eh
  ... truncated ...
```
