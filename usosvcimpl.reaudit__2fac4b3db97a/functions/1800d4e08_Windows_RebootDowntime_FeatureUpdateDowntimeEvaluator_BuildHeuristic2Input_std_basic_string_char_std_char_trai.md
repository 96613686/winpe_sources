# Windows::RebootDowntime::FeatureUpdateDowntimeEvaluator::BuildHeuristic2Input(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800d4e08`
- end: `0x1800d5d4b`
- name: `?BuildHeuristic2Input@FeatureUpdateDowntimeEvaluator@RebootDowntime@Windows@@QEAA?AV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@NU?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `3907`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800d489c`

## callees

- `0x1800108b4`
- `0x1800109f4`
- `0x1800112d0`
- `0x180011484`
- `0x180011680`
- `0x180041480`
- `0x180099878`
- `0x1800c4d00`
- `0x1800c4e84`
- `0x1800cd700`
- `0x1800d4e08`
- `0x1800d5f38`
- `0x1800d6148`
- `0x1800d63a0`
- `0x1800dd930`
- `0x1800de12c`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d4e70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d4e70`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5b8a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5b9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5baa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bda`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bfa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c0a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c1a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c2a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c3a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c4a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c5a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c6a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5b8a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5b9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5baa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bda`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5bfa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c0a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c1a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c2a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c3a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c4a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c5a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5c6a`

## string_xrefs

