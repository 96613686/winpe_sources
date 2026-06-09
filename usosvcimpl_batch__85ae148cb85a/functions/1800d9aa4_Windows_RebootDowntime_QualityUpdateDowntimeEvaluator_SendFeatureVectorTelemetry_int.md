# Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry(int)

- ea: `0x1800d9aa4`
- end: `0x1800da779`
- name: `?SendFeatureVectorTelemetry@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@AEAAXH@Z`
- size: `3285`
- prototype: `void __fastcall(Windows::RebootDowntime::QualityUpdateDowntimeEvaluator *__hidden this, int)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800d7310`

## callees

- `0x18000edb0`
- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18002e698`
- `0x18002e710`
- `0x18002ea8c`
- `0x18003007c`
- `0x18007023c`
- `0x180098664`
- `0x1800b8ae0`
- `0x1800baf98`
- `0x1800bb054`
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
- `0x1800d9aa4`
- `0x1800da780`
- `0x1800dd930`
- `0x1800dddf4`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d9b50`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d9b50`

## string_xrefs

- `0x1800da705`: `Feature vector value did not exist for key: {}, exit QU heuristic`
- `0x1800da737`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800da74c`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800da761`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry(
        Windows::RebootDowntime::QualityUpdateDowntimeEvaluator *this,
        int a2)
{
  unsigned __int64 v4; // r12
  TraceLoggingCorrelationVector *v5; // rbx
  HRESULT v6; // eax
  _QWORD *i; // rdi
  _QWORD *v8; // r15
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // r15d
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rax
  void *v16; // rax
  __int64 v17; // rax
  __int128 *v18; // xmm0_8
  __m128i v19; // xmm1
  __int128 *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdi
  __int64 v23; // rax
  void *v24; // rax
  __int64 v25; // rax
  __int128 *v26; // xmm0_8
  __m128i v27; // xmm1
  __int128 *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdi
  __int64 v31; // rax
  void *v32; // rax
  __int64 v33; // rax
  __int128 *v34; // xmm0_8
  __m128i v35; // xmm1
  __int128 *v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdi
  __int64 v39; // rax
  void *v40; // rax
  __int64 v41; // rax
  __int128 *v42; // xmm0_8
  __m128i v43; // xmm1
  __int128 *v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdi
  __int64 v47; // rax
  void *v48; // rax
  __int64 v49; // rax
  __int128 *v50; // xmm0_8
  __m128i v51; // xmm1
  __int128 *v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdi
  __int64 v55; // rax
  void *v56; // rax
  __int64 v57; // rax
  __int128 *v58; // xmm0_8
  __m128i v59; // xmm1
  __int128 *v60; // rdx
  __int64 v61; // r8
  int v62; // eax
  LPVOID v63; // rdi
  __int64 (__fastcall *v64)(LPVOID, __int64, _QWORD, const wchar_t *); // r14
  _QWORD *v65; // rcx
  int v66; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  _QWORD Src[3]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v70; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v71; // [rsp+60h] [rbp-A8h]
  __int128 v72; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+78h] [rbp-90h]
  __int64 v74; // [rsp+80h] [rbp-88h]
  __int128 v75; // [rsp+88h] [rbp-80h] BYREF
  __m128i v76; // [rsp+98h] [rbp-70h]
  float v77; // [rsp+A8h] [rbp-60h] BYREF
  char v78; // [rsp+ACh] [rbp-5Ch] BYREF
  __int128 v79; // [rsp+B0h] [rbp-58h] BYREF
  __m128i v80; // [rsp+C0h] [rbp-48h]
  TraceLoggingCorrelationVector *v81; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v82[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v83[32]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 *v84; // [rsp+118h] [rbp+10h] BYREF
  char v85; // [rsp+120h] [rbp+18h]
  __int64 v86; // [rsp+128h] [rbp+20h] BYREF
  int v87; // [rsp+130h] [rbp+28h] BYREF
  __int128 v88; // [rsp+138h] [rbp+30h] BYREF
  __int64 v89; // [rsp+148h] [rbp+40h]
  LPVOID v90; // [rsp+150h] [rbp+48h] BYREF
  __int128 v91; // [rsp+158h] [rbp+50h] BYREF
  __int64 v92; // [rsp+168h] [rbp+60h]
  char v93[144]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v4 = 0;
  v81 = 0;
  std::make_unique<TraceLoggingCorrelationVector,,0>(&v81);
  v5 = v81;
  TraceLoggingCorrelationVector::ToStringImpl(
    v81,
    _InterlockedExchangeAdd64((volatile signed __int64 *)v81 + 17, 0),
    v93);
  v90 = 0;
  v6 = CoCreateInstance(
         &GUID_df43bfd6_da50_426f_af99_5b63385f586a,
         0,
         4u,
         &GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b,
         &v90);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v88 = 0;
  v89 = 0;
  v84 = &v88;
  v85 = 1;
  v8 = (_QWORD *)*((_QWORD *)&Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 + 1);
  for ( i = (_QWORD *)Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3; i != v8; i += 9 )
  {
    v9 = i[6];
    v10 = i + 4;
    if ( i[7] > 7u )
      v10 = (_QWORD *)i[4];
    *(_QWORD *)&v75 = v10;
    *((_QWORD *)&v75 + 1) = v9;
    *(_OWORD *)&Src[1] = v75;
    Windows::RebootDowntime::InputBuilder::GetInputForKey(*((_QWORD *)this + 1), &v72, &Src[1]);
    if ( !(_BYTE)v73 )
    {
      *(_QWORD *)&v75 = L"Feature vector value did not exist for key: {}, exit QU heuristic";
      *((_QWORD *)&v75 + 1) = 65;
      *(_OWORD *)&Src[1] = v75;
      SystemInterface::Log<std::wstring &>(&Src[1], i + 4);
      goto LABEL_42;
    }
    if ( SBYTE8(v72) == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void_overloaded__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_2___Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_3____std::variant_unsigned_int_unsigned___int64__const___1_(v11);
    Windows::RebootDowntime::AddCustomFeature(&v88, i);
  }
  v12 = 0;
  v13 = -1;
  do
  {
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v4);
    v14 = std::to_wstring(v83, v12);
    *(_OWORD *)&Src[1] = 0;
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src[1], L"RSeTUC");
    v15 = std::wstring::append(&Src[1]);
    v79 = *(_OWORD *)v15;
    v80 = *(__m128i *)(v15 + 16);
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 24) = 7;
    *(_WORD *)v15 = 0;
    v16 = (void *)std::operator+<wchar_t>(v82, &v79, v14);
    v17 = std::wstring::append(v16);
    v75 = *(_OWORD *)v17;
    v18 = (__int128 *)v75;
    v76 = *(__m128i *)(v17 + 16);
    v19 = v76;
    *(_QWORD *)(v17 + 16) = 0;
    *(_QWORD *)(v17 + 24) = 7;
    *(_WORD *)v17 = 0;
    v20 = &v75;
    if ( _mm_srli_si128(v19, 8).m128i_u64[0] > 7 )
      v20 = v18;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v20 + v21) );
    std::wstring::_Construct<1,wchar_t const *>(&v72, v20);
    Windows::RebootDowntime::AddCustomFeature(&v88, &v72);
    std::wstring::~wstring(&v72);
    std::wstring::~wstring(&v75);
    std::wstring::~wstring(v82);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(&Src[1]);
    std::wstring::~wstring(v83);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v4);
    v22 = std::to_wstring(v82, v12);
    *(_OWORD *)&Src[1] = 0;
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src[1], L"RSeTi");
    v23 = std::wstring::append(&Src[1]);
    v75 = *(_OWORD *)v23;
    v76 = *(__m128i *)(v23 + 16);
    *(_QWORD *)(v23 + 16) = 0;
    *(_QWORD *)(v23 + 24) = 7;
    *(_WORD *)v23 = 0;
    v24 = (void *)std::operator+<wchar_t>(v83, &v75, v22);
    v25 = std::wstring::append(v24);
    v79 = *(_OWORD *)v25;
    v26 = (__int128 *)v79;
    v80 = *(__m128i *)(v25 + 16);
    v27 = v80;
    *(_QWORD *)(v25 + 16) = 0;
    *(_QWORD *)(v25 + 24) = 7;
    *(_WORD *)v25 = 0;
    v28 = &v79;
    if ( _mm_srli_si128(v27, 8).m128i_u64[0] > 7 )
      v28 = v26;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v28 + v29) );
    std::wstring::_Construct<1,wchar_t const *>(&v72, v28);
    Windows::RebootDowntime::AddCustomFeature(&v88, &v72);
    std::wstring::~wstring(&v72);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    std::wstring::~wstring(&v75);
    std::wstring::~wstring(&Src[1]);
    std::wstring::~wstring(v82);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v4);
    v30 = std::to_wstring(v82, v12);
    *(_OWORD *)&Src[1] = 0;
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src[1], L"RSeTUS");
    v31 = std::wstring::append(&Src[1]);
    v75 = *(_OWORD *)v31;
    v76 = *(__m128i *)(v31 + 16);
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 7;
    *(_WORD *)v31 = 0;
    v32 = (void *)std::operator+<wchar_t>(v83, &v75, v30);
    v33 = std::wstring::append(v32);
    v79 = *(_OWORD *)v33;
    v34 = (__int128 *)v79;
    v80 = *(__m128i *)(v33 + 16);
    v35 = v80;
    *(_QWORD *)(v33 + 16) = 0;
    *(_QWORD *)(v33 + 24) = 7;
    *(_WORD *)v33 = 0;
    v36 = &v79;
    if ( _mm_srli_si128(v35, 8).m128i_u64[0] > 7 )
      v36 = v34;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    std::wstring::_Construct<1,wchar_t const *>(&v72, v36);
    Windows::RebootDowntime::AddCustomFeature(&v88, &v72);
    std::wstring::~wstring(&v72);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    std::wstring::~wstring(&v75);
    std::wstring::~wstring(&Src[1]);
    std::wstring::~wstring(v82);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v4);
    v38 = std::to_wstring(v82, v12);
    *(_OWORD *)&Src[1] = 0;
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src[1], L"RSeTUC");
    v39 = std::wstring::append(&Src[1]);
    v75 = *(_OWORD *)v39;
    v76 = *(__m128i *)(v39 + 16);
    *(_QWORD *)(v39 + 16) = 0;
    *(_QWORD *)(v39 + 24) = 7;
    *(_WORD *)v39 = 0;
    v40 = (void *)std::operator+<wchar_t>(v83, &v75, v38);
    v41 = std::wstring::append(v40);
    v79 = *(_OWORD *)v41;
    v42 = (__int128 *)v79;
    v80 = *(__m128i *)(v41 + 16);
    v43 = v80;
    *(_QWORD *)(v41 + 16) = 0;
    *(_QWORD *)(v41 + 24) = 7;
    *(_WORD *)v41 = 0;
    v44 = &v79;
    if ( _mm_srli_si128(v43, 8).m128i_u64[0] > 7 )
      v44 = v42;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v45 = -1;
    do
      ++v45;
    while ( *((_WORD *)v44 + v45) );
    std::wstring::_Construct<1,wchar_t const *>(&v72, v44);
    Windows::RebootDowntime::AddCustomFeature(&v88, &v72);
    std::wstring::~wstring(&v72);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    std::wstring::~wstring(&v75);
    std::wstring::~wstring(&Src[1]);
    std::wstring::~wstring(v82);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasQUPresent(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v4);
    v46 = std::to_wstring(v82, v12);
    *(_OWORD *)&Src[1] = 0;
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src[1], L"RSeQU");
    v47 = std::wstring::append(&Src[1]);
    v75 = *(_OWORD *)v47;
    v76 = *(__m128i *)(v47 + 16);
    *(_QWORD *)(v47 + 16) = 0;
    *(_QWORD *)(v47 + 24) = 7;
    *(_WORD *)v47 = 0;
    v48 = (void *)std::operator+<wchar_t>(v83, &v75, v46);
    v49 = std::wstring::append(v48);
    v79 = *(_OWORD *)v49;
    v50 = (__int128 *)v79;
    v80 = *(__m128i *)(v49 + 16);
    v51 = v80;
    *(_QWORD *)(v49 + 16) = 0;
    *(_QWORD *)(v49 + 24) = 7;
    *(_WORD *)v49 = 0;
    v52 = &v79;
    if ( _mm_srli_si128(v51, 8).m128i_u64[0] > 7 )
      v52 = v50;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v53 = -1;
    do
      ++v53;
    while ( *((_WORD *)v52 + v53) );
    std::wstring::_Construct<1,wchar_t const *>(&v72, v52);
    Windows::RebootDowntime::AddCustomFeature(&v88, &v72);
    std::wstring::~wstring(&v72);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    std::wstring::~wstring(&v75);
    std::wstring::~wstring(&Src[1]);
    std::wstring::~wstring(v82);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasFUPresent(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v4);
    v54 = std::to_wstring(v82, v12);
    *(_OWORD *)&Src[1] = 0;
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src[1], L"RSeFU");
    v55 = std::wstring::append(&Src[1]);
    v75 = *(_OWORD *)v55;
    v76 = *(__m128i *)(v55 + 16);
    *(_QWORD *)(v55 + 16) = 0;
    *(_QWORD *)(v55 + 24) = 7;
    *(_WORD *)v55 = 0;
    v56 = (void *)std::operator+<wchar_t>(v83, &v75, v54);
    v57 = std::wstring::append(v56);
    v79 = *(_OWORD *)v57;
    v58 = (__int128 *)v79;
    v80 = *(__m128i *)(v57 + 16);
    v59 = v80;
    *(_QWORD *)(v57 + 16) = 0;
    *(_QWORD *)(v57 + 24) = 7;
    *(_WORD *)v57 = 0;
    v60 = &v79;
    if ( _mm_srli_si128(v59, 8).m128i_u64[0] > 7 )
      v60 = v58;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v61 = -1;
    do
      ++v61;
    while ( *((_WORD *)v60 + v61) );
    std::wstring::_Construct<1,wchar_t const *>(&v72, v60);
    Windows::RebootDowntime::AddCustomFeature(&v88, &v72);
    std::wstring::~wstring(&v72);
    std::wstring::~wstring(&v79);
    std::wstring::~wstring(v83);
    std::wstring::~wstring(&v75);
    std::wstring::~wstring(&Src[1]);
    std::wstring::~wstring(v82);
    ++v12;
    ++v4;
  }
  while ( (int)v12 < 6 );
  v87 = 0;
  v86 = 0;
  v62 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64, _QWORD, const wchar_t *))(*(_QWORD *)v90 + 40LL))(
          v90,
          0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v88 + 1) - v88) >> 3),
          v88,
          L"QU202506");
  if ( v62 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v62,
      (int)v93);
  *(_QWORD *)&v72 = &v86;
  *((_QWORD *)&v72 + 1) = &v87;
  LOBYTE(v73) = 1;
  v91 = 0;
  v92 = 0;
  v77 = (float)a2;
  *(_QWORD *)&v75 = &v77;
  *((_QWORD *)&v75 + 1) = &v78;
  *(_OWORD *)&Src[1] = v75;
  std::vector<float>::vector<float>(&v91, &Src[1]);
  v63 = v90;
  v64 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v90 + 32LL);
  *(_OWORD *)&Src[1] = 0;
  v70 = 0;
  v71 = 0;
  do
    ++v13;
  while ( v93[v13] );
  std::string::_Construct<1,char const *>(&Src[1], v93, v13);
  v65 = &Src[1];
  if ( v71 > 0xF )
    LODWORD(v65) = Src[1];
  ppva = (int)v65;
  v66 = v64(v63, (__int64)(*((_QWORD *)&v91 + 1) - v91) >> 2, v91, L"QU202506");
  if ( v66 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v66,
      ppva);
  std::string::~string(&Src[1]);
  std::vector<enum SystemInterface::Usage::LogonEvent>::~vector<enum SystemInterface::Usage::LogonEvent>(&v91);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v72);
LABEL_42:
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___(&v84);
  std::vector<CustomFeature>::~vector<CustomFeature>(&v88);
  if ( v90 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v90 + 16LL))(v90);
  if ( v5 )
    operator delete(v5, (const struct std::nothrow_t *)0x90);
}

```

