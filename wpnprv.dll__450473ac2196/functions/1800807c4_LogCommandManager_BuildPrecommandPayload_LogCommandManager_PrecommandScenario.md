# LogCommandManager::BuildPrecommandPayload(LogCommandManager::PrecommandScenario &)

- ea: `0x1800807c4`
- end: `0x180080efb`
- name: `?BuildPrecommandPayload@LogCommandManager@@CA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAUPrecommandScenario@1@@Z`
- size: `1847`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800812c4`

## callees

- `0x180007440`
- `0x18000ba54`
- `0x18000d06c`
- `0x18000fe0c`
- `0x18001d108`
- `0x180036de8`
- `0x180080464`
- `0x18008050c`
- `0x1800805fc`
- `0x1800807c4`
- `0x180080f04`
- `0x1800815cc`
- `0x180096010`

## string_xrefs

- `0x18008086b`: `Windows.Data.Json.JsonValue`
- `0x18008081f`: `Windows.Data.Json.JsonObject`
- `0x180080847`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080895`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080916`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080965`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x1800809dc`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080a2b`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080a7d`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080acc`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080b4c`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080b9b`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080c04`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080c53`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080cbc`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080d0b`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080d5d`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080dac`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080e23`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`
- `0x180080e72`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\logcommandmanager.cpp`

## pseudocode

```c
__int64 *__fastcall LogCommandManager::BuildPrecommandPayload(__int64 *a1, __int64 a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64); // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rbx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64); // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64, __int64 *); // rbx
  __int64 v38; // rdx
  int v39; // eax
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, _QWORD, __int64); // rdi
  __int64 v42; // rbx
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64, __int64 *); // rbx
  __int64 v56; // rdx
  int v57; // eax
  __int64 v58; // rsi
  __int64 (__fastcall *v59)(__int64, _QWORD, __int64); // rdi
  __int64 v60; // rbx
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // rdi
  __int64 (__fastcall *v67)(__int64, _QWORD, __int64 *); // rbx
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // rsi
  __int64 (__fastcall *v71)(__int64, _QWORD, __int64); // rdi
  __int64 v72; // rbx
  __int64 v73; // rax
  int v74; // eax
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rdi
  __int64 (__fastcall *v79)(__int64, _QWORD, __int64 *); // rbx
  __int64 v80; // rax
  int v81; // eax
  __int64 v82; // rsi
  __int64 (__fastcall *v83)(__int64, _QWORD, __int64); // rdi
  __int64 v84; // rbx
  __int64 v85; // rax
  int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // rdi
  __int64 (__fastcall *v91)(__int64, __int64, __int64 *); // rbx
  __int64 v92; // rdx
  int v93; // eax
  __int64 v94; // rsi
  __int64 (__fastcall *v95)(__int64, _QWORD, __int64); // rdi
  __int64 v96; // rbx
  __int64 v97; // rax
  int v98; // eax
  __int64 v99; // rdi
  __int64 (__fastcall *v100)(__int64, _QWORD, __int64 *); // rbx
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // rax
  int v105; // eax
  __int64 v106; // rsi
  __int64 (__fastcall *v107)(__int64, _QWORD, __int64); // rdi
  __int64 v108; // rbx
  __int64 v109; // rax
  int v110; // eax
  __int64 v111; // rdx
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // rdx
  __int64 v115; // r8
  __int64 v116; // r9
  __int64 v117; // rdx
  __int64 v118; // r8
  __int64 v119; // r9
  __int64 v120; // rdx
  __int64 v121; // r8
  __int64 v122; // r9
  __int64 v123; // rdx
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v126; // rdx
  __int64 v127; // r8
  __int64 v128; // r9
  int v130[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v131; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v132; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v133; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v134; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v135; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v136; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v137; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v138; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v139; // [rsp+68h] [rbp-98h] BYREF
  int v140; // [rsp+70h] [rbp-90h]
  __int64 *v141; // [rsp+78h] [rbp-88h]
  _BYTE v142[32]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v144; // [rsp+B8h] [rbp-48h]
  _BYTE v145[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v146[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v141 = a1;
  *a1 = 0;
  v140 = 1;
  v144 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v144, a1);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v4,
      v130[0]);
  *(_QWORD *)v130 = 0;
  v144 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
         v144,
         v130);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v5,
      v130[0]);
  if ( *(int *)(a2 + 104) < 0 )
  {
    v134 = 0;
    LogCommandManager::GetFailureContextAsString(v145, *(unsigned int *)(a2 + 88));
    v9 = *(_QWORD *)v130;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v130 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134, v11, v12, v13);
    v131 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v145);
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, &v131);
    v15 = v10(v9, *(_QWORD *)(v14 + 24), &v134);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v15,
        v130[0]);
    v16 = *a1;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
    v18 = v134;
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, off_1800983C8);
    v20 = v17(v16, *(_QWORD *)(v19 + 24), v18);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v20,
        v130[0]);
    v133 = 0;
    LogCommandManager::GetTimeAsString(&hstringHeader, *(_QWORD *)(a2 + 96));
    v21 = *(_QWORD *)v130;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v130 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133, v23, v24, v25);
    v131 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, &v131);
    v27 = v22(v21, *(_QWORD *)(v26 + 24), &v133);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v27,
        v130[0]);
    v28 = *a1;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
    v30 = v133;
    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, off_1800983A8);
    v32 = v29(v28, *(_QWORD *)(v31 + 24), v30);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v32,
        v130[0]);
    v132 = 0;
    v36 = *(_QWORD *)v130;
    v37 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v130 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132, v33, v34, v35);
    v39 = v37(v36, v38, &v132);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v39,
        v130[0]);
    v40 = *a1;
    v41 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
    v42 = v132;
    v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, off_1800983A0);
    v44 = v41(v40, *(_QWORD *)(v43 + 24), v42);
    if ( v44 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
        (const char *)(unsigned int)v44,
        v130[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132, v45, v46, v47);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133, v48, v49, v50);
    std::wstring::_Tidy_deallocate(v145);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134, v51, v52, v53);
  }
  v139 = 0;
  v54 = *(_QWORD *)v130;
  v55 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v130 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v139, v6, v7, v8);
  LOBYTE(v56) = *(_BYTE *)(a2 + 16);
  v57 = v55(v54, v56, &v139);
  if ( v57 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v57,
      v130[0]);
  v58 = *a1;
  v59 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
  v60 = v139;
  v61 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, &off_1800983D0);
  v62 = v59(v58, *(_QWORD *)(v61 + 24), v60);
  if ( v62 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v62,
      v130[0]);
  v138 = 0;
  v66 = *(_QWORD *)v130;
  v67 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v130 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138, v63, v64, v65);
  v131 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 24);
  v68 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, &v131);
  v69 = v67(v66, *(_QWORD *)(v68 + 24), &v138);
  if ( v69 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v69,
      v130[0]);
  v70 = *a1;
  v71 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
  v72 = v138;
  v73 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, off_1800983B8);
  v74 = v71(v70, *(_QWORD *)(v73 + 24), v72);
  if ( v74 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v74,
      v130[0]);
  v137 = 0;
  v78 = *(_QWORD *)v130;
  v79 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v130 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137, v75, v76, v77);
  v131 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 56);
  v80 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, &v131);
  v81 = v79(v78, *(_QWORD *)(v80 + 24), &v137);
  if ( v81 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v81,
      v130[0]);
  v82 = *a1;
  v83 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
  v84 = v137;
  v85 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, off_1800983C0);
  v86 = v83(v82, *(_QWORD *)(v85 + 24), v84);
  if ( v86 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v86,
      v130[0]);
  v136 = 0;
  v90 = *(_QWORD *)v130;
  v91 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v130 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136, v87, v88, v89);
  v93 = v91(v90, v92, &v136);
  if ( v93 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v93,
      v130[0]);
  v94 = *a1;
  v95 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
  v96 = v136;
  v97 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, off_180098398);
  v98 = v95(v94, *(_QWORD *)(v97 + 24), v96);
  if ( v98 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v98,
      v130[0]);
  v135 = 0;
  LogCommandManager::GetTimeAsString(v146, *(_QWORD *)(a2 + 8));
  v99 = *(_QWORD *)v130;
  v100 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v130 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135, v101, v102, v103);
  v131 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v146);
  v104 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, &v131);
  v105 = v100(v99, *(_QWORD *)(v104 + 24), &v135);
  if ( v105 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v105,
      v130[0]);
  v106 = *a1;
  v107 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a1 + 56LL);
  v108 = v135;
  v109 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v142, off_1800983B0);
  v110 = v107(v106, *(_QWORD *)(v109 + 24), v108);
  if ( v110 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\logcommandmanager.cpp",
      (const char *)(unsigned int)v110,
      v130[0]);
  std::wstring::_Tidy_deallocate(v146);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135, v111, v112, v113);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136, v114, v115, v116);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137, v117, v118, v119);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138, v120, v121, v122);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v139, v123, v124, v125);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v130, v126, v127, v128);
  return a1;
}

