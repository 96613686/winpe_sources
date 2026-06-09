# Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::EvaluateUPMLModel(float)

- ea: `0x1800d7bf4`
- end: `0x1800d8a10`
- name: `?EvaluateUPMLModel@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@AEAAMM@Z`
- size: `3612`
- prototype: `float __fastcall(Windows::RebootDowntime::QualityUpdateDowntimeEvaluator *__hidden this, float)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d7310`

## callees

- `0x18000edb0`
- `0x180010890`
- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18002e168`
- `0x18002e698`
- `0x18002ea8c`
- `0x18003007c`
- `0x180098664`
- `0x1800b8ae0`
- `0x1800ba814`
- `0x1800bad50`
- `0x1800c4d00`
- `0x1800cd700`
- `0x1800d0674`
- `0x1800d06fc`
- `0x1800d07a8`
- `0x1800d0834`
- `0x1800d08b0`
- `0x1800d5f38`
- `0x1800d5fa4`
- `0x1800d7b18`
- `0x1800d7bf4`
- `0x1800da780`
- `0x1800da93c`
- `0x1800dd930`
- `0x1800dddf4`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d87dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d880c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d87dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d880c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8824`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7cba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d7cba`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d7c6f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d7c6f`

## string_xrefs

- `0x1800d879f`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d8989`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d89b3`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d89c8`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d89e6`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d89fe`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
float __fastcall Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::EvaluateUPMLModel(
        Windows::RebootDowntime::QualityUpdateDowntimeEvaluator *this,
        float a2)
{
  const char *v4; // r9
  HRESULT v5; // eax
  __int64 i; // rbx
  __int64 v7; // rdi
  void *v8; // rcx
  _QWORD *v9; // rax
  unsigned int v10; // edi
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rax
  void *v14; // rax
  __int64 v15; // rax
  LPVOID *v16; // xmm0_8
  __m128i v17; // xmm1
  LPVOID *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  void *v22; // rax
  __int64 v23; // rax
  __int128 *v24; // xmm0_8
  __m128i v25; // xmm1
  __int128 *v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rbx
  __int64 v29; // rax
  void *v30; // rax
  __int64 v31; // rax
  __int128 *v32; // xmm0_8
  __m128i v33; // xmm1
  __int128 *v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rbx
  __int64 v37; // rax
  void *v38; // rax
  __int64 v39; // rax
  __int128 *v40; // xmm0_8
  __m128i v41; // xmm1
  __int128 *v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rbx
  __int64 v45; // rax
  void *v46; // rax
  __int64 v47; // rax
  __int128 *v48; // xmm0_8
  __m128i v49; // xmm1
  __int128 *v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rbx
  __int64 v53; // rax
  void *v54; // rax
  __int64 v55; // rax
  __int128 *v56; // xmm0_8
  __m128i v57; // xmm1
  __int128 *v58; // rdx
  __int64 v59; // r8
  LPVOID v60; // rbx
  __int64 (__fastcall *v61)(LPVOID, unsigned __int64, _QWORD, const wchar_t *); // rdi
  _QWORD *v62; // rax
  int v63; // eax
  __int64 v64; // rbx
  __int64 (__fastcall *v65)(__int64, _QWORD, __int64, const wchar_t *); // rdi
  _QWORD *v66; // rax
  int v67; // eax
  int v68; // ebx
  bool v69; // bl
  void *v70; // rcx
  void *v71; // rcx
  void *v72; // rcx
  LPVOID v73; // rbx
  __int64 (__fastcall *v74)(LPVOID, __int64, _QWORD, const wchar_t *); // rdi
  _QWORD *v75; // rax
  int v76; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  int ppvb; // [rsp+28h] [rbp-E0h]
  int ppvc; // [rsp+28h] [rbp-E0h]
  __int128 Src_8; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v83; // [rsp+58h] [rbp-B0h]
  __int64 v84; // [rsp+60h] [rbp-A8h]
  __int128 v85; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+78h] [rbp-90h]
  __int64 v87; // [rsp+80h] [rbp-88h]
  __int128 v88; // [rsp+88h] [rbp-80h] BYREF
  __m128i v89; // [rsp+98h] [rbp-70h]
  _BYTE v90[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v91[32]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 *v92; // [rsp+E8h] [rbp-20h] BYREF
  char v93; // [rsp+F0h] [rbp-18h]
  __int64 v94; // [rsp+F8h] [rbp-10h] BYREF
  float v95; // [rsp+100h] [rbp-8h] BYREF
  char v96; // [rsp+104h] [rbp-4h] BYREF
  LPVOID pv[2]; // [rsp+108h] [rbp+0h] BYREF
  __m128i v98; // [rsp+118h] [rbp+10h]
  unsigned int v99; // [rsp+128h] [rbp+20h] BYREF
  LPVOID v100; // [rsp+130h] [rbp+28h] BYREF
  __int128 v101; // [rsp+138h] [rbp+30h] BYREF
  __int64 v102; // [rsp+148h] [rbp+40h]
  __int64 v103; // [rsp+150h] [rbp+48h] BYREF
  __int128 v104; // [rsp+158h] [rbp+50h] BYREF
  __int64 v105; // [rsp+168h] [rbp+60h]
  void *v106[12]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  InitOnceExecuteOnce(
    &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
    `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1EFB,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\staging.h",
      v4);
  }
  v100 = 0;
  v5 = CoCreateInstance(
         &GUID_df43bfd6_da50_426f_af99_5b63385f586a,
         0,
         4u,
         &GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b,
         &v100);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v101 = 0;
  v102 = 0;
  v92 = &v101;
  v93 = 1;
  v7 = *((_QWORD *)&Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 + 1);
  for ( i = Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3; i != v7; i += 72 )
  {
    v8 = *(void **)(i + 48);
    v9 = (_QWORD *)(i + 32);
    if ( *(_QWORD *)(i + 56) > 7u )
      v9 = (_QWORD *)*v9;
    pv[0] = v9;
    pv[1] = v8;
    Src_8 = *(_OWORD *)pv;
    Windows::RebootDowntime::InputBuilder::GetInputForKey(*((_QWORD *)this + 1), &v85, &Src_8);
    if ( !(_BYTE)v86 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
    if ( SBYTE8(v85) == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void_overloaded__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_2___Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_3____std::variant_unsigned_int_unsigned___int64__const___1_(retaddr);
    ppv = *(_DWORD *)(i + 68);
    Windows::RebootDowntime::AddCustomFeature(&v101, i);
  }
  v10 = 0;
  v11 = 0;
  do
  {
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v12 = std::to_wstring(v90, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC", 6);
    v13 = std::wstring::append(&Src_8);
    v88 = *(_OWORD *)v13;
    v89 = *(__m128i *)(v13 + 16);
    *(_QWORD *)(v13 + 16) = 0;
    *(_QWORD *)(v13 + 24) = 7;
    *(_WORD *)v13 = 0;
    v14 = (void *)std::operator+<wchar_t>(v91, &v88, v12);
    v15 = std::wstring::append(v14);
    *(_OWORD *)pv = *(_OWORD *)v15;
    v16 = (LPVOID *)pv[0];
    v98 = *(__m128i *)(v15 + 16);
    v17 = v98;
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 24) = 7;
    *(_WORD *)v15 = 0;
    v18 = pv;
    if ( _mm_srli_si128(v17, 8).m128i_u64[0] > 7 )
      v18 = v16;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v18, v19);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(v91);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v90);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v20 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTi", 5);
    v21 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v21;
    v98 = *(__m128i *)(v21 + 16);
    *(_QWORD *)(v21 + 16) = 0;
    *(_QWORD *)(v21 + 24) = 7;
    *(_WORD *)v21 = 0;
    v22 = (void *)std::operator+<wchar_t>(v90, pv, v20);
    v23 = std::wstring::append(v22);
    v88 = *(_OWORD *)v23;
    v24 = (__int128 *)v88;
    v89 = *(__m128i *)(v23 + 16);
    v25 = v89;
    *(_QWORD *)(v23 + 16) = 0;
    *(_QWORD *)(v23 + 24) = 7;
    *(_WORD *)v23 = 0;
    v26 = &v88;
    if ( _mm_srli_si128(v25, 8).m128i_u64[0] > 7 )
      v26 = v24;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v26 + v27) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v26, v27);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v28 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUS", 6);
    v29 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v29;
    v98 = *(__m128i *)(v29 + 16);
    *(_QWORD *)(v29 + 16) = 0;
    *(_QWORD *)(v29 + 24) = 7;
    *(_WORD *)v29 = 0;
    v30 = (void *)std::operator+<wchar_t>(v90, pv, v28);
    v31 = std::wstring::append(v30);
    v88 = *(_OWORD *)v31;
    v32 = (__int128 *)v88;
    v89 = *(__m128i *)(v31 + 16);
    v33 = v89;
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 7;
    *(_WORD *)v31 = 0;
    v34 = &v88;
    if ( _mm_srli_si128(v33, 8).m128i_u64[0] > 7 )
      v34 = v32;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v35 = -1;
    do
      ++v35;
    while ( *((_WORD *)v34 + v35) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v34, v35);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v36 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC", 6);
    v37 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v37;
    v98 = *(__m128i *)(v37 + 16);
    *(_QWORD *)(v37 + 16) = 0;
    *(_QWORD *)(v37 + 24) = 7;
    *(_WORD *)v37 = 0;
    v38 = (void *)std::operator+<wchar_t>(v90, pv, v36);
    v39 = std::wstring::append(v38);
    v88 = *(_OWORD *)v39;
    v40 = (__int128 *)v88;
    v89 = *(__m128i *)(v39 + 16);
    v41 = v89;
    *(_QWORD *)(v39 + 16) = 0;
    *(_QWORD *)(v39 + 24) = 7;
    *(_WORD *)v39 = 0;
    v42 = &v88;
    if ( _mm_srli_si128(v41, 8).m128i_u64[0] > 7 )
      v42 = v40;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v42, v43);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasQUPresent(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v44 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeQU", 5);
    v45 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v45;
    v98 = *(__m128i *)(v45 + 16);
    *(_QWORD *)(v45 + 16) = 0;
    *(_QWORD *)(v45 + 24) = 7;
    *(_WORD *)v45 = 0;
    v46 = (void *)std::operator+<wchar_t>(v90, pv, v44);
    v47 = std::wstring::append(v46);
    v88 = *(_OWORD *)v47;
    v48 = (__int128 *)v88;
    v89 = *(__m128i *)(v47 + 16);
    v49 = v89;
    *(_QWORD *)(v47 + 16) = 0;
    *(_QWORD *)(v47 + 24) = 7;
    *(_WORD *)v47 = 0;
    v50 = &v88;
    if ( _mm_srli_si128(v49, 8).m128i_u64[0] > 7 )
      v50 = v48;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v51 = -1;
    do
      ++v51;
    while ( *((_WORD *)v50 + v51) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v50, v51);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasFUPresent(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v52 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeFU", 5);
    v53 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v53;
    v98 = *(__m128i *)(v53 + 16);
    *(_QWORD *)(v53 + 16) = 0;
    *(_QWORD *)(v53 + 24) = 7;
    *(_WORD *)v53 = 0;
    v54 = (void *)std::operator+<wchar_t>(v90, pv, v52);
    v55 = std::wstring::append(v54);
    v88 = *(_OWORD *)v55;
    v56 = (__int128 *)v88;
    v89 = *(__m128i *)(v55 + 16);
    v57 = v89;
    *(_QWORD *)(v55 + 16) = 0;
    *(_QWORD *)(v55 + 24) = 7;
    *(_WORD *)v55 = 0;
    v58 = &v88;
    if ( _mm_srli_si128(v57, 8).m128i_u64[0] > 7 )
      v58 = v56;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v59 = -1;
    do
      ++v59;
    while ( *((_WORD *)v58 + v59) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v58, v59);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    ++v10;
    ++v11;
  }
  while ( (int)v10 < 6 );
  memset(v106, 0, sizeof(v106));
  Windows::CorrelationVector::CorrelationVector((Windows::CorrelationVector *)v106);
  v99 = 0;
  v94 = 0;
  v60 = v100;
  v61 = *(__int64 (__fastcall **)(LPVOID, unsigned __int64, _QWORD, const wchar_t *))(*(_QWORD *)v100 + 40LL);
  v62 = (_QWORD *)Windows::CorrelationVector::to_string(v106, v90);
  if ( v62[3] > 0xFu )
    v62 = (_QWORD *)*v62;
  ppva = (int)v62;
  v63 = v61(v60, 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v101 + 1) - v101) >> 3), v101, L"QU202506");
  if ( v63 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v63,
      ppva);
  std::string::~string(v90);
  *(_QWORD *)&v85 = &v94;
  *((_QWORD *)&v85 + 1) = &v99;
  LOBYTE(v86) = 1;
  v103 = 0;
  if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v100)(
         v100,
         &GUID_68538015_9da0_4cb8_a6af_d52af2ea035b,
         &v103) >= 0 )
  {
    v95 = 0.0;
    pv[0] = 0;
    v64 = v103;
    v65 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v103 + 48LL);
    *(_QWORD *)&Src_8 = pv;
    *((_QWORD *)&Src_8 + 1) = 0;
    LOBYTE(v83) = 1;
    v66 = (_QWORD *)Windows::CorrelationVector::to_string(v106, v90);
    if ( v66[3] > 0xFu )
      v66 = (_QWORD *)*v66;
    ppvb = (int)v66;
    v67 = v65(v64, v99, v94, L"QUUPMLV1");
    v68 = v67;
    if ( v67 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)(unsigned int)v67,
        ppvb);
    v69 = v68 >= 0;
    std::string::~string(v90);
    if ( (_BYTE)v83 )
    {
      v70 = *(void **)Src_8;
      *(_QWORD *)Src_8 = *((_QWORD *)&Src_8 + 1);
      if ( v70 )
        CoTaskMemFree(v70);
    }
    if ( v69 )
    {
      if ( LODWORD(v95) != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
          (const char *)0x8000FFFFLL,
          ppvb);
      v71 = pv[0];
      a2 = *(float *)pv[0];
      pv[0] = 0;
      if ( v71 )
        CoTaskMemFree(v71);
      goto LABEL_57;
    }
    v72 = pv[0];
    pv[0] = 0;
    if ( v72 )
      CoTaskMemFree(v72);
  }
  v104 = 0;
  v105 = 0;
  v95 = a2;
  pv[0] = &v95;
  pv[1] = &v96;
  Src_8 = *(_OWORD *)pv;
  std::vector<float>::vector<float>(&v104, &Src_8);
  v73 = v100;
  v74 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v100 + 32LL);
  v75 = (_QWORD *)Windows::CorrelationVector::to_string(v106, v90);
  if ( v75[3] > 0xFu )
    v75 = (_QWORD *)*v75;
  ppvc = (int)v75;
  v76 = v74(v73, (__int64)(*((_QWORD *)&v104 + 1) - v104) >> 2, v104, L"QU202506");
  if ( v76 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v76,
      ppvc);
  std::string::~string(v90);
  std::vector<enum SystemInterface::Usage::LogonEvent>::~vector<enum SystemInterface::Usage::LogonEvent>(&v104);