## disassembly

```asm
0x1800d9aa4  mov     rax, rsp
0x1800d9aa7  mov     [rax+10h], rbx
0x1800d9aab  mov     [rax+18h], rsi
0x1800d9aaf  mov     [rax+20h], rdi
0x1800d9ab3  push    rbp
0x1800d9ab4  push    r12
0x1800d9ab6  push    r13
0x1800d9ab8  push    r14
0x1800d9aba  push    r15
0x1800d9abc  lea     rbp, [rax-198h]
0x1800d9ac3  sub     rsp, 270h
0x1800d9aca  movaps  xmmword ptr [rax-38h], xmm6
0x1800d9ace  movaps  xmmword ptr [rax-48h], xmm7
0x1800d9ad2  movaps  xmmword ptr [rax-58h], xmm8
0x1800d9ad7  movaps  xmmword ptr [rax-68h], xmm9
0x1800d9adc  movaps  xmmword ptr [rax-78h], xmm10
0x1800d9ae1  movaps  xmmword ptr [rax-88h], xmm11
0x1800d9ae9  mov     rax, cs:__security_cookie
0x1800d9af0  xor     rax, rsp
0x1800d9af3  mov     [rbp+190h+var_90], rax
0x1800d9afa  mov     r13d, edx
0x1800d9afd  mov     r14, rcx
0x1800d9b00  xor     r12d, r12d
0x1800d9b03  mov     [rbp+190h+var_1C8], r12
0x1800d9b07  lea     rcx, [rbp+190h+var_1C8]
0x1800d9b0b  call    ??$make_unique@VTraceLoggingCorrelationVector@@$$V$0A@@std@@YA?AV?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@0@XZ; std::make_unique<TraceLoggingCorrelationVector,,0>(void)
0x1800d9b10  nop
0x1800d9b11  mov     rbx, [rbp+190h+var_1C8]
0x1800d9b15  mov     edx, r12d
0x1800d9b18  lock xadd [rbx+88h], rdx; unsigned __int64
0x1800d9b21  lea     r8, [rbp+190h+var_120]; char *
0x1800d9b25  mov     rcx, rbx; this
0x1800d9b28  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800d9b2d  nop
0x1800d9b2e  mov     [rbp+190h+var_148], r12
0x1800d9b32  lea     rax, [rbp+190h+var_148]
0x1800d9b36  mov     [rsp+290h+ppv], rax; int
0x1800d9b3b  lea     r9, _GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b; riid
0x1800d9b42  xor     edx, edx; pUnkOuter
0x1800d9b44  lea     r8d, [r12+4]; dwClsContext
0x1800d9b49  lea     rcx, _GUID_df43bfd6_da50_426f_af99_5b63385f586a; rclsid
0x1800d9b50  call    cs:__imp_CoCreateInstance
0x1800d9b56  mov     rcx, [rbp+198h]; this
0x1800d9b5d  test    eax, eax
0x1800d9b5f  js      loc_1800DA749
0x1800d9b65  xorps   xmm1, xmm1
0x1800d9b68  movdqu  [rbp+190h+var_160], xmm1
0x1800d9b6d  mov     [rbp+190h+var_150], r12
0x1800d9b71  lea     rax, [rbp+190h+var_160]
0x1800d9b75  mov     [rbp+190h+var_180], rax
0x1800d9b79  mov     [rbp+190h+var_178], 1
0x1800d9b7d  mov     rdi, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800d9b84  mov     r15, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B+8; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800d9b8b  jmp     loc_1800D9C50
0x1800d9b90  mov     rcx, [rdi+30h]
0x1800d9b94  lea     rsi, [rdi+20h]
0x1800d9b98  mov     rax, rsi
0x1800d9b9b  cmp     qword ptr [rdi+38h], 7
0x1800d9ba0  jbe     short loc_1800D9BA5
0x1800d9ba2  mov     rax, [rsi]
0x1800d9ba5  mov     qword ptr [rbp+190h+var_210], rax
0x1800d9ba9  mov     qword ptr [rbp+190h+var_210+8], rcx
0x1800d9bad  movaps  xmm0, [rbp+190h+var_210]
0x1800d9bb1  movdqa  xmmword ptr [rsp+290h+Src+8], xmm0
0x1800d9bb7  lea     r8, [rsp+290h+Src+8]
0x1800d9bbc  lea     rdx, [rsp+290h+var_238+8]
0x1800d9bc1  mov     rcx, [r14+8]
0x1800d9bc5  call    ?GetInputForKey@InputBuilder@RebootDowntime@Windows@@QEAA?AV?$optional@V?$variant@I_K@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::RebootDowntime::InputBuilder::GetInputForKey(wil::basic_zstring_view<wchar_t>)
0x1800d9bca  cmp     byte ptr [rsp+290h+var_220], r12b
0x1800d9bcf  jz      loc_1800DA705
0x1800d9bd5  movsx   rax, byte ptr [rsp+290h+var_228]
0x1800d9bdb  add     rax, 1
0x1800d9bdf  jz      loc_1800DA773
0x1800d9be5  lea     r9, [rbp+190h+var_160]
0x1800d9be9  xorps   xmm2, xmm2
0x1800d9bec  cmp     rax, 1
0x1800d9bf0  jz      short loc_1800D9C1A
0x1800d9bf2  mov     rcx, qword ptr [rsp+290h+var_238+8]
0x1800d9bf7  test    rcx, rcx
0x1800d9bfa  js      short loc_1800D9C03
0x1800d9bfc  cvtsi2ss xmm2, rcx
0x1800d9c01  jmp     short loc_1800D9C23
0x1800d9c03  mov     rax, rcx
0x1800d9c06  shr     rax, 1
0x1800d9c09  and     ecx, 1
0x1800d9c0c  or      rax, rcx
0x1800d9c0f  cvtsi2ss xmm2, rax
0x1800d9c14  addss   xmm2, xmm2
0x1800d9c18  jmp     short loc_1800D9C23
0x1800d9c1a  mov     eax, dword ptr [rsp+290h+var_238+8]
0x1800d9c1e  cvtsi2ss xmm2, rax
0x1800d9c23  mov     r8d, 44h ; 'D'
0x1800d9c29  mov     rdx, rdi
0x1800d9c2c  lea     ecx, [r8-4]
0x1800d9c30  mov     rax, rdi
0x1800d9c33  movss   xmm0, dword ptr [r8+rdx]
0x1800d9c39  movss   dword ptr [rsp+290h+ppv], xmm0
0x1800d9c3f  movss   xmm3, dword ptr [rax+rcx]
0x1800d9c44  mov     rcx, r9
0x1800d9c47  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d9c4c  add     rdi, 48h ; 'H'
0x1800d9c50  cmp     rdi, r15
0x1800d9c53  jnz     loc_1800D9B90
0x1800d9c59  mov     r15d, r12d
0x1800d9c5c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d9c60  movss   xmm8, cs:__real@42c80000
0x1800d9c69  movss   xmm9, cs:__real@46610000
0x1800d9c72  movss   xmm10, cs:__real@4e8f0d18
0x1800d9c7b  movss   xmm11, cs:__real@41a00000
0x1800d9c84  movss   xmm7, cs:__real@3f800000
0x1800d9c8c  mov     rdx, r12; unsigned __int64
0x1800d9c8f  mov     rcx, [r14+8]; this
0x1800d9c93  call    ?QueryPastDowntimeTotalNumerOfUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(unsigned __int64)
0x1800d9c98  xorps   xmm6, xmm6
0x1800d9c9b  cvtsd2ss xmm6, xmm0
0x1800d9c9f  mov     edx, r15d
0x1800d9ca2  lea     rcx, [rbp+190h+var_1A0]
0x1800d9ca6  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d9cab  mov     rdi, rax
0x1800d9cae  xorps   xmm0, xmm0
0x1800d9cb1  movups  xmmword ptr [rsp+290h+Src+8], xmm0
0x1800d9cb6  xor     eax, eax
0x1800d9cb8  mov     [rsp+290h+var_240], rax
0x1800d9cbd  mov     qword ptr [rsp+290h+var_238], rax
0x1800d9cc2  lea     r8d, [rax+6]
0x1800d9cc6  lea     rdx, aRsetuc; "RSeTUC"
0x1800d9ccd  lea     rcx, [rsp+290h+Src+8]
0x1800d9cd2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9cd7  nop
0x1800d9cd8  mov     r8d, 1
0x1800d9cde  lea     rdx, aN; "N"
0x1800d9ce5  lea     rcx, [rsp+290h+Src+8]; Src
0x1800d9cea  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d9cef  movups  xmm0, xmmword ptr [rax]
0x1800d9cf2  movups  [rbp+190h+var_1E8], xmm0
0x1800d9cf6  movups  xmm1, xmmword ptr [rax+10h]
0x1800d9cfa  movups  [rbp+190h+var_1D8], xmm1
0x1800d9cfe  xor     ecx, ecx
0x1800d9d00  mov     [rax+10h], rcx
0x1800d9d04  mov     qword ptr [rax+18h], 7
0x1800d9d0c  mov     [rax], cx
0x1800d9d0f  mov     r8, rdi
0x1800d9d12  lea     rdx, [rbp+190h+var_1E8]
0x1800d9d16  lea     rcx, [rbp+190h+var_1C0]
0x1800d9d1a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800d9d1f  nop
0x1800d9d20  mov     r8d, 2
0x1800d9d26  lea     rdx, aV2; "V2"
0x1800d9d2d  mov     rcx, rax; Src
0x1800d9d30  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d9d35  movups  xmm0, xmmword ptr [rax]
0x1800d9d38  movups  [rbp+190h+var_210], xmm0
0x1800d9d3c  movups  xmm1, xmmword ptr [rax+10h]
0x1800d9d40  movups  [rbp+190h+var_200], xmm1
0x1800d9d44  xor     r9d, r9d
0x1800d9d47  mov     [rax+10h], r9
0x1800d9d4b  mov     qword ptr [rax+18h], 7
0x1800d9d53  mov     [rax], r9w
0x1800d9d57  lea     rdx, [rbp+190h+var_210]
0x1800d9d5b  movq    rcx, xmm0
0x1800d9d60  psrldq  xmm1, 8
0x1800d9d65  movq    rax, xmm1
0x1800d9d6a  cmp     rax, 7
0x1800d9d6e  cmova   rdx, rcx
0x1800d9d72  xorps   xmm0, xmm0
0x1800d9d75  movups  [rsp+290h+var_238+8], xmm0
0x1800d9d7a  mov     [rsp+290h+var_220], r9
0x1800d9d7f  mov     [rsp+290h+var_218], r9
0x1800d9d84  mov     r8, rsi
0x1800d9d87  inc     r8
0x1800d9d8a  cmp     [rdx+r8*2], r9w
0x1800d9d8f  jnz     short loc_1800D9D87
0x1800d9d91  lea     rcx, [rsp+290h+var_238+8]
0x1800d9d96  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9d9b  nop
0x1800d9d9c  movss   dword ptr [rsp+290h+ppv], xmm8
0x1800d9da3  xorps   xmm3, xmm3
0x1800d9da6  movaps  xmm2, xmm6
0x1800d9da9  lea     rdx, [rsp+290h+var_238+8]
0x1800d9dae  lea     rcx, [rbp+190h+var_160]
0x1800d9db2  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d9db7  nop
0x1800d9db8  lea     rcx, [rsp+290h+var_238+8]; void *
0x1800d9dbd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9dc2  nop
0x1800d9dc3  lea     rcx, [rbp+190h+var_210]; void *
0x1800d9dc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9dcc  nop
0x1800d9dcd  lea     rcx, [rbp+190h+var_1C0]; void *
0x1800d9dd1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9dd6  nop
0x1800d9dd7  lea     rcx, [rbp+190h+var_1E8]; void *
0x1800d9ddb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9de0  nop
0x1800d9de1  lea     rcx, [rsp+290h+Src+8]; void *
0x1800d9de6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9deb  nop
0x1800d9dec  lea     rcx, [rbp+190h+var_1A0]; void *
0x1800d9df0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9df5  mov     rdx, r12; unsigned __int64
0x1800d9df8  mov     rcx, [r14+8]; this
0x1800d9dfc  call    ?QueryPastDowntimeDurationSeconds@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(unsigned __int64)
0x1800d9e01  xorps   xmm6, xmm6
0x1800d9e04  cvtsd2ss xmm6, xmm0
0x1800d9e08  mov     edx, r15d
0x1800d9e0b  lea     rcx, [rbp+190h+var_1C0]
0x1800d9e0f  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d9e14  mov     rdi, rax
0x1800d9e17  xorps   xmm0, xmm0
0x1800d9e1a  movups  xmmword ptr [rsp+290h+Src+8], xmm0
0x1800d9e1f  xor     eax, eax
0x1800d9e21  mov     [rsp+290h+var_240], rax
0x1800d9e26  mov     qword ptr [rsp+290h+var_238], rax
0x1800d9e2b  lea     r8d, [rax+5]
0x1800d9e2f  lea     rdx, aRseti; "RSeTi"
0x1800d9e36  lea     rcx, [rsp+290h+Src+8]
0x1800d9e3b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9e40  nop
0x1800d9e41  mov     r8d, 1
0x1800d9e47  lea     rdx, aN; "N"
0x1800d9e4e  lea     rcx, [rsp+290h+Src+8]; Src
0x1800d9e53  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d9e58  movups  xmm0, xmmword ptr [rax]
0x1800d9e5b  movups  [rbp+190h+var_210], xmm0
0x1800d9e5f  movups  xmm1, xmmword ptr [rax+10h]
0x1800d9e63  movups  [rbp+190h+var_200], xmm1
0x1800d9e67  xor     ecx, ecx
0x1800d9e69  mov     [rax+10h], rcx
0x1800d9e6d  mov     qword ptr [rax+18h], 7
0x1800d9e75  mov     [rax], cx
0x1800d9e78  mov     r8, rdi
0x1800d9e7b  lea     rdx, [rbp+190h+var_210]
0x1800d9e7f  lea     rcx, [rbp+190h+var_1A0]
0x1800d9e83  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800d9e88  nop
0x1800d9e89  mov     r8d, 2
0x1800d9e8f  lea     rdx, aV1; "V1"
0x1800d9e96  mov     rcx, rax; Src
0x1800d9e99  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d9e9e  movups  xmm0, xmmword ptr [rax]
0x1800d9ea1  movups  [rbp+190h+var_1E8], xmm0
0x1800d9ea5  movups  xmm1, xmmword ptr [rax+10h]
0x1800d9ea9  movups  [rbp+190h+var_1D8], xmm1
0x1800d9ead  xor     r9d, r9d
0x1800d9eb0  mov     [rax+10h], r9
0x1800d9eb4  mov     qword ptr [rax+18h], 7
0x1800d9ebc  mov     [rax], r9w
0x1800d9ec0  lea     rdx, [rbp+190h+var_1E8]
0x1800d9ec4  movq    rcx, xmm0
0x1800d9ec9  psrldq  xmm1, 8
0x1800d9ece  movq    rax, xmm1
0x1800d9ed3  cmp     rax, 7
0x1800d9ed7  cmova   rdx, rcx
0x1800d9edb  xorps   xmm0, xmm0
0x1800d9ede  movups  [rsp+290h+var_238+8], xmm0
0x1800d9ee3  mov     [rsp+290h+var_220], r9
0x1800d9ee8  mov     [rsp+290h+var_218], r9
0x1800d9eed  mov     r8, rsi
0x1800d9ef0  inc     r8
0x1800d9ef3  cmp     [rdx+r8*2], r9w
0x1800d9ef8  jnz     short loc_1800D9EF0
0x1800d9efa  lea     rcx, [rsp+290h+var_238+8]
0x1800d9eff  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9f04  nop
0x1800d9f05  movss   dword ptr [rsp+290h+ppv], xmm9
0x1800d9f0c  xorps   xmm3, xmm3
0x1800d9f0f  movaps  xmm2, xmm6
0x1800d9f12  lea     rdx, [rsp+290h+var_238+8]
0x1800d9f17  lea     rcx, [rbp+190h+var_160]
0x1800d9f1b  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d9f20  nop
0x1800d9f21  lea     rcx, [rsp+290h+var_238+8]; void *
0x1800d9f26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9f2b  nop
0x1800d9f2c  lea     rcx, [rbp+190h+var_1E8]; void *
0x1800d9f30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9f35  nop
0x1800d9f36  lea     rcx, [rbp+190h+var_1A0]; void *
0x1800d9f3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9f3f  nop
0x1800d9f40  lea     rcx, [rbp+190h+var_210]; void *
0x1800d9f44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9f49  nop
0x1800d9f4a  lea     rcx, [rsp+290h+Src+8]; void *
0x1800d9f4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9f54  nop
0x1800d9f55  lea     rcx, [rbp+190h+var_1C0]; void *
0x1800d9f59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9f5e  mov     rdx, r12; unsigned __int64
0x1800d9f61  mov     rcx, [r14+8]; this
0x1800d9f65  call    ?QueryPastDowntimeTotalSizeUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(unsigned __int64)
0x1800d9f6a  xorps   xmm6, xmm6
0x1800d9f6d  cvtsd2ss xmm6, xmm0
0x1800d9f71  mov     edx, r15d
0x1800d9f74  lea     rcx, [rbp+190h+var_1C0]
0x1800d9f78  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d9f7d  mov     rdi, rax
0x1800d9f80  xorps   xmm0, xmm0
0x1800d9f83  movups  xmmword ptr [rsp+290h+Src+8], xmm0
0x1800d9f88  xor     eax, eax
  ... truncated ...
```