```

## disassembly

```asm
0x1800807c4  mov     [rsp-8+arg_10], rbx
0x1800807c9  mov     [rsp-8+arg_18], rsi
0x1800807ce  push    rbp
0x1800807cf  push    rdi
0x1800807d0  push    r12
0x1800807d2  push    r14
0x1800807d4  push    r15
0x1800807d6  lea     rbp, [rsp-10h]
0x1800807db  sub     rsp, 110h
0x1800807e2  mov     rax, cs:__security_cookie
0x1800807e9  xor     rax, rsp
0x1800807ec  mov     [rbp+30h+var_30], rax
0x1800807f0  mov     r15, rdx
0x1800807f3  mov     r14, rcx
0x1800807f6  mov     [rsp+130h+var_B8], rcx
0x1800807fb  xor     r12d, r12d
0x1800807fe  mov     [rsp+130h+var_C0], r12d
0x180080803  mov     [rcx], r12
0x180080806  mov     [rsp+130h+var_C0], 1
0x18008080e  mov     [rbp+30h+var_78], r12
0x180080812  lea     ebx, [r12+1Ch]
0x180080817  mov     r9d, ebx; unsigned int
0x18008081a  lea     r8d, [r12+1Dh]; unsigned int
0x18008081f  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180080826  lea     rcx, [rbp+30h+hstringHeader]; hstringHeader
0x18008082a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008082f  nop
0x180080830  mov     rdx, r14
0x180080833  mov     rcx, [rbp+30h+var_78]
0x180080837  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18008083c  mov     rcx, [rbp+38h]; this
0x180080840  test    eax, eax
0x180080842  jns     short loc_180080859
0x180080844  mov     r9d, eax; char *
0x180080847  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008084e  mov     edx, 0CEh; void *
0x180080853  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080859  mov     qword ptr [rsp+130h+var_110], r12; int
0x18008085e  mov     [rbp+30h+var_78], r12
0x180080862  mov     r9d, 1Bh; unsigned int
0x180080868  mov     r8d, ebx; unsigned int
0x18008086b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180080872  lea     rcx, [rbp+30h+hstringHeader]; hstringHeader
0x180080876  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008087b  nop
0x18008087c  lea     rdx, [rsp+130h+var_110]
0x180080881  mov     rcx, [rbp+30h+var_78]
0x180080885  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x18008088a  mov     rcx, [rbp+38h]; this
0x18008088e  test    eax, eax
0x180080890  jns     short loc_1800808A7
0x180080892  mov     r9d, eax; char *
0x180080895  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008089c  mov     edx, 0D1h; void *
0x1800808a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800808a7  cmp     [r15+68h], r12d
0x1800808ab  jge     loc_180080B12
0x1800808b1  mov     [rsp+130h+var_F0], r12
0x1800808b6  mov     edx, [r15+58h]
0x1800808ba  lea     rcx, [rbp+30h+var_70]
0x1800808be  call    ?GetFailureContextAsString@LogCommandManager@@CA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4LogCommandFailureContext@@@Z; LogCommandManager::GetFailureContextAsString(LogCommandFailureContext)
0x1800808c3  nop
0x1800808c4  mov     rdi, qword ptr [rsp+130h+var_110]
0x1800808c9  mov     rax, [rdi]
0x1800808cc  mov     rbx, [rax+50h]
0x1800808d0  lea     rcx, [rsp+130h+var_F0]
0x1800808d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800808da  lea     rcx, [rbp+30h+var_70]
0x1800808de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800808e3  mov     [rsp+130h+var_108], rax
0x1800808e8  lea     rdx, [rsp+130h+var_108]
0x1800808ed  lea     rcx, [rbp+30h+var_B0]
0x1800808f1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800808f6  nop
0x1800808f7  lea     r8, [rsp+130h+var_F0]
0x1800808fc  mov     rdx, [rax+18h]
0x180080900  mov     rcx, rdi
0x180080903  mov     rax, rbx
0x180080906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008090b  mov     rcx, [rbp+38h]; this
0x18008090f  test    eax, eax
0x180080911  jns     short loc_180080928
0x180080913  mov     r9d, eax; char *
0x180080916  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008091d  mov     edx, 0D8h; void *
0x180080922  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080928  mov     rsi, [r14]
0x18008092b  mov     rax, [rsi]
0x18008092e  mov     rdi, [rax+38h]
0x180080932  mov     rbx, [rsp+130h+var_F0]
0x180080937  lea     rdx, off_1800983C8; "FailureContext"
0x18008093e  lea     rcx, [rbp+30h+var_B0]
0x180080942  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180080947  nop
0x180080948  mov     r8, rbx
0x18008094b  mov     rdx, [rax+18h]
0x18008094f  mov     rcx, rsi
0x180080952  mov     rax, rdi
0x180080955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008095a  mov     rcx, [rbp+38h]; this
0x18008095e  test    eax, eax
0x180080960  jns     short loc_180080977
0x180080962  mov     r9d, eax; char *
0x180080965  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008096c  mov     edx, 0D9h; void *
0x180080971  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080977  mov     [rsp+130h+var_F8], r12
0x18008097c  mov     rdx, [r15+60h]
0x180080980  lea     rcx, [rbp+30h+hstringHeader]
0x180080984  call    ?GetTimeAsString@LogCommandManager@@CA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@Z; LogCommandManager::GetTimeAsString(__int64)
0x180080989  nop
0x18008098a  mov     rdi, qword ptr [rsp+130h+var_110]
0x18008098f  mov     rax, [rdi]
0x180080992  mov     rbx, [rax+50h]
0x180080996  lea     rcx, [rsp+130h+var_F8]
0x18008099b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800809a0  lea     rcx, [rbp+30h+hstringHeader]
0x1800809a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800809a9  mov     [rsp+130h+var_108], rax
0x1800809ae  lea     rdx, [rsp+130h+var_108]
0x1800809b3  lea     rcx, [rbp+30h+var_B0]
0x1800809b7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800809bc  nop
0x1800809bd  lea     r8, [rsp+130h+var_F8]
0x1800809c2  mov     rdx, [rax+18h]
0x1800809c6  mov     rcx, rdi
0x1800809c9  mov     rax, rbx
0x1800809cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800809d1  mov     rcx, [rbp+38h]; this
0x1800809d5  test    eax, eax
0x1800809d7  jns     short loc_1800809EE
0x1800809d9  mov     r9d, eax; char *
0x1800809dc  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800809e3  mov     edx, 0DDh; void *
0x1800809e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800809ee  mov     rsi, [r14]
0x1800809f1  mov     rax, [rsi]
0x1800809f4  mov     rdi, [rax+38h]
0x1800809f8  mov     rbx, [rsp+130h+var_F8]
0x1800809fd  lea     rdx, off_1800983A8; "LastErrorTime"
0x180080a04  lea     rcx, [rbp+30h+var_B0]
0x180080a08  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180080a0d  nop
0x180080a0e  mov     r8, rbx
0x180080a11  mov     rdx, [rax+18h]
0x180080a15  mov     rcx, rsi
0x180080a18  mov     rax, rdi
0x180080a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080a20  mov     rcx, [rbp+38h]; this
0x180080a24  test    eax, eax
0x180080a26  jns     short loc_180080A3D
0x180080a28  mov     r9d, eax; char *
0x180080a2b  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080a32  mov     edx, 0DEh; void *
0x180080a37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080a3d  mov     [rsp+130h+var_100], r12
0x180080a42  mov     rdi, qword ptr [rsp+130h+var_110]
0x180080a47  mov     rax, [rdi]
0x180080a4a  mov     rbx, [rax+48h]
0x180080a4e  lea     rcx, [rsp+130h+var_100]
0x180080a53  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080a58  movd    xmm1, dword ptr [r15+68h]
0x180080a5e  cvtdq2pd xmm1, xmm1
0x180080a62  lea     r8, [rsp+130h+var_100]
0x180080a67  mov     rcx, rdi
0x180080a6a  mov     rax, rbx
0x180080a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080a72  mov     rcx, [rbp+38h]; this
0x180080a76  test    eax, eax
0x180080a78  jns     short loc_180080A8F
0x180080a7a  mov     r9d, eax; char *
0x180080a7d  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080a84  mov     edx, 0E1h; void *
0x180080a89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080a8f  mov     rsi, [r14]
0x180080a92  mov     rax, [rsi]
0x180080a95  mov     rdi, [rax+38h]
0x180080a99  mov     rbx, [rsp+130h+var_100]
0x180080a9e  lea     rdx, off_1800983A0; "LastHrError"
0x180080aa5  lea     rcx, [rbp+30h+var_B0]
0x180080aa9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180080aae  nop
0x180080aaf  mov     r8, rbx
0x180080ab2  mov     rdx, [rax+18h]
0x180080ab6  mov     rcx, rsi
0x180080ab9  mov     rax, rdi
0x180080abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080ac1  mov     rcx, [rbp+38h]; this
0x180080ac5  test    eax, eax
0x180080ac7  jns     short loc_180080ADE
0x180080ac9  mov     r9d, eax; char *
0x180080acc  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080ad3  mov     edx, 0E2h; void *
0x180080ad8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080ade  lea     rcx, [rsp+130h+var_100]
0x180080ae3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080ae8  nop
0x180080ae9  lea     rcx, [rbp+30h+hstringHeader]
0x180080aed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080af2  nop
0x180080af3  lea     rcx, [rsp+130h+var_F8]
0x180080af8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080afd  nop
0x180080afe  lea     rcx, [rbp+30h+var_70]
0x180080b02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080b07  nop
0x180080b08  lea     rcx, [rsp+130h+var_F0]
0x180080b0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080b12  mov     [rsp+130h+var_C8], r12
0x180080b17  mov     rdi, qword ptr [rsp+130h+var_110]
0x180080b1c  mov     rax, [rdi]
0x180080b1f  mov     rbx, [rax+40h]
0x180080b23  lea     rcx, [rsp+130h+var_C8]
0x180080b28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080b2d  lea     r8, [rsp+130h+var_C8]
0x180080b32  mov     dl, [r15+10h]
0x180080b36  mov     rcx, rdi
0x180080b39  mov     rax, rbx
0x180080b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b41  mov     rcx, [rbp+38h]; this
0x180080b45  test    eax, eax
0x180080b47  jns     short loc_180080B5E
0x180080b49  mov     r9d, eax; char *
0x180080b4c  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080b53  mov     edx, 0E6h; void *
0x180080b58  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080b5e  mov     rsi, [r14]
0x180080b61  mov     rax, [rsi]
0x180080b64  mov     rdi, [rax+38h]
0x180080b68  mov     rbx, [rsp+130h+var_C8]
0x180080b6d  lea     rdx, off_1800983D0; "IsGroupPolicyEnabled"
0x180080b74  lea     rcx, [rbp+30h+var_B0]
0x180080b78  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180080b7d  nop
0x180080b7e  mov     r8, rbx
0x180080b81  mov     rdx, [rax+18h]
0x180080b85  mov     rcx, rsi
0x180080b88  mov     rax, rdi
0x180080b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b90  mov     rcx, [rbp+38h]; this
0x180080b94  test    eax, eax
0x180080b96  jns     short loc_180080BAD
0x180080b98  mov     r9d, eax; char *
0x180080b9b  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080ba2  mov     edx, 0E7h; void *
0x180080ba7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080bad  mov     [rsp+130h+var_D0], r12
0x180080bb2  mov     rdi, qword ptr [rsp+130h+var_110]
0x180080bb7  mov     rax, [rdi]
0x180080bba  mov     rbx, [rax+50h]
0x180080bbe  lea     rcx, [rsp+130h+var_D0]
0x180080bc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080bc8  lea     rcx, [r15+18h]
0x180080bcc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180080bd1  mov     [rsp+130h+var_108], rax
0x180080bd6  lea     rdx, [rsp+130h+var_108]
0x180080bdb  lea     rcx, [rbp+30h+var_B0]
0x180080bdf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180080be4  nop
0x180080be5  lea     r8, [rsp+130h+var_D0]
0x180080bea  mov     rdx, [rax+18h]
0x180080bee  mov     rcx, rdi
0x180080bf1  mov     rax, rbx
0x180080bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080bf9  mov     rcx, [rbp+38h]; this
0x180080bfd  test    eax, eax
0x180080bff  jns     short loc_180080C16
0x180080c01  mov     r9d, eax; char *
0x180080c04  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080c0b  mov     edx, 0EAh; void *
0x180080c10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080c16  mov     rsi, [r14]
0x180080c19  mov     rax, [rsi]
0x180080c1c  mov     rdi, [rax+38h]
0x180080c20  mov     rbx, [rsp+130h+var_D0]
0x180080c25  lea     rdx, off_1800983B8; "WnsServerName"
0x180080c2c  lea     rcx, [rbp+30h+var_B0]
0x180080c30  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180080c35  nop
0x180080c36  mov     r8, rbx
0x180080c39  mov     rdx, [rax+18h]
0x180080c3d  mov     rcx, rsi
0x180080c40  mov     rax, rdi
0x180080c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080c48  mov     rcx, [rbp+38h]; this
0x180080c4c  test    eax, eax
0x180080c4e  jns     short loc_180080C65
0x180080c50  mov     r9d, eax; char *
0x180080c53  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080c5a  mov     edx, 0EBh; void *
0x180080c5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080c65  mov     [rsp+130h+var_D8], r12
0x180080c6a  mov     rdi, qword ptr [rsp+130h+var_110]
0x180080c6f  mov     rax, [rdi]
0x180080c72  mov     rbx, [rax+50h]
0x180080c76  lea     rcx, [rsp+130h+var_D8]
0x180080c7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080c80  lea     rcx, [r15+38h]
0x180080c84  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180080c89  mov     [rsp+130h+var_108], rax
  ... truncated ...
```