LABEL_57:
  if ( v103 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v85);
  if ( v106[1] )
    operator delete(v106[1], (const struct std::nothrow_t *)0x90);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___(&v92);
  std::vector<CustomFeature>::~vector<CustomFeature>(&v101);
  if ( v100 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v100 + 16LL))(v100);
  return a2;
}

```

## disassembly

```asm
0x1800d7bf4  mov     rax, rsp
0x1800d7bf7  mov     [rax+10h], rbx
0x1800d7bfb  mov     [rax+18h], rsi
0x1800d7bff  mov     [rax+20h], rdi
0x1800d7c03  push    rbp
0x1800d7c04  push    r12
0x1800d7c06  push    r13
0x1800d7c08  push    r14
0x1800d7c0a  push    r15
0x1800d7c0c  lea     rbp, [rax-178h]
0x1800d7c13  sub     rsp, 250h
0x1800d7c1a  movaps  xmmword ptr [rax-38h], xmm6
0x1800d7c1e  movaps  xmmword ptr [rax-48h], xmm7
0x1800d7c22  movaps  xmmword ptr [rax-58h], xmm8
0x1800d7c27  movaps  xmmword ptr [rax-68h], xmm9
0x1800d7c2c  movaps  xmmword ptr [rax-78h], xmm10
0x1800d7c31  movaps  xmmword ptr [rax-88h], xmm11
0x1800d7c39  movaps  xmmword ptr [rax-98h], xmm12
0x1800d7c41  mov     rax, cs:__security_cookie
0x1800d7c48  xor     rax, rsp
0x1800d7c4b  mov     [rbp+170h+var_A0], rax
0x1800d7c52  movaps  xmm6, xmm1
0x1800d7c55  mov     r14, rcx
0x1800d7c58  xor     r15d, r15d
0x1800d7c5b  xor     r9d, r9d; Context
0x1800d7c5e  xor     r8d, r8d; Parameter
0x1800d7c61  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800d7c68  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x1800d7c6f  call    cs:__imp_InitOnceExecuteOnce
0x1800d7c75  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, r15b; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x1800d7c7c  jz      short loc_1800D7C99
0x1800d7c7e  mov     rbx, [rbp+178h]
0x1800d7c85  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::GetImpl(void)'::`2'::impl
0x1800d7c8c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::__private_IsEnabled(wil::ReportingKind)
0x1800d7c91  test    al, al
0x1800d7c93  jz      loc_1800D899B
0x1800d7c99  mov     [rbp+170h+var_148], r15
0x1800d7c9d  lea     rax, [rbp+170h+var_148]
0x1800d7ca1  mov     [rsp+270h+ppv], rax; int
0x1800d7ca6  lea     r9, _GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b; riid
0x1800d7cad  xor     edx, edx; pUnkOuter
0x1800d7caf  lea     r8d, [rdx+4]; dwClsContext
0x1800d7cb3  lea     rcx, _GUID_df43bfd6_da50_426f_af99_5b63385f586a; rclsid
0x1800d7cba  call    cs:__imp_CoCreateInstance
0x1800d7cc0  mov     rcx, [rbp+178h]; this
0x1800d7cc7  test    eax, eax
0x1800d7cc9  js      loc_1800D89B0
0x1800d7ccf  xorps   xmm1, xmm1
0x1800d7cd2  movdqu  [rbp+170h+var_140], xmm1
0x1800d7cd7  mov     [rbp+170h+var_130], r15
0x1800d7cdb  lea     rax, [rbp+170h+var_140]
0x1800d7cdf  mov     [rbp+170h+var_190], rax
0x1800d7ce3  mov     r12d, 1
0x1800d7ce9  mov     [rbp+170h+var_188], r12b
0x1800d7ced  mov     rbx, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800d7cf4  mov     rdi, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B+8; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800d7cfb  lea     r13d, [r12+6]
0x1800d7d00  cmp     rbx, rdi
0x1800d7d03  jz      loc_1800D7DE3
0x1800d7d09  lea     esi, [r12+3Fh]
0x1800d7d0e  lea     r13d, [r12+43h]
0x1800d7d13  mov     rcx, [rbx+30h]
0x1800d7d17  lea     rax, [rbx+20h]
0x1800d7d1b  cmp     qword ptr [rbx+38h], 7
0x1800d7d20  jbe     short loc_1800D7D25
0x1800d7d22  mov     rax, [rax]
0x1800d7d25  mov     [rbp+170h+pv], rax
0x1800d7d29  mov     [rbp+170h+pv+8], rcx
0x1800d7d2d  movaps  xmm0, xmmword ptr [rbp+170h+pv]
0x1800d7d31  movdqa  [rsp+270h+Src+8], xmm0
0x1800d7d37  lea     r8, [rsp+270h+Src+8]
0x1800d7d3c  lea     rdx, [rsp+270h+var_218+8]
0x1800d7d41  mov     rcx, [r14+8]
0x1800d7d45  call    ?GetInputForKey@InputBuilder@RebootDowntime@Windows@@QEAA?AV?$optional@V?$variant@I_K@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::RebootDowntime::InputBuilder::GetInputForKey(wil::basic_zstring_view<wchar_t>)
0x1800d7d4a  mov     rcx, [rbp+178h]; this
0x1800d7d51  mov     al, byte ptr [rsp+270h+var_200]
0x1800d7d55  test    al, al
0x1800d7d57  jz      loc_1800D89E0
0x1800d7d5d  movsx   rax, byte ptr [rsp+270h+var_208]
0x1800d7d63  add     rax, r12
0x1800d7d66  jz      loc_1800D89DA
0x1800d7d6c  lea     r9, [rbp+170h+var_140]
0x1800d7d70  xorps   xmm2, xmm2
0x1800d7d73  cmp     rax, 1
0x1800d7d77  jz      short loc_1800D7DA1
0x1800d7d79  mov     rcx, qword ptr [rsp+270h+var_218+8]
0x1800d7d7e  test    rcx, rcx
0x1800d7d81  js      short loc_1800D7D8A
0x1800d7d83  cvtsi2ss xmm2, rcx
0x1800d7d88  jmp     short loc_1800D7DAA
0x1800d7d8a  mov     rax, rcx
0x1800d7d8d  shr     rax, 1
0x1800d7d90  and     rcx, r12
0x1800d7d93  or      rax, rcx
0x1800d7d96  cvtsi2ss xmm2, rax
0x1800d7d9b  addss   xmm2, xmm2
0x1800d7d9f  jmp     short loc_1800D7DAA
0x1800d7da1  mov     eax, dword ptr [rsp+270h+var_218+8]
0x1800d7da5  cvtsi2ss xmm2, rax
0x1800d7daa  mov     r8, r13
0x1800d7dad  mov     rdx, rbx
0x1800d7db0  mov     rcx, rsi
0x1800d7db3  mov     rax, rbx
0x1800d7db6  movss   xmm0, dword ptr [r13+rbx+0]
0x1800d7dbd  movss   dword ptr [rsp+270h+ppv], xmm0
0x1800d7dc3  movss   xmm3, dword ptr [rbx+rcx]
0x1800d7dc8  mov     rcx, r9
0x1800d7dcb  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d7dd0  add     rbx, 48h ; 'H'
0x1800d7dd4  cmp     rbx, rdi
0x1800d7dd7  jnz     loc_1800D7D13
0x1800d7ddd  mov     r13d, 7
0x1800d7de3  mov     edi, r15d
0x1800d7de6  mov     rsi, r15
0x1800d7de9  movss   xmm9, cs:__real@42c80000
0x1800d7df2  movss   xmm10, cs:__real@46610000
0x1800d7dfb  movss   xmm11, cs:__real@4e8f0d18
0x1800d7e04  movss   xmm12, cs:__real@41a00000
0x1800d7e0d  movss   xmm8, cs:__real@3f800000
0x1800d7e16  mov     rdx, rsi; unsigned __int64
0x1800d7e19  mov     rcx, [r14+8]; this
0x1800d7e1d  call    ?QueryPastDowntimeTotalNumerOfUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(unsigned __int64)
0x1800d7e22  xorps   xmm7, xmm7
0x1800d7e25  cvtsd2ss xmm7, xmm0
0x1800d7e29  mov     edx, edi
0x1800d7e2b  lea     rcx, [rbp+170h+var_1D0]
0x1800d7e2f  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d7e34  mov     rbx, rax
0x1800d7e37  xorps   xmm0, xmm0
0x1800d7e3a  movups  [rsp+270h+Src+8], xmm0
0x1800d7e3f  mov     [rsp+270h+var_220], r15
0x1800d7e44  mov     qword ptr [rsp+270h+var_218], r15
0x1800d7e49  mov     r8d, 6
0x1800d7e4f  lea     rdx, aRsetuc; "RSeTUC"
0x1800d7e56  lea     rcx, [rsp+270h+Src+8]
0x1800d7e5b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d7e60  nop
0x1800d7e61  mov     r8, r12
0x1800d7e64  lea     rdx, aN; "N"
0x1800d7e6b  lea     rcx, [rsp+270h+Src+8]; Src
0x1800d7e70  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d7e75  movups  xmm0, xmmword ptr [rax]
0x1800d7e78  movups  [rbp+170h+var_1F0], xmm0
0x1800d7e7c  movups  xmm1, xmmword ptr [rax+10h]
0x1800d7e80  movups  [rbp+170h+var_1E0], xmm1
0x1800d7e84  mov     [rax+10h], r15
0x1800d7e88  mov     [rax+18h], r13
0x1800d7e8c  mov     [rax], r15w
0x1800d7e90  mov     r8, rbx
0x1800d7e93  lea     rdx, [rbp+170h+var_1F0]
0x1800d7e97  lea     rcx, [rbp+170h+var_1B0]
0x1800d7e9b  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800d7ea0  nop
0x1800d7ea1  mov     r8d, 2
0x1800d7ea7  lea     rdx, aV2; "V2"
0x1800d7eae  mov     rcx, rax; Src
0x1800d7eb1  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d7eb6  movups  xmm0, xmmword ptr [rax]
0x1800d7eb9  movups  xmmword ptr [rbp+170h+pv], xmm0
0x1800d7ebd  movups  xmm1, xmmword ptr [rax+10h]
0x1800d7ec1  movups  [rbp+170h+var_160], xmm1
0x1800d7ec5  mov     [rax+10h], r15
0x1800d7ec9  mov     [rax+18h], r13
0x1800d7ecd  mov     [rax], r15w
0x1800d7ed1  lea     rdx, [rbp+170h+pv]
0x1800d7ed5  movq    rcx, xmm0
0x1800d7eda  psrldq  xmm1, 8
0x1800d7edf  movq    rax, xmm1
0x1800d7ee4  cmp     rax, r13
0x1800d7ee7  cmova   rdx, rcx
0x1800d7eeb  xorps   xmm0, xmm0
0x1800d7eee  movups  [rsp+270h+var_218+8], xmm0
0x1800d7ef3  mov     [rsp+270h+var_200], r15
0x1800d7ef8  mov     [rsp+270h+var_1F8], r15
0x1800d7efd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d7f01  inc     r8
0x1800d7f04  cmp     [rdx+r8*2], r15w
0x1800d7f09  jnz     short loc_1800D7F01
0x1800d7f0b  lea     rcx, [rsp+270h+var_218+8]
0x1800d7f10  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d7f15  nop
0x1800d7f16  movss   dword ptr [rsp+270h+ppv], xmm9
0x1800d7f1d  xorps   xmm3, xmm3
0x1800d7f20  movaps  xmm2, xmm7
0x1800d7f23  lea     rdx, [rsp+270h+var_218+8]
0x1800d7f28  lea     rcx, [rbp+170h+var_140]
0x1800d7f2c  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d7f31  nop
0x1800d7f32  lea     rcx, [rsp+270h+var_218+8]; void *
0x1800d7f37  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7f3c  nop
0x1800d7f3d  lea     rcx, [rbp+170h+pv]; void *
0x1800d7f41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7f46  nop
0x1800d7f47  lea     rcx, [rbp+170h+var_1B0]; void *
0x1800d7f4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7f50  nop
0x1800d7f51  lea     rcx, [rbp+170h+var_1F0]; void *
0x1800d7f55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7f5a  nop
0x1800d7f5b  lea     rcx, [rsp+270h+Src+8]; void *
0x1800d7f60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7f65  nop
0x1800d7f66  lea     rcx, [rbp+170h+var_1D0]; void *
0x1800d7f6a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7f6f  mov     rdx, rsi; unsigned __int64
0x1800d7f72  mov     rcx, [r14+8]; this
0x1800d7f76  call    ?QueryPastDowntimeDurationSeconds@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(unsigned __int64)
0x1800d7f7b  xorps   xmm7, xmm7
0x1800d7f7e  cvtsd2ss xmm7, xmm0
0x1800d7f82  mov     edx, edi
0x1800d7f84  lea     rcx, [rbp+170h+var_1B0]
0x1800d7f88  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d7f8d  mov     rbx, rax
0x1800d7f90  xorps   xmm0, xmm0
0x1800d7f93  movups  [rsp+270h+Src+8], xmm0
0x1800d7f98  mov     [rsp+270h+var_220], r15
0x1800d7f9d  mov     qword ptr [rsp+270h+var_218], r15
0x1800d7fa2  mov     r8d, 5
0x1800d7fa8  lea     rdx, aRseti; "RSeTi"
0x1800d7faf  lea     rcx, [rsp+270h+Src+8]
0x1800d7fb4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d7fb9  nop
0x1800d7fba  mov     r8, r12
0x1800d7fbd  lea     rdx, aN; "N"
0x1800d7fc4  lea     rcx, [rsp+270h+Src+8]; Src
0x1800d7fc9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d7fce  movups  xmm0, xmmword ptr [rax]
0x1800d7fd1  movups  xmmword ptr [rbp+170h+pv], xmm0
0x1800d7fd5  movups  xmm1, xmmword ptr [rax+10h]
0x1800d7fd9  movups  [rbp+170h+var_160], xmm1
0x1800d7fdd  mov     [rax+10h], r15
0x1800d7fe1  mov     [rax+18h], r13
0x1800d7fe5  mov     [rax], r15w
0x1800d7fe9  mov     r8, rbx
0x1800d7fec  lea     rdx, [rbp+170h+pv]
0x1800d7ff0  lea     rcx, [rbp+170h+var_1D0]
0x1800d7ff4  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800d7ff9  nop
0x1800d7ffa  mov     r8d, 2
0x1800d8000  lea     rdx, aV1; "V1"
0x1800d8007  mov     rcx, rax; Src
0x1800d800a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d800f  movups  xmm0, xmmword ptr [rax]
0x1800d8012  movups  [rbp+170h+var_1F0], xmm0
0x1800d8016  movups  xmm1, xmmword ptr [rax+10h]
0x1800d801a  movups  [rbp+170h+var_1E0], xmm1
0x1800d801e  mov     [rax+10h], r15
0x1800d8022  mov     [rax+18h], r13
0x1800d8026  mov     [rax], r15w
0x1800d802a  lea     rdx, [rbp+170h+var_1F0]
0x1800d802e  movq    rcx, xmm0
0x1800d8033  psrldq  xmm1, 8
0x1800d8038  movq    rax, xmm1
0x1800d803d  cmp     rax, r13
0x1800d8040  cmova   rdx, rcx
0x1800d8044  xorps   xmm0, xmm0
0x1800d8047  movups  [rsp+270h+var_218+8], xmm0
0x1800d804c  mov     [rsp+270h+var_200], r15
0x1800d8051  mov     [rsp+270h+var_1F8], r15
0x1800d8056  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d805a  inc     r8
0x1800d805d  cmp     [rdx+r8*2], r15w
0x1800d8062  jnz     short loc_1800D805A
0x1800d8064  lea     rcx, [rsp+270h+var_218+8]
0x1800d8069  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d806e  nop
0x1800d806f  movss   dword ptr [rsp+270h+ppv], xmm10
0x1800d8076  xorps   xmm3, xmm3
0x1800d8079  movaps  xmm2, xmm7
0x1800d807c  lea     rdx, [rsp+270h+var_218+8]
0x1800d8081  lea     rcx, [rbp+170h+var_140]
0x1800d8085  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d808a  nop
0x1800d808b  lea     rcx, [rsp+270h+var_218+8]; void *
0x1800d8090  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8095  nop
0x1800d8096  lea     rcx, [rbp+170h+var_1F0]; void *
0x1800d809a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d809f  nop
0x1800d80a0  lea     rcx, [rbp+170h+var_1D0]; void *
0x1800d80a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d80a9  nop
0x1800d80aa  lea     rcx, [rbp+170h+pv]; void *
0x1800d80ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d80b3  nop
0x1800d80b4  lea     rcx, [rsp+270h+Src+8]; void *
0x1800d80b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d80be  nop
0x1800d80bf  lea     rcx, [rbp+170h+var_1B0]; void *
0x1800d80c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d80c8  mov     rdx, rsi; unsigned __int64
0x1800d80cb  mov     rcx, [r14+8]; this
0x1800d80cf  call    ?QueryPastDowntimeTotalSizeUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(unsigned __int64)
0x1800d80d4  xorps   xmm7, xmm7
0x1800d80d7  cvtsd2ss xmm7, xmm0
0x1800d80db  mov     edx, edi
0x1800d80dd  lea     rcx, [rbp+170h+var_1B0]
0x1800d80e1  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d80e6  mov     rbx, rax
  ... truncated ...
```