- `0x1800d55eb`: `NumComAV1`
- `0x1800d5cd0`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\FeatureUpdateDowntimeEvaluator.cpp`
- `0x1800d5d15`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\FeatureUpdateDowntimeEvaluator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
_QWORD *__fastcall Windows::RebootDowntime::FeatureUpdateDowntimeEvaluator::BuildHeuristic2Input(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  HRESULT v6; // eax
  __int64 v7; // rax
  __int64 InputForKey; // rax
  __int64 v9; // rbx
  BSTR v10; // rcx
  __int64 v11; // rdx
  BSTR v12; // rcx
  __int64 v13; // rdx
  BSTR v14; // rcx
  __int64 v15; // rdx
  BSTR v16; // rcx
  __int64 v17; // rdx
  BSTR v18; // rcx
  __int64 v19; // rdx
  BSTR v20; // rcx
  __int64 v21; // rdx
  BSTR v22; // rcx
  __int64 v23; // rdx
  BSTR v24; // rcx
  __int64 v25; // rdx
  BSTR v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // ebx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rbx
  float v39; // xmm0_4
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rbx
  float v44; // xmm0_4
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // ebx
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rax
  int v52; // ebx
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rbx
  float v57; // xmm0_4
  __int64 v58; // rdx
  __int64 v59; // rdx
  int v60; // eax
  _QWORD *v61; // rax
  unsigned int i; // ebx
  double v63; // xmm6_8
  __int64 v64; // rdx
  __int64 v65; // r8
  int ppv; // [rsp+28h] [rbp-E0h]
  int v68; // [rsp+48h] [rbp-C0h] BYREF
  float v69; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v70; // [rsp+50h] [rbp-B8h] BYREF
  float v71[4]; // [rsp+58h] [rbp-B0h] BYREF
  BSTR v72; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+70h] [rbp-98h]
  __int64 v74; // [rsp+78h] [rbp-90h]
  _QWORD v75[2]; // [rsp+80h] [rbp-88h] BYREF
  char v76; // [rsp+90h] [rbp-78h]
  _OWORD v77[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v78; // [rsp+B8h] [rbp-50h]
  __int64 v79; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v80; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v81; // [rsp+E0h] [rbp-28h]
  unsigned int v82; // [rsp+E8h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+F0h] [rbp-18h] BYREF
  BSTR v84; // [rsp+F8h] [rbp-10h] BYREF
  BSTR v85; // [rsp+100h] [rbp-8h] BYREF
  BSTR v86; // [rsp+108h] [rbp+0h] BYREF
  BSTR v87; // [rsp+110h] [rbp+8h] BYREF
  BSTR v88; // [rsp+118h] [rbp+10h] BYREF
  BSTR v89; // [rsp+120h] [rbp+18h] BYREF
  BSTR v90; // [rsp+128h] [rbp+20h] BYREF
  BSTR v91; // [rsp+130h] [rbp+28h] BYREF
  BSTR v92; // [rsp+138h] [rbp+30h] BYREF
  BSTR v93; // [rsp+140h] [rbp+38h] BYREF
  BSTR v94; // [rsp+148h] [rbp+40h] BYREF
  BSTR v95; // [rsp+150h] [rbp+48h] BYREF
  BSTR v96; // [rsp+158h] [rbp+50h] BYREF
  BSTR v97; // [rsp+160h] [rbp+58h] BYREF
  BSTR v98; // [rsp+168h] [rbp+60h] BYREF
  LPVOID v99; // [rsp+170h] [rbp+68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v78 = a2;
  LODWORD(v74) = 0;
  v99 = 0;
  v6 = CoCreateInstance(
         &GUID_df43bfd6_da50_426f_af99_5b63385f586a,
         0,
         4u,
         &GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b,
         &v99);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\FeatureUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v80 = 0;
  v81 = 0;
  v7 = -1;
  do
    ++v7;
  while ( Windows::RebootDowntime::InputBuilder::rebootDowntimeSignalKey[v7] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::rebootDowntimeSignalKey;
  v73 = v7;
  InputForKey = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(InputForKey + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(InputForKey + 8) != 1 )
    std::_Throw_bad_variant_access();
  v9 = *(_QWORD *)InputForKey;
  v98 = 0;
  wil::make_bstr(&v98, L"NeoLCUpoV1");
  v69 = FLOAT_1_0;
  LODWORD(v70) = 0;
  LOBYTE(v68) = v9 == 1010;
  v10 = v98;
  *(_QWORD *)v71 = v98;
  v11 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v70,
      &v69);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 1010);
    *(_QWORD *)v11 = v10;
    *(_DWORD *)(v11 + 12) = 0;
    *(float *)(v11 + 16) = FLOAT_1_0;
    *(_DWORD *)(v11 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v97 = 0;
  wil::make_bstr(&v97, L"NeoLCUV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 1020;
  v12 = v97;
  *(_QWORD *)v71 = v97;
  v13 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 1020);
    *(_QWORD *)v13 = v12;
    *(_DWORD *)(v13 + 12) = 0;
    *(float *)(v13 + 16) = FLOAT_1_0;
    *(_DWORD *)(v13 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v96 = 0;
  wil::make_bstr(&v96, L"NeoWCOSV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 2010;
  v14 = v96;
  *(_QWORD *)v71 = v96;
  v15 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 2010);
    *(_QWORD *)v15 = v14;
    *(_DWORD *)(v15 + 12) = 0;
    *(float *)(v15 + 16) = FLOAT_1_0;
    *(_DWORD *)(v15 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v95 = 0;
  wil::make_bstr(&v95, L"NeoFUldsV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10010;
  v16 = v95;
  *(_QWORD *)v71 = v95;
  v17 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10010);
    *(_QWORD *)v17 = v16;
    *(_DWORD *)(v17 + 12) = 0;
    *(float *)(v17 + 16) = FLOAT_1_0;
    *(_DWORD *)(v17 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v94 = 0;
  wil::make_bstr(&v94, L"NeoFUoffV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10020;
  v18 = v94;
  *(_QWORD *)v71 = v94;
  v19 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10020);
    *(_QWORD *)v19 = v18;
    *(_DWORD *)(v19 + 12) = 0;
    *(float *)(v19 + 16) = FLOAT_1_0;
    *(_DWORD *)(v19 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v93 = 0;
  wil::make_bstr(&v93, L"NeoFUV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10030;
  v20 = v93;
  *(_QWORD *)v71 = v93;
  v21 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10030);
    *(_QWORD *)v21 = v20;
    *(_DWORD *)(v21 + 12) = 0;
    *(float *)(v21 + 16) = FLOAT_1_0;
    *(_DWORD *)(v21 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v92 = 0;
  wil::make_bstr(&v92, L"NeoFUssbV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10040;
  v22 = v92;
  *(_QWORD *)v71 = v92;
  v23 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10040);
    *(_QWORD *)v23 = v22;
    *(_DWORD *)(v23 + 12) = 0;
    *(float *)(v23 + 16) = FLOAT_1_0;
    *(_DWORD *)(v23 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v91 = 0;
  wil::make_bstr(&v91, L"NeoFUsfbV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10050;
  v24 = v91;
  *(_QWORD *)v71 = v91;
  v25 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10050);
    *(_QWORD *)v25 = v24;
    *(_DWORD *)(v25 + 12) = 0;
    *(float *)(v25 + 16) = FLOAT_1_0;
    *(_DWORD *)(v25 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v90 = 0;
  wil::make_bstr(&v90, L"NeoFUsosV1");
  *(float *)&v70 = FLOAT_1_0;
  v69 = 0.0;
  LOBYTE(v68) = v9 == 10060;
  v26 = v90;
  *(_QWORD *)v71 = v90;
  v27 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(
      &v80,
      *((_QWORD *)&v80 + 1),
      v71,
      &v68,
      &v69,
      &v70);
  }
  else
  {
    *(float *)(*((_QWORD *)&v80 + 1) + 8LL) = (float)(v9 == 10060);
    *(_QWORD *)v27 = v26;
    *(_DWORD *)(v27 + 12) = 0;
    *(float *)(v27 + 16) = FLOAT_1_0;
    *(_DWORD *)(v27 + 20) = 0;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v28 = -1;
  do
    ++v28;
  while ( Windows::RebootDowntime::InputBuilder::didNumWin32ChangeKey[v28] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::didNumWin32ChangeKey;
  v73 = v28;
  v29 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v29 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v29 + 8) )
    std::_Throw_bad_variant_access();
  v30 = *(_DWORD *)v29;
  v89 = 0;
  wil::make_bstr(&v89, L"W32AChV1");
  LODWORD(v70) = 1065353216;
  v69 = 0.0;
  v71[0] = (float)v30;
  v72 = v89;
  v31 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      v71,
      &v69,
      &v70);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v89;
    *(float *)(v31 + 8) = (float)v30;
    *(_DWORD *)(v31 + 12) = 0;
    *(_QWORD *)(v31 + 16) = 1065353216;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v32 = -1;
  do
    ++v32;
  while ( Windows::RebootDowntime::InputBuilder::didTopAppsChangeVersionKey[v32] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::didTopAppsChangeVersionKey;
  v73 = v32;
  v33 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v33 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v33 + 8) )
    std::_Throw_bad_variant_access();
  v34 = *(_DWORD *)v33;
  v88 = 0;
  wil::make_bstr(&v88, L"OthAChV1");
  v71[0] = 1.0;
  LODWORD(v70) = 0;
  v69 = (float)v34;
  v72 = v88;
  v35 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v88;
    *(float *)(v35 + 8) = (float)v34;
    *(_DWORD *)(v35 + 12) = 0;
    *(_QWORD *)(v35 + 16) = 1065353216;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v36 = -1;
  do
    ++v36;
  while ( Windows::RebootDowntime::InputBuilder::numTopAppsKey[v36] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numTopAppsKey;
  v73 = v36;
  v37 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v37 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v37 + 8) != 1 )
    std::_Throw_bad_variant_access();
  v38 = *(_QWORD *)v37;
  v87 = 0;
  wil::make_bstr(&v87, L"NumComAV1");
  v71[0] = 5.0;
  LODWORD(v70) = 0;
  if ( v38 < 0 )
    v39 = (float)(v38 & 1 | (unsigned int)((unsigned __int64)v38 >> 1))
        + (float)(v38 & 1 | (unsigned int)((unsigned __int64)v38 >> 1));
  else
    v39 = (float)(int)v38;
  v69 = v39;
  v72 = v87;
  v40 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v87;
    *(float *)(v40 + 8) = v39;
    *(_DWORD *)(v40 + 12) = 0;
    *(_QWORD *)(v40 + 16) = 1084227584;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v41 = -1;
  do
    ++v41;
  while ( Windows::RebootDowntime::InputBuilder::numWin32AppsKey[v41] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numWin32AppsKey;
  v73 = v41;
  v42 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v42 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v42 + 8) != 1 )
    std::_Throw_bad_variant_access();
  v43 = *(_QWORD *)v42;
  v86 = 0;
  wil::make_bstr(&v86, L"NumW32AV1");
  v71[0] = 200.0;
  LODWORD(v70) = 0;
  if ( v43 < 0 )
    v44 = (float)(v43 & 1 | (unsigned int)((unsigned __int64)v43 >> 1))
        + (float)(v43 & 1 | (unsigned int)((unsigned __int64)v43 >> 1));
  else
    v44 = (float)(int)v43;
  v69 = v44;
  v72 = v86;
  v45 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v86;
    *(float *)(v45 + 8) = v44;
    *(_DWORD *)(v45 + 12) = 0;
    *(_QWORD *)(v45 + 16) = 1128792064;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v46 = -1;
  do
    ++v46;
  while ( Windows::RebootDowntime::InputBuilder::numInstalledFodKey[v46] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numInstalledFodKey;
  v73 = v46;
  v47 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v47 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v47 + 8) )
    std::_Throw_bad_variant_access();
  v48 = *(_DWORD *)v47;
  v85 = 0;
  wil::make_bstr(&v85, L"NumFODV1");
  v71[0] = 50.0;
  LODWORD(v70) = 0;
  v69 = (float)v48;
  v72 = v85;
  v49 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v85;
    *(float *)(v49 + 8) = (float)v48;
    *(_DWORD *)(v49 + 12) = 0;
    *(_QWORD *)(v49 + 16) = 1112014848;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v50 = -1;
  do
    ++v50;
  while ( Windows::RebootDowntime::InputBuilder::numUserProfilesKey[v50] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::numUserProfilesKey;
  v73 = v50;
  v51 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v51 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v51 + 8) )
    std::_Throw_bad_variant_access();
  v52 = *(_DWORD *)v51;
  v84 = 0;
  wil::make_bstr(&v84, L"NumUsrPrV1");
  v71[0] = 10.0;
  LODWORD(v70) = 0;
  v69 = (float)v52;
  v72 = v84;
  v53 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = v84;
    *(float *)(v53 + 8) = (float)v52;
    *(_DWORD *)(v53 + 12) = 0;
    *(_QWORD *)(v53 + 16) = 1092616192;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v54 = -1;
  do
    ++v54;
  while ( Windows::RebootDowntime::InputBuilder::fuSizeKey[v54] );
  v72 = (BSTR)Windows::RebootDowntime::InputBuilder::fuSizeKey;
  v73 = v54;
  v55 = Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), v75, &v72);
  if ( !*(_BYTE *)(v55 + 16) )
    std::_Throw_bad_optional_access();
  if ( *(_BYTE *)(v55 + 8) != 1 )
    std::_Throw_bad_variant_access();
  v56 = *(_QWORD *)v55;
  bstrString = 0;
  wil::make_bstr(&bstrString, L"SzFUV1");
  v71[0] = 8000000000.0;
  LODWORD(v70) = 0;
  if ( v56 < 0 )
    v57 = (float)(v56 & 1 | (unsigned int)((unsigned __int64)v56 >> 1))
        + (float)(v56 & 1 | (unsigned int)((unsigned __int64)v56 >> 1));
  else
    v57 = (float)(int)v56;
  v69 = v57;
  v72 = bstrString;
  v58 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) == v81 )
  {
    std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,float const &,float const &,float const &>(
      &v80,
      *((_QWORD *)&v80 + 1),
      &v72,
      &v69,
      &v70,
      v71);
    v59 = *((_QWORD *)&v80 + 1);
  }
  else
  {
    **((_QWORD **)&v80 + 1) = bstrString;
    *(float *)(v58 + 8) = v57;
    *(_DWORD *)(v58 + 12) = 0;
    *(_QWORD *)(v58 + 16) = 1341025064;
    v59 = *((_QWORD *)&v80 + 1) + 24LL;
    *((_QWORD *)&v80 + 1) += 24LL;
  }
  v82 = 0;
  v79 = 0;
  if ( a3[3] > 0xFu )
    a3 = (_QWORD *)*a3;
  v60 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64, _QWORD, const wchar_t *))(*(_QWORD *)v99 + 40LL))(
          v99,
          0xAAAAAAAAAAAAAAABuLL * ((v59 - (__int64)v80) >> 3),
          v80,
          L"FU202409");
  if ( v60 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\FeatureUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v60,
      (int)a3);
  v75[0] = &v79;
  v75[1] = &v82;
  v76 = 1;
  memset(a2, 0, 0x40u);
  *(_DWORD *)a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v61 = operator new(0x38u);
  *v61 = v61;
  v61[1] = v61;
  a2[1] = v61;
  a2[3] = 0;
  a2[4] = 0;
  a2[5] = 0;
  a2[6] = 7;
  a2[7] = 8;
  *(_DWORD *)a2 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<enum Windows::RebootDowntime::InputBuilder::UpdateType>>,std::_Iterator_base0>>>::_Assign_grow(
    a2 + 3,
    16,
    a2[1]);
  LODWORD(v74) = 1;
  for ( i = 0; i < v82; ++i )
  {
    v63 = *(float *)(v79 + 16LL * i + 8);
    v64 = *(_QWORD *)(v79 + 16LL * i);
    memset(v77, 0, sizeof(v77));
    v65 = -1;
    do
      ++v65;
    while ( *(_WORD *)(v64 + 2 * v65) );
    std::wstring::_Construct<1,wchar_t const *>(v77, v64, v65);
    *(double *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Try_emplace<std::wstring,>(
                             a2,
                             &v72,
                             v77)
              + 48LL) = v63;
    std::wstring::~wstring(v77);
  }
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(v75);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v84 )
    SysFreeString(v84);
  if ( v85 )
    SysFreeString(v85);
  if ( v86 )
    SysFreeString(v86);
  if ( v87 )
    SysFreeString(v87);
  if ( v88 )
    SysFreeString(v88);
  if ( v89 )
    SysFreeString(v89);
  if ( v90 )
    SysFreeString(v90);
  if ( v91 )
    SysFreeString(v91);
  if ( v92 )
    SysFreeString(v92);
  if ( v93 )
    SysFreeString(v93);
  if ( v94 )
    SysFreeString(v94);
  if ( v95 )
    SysFreeString(v95);
  if ( v96 )
    SysFreeString(v96);
  if ( v97 )
    SysFreeString(v97);
  if ( v98 )
    SysFreeString(v98);
  std::vector<CustomFeature>::~vector<CustomFeature>(&v80);
  if ( v99 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v99 + 16LL))(v99);
  return a2;
}

```

