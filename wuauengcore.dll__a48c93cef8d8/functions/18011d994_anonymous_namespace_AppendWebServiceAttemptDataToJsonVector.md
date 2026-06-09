# _anonymous_namespace_::AppendWebServiceAttemptDataToJsonVector

- ea: `0x18011d994`
- end: `0x18011e9fd`
- name: `_anonymous_namespace_::AppendWebServiceAttemptDataToJsonVector`
- size: `4201`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011ea04`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x1800b30b8`
- `0x18011d098`
- `0x18011d994`
- `0x18011fff0`
- `0x180120124`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d9eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011dab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011e242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d9eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011dab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011e242`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18011da25`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18011da25`

## string_xrefs

- `0x18011dab2`: `Windows.Data.Json.JsonObject`
- `0x18011e23b`: `Windows.Data.Json.JsonArray`
- `0x18011d9e4`: `Windows.Data.Json.JsonValue`
- `0x18011da38`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011dae5`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011dbbd`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011dc7d`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011dd71`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011de31`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011df23`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011dfe3`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e0cb`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e18b`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e26e`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e36a`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e474`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e572`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e666`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e781`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011e856`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall anonymous_namespace_::AppendWebServiceAttemptDataToJsonVector(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HSTRING v7; // rbx
  __int64 v8; // rcx
  int ActivationFactory; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  __int64 v19; // rdx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v26; // rcx
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v29; // rcx
  _QWORD *v30; // rcx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v33)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v34; // rdi
  __int64 v35; // rax
  int v36; // eax
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  __int64 v40; // rcx
  _QWORD *v41; // rcx
  __int64 v42; // rbx
  __int64 (__fastcall *v43)(__int64, _QWORD, _QWORD **); // rdi
  _QWORD *v44; // rcx
  int v45; // eax
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v47; // rcx
  _QWORD *v48; // rcx
  __int64 v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v51)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v52; // rdi
  __int64 v53; // rax
  int v54; // eax
  __int64 (__fastcall ***v55)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v56; // rcx
  _QWORD *v57; // rcx
  __int64 v58; // rcx
  _QWORD *v59; // rcx
  __int64 v60; // rbx
  __int64 (__fastcall *v61)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v62; // rcx
  int v63; // eax
  __int64 (__fastcall ***v64)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v65; // rcx
  _QWORD *v66; // rcx
  __int64 v67; // rcx
  __int64 (__fastcall ***v68)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v69)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v70; // rdi
  __int64 v71; // rax
  int v72; // eax
  __int64 (__fastcall ***v73)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v74; // rcx
  _QWORD *v75; // rcx
  __int64 v76; // rcx
  _QWORD *v77; // rcx
  __int64 v78; // rbx
  __int64 (__fastcall *v79)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v80; // rcx
  int v81; // eax
  __int64 (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v83; // rcx
  _QWORD *v84; // rcx
  __int64 v85; // rcx
  __int64 (__fastcall ***v86)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v87)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v88; // rdi
  __int64 v89; // rax
  int v90; // eax
  __int64 (__fastcall ***v91)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v92; // rcx
  _QWORD *v93; // rcx
  __int64 v94; // rcx
  _QWORD *v95; // rcx
  HRESULT v96; // eax
  int v97; // edx
  unsigned int v98; // r8d
  int v99; // eax
  __int64 (__fastcall ***v100)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v101)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v102)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v103; // rcx
  _QWORD *v104; // rcx
  __int64 v105; // rcx
  __int64 (__fastcall ***v106)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v107)(_QWORD, GUID *, _QWORD); // rdi
  __int64 (__fastcall ***v108)(_QWORD, _QWORD, _QWORD); // rcx
  int v109; // eax
  __int64 (__fastcall ***v110)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v111)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v112)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v113; // rcx
  _QWORD *v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rbx
  int i; // edi
  __int64 (__fastcall ***v118)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v119)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v120)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v121; // rcx
  _QWORD *v122; // rcx
  __int64 v123; // rcx
  __int64 (__fastcall ***v124)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v125)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v126; // rcx
  int v127; // eax
  __int64 (__fastcall ***v128)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v129)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v130)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v131; // rcx
  _QWORD *v132; // rcx
  __int64 v133; // rcx
  __int64 (__fastcall ***v134)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v135)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v136; // rdi
  __int64 v137; // rax
  int v138; // eax
  __int64 (__fastcall ***v139)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v140)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v141)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v142; // rcx
  _QWORD *v143; // rcx
  __int64 v144; // rcx
  _QWORD *v145; // rdx
  __int64 (__fastcall ***v146)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v147)(_QWORD, GUID *, _QWORD **); // rdi
  int v148; // eax
  __int64 (__fastcall ***v149)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v150)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v151)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v152; // rcx
  _QWORD *v153; // rcx
  __int64 v154; // rcx
  int v155; // eax
  __int64 (__fastcall ***v156)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v157)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v158)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v159; // rcx
  _QWORD *v160; // rcx
  __int64 v161; // rcx
  _QWORD *v162; // rcx
  __int64 (__fastcall ***v163)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v164)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v165)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v166; // rcx
  _QWORD *v167; // rcx
  __int64 v168; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v171[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v172; // [rsp+50h] [rbp-30h] BYREF
  __int64 v173; // [rsp+58h] [rbp-28h] BYREF
  __int64 (__fastcall ***v174)(_QWORD, GUID *, _QWORD **); // [rsp+60h] [rbp-20h] BYREF
  __int64 (__fastcall ***v175)(_QWORD, GUID *, _QWORD **); // [rsp+68h] [rbp-18h] BYREF
  __int64 (__fastcall ***v176)(_QWORD, GUID *, _QWORD); // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v171[1] = a2;
  v172 = 0;
  v173 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v4 < 0 )
    goto LABEL_251;
  v7 = string;
  v8 = v173;
  if ( v173 )
  {
    v173 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  ActivationFactory = RoGetActivationFactory(v7, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v173);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    v11 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
    }
    v13 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v10;
  }
  v174 = 0;
  string = 0;
  v15 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v15 < 0 )
  {
LABEL_252:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    JUMPOUT(0x18011E9FCLL);
  }
  v18 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(
          string,
          &v174);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v18,
      (int)hstringHeader.Reserved.Reserved1);
    v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    if ( v174 )
    {
      v174 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v20)[2])(v20);
    }
    v21 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
    }
    v23 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v10;
  }
  if ( *(_QWORD *)(a1 + 32) )
  {
    v24 = v173;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v173 + 72LL);
    v26 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
    }
    v27 = v25(v24, v19, &v172);
    v10 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v27,
        (int)hstringHeader.Reserved.Reserved1);
      v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v28)[2])(v28);
      }
      v29 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
      }
      v31 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      return v10;
    }
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    v33 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v174)[7];
    v34 = v172;
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180294BB0);
    v36 = v33(v32, *(GUID **)(v35 + 24), v34);
    v10 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v36,
        (int)hstringHeader.Reserved.Reserved1);
      v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v37)[2])(v37);
      }
      v38 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      v39 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
      }
      v40 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      return v10;
    }
    v41 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
    }
  }
  if ( *(_QWORD *)(a1 + 40) )
  {
    v42 = v173;
    v43 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v173 + 72LL);
    v44 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
    }
    v45 = v43(v42, **(unsigned int **)(a1 + 40), &v172);
    v10 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v45,
        (int)hstringHeader.Reserved.Reserved1);
      v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v46)[2])(v46);
      }
      v47 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      v48 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
      }
      v49 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      return v10;
    }
    v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    v51 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v174)[7];
    v52 = v172;
    v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180294BB8);
    v54 = v51(v50, *(GUID **)(v53 + 24), v52);
    v10 = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v54,
        (int)hstringHeader.Reserved.Reserved1);
      v55 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v55)[2])(v55);
      }
      v56 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      v57 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v57 + 16LL))(v57);
      }
      v58 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      }
      return v10;
    }
    v59 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v59 + 16LL))(v59);
    }
  }
  if ( *(_QWORD *)(a1 + 48) )
  {
    v60 = v173;
    v61 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v173 + 72LL);
    v62 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    }
    v63 = v61(v60, v19, &v172);
    v10 = v63;
    if ( v63 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v63,
        (int)hstringHeader.Reserved.Reserved1);
      v64 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v64)[2])(v64);
      }
      v65 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      }
      v66 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v66 + 16LL))(v66);
      }
      v67 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      return v10;
    }
    v68 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    v69 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v174)[7];
    v70 = v172;
    v71 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180294BA0);
    v72 = v69(v68, *(GUID **)(v71 + 24), v70);
    v10 = v72;
    if ( v72 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v72,
        (int)hstringHeader.Reserved.Reserved1);
      v73 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v73)[2])(v73);
      }
      v74 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      }
      v75 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v75 + 16LL))(v75);
      }
      v76 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      }
      return v10;
    }
    v77 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
    }
  }
  v78 = v173;
  v79 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v173 + 72LL);
  v80 = v172;
  if ( v172 )
  {
    v172 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v80 + 16LL))(v80);
  }
  v81 = v79(v78, v19, &v172);
  v10 = v81;
  if ( v81 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v81,
      (int)hstringHeader.Reserved.Reserved1);
    v82 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    if ( v174 )
    {
      v174 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v82)[2])(v82);
    }
    v83 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    v84 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    }
    v85 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    return v10;
  }
  v86 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
  v87 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v174)[7];
  v88 = v172;
  v89 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180294BD0);
  v90 = v87(v86, *(GUID **)(v89 + 24), v88);
  v10 = v90;
  if ( v90 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v90,
      (int)hstringHeader.Reserved.Reserved1);
    v91 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    if ( v174 )
    {
      v174 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v91)[2])(v91);
    }
    v92 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    }
    v93 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v93 + 16LL))(v93);
    }
    v94 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    }
    return v10;
  }
  v95 = v172;
  if ( v172 )
  {
    v172 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v95 + 16LL))(v95);
  }
  v176 = 0;
  v175 = 0;
  string = 0;
  v96 = WindowsCreateStringReference(L"Windows.Data.Json.JsonArray", 0x1Bu, &hstringHeader, &string);
  if ( v96 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v96, v97, v98);
LABEL_251:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    goto LABEL_252;
  }
  v99 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonArray>>(
          string,
          &v176);
  v10 = v99;
  if ( v99 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v99,
      (int)hstringHeader.Reserved.Reserved1);
    v100 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
    if ( v175 )
    {
      v175 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v100)[2])(v100);
    }
    v101 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
    if ( v176 )
    {
      v176 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v101)[2])(v101);
    }
    v102 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    if ( v174 )
    {
      v174 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v102)[2])(v102);
    }
    v103 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
    }
    v104 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v104 + 16LL))(v104);
    }
    v105 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
    }
    return v10;
  }
  v106 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
  v107 = **v176;
  v108 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
  if ( v175 )
  {
    v175 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v108)[2])(v108);
  }
  v109 = v107(v106, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v175);
  v10 = v109;
  if ( v109 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v109,
      (int)hstringHeader.Reserved.Reserved1);
    v110 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
    if ( v175 )
    {
      v175 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v110)[2])(v110);
    }
    v111 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
    if ( v176 )
    {
      v176 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v111)[2])(v111);
    }
    v112 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    if ( v174 )
    {
      v174 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v112)[2])(v112);
    }
    v113 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
    }
    v114 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v114 + 16LL))(v114);
    }
    v115 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
    }
    return v10;
  }
  v116 = *(_QWORD *)(a1 + 24);
  if ( !v116 )
    goto LABEL_173;
  for ( i = 0; i >= 0; i = anonymous_namespace_::AppendRetryAttemptDataToJsonVector(v116, v171) )
  {
    v116 = *(_QWORD *)(v116 + 8);
    if ( !v116 )
      break;
    v171[0] = v175;
    if ( v175 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v175)[1])(v175);
  }
  if ( i < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)i,
      (int)hstringHeader.Reserved.Reserved1);
    v118 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
    if ( v175 )
    {
      v175 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v118)[2])(v118);
    }
    v119 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
    if ( v176 )
    {
      v176 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v119)[2])(v119);
    }
    v120 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    if ( v174 )
    {
      v174 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v120)[2])(v120);
    }
    v121 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
    }
    v122 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v122 + 16LL))(v122);
    }
    v123 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
    }
    return (unsigned int)i;
  }
  else
  {
LABEL_173:
    v124 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
    v125 = **v175;
    v126 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v126 + 16LL))(v126);
    }
    v127 = v125(v124, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v172);
    v10 = v127;
    if ( v127 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v127,
        (int)hstringHeader.Reserved.Reserved1);
      v128 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v128)[2])(v128);
      }
      v129 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v129)[2])(v129);
      }
      v130 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v130)[2])(v130);
      }
      v131 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
      }
      v132 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v132 + 16LL))(v132);
      }
      v133 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
      }
      return v10;
    }
    v134 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    v135 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))(*v174)[7];
    v136 = v172;
    v137 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180294BA8);
    v138 = v135(v134, *(GUID **)(v137 + 24), v136);
    v10 = v138;
    if ( v138 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v138,
        (int)hstringHeader.Reserved.Reserved1);
      v139 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v139)[2])(v139);
      }
      v140 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v140)[2])(v140);
      }
      v141 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v141)[2])(v141);
      }
      v142 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v142 + 16LL))(v142);
      }
      v143 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v143 + 16LL))(v143);
      }
      v144 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v144 + 16LL))(v144);
      }
      return v10;
    }
    v145 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v145 + 16LL))(v145);
      v145 = v172;
    }
    v146 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    v147 = **v174;
    if ( v145 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v145 + 16LL))(v145);
    }
    v148 = v147(v146, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v172);
    v10 = v148;
    if ( v148 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v148,
        (int)hstringHeader.Reserved.Reserved1);
      v149 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v149)[2])(v149);
      }
      v150 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v150)[2])(v150);
      }
      v151 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v151)[2])(v151);
      }
      v152 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v152 + 16LL))(v152);
      }
      v153 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v153 + 16LL))(v153);
      }
      v154 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 16LL))(v154);
      }
      return v10;
    }
    v155 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a2 + 104LL))(*a2, v172);
    v10 = v155;
    if ( v155 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
        (const char *)(unsigned int)v155,
        (int)hstringHeader.Reserved.Reserved1);
      v156 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v156)[2])(v156);
      }
      v157 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v157)[2])(v157);
      }
      v158 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
      if ( v174 )
      {
        v174 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v158)[2])(v158);
      }
      v159 = v173;
      if ( v173 )
      {
        v173 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 16LL))(v159);
      }
      v160 = v172;
      if ( v172 )
      {
        v172 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v160 + 16LL))(v160);
      }
      v161 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v161 + 16LL))(v161);
      }
      return v10;
    }
    v162 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v162 + 16LL))(v162);
    }
    v163 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
    if ( v175 )
    {
      v175 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v163)[2])(v163);
    }
    v164 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
    if ( v176 )
    {
      v176 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v164)[2])(v164);
    }
    v165 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v174;
    if ( v174 )
    {
      v174 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v165)[2])(v165);
    }
    v166 = v173;
    if ( v173 )
    {
      v173 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v166 + 16LL))(v166);
    }
    v167 = v172;
    if ( v172 )
    {
      v172 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v167 + 16LL))(v167);
    }
    v168 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v168 + 16LL))(v168);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18011d994  mov     [rsp-28h+arg_10], rbx
0x18011d999  mov     [rsp-28h+arg_18], rsi
0x18011d99e  push    rbp
0x18011d99f  push    rdi
0x18011d9a0  push    r12
0x18011d9a2  push    r14
0x18011d9a4  push    r15
0x18011d9a6  mov     rbp, rsp
0x18011d9a9  sub     rsp, 80h
0x18011d9b0  mov     rax, cs:__security_cookie
0x18011d9b7  xor     rax, rsp
0x18011d9ba  mov     [rbp+var_8], rax
0x18011d9be  mov     r14, rdx
0x18011d9c1  mov     r15, rcx
0x18011d9c4  mov     [rbp+var_38], rdx
0x18011d9c8  xor     r12d, r12d
0x18011d9cb  mov     [rbp+var_30], r12
0x18011d9cf  mov     [rbp+var_28], r12
0x18011d9d3  mov     [rbp+string], r12
0x18011d9d7  lea     r9, [rbp+string]; string
0x18011d9db  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18011d9df  lea     edx, [r12+1Bh]; length
0x18011d9e4  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x18011d9eb  call    cs:__imp_WindowsCreateStringReference
0x18011d9f1  test    eax, eax
0x18011d9f3  js      loc_18011E9ED
0x18011d9f9  mov     rbx, [rbp+string]
0x18011d9fd  mov     rcx, [rbp+var_28]
0x18011da01  test    rcx, rcx
0x18011da04  jz      short loc_18011DA17
0x18011da06  mov     [rbp+var_28], r12
0x18011da0a  mov     rax, [rcx]
0x18011da0d  mov     rax, [rax+10h]
0x18011da11  call    _guard_dispatch_icall
0x18011da16  nop
0x18011da17  lea     r8, [rbp+var_28]
0x18011da1b  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18011da22  mov     rcx, rbx
0x18011da25  call    cs:__imp_RoGetActivationFactory
0x18011da2b  mov     ebx, eax
0x18011da2d  test    eax, eax
0x18011da2f  jns     short loc_18011DA9D
0x18011da31  mov     rcx, [rbp+28h]; this
0x18011da35  mov     r9d, eax; char *
0x18011da38  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011da3f  mov     edx, 54h ; 'T'; void *
0x18011da44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011da49  nop
0x18011da4a  mov     rcx, [rbp+var_28]
0x18011da4e  test    rcx, rcx
0x18011da51  jz      short loc_18011DA64
0x18011da53  mov     [rbp+var_28], r12
0x18011da57  mov     rax, [rcx]
0x18011da5a  mov     rax, [rax+10h]
0x18011da5e  call    _guard_dispatch_icall
0x18011da63  nop
0x18011da64  mov     rcx, [rbp+var_30]
0x18011da68  test    rcx, rcx
0x18011da6b  jz      short loc_18011DA7E
0x18011da6d  mov     [rbp+var_30], r12
0x18011da71  mov     rax, [rcx]
0x18011da74  mov     rax, [rax+10h]
0x18011da78  call    _guard_dispatch_icall
0x18011da7d  nop
0x18011da7e  mov     rcx, [r14]
0x18011da81  test    rcx, rcx
0x18011da84  jz      short loc_18011DA96
0x18011da86  mov     [r14], r12
0x18011da89  mov     rax, [rcx]
0x18011da8c  mov     rax, [rax+10h]
0x18011da90  call    _guard_dispatch_icall
0x18011da95  nop
0x18011da96  mov     eax, ebx
0x18011da98  jmp     loc_18011E9BD
0x18011da9d  mov     [rbp+var_20], r12
0x18011daa1  mov     [rbp+string], r12
0x18011daa5  lea     r9, [rbp+string]; string
0x18011daa9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18011daad  mov     edx, 1Ch; length
0x18011dab2  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18011dab9  call    cs:__imp_WindowsCreateStringReference
0x18011dabf  test    eax, eax
0x18011dac1  js      loc_18011E9F5
0x18011dac7  lea     rdx, [rbp+var_20]
0x18011dacb  mov     rcx, [rbp+string]
0x18011dacf  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonObject>>)
0x18011dad4  mov     ebx, eax
0x18011dad6  test    eax, eax
0x18011dad8  jns     loc_18011DB62
0x18011dade  mov     rcx, [rbp+28h]; this
0x18011dae2  mov     r9d, eax; char *
0x18011dae5  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011daec  mov     edx, 57h ; 'W'; void *
0x18011daf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011daf6  nop
0x18011daf7  mov     rcx, [rbp+var_20]
0x18011dafb  test    rcx, rcx
0x18011dafe  jz      short loc_18011DB11
0x18011db00  mov     [rbp+var_20], r12
0x18011db04  mov     rax, [rcx]
0x18011db07  mov     rax, [rax+10h]
0x18011db0b  call    _guard_dispatch_icall
0x18011db10  nop
0x18011db11  mov     rcx, [rbp+var_28]
0x18011db15  test    rcx, rcx
0x18011db18  jz      short loc_18011DB2B
0x18011db1a  mov     [rbp+var_28], r12
0x18011db1e  mov     rax, [rcx]
0x18011db21  mov     rax, [rax+10h]
0x18011db25  call    _guard_dispatch_icall
0x18011db2a  nop
0x18011db2b  mov     rcx, [rbp+var_30]
0x18011db2f  test    rcx, rcx
0x18011db32  jz      short loc_18011DB45
0x18011db34  mov     [rbp+var_30], r12
0x18011db38  mov     rax, [rcx]
0x18011db3b  mov     rax, [rax+10h]
0x18011db3f  call    _guard_dispatch_icall
0x18011db44  nop
0x18011db45  mov     rcx, [r14]
0x18011db48  test    rcx, rcx
0x18011db4b  jz      short loc_18011DB5D
0x18011db4d  mov     [r14], r12
0x18011db50  mov     rax, [rcx]
0x18011db53  mov     rax, [rax+10h]
0x18011db57  call    _guard_dispatch_icall
0x18011db5c  nop
0x18011db5d  jmp     loc_18011DA96
0x18011db62  cmp     [r15+20h], r12
0x18011db66  jz      loc_18011DD14
0x18011db6c  mov     rbx, [rbp+var_28]
0x18011db70  mov     rax, [rbx]
0x18011db73  mov     rdi, [rax+48h]
0x18011db77  mov     rcx, [rbp+var_30]
0x18011db7b  test    rcx, rcx
0x18011db7e  jz      short loc_18011DB91
0x18011db80  mov     [rbp+var_30], r12
0x18011db84  mov     rdx, [rcx]
0x18011db87  mov     rax, [rdx+10h]
0x18011db8b  call    _guard_dispatch_icall
0x18011db90  nop
0x18011db91  mov     rcx, [r15+20h]
0x18011db95  movd    xmm1, dword ptr [rcx]
0x18011db99  cvtdq2pd xmm1, xmm1
0x18011db9d  lea     r8, [rbp+var_30]
0x18011dba1  mov     rcx, rbx
0x18011dba4  mov     rax, rdi
0x18011dba7  call    _guard_dispatch_icall
0x18011dbac  mov     ebx, eax
0x18011dbae  test    eax, eax
0x18011dbb0  jns     loc_18011DC3A
0x18011dbb6  mov     rcx, [rbp+28h]; this
0x18011dbba  mov     r9d, eax; char *
0x18011dbbd  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011dbc4  mov     edx, 5Bh ; '['; void *
0x18011dbc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011dbce  nop
0x18011dbcf  mov     rcx, [rbp+var_20]
0x18011dbd3  test    rcx, rcx
0x18011dbd6  jz      short loc_18011DBE9
0x18011dbd8  mov     [rbp+var_20], r12
0x18011dbdc  mov     rax, [rcx]
0x18011dbdf  mov     rax, [rax+10h]
0x18011dbe3  call    _guard_dispatch_icall
0x18011dbe8  nop
0x18011dbe9  mov     rcx, [rbp+var_28]
0x18011dbed  test    rcx, rcx
0x18011dbf0  jz      short loc_18011DC03
0x18011dbf2  mov     [rbp+var_28], r12
0x18011dbf6  mov     rax, [rcx]
0x18011dbf9  mov     rax, [rax+10h]
0x18011dbfd  call    _guard_dispatch_icall
0x18011dc02  nop
0x18011dc03  mov     rcx, [rbp+var_30]
0x18011dc07  test    rcx, rcx
0x18011dc0a  jz      short loc_18011DC1D
0x18011dc0c  mov     [rbp+var_30], r12
0x18011dc10  mov     rax, [rcx]
0x18011dc13  mov     rax, [rax+10h]
0x18011dc17  call    _guard_dispatch_icall
0x18011dc1c  nop
0x18011dc1d  mov     rcx, [r14]
0x18011dc20  test    rcx, rcx
0x18011dc23  jz      short loc_18011DC35
0x18011dc25  mov     [r14], r12
0x18011dc28  mov     rax, [rcx]
0x18011dc2b  mov     rax, [rax+10h]
0x18011dc2f  call    _guard_dispatch_icall
0x18011dc34  nop
0x18011dc35  jmp     loc_18011DA96
0x18011dc3a  mov     rbx, [rbp+var_20]
0x18011dc3e  mov     rax, [rbx]
0x18011dc41  mov     rsi, [rax+38h]
0x18011dc45  mov     rdi, [rbp+var_30]
0x18011dc49  lea     rdx, off_180294BB0; "ErrorCode"
0x18011dc50  lea     rcx, [rbp+hstringHeader]
0x18011dc54  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18011dc59  nop
0x18011dc5a  mov     r8, rdi
0x18011dc5d  mov     rdx, [rax+18h]
0x18011dc61  mov     rcx, rbx
0x18011dc64  mov     rax, rsi
0x18011dc67  call    _guard_dispatch_icall
0x18011dc6c  mov     ebx, eax
0x18011dc6e  test    eax, eax
0x18011dc70  jns     loc_18011DCFA
0x18011dc76  mov     rcx, [rbp+28h]; this
0x18011dc7a  mov     r9d, eax; char *
0x18011dc7d  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011dc84  mov     edx, 5Ch ; '\'; void *
0x18011dc89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011dc8e  nop
0x18011dc8f  mov     rcx, [rbp+var_20]
0x18011dc93  test    rcx, rcx
0x18011dc96  jz      short loc_18011DCA9
0x18011dc98  mov     [rbp+var_20], r12
0x18011dc9c  mov     rax, [rcx]
0x18011dc9f  mov     rax, [rax+10h]
0x18011dca3  call    _guard_dispatch_icall
0x18011dca8  nop
0x18011dca9  mov     rcx, [rbp+var_28]
0x18011dcad  test    rcx, rcx
0x18011dcb0  jz      short loc_18011DCC3
0x18011dcb2  mov     [rbp+var_28], r12
0x18011dcb6  mov     rax, [rcx]
0x18011dcb9  mov     rax, [rax+10h]
0x18011dcbd  call    _guard_dispatch_icall
0x18011dcc2  nop
0x18011dcc3  mov     rcx, [rbp+var_30]
0x18011dcc7  test    rcx, rcx
0x18011dcca  jz      short loc_18011DCDD
0x18011dccc  mov     [rbp+var_30], r12
0x18011dcd0  mov     rax, [rcx]
0x18011dcd3  mov     rax, [rax+10h]
0x18011dcd7  call    _guard_dispatch_icall
0x18011dcdc  nop
0x18011dcdd  mov     rcx, [r14]
0x18011dce0  test    rcx, rcx
0x18011dce3  jz      short loc_18011DCF5
0x18011dce5  mov     [r14], r12
0x18011dce8  mov     rax, [rcx]
0x18011dceb  mov     rax, [rax+10h]
0x18011dcef  call    _guard_dispatch_icall
0x18011dcf4  nop
0x18011dcf5  jmp     loc_18011DA96
0x18011dcfa  mov     rcx, [rbp+var_30]
0x18011dcfe  test    rcx, rcx
0x18011dd01  jz      short loc_18011DD14
0x18011dd03  mov     [rbp+var_30], r12
0x18011dd07  mov     rax, [rcx]
0x18011dd0a  mov     rax, [rax+10h]
0x18011dd0e  call    _guard_dispatch_icall
0x18011dd13  nop
0x18011dd14  cmp     [r15+28h], r12
0x18011dd18  jz      loc_18011DEC8
0x18011dd1e  mov     rbx, [rbp+var_28]
0x18011dd22  mov     rax, [rbx]
0x18011dd25  mov     rdi, [rax+48h]
0x18011dd29  mov     rcx, [rbp+var_30]
0x18011dd2d  test    rcx, rcx
0x18011dd30  jz      short loc_18011DD43
0x18011dd32  mov     [rbp+var_30], r12
0x18011dd36  mov     rax, [rcx]
0x18011dd39  mov     rax, [rax+10h]
0x18011dd3d  call    _guard_dispatch_icall
0x18011dd42  nop
0x18011dd43  mov     rcx, [r15+28h]
0x18011dd47  mov     edx, [rcx]
0x18011dd49  xorps   xmm1, xmm1
0x18011dd4c  cvtsi2sd xmm1, rdx
0x18011dd51  lea     r8, [rbp+var_30]
0x18011dd55  mov     rcx, rbx
0x18011dd58  mov     rax, rdi
0x18011dd5b  call    _guard_dispatch_icall
0x18011dd60  mov     ebx, eax
0x18011dd62  test    eax, eax
0x18011dd64  jns     loc_18011DDEE
0x18011dd6a  mov     rcx, [rbp+28h]; this
0x18011dd6e  mov     r9d, eax; char *
0x18011dd71  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011dd78  mov     edx, 62h ; 'b'; void *
0x18011dd7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011dd82  nop
0x18011dd83  mov     rcx, [rbp+var_20]
0x18011dd87  test    rcx, rcx
0x18011dd8a  jz      short loc_18011DD9D
0x18011dd8c  mov     [rbp+var_20], r12
0x18011dd90  mov     rax, [rcx]
0x18011dd93  mov     rax, [rax+10h]
0x18011dd97  call    _guard_dispatch_icall
0x18011dd9c  nop
0x18011dd9d  mov     rcx, [rbp+var_28]
0x18011dda1  test    rcx, rcx
0x18011dda4  jz      short loc_18011DDB7
0x18011dda6  mov     [rbp+var_28], r12
0x18011ddaa  mov     rax, [rcx]
0x18011ddad  mov     rax, [rax+10h]
0x18011ddb1  call    _guard_dispatch_icall
0x18011ddb6  nop
0x18011ddb7  mov     rcx, [rbp+var_30]
  ... truncated ...
```