## disassembly

```asm
0x1800d4e08  mov     rax, rsp
0x1800d4e0b  mov     [rax+20h], rbx
0x1800d4e0f  push    rbp
0x1800d4e10  push    rsi
0x1800d4e11  push    rdi
0x1800d4e12  push    r14
0x1800d4e14  push    r15
0x1800d4e16  lea     rbp, [rax-0C8h]
0x1800d4e1d  sub     rsp, 1A0h
0x1800d4e24  movaps  xmmword ptr [rax-38h], xmm6
0x1800d4e28  movaps  xmmword ptr [rax-48h], xmm7
0x1800d4e2c  mov     rax, cs:__security_cookie
0x1800d4e33  xor     rax, rsp
0x1800d4e36  mov     [rbp+0C0h+var_50], rax
0x1800d4e3a  mov     r14, r8
0x1800d4e3d  mov     rsi, rdx
0x1800d4e40  mov     rdi, rcx
0x1800d4e43  mov     [rbp+0C0h+var_110], rdx
0x1800d4e47  xor     r15d, r15d
0x1800d4e4a  mov     dword ptr [rsp+1C0h+var_150], r15d
0x1800d4e4f  mov     [rbp+0C0h+var_58], r15
0x1800d4e53  lea     rax, [rbp+0C0h+var_58]
0x1800d4e57  mov     [rsp+1C0h+ppv], rax; int
0x1800d4e5c  lea     r9, _GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b; riid
0x1800d4e63  xor     edx, edx; pUnkOuter
0x1800d4e65  lea     r8d, [r15+4]; dwClsContext
0x1800d4e69  lea     rcx, _GUID_df43bfd6_da50_426f_af99_5b63385f586a; rclsid
0x1800d4e70  call    cs:__imp_CoCreateInstance
0x1800d4e76  mov     rcx, [rbp+0C8h]; this
0x1800d4e7d  test    eax, eax
0x1800d4e7f  js      loc_1800D5CCD
0x1800d4e85  xorps   xmm1, xmm1
0x1800d4e88  movdqu  [rbp+0C0h+var_F8], xmm1
0x1800d4e8d  mov     [rbp+0C0h+var_E8], r15
0x1800d4e91  mov     rdx, cs:?rebootDowntimeSignalKey@InputBuilder@RebootDowntime@Windows@@2QEB_WEB; wchar_t const * const Windows::RebootDowntime::InputBuilder::rebootDowntimeSignalKey
0x1800d4e98  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d4e9c  inc     rax
0x1800d4e9f  cmp     [rdx+rax*2], r15w
0x1800d4ea4  jnz     short loc_1800D4E9C
0x1800d4ea6  mov     [rsp+1C0h+var_160], rdx
0x1800d4eab  mov     [rsp+1C0h+var_158], rax
0x1800d4eb0  lea     r8, [rsp+1C0h+var_160]
0x1800d4eb5  lea     rdx, [rsp+1C0h+var_148]
0x1800d4eba  mov     rcx, [rdi+8]
0x1800d4ebe  call    ?GetInputForKey@InputBuilder@RebootDowntime@Windows@@QEAA?AV?$optional@V?$variant@I_K@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::RebootDowntime::InputBuilder::GetInputForKey(wil::basic_zstring_view<wchar_t>)
0x1800d4ec3  cmp     [rax+10h], r15b
0x1800d4ec7  jz      loc_1800D5CE2
0x1800d4ecd  cmp     byte ptr [rax+8], 1
0x1800d4ed1  jnz     loc_1800D5CC7
0x1800d4ed7  mov     rbx, [rax]
0x1800d4eda  mov     [rbp+0C0h+var_60], r15
0x1800d4ede  lea     rdx, aNeolcupov1; "NeoLCUpoV1"
0x1800d4ee5  lea     rcx, [rbp+0C0h+var_60]
0x1800d4ee9  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d4eee  nop
0x1800d4eef  movss   xmm6, cs:__real@3f800000
0x1800d4ef7  movss   [rsp+1C0h+var_17C], xmm6
0x1800d4efd  xorps   xmm7, xmm7
0x1800d4f00  movss   dword ptr [rsp+1C0h+var_178], xmm7
0x1800d4f06  cmp     rbx, 3F2h
0x1800d4f0d  setz    al
0x1800d4f10  mov     byte ptr [rsp+1C0h+var_180], al
0x1800d4f14  mov     rcx, [rbp+0C0h+var_60]
0x1800d4f18  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1800d4f1d  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1800d4f21  cmp     rdx, [rbp+0C0h+var_E8]
0x1800d4f25  jz      short loc_1800D4F4F
0x1800d4f27  movzx   eax, al
0x1800d4f2a  movd    xmm0, eax
0x1800d4f2e  cvtdq2ps xmm0, xmm0
0x1800d4f31  movss   dword ptr [rdx+8], xmm0
0x1800d4f36  mov     [rdx], rcx
0x1800d4f39  movss   dword ptr [rdx+0Ch], xmm7
0x1800d4f3e  movss   dword ptr [rdx+10h], xmm6
0x1800d4f43  xor     eax, eax
0x1800d4f45  mov     [rdx+14h], eax
0x1800d4f48  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1800d4f4d  jmp     short loc_1800D4F76
0x1800d4f4f  lea     rax, [rsp+1C0h+var_17C]
0x1800d4f54  mov     [rsp+1C0h+var_198], rax
0x1800d4f59  lea     rax, [rsp+1C0h+var_178]
0x1800d4f5e  mov     [rsp+1C0h+ppv], rax
0x1800d4f63  lea     r9, [rsp+1C0h+var_180]
0x1800d4f68  lea     r8, [rsp+1C0h+var_170]
0x1800d4f6d  lea     rcx, [rbp+0C0h+var_F8]
0x1800d4f71  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1800d4f76  mov     [rbp+0C0h+var_68], r15
0x1800d4f7a  lea     rdx, aNeolcuv1; "NeoLCUV1"
0x1800d4f81  lea     rcx, [rbp+0C0h+var_68]
0x1800d4f85  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d4f8a  nop
0x1800d4f8b  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1800d4f91  movss   [rsp+1C0h+var_17C], xmm7
0x1800d4f97  cmp     rbx, 3FCh
0x1800d4f9e  setz    al
0x1800d4fa1  mov     byte ptr [rsp+1C0h+var_180], al
0x1800d4fa5  mov     rcx, [rbp+0C0h+var_68]
0x1800d4fa9  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1800d4fae  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1800d4fb2  cmp     rdx, [rbp+0C0h+var_E8]
0x1800d4fb6  jz      short loc_1800D4FE0
0x1800d4fb8  movzx   eax, al
0x1800d4fbb  movd    xmm0, eax
0x1800d4fbf  cvtdq2ps xmm0, xmm0
0x1800d4fc2  movss   dword ptr [rdx+8], xmm0
0x1800d4fc7  mov     [rdx], rcx
0x1800d4fca  movss   dword ptr [rdx+0Ch], xmm7
0x1800d4fcf  movss   dword ptr [rdx+10h], xmm6
0x1800d4fd4  xor     eax, eax
0x1800d4fd6  mov     [rdx+14h], eax
0x1800d4fd9  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1800d4fde  jmp     short loc_1800D5007
0x1800d4fe0  lea     rax, [rsp+1C0h+var_178]
0x1800d4fe5  mov     [rsp+1C0h+var_198], rax
0x1800d4fea  lea     rax, [rsp+1C0h+var_17C]
0x1800d4fef  mov     [rsp+1C0h+ppv], rax
0x1800d4ff4  lea     r9, [rsp+1C0h+var_180]
0x1800d4ff9  lea     r8, [rsp+1C0h+var_170]
0x1800d4ffe  lea     rcx, [rbp+0C0h+var_F8]
0x1800d5002  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1800d5007  mov     [rbp+0C0h+var_70], r15
0x1800d500b  lea     rdx, aNeowcosv1; "NeoWCOSV1"
0x1800d5012  lea     rcx, [rbp+0C0h+var_70]
0x1800d5016  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d501b  nop
0x1800d501c  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1800d5022  movss   [rsp+1C0h+var_17C], xmm7
0x1800d5028  cmp     rbx, 7DAh
0x1800d502f  setz    al
0x1800d5032  mov     byte ptr [rsp+1C0h+var_180], al
0x1800d5036  mov     rcx, [rbp+0C0h+var_70]
0x1800d503a  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1800d503f  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1800d5043  cmp     rdx, [rbp+0C0h+var_E8]
0x1800d5047  jz      short loc_1800D5071
0x1800d5049  movzx   eax, al
0x1800d504c  movd    xmm0, eax
0x1800d5050  cvtdq2ps xmm0, xmm0
0x1800d5053  movss   dword ptr [rdx+8], xmm0
0x1800d5058  mov     [rdx], rcx
0x1800d505b  movss   dword ptr [rdx+0Ch], xmm7
0x1800d5060  movss   dword ptr [rdx+10h], xmm6
0x1800d5065  xor     eax, eax
0x1800d5067  mov     [rdx+14h], eax
0x1800d506a  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1800d506f  jmp     short loc_1800D5098
0x1800d5071  lea     rax, [rsp+1C0h+var_178]
0x1800d5076  mov     [rsp+1C0h+var_198], rax
0x1800d507b  lea     rax, [rsp+1C0h+var_17C]
0x1800d5080  mov     [rsp+1C0h+ppv], rax
0x1800d5085  lea     r9, [rsp+1C0h+var_180]
0x1800d508a  lea     r8, [rsp+1C0h+var_170]
0x1800d508f  lea     rcx, [rbp+0C0h+var_F8]
0x1800d5093  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1800d5098  mov     [rbp+0C0h+var_78], r15
0x1800d509c  lea     rdx, aNeofuldsv1; "NeoFUldsV1"
0x1800d50a3  lea     rcx, [rbp+0C0h+var_78]
0x1800d50a7  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d50ac  nop
0x1800d50ad  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1800d50b3  movss   [rsp+1C0h+var_17C], xmm7
0x1800d50b9  cmp     rbx, 271Ah
0x1800d50c0  setz    al
0x1800d50c3  mov     byte ptr [rsp+1C0h+var_180], al
0x1800d50c7  mov     rcx, [rbp+0C0h+var_78]
0x1800d50cb  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1800d50d0  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1800d50d4  cmp     rdx, [rbp+0C0h+var_E8]
0x1800d50d8  jz      short loc_1800D5102
0x1800d50da  movzx   eax, al
0x1800d50dd  movd    xmm0, eax
0x1800d50e1  cvtdq2ps xmm0, xmm0
0x1800d50e4  movss   dword ptr [rdx+8], xmm0
0x1800d50e9  mov     [rdx], rcx
0x1800d50ec  movss   dword ptr [rdx+0Ch], xmm7
0x1800d50f1  movss   dword ptr [rdx+10h], xmm6
0x1800d50f6  xor     eax, eax
0x1800d50f8  mov     [rdx+14h], eax
0x1800d50fb  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1800d5100  jmp     short loc_1800D5129
0x1800d5102  lea     rax, [rsp+1C0h+var_178]
0x1800d5107  mov     [rsp+1C0h+var_198], rax
0x1800d510c  lea     rax, [rsp+1C0h+var_17C]
0x1800d5111  mov     [rsp+1C0h+ppv], rax
0x1800d5116  lea     r9, [rsp+1C0h+var_180]
0x1800d511b  lea     r8, [rsp+1C0h+var_170]
0x1800d5120  lea     rcx, [rbp+0C0h+var_F8]
0x1800d5124  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1800d5129  mov     [rbp+0C0h+var_80], r15
0x1800d512d  lea     rdx, aNeofuoffv1; "NeoFUoffV1"
0x1800d5134  lea     rcx, [rbp+0C0h+var_80]
0x1800d5138  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d513d  nop
0x1800d513e  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1800d5144  movss   [rsp+1C0h+var_17C], xmm7
0x1800d514a  cmp     rbx, 2724h
0x1800d5151  setz    al
0x1800d5154  mov     byte ptr [rsp+1C0h+var_180], al
0x1800d5158  mov     rcx, [rbp+0C0h+var_80]
0x1800d515c  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1800d5161  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1800d5165  cmp     rdx, [rbp+0C0h+var_E8]
0x1800d5169  jz      short loc_1800D5193
0x1800d516b  movzx   eax, al
0x1800d516e  movd    xmm0, eax
0x1800d5172  cvtdq2ps xmm0, xmm0
0x1800d5175  movss   dword ptr [rdx+8], xmm0
0x1800d517a  mov     [rdx], rcx
0x1800d517d  movss   dword ptr [rdx+0Ch], xmm7
0x1800d5182  movss   dword ptr [rdx+10h], xmm6
0x1800d5187  xor     eax, eax
0x1800d5189  mov     [rdx+14h], eax
0x1800d518c  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1800d5191  jmp     short loc_1800D51BA
0x1800d5193  lea     rax, [rsp+1C0h+var_178]
0x1800d5198  mov     [rsp+1C0h+var_198], rax
0x1800d519d  lea     rax, [rsp+1C0h+var_17C]
0x1800d51a2  mov     [rsp+1C0h+ppv], rax
0x1800d51a7  lea     r9, [rsp+1C0h+var_180]
0x1800d51ac  lea     r8, [rsp+1C0h+var_170]
0x1800d51b1  lea     rcx, [rbp+0C0h+var_F8]
0x1800d51b5  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1800d51ba  mov     [rbp+0C0h+var_88], r15
0x1800d51be  lea     rdx, aNeofuv1; "NeoFUV1"
0x1800d51c5  lea     rcx, [rbp+0C0h+var_88]
0x1800d51c9  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d51ce  nop
0x1800d51cf  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1800d51d5  movss   [rsp+1C0h+var_17C], xmm7
0x1800d51db  cmp     rbx, 272Eh
0x1800d51e2  setz    al
0x1800d51e5  mov     byte ptr [rsp+1C0h+var_180], al
0x1800d51e9  mov     rcx, [rbp+0C0h+var_88]
0x1800d51ed  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1800d51f2  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1800d51f6  cmp     rdx, [rbp+0C0h+var_E8]
0x1800d51fa  jz      short loc_1800D5224
0x1800d51fc  movzx   eax, al
0x1800d51ff  movd    xmm0, eax
0x1800d5203  cvtdq2ps xmm0, xmm0
0x1800d5206  movss   dword ptr [rdx+8], xmm0
0x1800d520b  mov     [rdx], rcx
0x1800d520e  movss   dword ptr [rdx+0Ch], xmm7
0x1800d5213  movss   dword ptr [rdx+10h], xmm6
0x1800d5218  xor     eax, eax
0x1800d521a  mov     [rdx+14h], eax
0x1800d521d  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1800d5222  jmp     short loc_1800D524B
0x1800d5224  lea     rax, [rsp+1C0h+var_178]
0x1800d5229  mov     [rsp+1C0h+var_198], rax
0x1800d522e  lea     rax, [rsp+1C0h+var_17C]
0x1800d5233  mov     [rsp+1C0h+ppv], rax
0x1800d5238  lea     r9, [rsp+1C0h+var_180]
0x1800d523d  lea     r8, [rsp+1C0h+var_170]
0x1800d5242  lea     rcx, [rbp+0C0h+var_F8]
0x1800d5246  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1800d524b  mov     [rbp+0C0h+var_90], r15
0x1800d524f  lea     rdx, aNeofussbv1; "NeoFUssbV1"
0x1800d5256  lea     rcx, [rbp+0C0h+var_90]
0x1800d525a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d525f  nop
0x1800d5260  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1800d5266  movss   [rsp+1C0h+var_17C], xmm7
0x1800d526c  cmp     rbx, 2738h
0x1800d5273  setz    al
0x1800d5276  mov     byte ptr [rsp+1C0h+var_180], al
0x1800d527a  mov     rcx, [rbp+0C0h+var_90]
0x1800d527e  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1800d5283  mov     rdx, qword ptr [rbp+0C0h+var_F8+8]
0x1800d5287  cmp     rdx, [rbp+0C0h+var_E8]
0x1800d528b  jz      short loc_1800D52B5
0x1800d528d  movzx   eax, al
0x1800d5290  movd    xmm0, eax
0x1800d5294  cvtdq2ps xmm0, xmm0
0x1800d5297  movss   dword ptr [rdx+8], xmm0
0x1800d529c  mov     [rdx], rcx
0x1800d529f  movss   dword ptr [rdx+0Ch], xmm7
0x1800d52a4  movss   dword ptr [rdx+10h], xmm6
0x1800d52a9  xor     eax, eax
0x1800d52ab  mov     [rdx+14h], eax
0x1800d52ae  add     qword ptr [rbp+0C0h+var_F8+8], 18h
0x1800d52b3  jmp     short loc_1800D52DC
0x1800d52b5  lea     rax, [rsp+1C0h+var_178]
0x1800d52ba  mov     [rsp+1C0h+var_198], rax
0x1800d52bf  lea     rax, [rsp+1C0h+var_17C]
0x1800d52c4  mov     [rsp+1C0h+ppv], rax
0x1800d52c9  lea     r9, [rsp+1C0h+var_180]
0x1800d52ce  lea     r8, [rsp+1C0h+var_170]
0x1800d52d3  lea     rcx, [rbp+0C0h+var_F8]
0x1800d52d7  call    ??$_Emplace_reallocate@PEA_W_NMM@?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEAAPEAUCustomFeature@@QEAU2@$$QEAPEA_W$$QEA_N$$QEAM3@Z; std::vector<CustomFeature>::_Emplace_reallocate<wchar_t *,bool,float,float>(CustomFeature * const,wchar_t * &&,bool &&,float &&,float &&)
0x1800d52dc  mov     [rbp+0C0h+var_98], r15
0x1800d52e0  lea     rdx, aNeofusfbv1; "NeoFUsfbV1"
0x1800d52e7  lea     rcx, [rbp+0C0h+var_98]
0x1800d52eb  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800d52f0  nop
0x1800d52f1  movss   dword ptr [rsp+1C0h+var_178], xmm6
0x1800d52f7  movss   [rsp+1C0h+var_17C], xmm7
0x1800d52fd  cmp     rbx, 2742h
0x1800d5304  setz    al
0x1800d5307  mov     byte ptr [rsp+1C0h+var_180], al
  ... truncated ...
```
