# LaunchToast(Windows::System::IUser *,TOAST_DATA const *)

- ea: `0x18003584c`
- end: `0x180037011`
- name: `?LaunchToast@@YAJPEAUIUser@System@Windows@@PEBUTOAST_DATA@@@Z`
- size: `6085`
- prototype: `__int64 __fastcall(struct Windows::System::IUser *, const struct TOAST_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180070d70`

## callees

- `0x18000d030`
- `0x180012734`
- `0x180014a00`
- `0x180017500`
- `0x180018d54`
- `0x180022574`
- `0x18002ccd8`
- `0x180035784`
- `0x1800357fc`
- `0x18003584c`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035e61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035ebd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035f39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035f98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035e61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035ebd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035f39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035f98`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800358db`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036c16`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800358db`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036c16`

## string_xrefs

- `0x180035e5a`: `storsvc.dll`
- `0x180035eb6`: `storsvc.dll`
- `0x180035f32`: `storsvc.dll`
- `0x180035f91`: `storsvc.dll`
- `0x1800358f8`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x18003594e`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x1800359ad`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180035a21`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180035a7e`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180035b22`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180035d61`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180036057`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x1800362e2`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180036c2e`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180036ecd`: `onecore\drivers\storage\storsvc\service\storagenotification.cpp`
- `0x180035c32`: `template`

## pseudocode

```c
__int64 __fastcall LaunchToast(struct Windows::System::IUser *a1, const struct TOAST_DATA *a2)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, struct Windows::System::IUser *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rbx
  int v20; // eax
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, _QWORD); // rbx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64, __int64); // rdi
  __int64 v31; // rbx
  unsigned __int16 *v32; // r15
  unsigned __int16 *v33; // r12
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v35)(_QWORD, GUID *, __int64 *); // rbx
  int v36; // eax
  __int64 v37; // rdx
  unsigned __int64 v38; // r9
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, _QWORD, __int64 *); // rbx
  unsigned int v41; // ebx
  HMODULE ModuleHandleW; // rax
  int v43; // edi
  int v44; // esi
  unsigned __int16 v45; // r8
  unsigned int v46; // ebx
  HMODULE v47; // rax
  unsigned __int16 v48; // r8
  unsigned int v49; // esi
  HMODULE v50; // rax
  unsigned __int16 v51; // r8
  unsigned int v52; // ebx
  HMODULE v53; // rax
  unsigned __int16 v54; // r8
  __int64 (__fastcall ***v55)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v56)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v57; // rax
  __int64 v58; // rdi
  __int64 (__fastcall *v59)(__int64, __int64, __int64 *); // rbx
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, __int64, __int64 *); // rbx
  __int64 (__fastcall ***v62)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v63)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v64; // rax
  __int64 v65; // rdi
  __int64 (__fastcall *v66)(__int64, __int64, __int64 *); // rbx
  __int64 (__fastcall ***v67)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v68)(_QWORD, GUID *, __int64 *); // rbx
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rsi
  __int64 (__fastcall *v72)(__int64, __int64, __int64); // rdi
  __int64 v73; // rbx
  __int64 v74; // rsi
  __int64 (__fastcall *v75)(__int64, __int64, __int64); // rdi
  __int64 v76; // rbx
  __int64 v77; // rsi
  __int64 (__fastcall *v78)(__int64, __int64, __int64); // rdi
  __int64 v79; // rbx
  __int64 v80; // rsi
  __int64 (__fastcall *v81)(__int64, __int64, __int64); // rdi
  __int64 v82; // rbx
  __int64 (__fastcall ***v83)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v84)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v85; // rdi
  __int64 (__fastcall *v86)(__int64, __int64, __int64 *); // rbx
  __int64 (__fastcall ***v87)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v88)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall ***v89)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v90)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v91; // rdi
  __int64 (__fastcall *v92)(__int64, __int64, __int64 *); // rbx
  __int64 v93; // rsi
  __int64 (__fastcall *v94)(__int64, __int64, __int64); // rdi
  __int64 v95; // rbx
  __int64 v96; // rsi
  __int64 (__fastcall *v97)(__int64, __int64, __int64); // rdi
  __int64 v98; // rbx
  __int64 v99; // rsi
  __int64 (__fastcall *v100)(__int64, __int64, __int64); // rdi
  __int64 v101; // rbx
  __int64 v102; // rsi
  __int64 (__fastcall *v103)(__int64, __int64, __int64); // rdi
  __int64 v104; // rbx
  __int64 (__fastcall ***v105)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v106)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v107; // rdi
  __int64 (__fastcall *v108)(__int64, __int64, __int64 *); // rbx
  __int64 v109; // rsi
  __int64 (__fastcall *v110)(__int64, __int64, __int64); // rdi
  __int64 v111; // rbx
  __int64 v112; // rsi
  __int64 (__fastcall *v113)(__int64, __int64, __int64); // rdi
  __int64 v114; // rbx
  __int64 v115; // rsi
  __int64 (__fastcall *v116)(__int64, __int64, __int64); // rdi
  __int64 v117; // rbx
  __int64 v118; // rsi
  __int64 (__fastcall *v119)(__int64, __int64, __int64); // rdi
  __int64 v120; // rbx
  __int64 v121; // rbx
  int v122; // eax
  __int64 v123; // rdx
  __int64 v124; // rdi
  __int64 (__fastcall *v125)(__int64, _QWORD, _QWORD); // rbx
  __int64 (__fastcall ***v126)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v127)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v128; // rdi
  __int64 (__fastcall *v129)(__int64, __int64); // rbx
  __int64 v130; // rdi
  __int64 (__fastcall *v131)(__int64, _QWORD); // rbx
  __int64 v132; // rax
  __int64 v133; // rdx
  int v134; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v135)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v136; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v137; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v138; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v139; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v140; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v141; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v142)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 v143; // [rsp+70h] [rbp-90h] BYREF
  __int64 v144; // [rsp+78h] [rbp-88h] BYREF
  __int64 v145; // [rsp+80h] [rbp-80h] BYREF
  __int64 v146; // [rsp+88h] [rbp-78h] BYREF
  __int64 v147; // [rsp+90h] [rbp-70h] BYREF
  __int64 v148; // [rsp+98h] [rbp-68h] BYREF
  __int64 v149; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v150; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v151; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v152; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v153; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v154; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v155; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v156; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v157[3]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v158[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v159[3]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v160[3]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v161[3]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v162; // [rsp+158h] [rbp+58h] BYREF
  __int64 (__fastcall ***v163)(_QWORD, GUID *, __int64 *); // [rsp+160h] [rbp+60h] BYREF
  __int64 v164; // [rsp+168h] [rbp+68h] BYREF
  __int64 (__fastcall ***v165)(_QWORD, GUID *, __int64 *); // [rsp+170h] [rbp+70h] BYREF
  int v166; // [rsp+178h] [rbp+78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+180h] [rbp+80h] BYREF
  __int64 v168; // [rsp+198h] [rbp+98h]
  HSTRING_HEADER v169; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID *v170; // [rsp+1B8h] [rbp+B8h]
  HSTRING_HEADER v171; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v172; // [rsp+1D8h] [rbp+D8h]
  HSTRING_HEADER v173; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v174; // [rsp+1F8h] [rbp+F8h]
  HSTRING_HEADER v175; // [rsp+200h] [rbp+100h] BYREF
  GUID *v176; // [rsp+218h] [rbp+118h]
  HSTRING_HEADER v177; // [rsp+220h] [rbp+120h] BYREF
  __int64 v178; // [rsp+238h] [rbp+138h]
  HSTRING_HEADER v179; // [rsp+240h] [rbp+140h] BYREF
  __int64 v180; // [rsp+258h] [rbp+158h]
  HSTRING_HEADER v181; // [rsp+260h] [rbp+160h] BYREF
  __int64 v182; // [rsp+278h] [rbp+178h]
  HSTRING_HEADER v183; // [rsp+280h] [rbp+180h] BYREF
  __int64 v184; // [rsp+298h] [rbp+198h]
  HSTRING_HEADER v185; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v186; // [rsp+2B8h] [rbp+1B8h]
  HSTRING_HEADER v187; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v188; // [rsp+2D8h] [rbp+1D8h]
  HSTRING_HEADER v189; // [rsp+2E0h] [rbp+1E0h] BYREF
  GUID *v190; // [rsp+2F8h] [rbp+1F8h]
  HSTRING_HEADER v191; // [rsp+300h] [rbp+200h] BYREF
  GUID *v192; // [rsp+318h] [rbp+218h]
  HSTRING_HEADER v193; // [rsp+320h] [rbp+220h] BYREF
  __int64 v194; // [rsp+338h] [rbp+238h]
  HSTRING_HEADER v195; // [rsp+340h] [rbp+240h] BYREF
  __int64 v196; // [rsp+358h] [rbp+258h]
  HSTRING_HEADER v197; // [rsp+360h] [rbp+260h] BYREF
  __int64 v198; // [rsp+378h] [rbp+278h]
  HSTRING_HEADER v199; // [rsp+380h] [rbp+280h] BYREF
  __int64 v200; // [rsp+398h] [rbp+298h]
  HSTRING_HEADER v201; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v202; // [rsp+3B8h] [rbp+2B8h]
  HSTRING_HEADER v203; // [rsp+3C0h] [rbp+2C0h] BYREF
  GUID *v204; // [rsp+3D8h] [rbp+2D8h]
  HSTRING_HEADER v205; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int64 v206; // [rsp+3F8h] [rbp+2F8h]
  HSTRING_HEADER v207; // [rsp+400h] [rbp+300h] BYREF
  __int64 v208; // [rsp+418h] [rbp+318h]
  HSTRING_HEADER v209; // [rsp+420h] [rbp+320h] BYREF
  __int64 v210; // [rsp+438h] [rbp+338h]
  HSTRING_HEADER v211; // [rsp+440h] [rbp+340h] BYREF
  __int64 v212; // [rsp+458h] [rbp+358h]
  HSTRING_HEADER v213; // [rsp+460h] [rbp+360h] BYREF
  __int64 v214; // [rsp+478h] [rbp+378h]
  HSTRING_HEADER v215; // [rsp+480h] [rbp+380h] BYREF
  __int64 v216; // [rsp+498h] [rbp+398h]
  HSTRING_HEADER v217; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v218; // [rsp+4B8h] [rbp+3B8h]
  _BYTE v219[24]; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v220; // [rsp+4D8h] [rbp+3D8h]
  _BYTE v221[24]; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v222; // [rsp+4F8h] [rbp+3F8h]
  _BYTE v223[24]; // [rsp+500h] [rbp+400h] BYREF
  __int64 v224; // [rsp+518h] [rbp+418h]
  _BYTE v225[24]; // [rsp+520h] [rbp+420h] BYREF
  __int64 v226; // [rsp+538h] [rbp+438h]
  _BYTE v227[24]; // [rsp+540h] [rbp+440h] BYREF
  __int64 v228; // [rsp+558h] [rbp+458h]
  _BYTE v229[24]; // [rsp+560h] [rbp+460h] BYREF
  __int64 v230; // [rsp+578h] [rbp+478h]
  _BYTE v231[24]; // [rsp+580h] [rbp+480h] BYREF
  __int64 v232; // [rsp+598h] [rbp+498h]
  _BYTE v233[24]; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v234; // [rsp+5B8h] [rbp+4B8h]
  _BYTE v235[24]; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int64 v236; // [rsp+5D8h] [rbp+4D8h]
  _BYTE v237[24]; // [rsp+5E0h] [rbp+4E0h] BYREF
  __int64 v238; // [rsp+5F8h] [rbp+4F8h]
  _BYTE v239[24]; // [rsp+600h] [rbp+500h] BYREF
  __int64 v240; // [rsp+618h] [rbp+518h]
  _BYTE v241[24]; // [rsp+620h] [rbp+520h] BYREF
  __int64 v242; // [rsp+638h] [rbp+538h]
  _BYTE v243[24]; // [rsp+640h] [rbp+540h] BYREF
  __int64 v244; // [rsp+658h] [rbp+558h]
  wil::details::in1diag3 *retaddr; // [rsp+6A8h] [rbp+5A8h]

  if ( !a2 )
    return 2147942487LL;
  v165 = 0;
  v168 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Notifications.ToastNotificationManager",
    0x32u,
    0x31u);
  v5 = v168;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v165);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v165);
  v7 = ActivationFactory;
  v168 = 0;
  if ( ActivationFactory >= 0 )
  {
    v137 = 0;
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v165;
    v9 = **v165;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v137);
    v10 = v9(v8, &GUID_8f993fd3_e516_45fb_8130_398e93fa52c3, &v137);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
        (const char *)(unsigned int)v10,
        v134);
LABEL_7:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v137);
      goto LABEL_135;
    }
    v138 = 0;
    v11 = v137;
    v12 = *(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, __int64 *))(*(_QWORD *)v137 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v138);
    v13 = v12(v11, a1, &v138);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
        (const char *)(unsigned int)v13,
        v134);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v138);
      goto LABEL_7;
    }
    v139 = 0;
    v14 = v138;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v138 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v139);
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v219, a2);
    v17 = v15(v14, *(_QWORD *)(v16 + 24), &v139);
    v7 = v17;
    v220 = 0;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
        (const char *)(unsigned int)v17,
        v134);
LABEL_13:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v139);
      goto LABEL_10;
    }
    v135 = 0;
    v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v165;
    v19 = (*v165)[8];
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v135);
    v20 = v19(v18, (GUID *)5, (__int64 *)&v135);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
        (const char *)(unsigned int)v20,
        v134);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v135);
      goto LABEL_13;
    }
    v140 = 0;
    v142 = 0;
    v141 = 0;
    v166 = 0;
    v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
    v22 = (*v135)[16];
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v140);
    v170 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v169, L"binding", 8u, 7u);
    v23 = v22(v21, v170, &v140);
    v7 = v23;
    v170 = 0;
    if ( v23 < 0 )
    {
      v24 = 63;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
        (const char *)(unsigned int)v23,
        v134);
LABEL_20:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v141);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v142);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v140);
      goto LABEL_16;
    }
    v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v140 + 48LL))(v140, &v166);
    v7 = v23;
    if ( v23 < 0 )
    {
      v24 = 64;
      goto LABEL_19;
    }
    v25 = v140;
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v140 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v142);
    v23 = v26(v25, 0, &v142);
    v7 = v23;
    if ( v23 < 0 )
    {
      v24 = 65;
      goto LABEL_19;
    }
    v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v142;
    v28 = **v142;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v141);
    v23 = v28(v27, &GUID_2dfb8a1f_6b10_4ef8_9f83_efcce8faec37, &v141);
    v7 = v23;
    if ( v23 < 0 )
    {
      v24 = 66;
      goto LABEL_19;
    }
    v29 = v141;
    v30 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v141 + 64LL);
    v174 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v173, L"ToastGeneric", 0xDu, 0xCu);
    v31 = v174;
    v172 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v171, L"template", 9u, 8u);
    v23 = v30(v29, v172, v31);
    v7 = v23;
    v172 = 0;
    v174 = 0;
    if ( v23 < 0 )
    {
      v24 = 67;
      goto LABEL_19;
    }
    v150 = 0;
    v144 = 0;
    v143 = 0;
    v146 = 0;
    v149 = 0;
    v151 = 0;
    v154 = 0;
    v136 = 0;
    v148 = 0;
    v147 = 0;
    v145 = 0;
    v153 = 0;
    memset(v161, 0, sizeof(v161));
    memset(v160, 0, sizeof(v160));
    v32 = 0;
    memset(v159, 0, sizeof(v159));
    v33 = 0;
    memset(v158, 0, sizeof(v158));
    memset(v157, 0, sizeof(v157));
    v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
    v35 = (*v135)[16];
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v150);
    v176 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v175, L"text", 5u, 4u);
    v36 = v35(v34, v176, &v150);
    v7 = v36;
    v176 = 0;
    if ( v36 < 0 )
    {
      v37 = 91;
LABEL_31:
      v38 = (unsigned int)v36;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
        (const char *)v38,
        v134);
LABEL_33:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v157);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v158);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v159);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v160);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v161);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v153);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v147);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v148);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v136);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v154);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v151);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v149);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v146);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v143);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v150);
      goto LABEL_20;
    }
    v39 = v150;
    v40 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v150 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
    v36 = v40(v39, 0, &v144);
    v7 = v36;
    if ( v36 < 0 )
    {
      v37 = 92;
      goto LABEL_31;
    }
    v41 = *((_DWORD *)a2 + 2);
    ModuleHandleW = GetModuleHandleW(L"storsvc.dll");
    v43 = -2147467259;
    v44 = -2147467259;
    v156 = 0;
    v152 = 0;
    if ( Windows::Internal::ResourceString::FindAndSize(
           ModuleHandleW,
           v41,
           v45,
           (const unsigned __int16 **)&v156,
           &v152)
      && (v44 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  v161,
                  v156,
                  v152),
          v44 >= 0) )
    {
      v46 = *((_DWORD *)a2 + 3);
      v47 = GetModuleHandleW(L"storsvc.dll");
      v44 = -2147467259;
      v156 = 0;
      v152 = 0;
      if ( Windows::Internal::ResourceString::FindAndSize(v47, v46, v48, (const unsigned __int16 **)&v156, &v152) )
      {
        v44 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v160,
                v156,
                v152);
        if ( v44 >= 0 )
        {
          v36 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  v157,
                  *((_QWORD *)a2 + 6),
                  -1);
          v7 = v36;
          if ( v36 < 0 )
          {
            v37 = 96;
            goto LABEL_31;
          }
          v49 = *((_DWORD *)a2 + 4);
          if ( v49 )
          {
            v50 = GetModuleHandleW(L"storsvc.dll");
            v7 = -2147467259;
            v156 = 0;
            v152 = 0;
            if ( !Windows::Internal::ResourceString::FindAndSize(v50, v49, v51, (const unsigned __int16 **)&v156, &v152)
              || (v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                         v159,
                         v156,
                         v152),
                  v7 < 0) )
            {
              v38 = (unsigned int)v7;
              v37 = 100;
              goto LABEL_32;
            }
            v32 = (unsigned __int16 *)v159[0];
          }
          v52 = *((_DWORD *)a2 + 8);
          if ( v52 )
          {
            v53 = GetModuleHandleW(L"storsvc.dll");
            v156 = 0;
            v152 = 0;
            if ( !Windows::Internal::ResourceString::FindAndSize(v53, v52, v54, (const unsigned __int16 **)&v156, &v152)
              || (v43 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                          v158,
                          v156,
                          v152),
                  v43 < 0) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x69,
                (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
                (const char *)(unsigned int)v43,
                v134);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v157);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v158);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v159);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v160);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v161);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v153);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v147);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v148);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v136);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v154);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v151);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v149);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v146);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v143);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v150);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v141);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v142);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v140);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v135);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v139);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v138);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v137);
              v7 = v43;
              goto LABEL_135;
            }
            v33 = (unsigned __int16 *)v158[0];
          }
          v55 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
          v56 = (*v135)[11];
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v143);
          v156 = (unsigned __int16 *)v161[0];
          v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v221, &v156);
          v36 = v56(v55, *(GUID **)(v57 + 24), &v143);
          v7 = v36;
          v222 = 0;
          if ( v36 < 0 )
          {
            v37 = 108;
            goto LABEL_31;
          }
          v36 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                  &v143,
                  &v146);
          v7 = v36;
          if ( v36 < 0 )
          {
            v37 = 109;
            goto LABEL_31;
          }
          v58 = v144;
          v59 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v144 + 176LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v149);
          v36 = v59(v58, v146, &v149);
          v7 = v36;
          if ( v36 < 0 )
          {
            v37 = 110;
            goto LABEL_31;
          }
          v60 = v150;
          v61 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v150 + 56LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
          v36 = v61(v60, 1, &v144);
          v7 = v36;
          if ( v36 < 0 )
          {
            v37 = 112;
            goto LABEL_31;
          }
          v62 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
          v63 = (*v135)[11];
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v143);
          v156 = (unsigned __int16 *)v160[0];
          v64 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v223, &v156);
          v36 = v63(v62, *(GUID **)(v64 + 24), &v143);
          v7 = v36;
          v224 = 0;
          if ( v36 < 0 )
          {
            v37 = 113;
            goto LABEL_31;
          }
          v36 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                  &v143,
                  &v146);
          v7 = v36;
          if ( v36 < 0 )
          {
            v37 = 114;
            goto LABEL_31;
          }
          v65 = v144;
          v66 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v144 + 176LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v149);
          v36 = v66(v65, v146, &v149);
          v7 = v36;
          if ( v36 < 0 )
          {
            v37 = 115;
            goto LABEL_31;
          }
          v155 = 0;
          v67 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
          v68 = (*v135)[8];
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v155);
          v69 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v68)(v67, &v155);
          v7 = v69;
          if ( v69 >= 0 )
          {
            v71 = v155;
            v72 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v155 + 64LL);
            v180 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v179, L"long", 5u, 4u);
            v73 = v180;
            v178 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v177, L"duration", 9u, 8u);
            v69 = v72(v71, v178, v73);
            v7 = v69;
            v178 = 0;
            v180 = 0;
            if ( v69 >= 0 )
            {
              v74 = v155;
              v75 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v155 + 64LL);
              v156 = (unsigned __int16 *)v157[0];
              v76 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v225, &v156) + 24);
              v182 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v181, L"hint-toastId", 0xDu, 0xCu);
              v69 = v75(v74, v182, v76);
              v7 = v69;
              v182 = 0;
              v226 = 0;
              if ( v69 >= 0 )
              {
                v77 = v155;
                v78 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v155 + 64LL);
                v79 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v227, (char *)a2 + 64)
                                + 24);
                v184 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v183, L"launch", 7u, 6u);
                v69 = v78(v77, v184, v79);
                v7 = v69;
                v184 = 0;
                v228 = 0;
                if ( v69 >= 0 )
                {
                  v80 = v155;
                  v81 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v155 + 64LL);
                  v82 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v229, (char *)a2 + 72)
                                  + 24);
                  v186 = 0;
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v185, L"activationType", 0xFu, 0xEu);
                  v69 = v81(v80, v186, v82);
                  v7 = v69;
                  v186 = 0;
                  v230 = 0;
                  if ( v69 >= 0 )
                  {
                    if ( *((_DWORD *)a2 + 4) && *((_DWORD *)a2 + 8) )
                    {
                      v83 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
                      v84 = **v135;
                      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v151);
                      v69 = v84(v83, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v151);
                      v7 = v69;
                      if ( v69 < 0 )
                      {
                        v70 = 132;
                        goto LABEL_68;
                      }
                      v85 = v151;
                      v86 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v151 + 48LL);
                      v188 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v187, L"/toast", 7u, 6u);
                      v69 = v86(v85, v188, &v153);
                      v7 = v69;
                      v188 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 133;
                        goto LABEL_68;
                      }
                      v87 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
                      v88 = (*v135)[9];
                      v190 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v189, L"actions", 8u, 7u);
                      v69 = v88(v87, v190, &v154);
                      v7 = v69;
                      v190 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 136;
                        goto LABEL_68;
                      }
                      v69 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                              &v154,
                              &v148);
                      v7 = v69;
                      if ( v69 < 0 )
                      {
                        v70 = 137;
                        goto LABEL_68;
                      }
                      v69 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v153 + 176LL))(
                              v153,
                              v148,
                              &v145);
                      v7 = v69;
                      if ( v69 < 0 )
                      {
                        v70 = 138;
                        goto LABEL_68;
                      }
                      v89 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
                      v90 = (*v135)[9];
                      v192 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v191, L"action", 7u, 6u);
                      v69 = v90(v89, v192, &v136);
                      v7 = v69;
                      v192 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 141;
                        goto LABEL_68;
                      }
                      v69 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                              &v136,
                              &v147);
                      v7 = v69;
                      if ( v69 < 0 )
                      {
                        v70 = 142;
                        goto LABEL_68;
                      }
                      v91 = v148;
                      v92 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v148 + 176LL);
                      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
                      v69 = v92(v91, v147, &v145);
                      v7 = v69;
                      if ( v69 < 0 )
                      {
                        v70 = 143;
                        goto LABEL_68;
                      }
                      v93 = v136;
                      v94 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v156 = v32;
                      v95 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v231, &v156) + 24);
                      v194 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v193, L"content", 8u, 7u);
                      v69 = v94(v93, v194, v95);
                      v7 = v69;
                      v194 = 0;
                      v232 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 144;
                        goto LABEL_68;
                      }
                      v96 = v136;
                      v97 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v198 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v197, L"Foreground", 0xBu, 0xAu);
                      v98 = v198;
                      v196 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v195, L"activationType", 0xFu, 0xEu);
                      v69 = v97(v96, v196, v98);
                      v7 = v69;
                      v196 = 0;
                      v198 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 145;
                        goto LABEL_68;
                      }
                      v99 = v136;
                      v100 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v101 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                           v233,
                                           (char *)a2 + 24)
                                       + 24);
                      v200 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v199, L"arguments", 0xAu, 9u);
                      v69 = v100(v99, v200, v101);
                      v7 = v69;
                      v200 = 0;
                      v234 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 146;
                        goto LABEL_68;
                      }
                      v102 = v136;
                      v103 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v104 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                           v235,
                                           (char *)a2 + 24)
                                       + 24);
                      v202 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v201, L"hint-actionId", 0xEu, 0xDu);
                      v69 = v103(v102, v202, v104);
                      v7 = v69;
                      v202 = 0;
                      v236 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 147;
                        goto LABEL_68;
                      }
                      v105 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v135;
                      v106 = (*v135)[9];
                      v204 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v203, L"action", 7u, 6u);
                      v69 = v106(v105, v204, &v136);
                      v7 = v69;
                      v204 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 150;
                        goto LABEL_68;
                      }
                      v69 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                              &v136,
                              &v147);
                      v7 = v69;
                      if ( v69 < 0 )
                      {
                        v70 = 151;
                        goto LABEL_68;
                      }
                      v107 = v148;
                      v108 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v148 + 176LL);
                      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
                      v69 = v108(v107, v147, &v145);
                      v7 = v69;
                      if ( v69 < 0 )
                      {
                        v70 = 152;
                        goto LABEL_68;
                      }
                      v109 = v136;
                      v110 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v156 = v33;
                      v111 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v237, &v156) + 24);
                      v206 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v205, L"content", 8u, 7u);
                      v69 = v110(v109, v206, v111);
                      v7 = v69;
                      v206 = 0;
                      v238 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 153;
                        goto LABEL_68;
                      }
                      v112 = v136;
                      v113 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v210 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v209, L"Foreground", 0xBu, 0xAu);
                      v114 = v210;
                      v208 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v207, L"activationType", 0xFu, 0xEu);
                      v69 = v113(v112, v208, v114);
                      v7 = v69;
                      v208 = 0;
                      v210 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 155;
                        goto LABEL_68;
                      }
                      v115 = v136;
                      v116 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v117 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                           v239,
                                           (char *)a2 + 40)
                                       + 24);
                      v212 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v211, L"arguments", 0xAu, 9u);
                      v69 = v116(v115, v212, v117);
                      v7 = v69;
                      v212 = 0;
                      v240 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 156;
                        goto LABEL_68;
                      }
                      v118 = v136;
                      v119 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 64LL);
                      v120 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                           v241,
                                           (char *)a2 + 40)
                                       + 24);
                      v214 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v213, L"hint-actionId", 0xEu, 0xDu);
                      v69 = v119(v118, v214, v120);
                      v7 = v69;
                      v214 = 0;
                      v242 = 0;
                      if ( v69 < 0 )
                      {
                        v70 = 157;
                        goto LABEL_68;
                      }
                    }
                    v164 = 0;
                    v163 = 0;
                    v162 = 0;
                    v216 = 0;
                    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                      &v215,
                      L"Windows.UI.Notifications.ToastNotification",
                      0x2Bu,
                      0x2Au);
                    v121 = v216;
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v164);
                    v122 = RoGetActivationFactory(v121, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v164);
                    v7 = v122;
                    v216 = 0;
                    if ( v122 >= 0 )
                    {
                      v124 = v164;
                      v125 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v164 + 48LL);
                      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v163);
                      v122 = v125(v124, v135, &v163);
                      v7 = v122;
                      if ( v122 >= 0 )
                      {
                        v126 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v163;
                        v127 = **v163;
                        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v162);
                        v122 = v127(v126, &GUID_9dfb9fd1_143a_490e_90bf_b9fba7132de7, &v162);
                        v7 = v122;
                        if ( v122 >= 0 )
                        {
                          v128 = v162;
                          v129 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v162 + 64LL);
                          v218 = 0;
                          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v217, L"MSStorGroup", 0xCu, 0xBu);
                          v122 = v129(v128, v218);
                          v7 = v122;
                          v218 = 0;
                          if ( v122 >= 0 )
                          {
                            v130 = v162;
                            v131 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v162 + 48LL);
                            v132 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v243, (char *)a2 + 56);
                            v122 = v131(v130, *(_QWORD *)(v132 + 24));
                            v7 = v122;
                            v244 = 0;
                            if ( v122 >= 0 )
                            {
                              v122 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v139 + 48LL))(
                                       v139,
                                       v163);
                              v7 = v122;
                              if ( v122 >= 0 )
                              {
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v162);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v163);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v164);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v155);
                                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v157);
                                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v158);
                                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v159);
                                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v160);
                                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v161);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v153);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v147);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v148);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v136);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v154);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v151);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v149);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v146);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v143);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v150);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v141);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v142);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v140);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v135);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v139);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v138);
                                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v137);
                                v7 = 0;
                                goto LABEL_135;
                              }
                              v123 = 176;
                            }
                            else
                            {
                              v123 = 173;
                            }
                          }
                          else
                          {
                            v123 = 172;
                          }
                        }
                        else
                        {
                          v123 = 171;
                        }
                      }
                      else
                      {
                        v123 = 168;
                      }
                    }
                    else
                    {
                      v123 = 167;
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v123,
                      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
                      (const char *)(unsigned int)v122,
                      v134);
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v162);
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v163);
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v164);
                    goto LABEL_69;
                  }
                  v70 = 125;
                }
                else
                {
                  v70 = 124;
                }
              }
              else
              {
                v70 = 121;
              }
            }
            else
            {
              v70 = 120;
            }
          }
          else
          {
            v70 = 119;
          }
LABEL_68:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v70,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
            (const char *)(unsigned int)v69,
            v134);
LABEL_69:
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v155);
          goto LABEL_33;
        }
      }
      v133 = 95;
    }
    else
    {
      v133 = 94;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v133,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
      (const char *)(unsigned int)v44,
      v134);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v157);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v158);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v159);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v160);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v161);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v153);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v147);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v148);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v154);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v151);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v149);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v146);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v143);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v150);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v141);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v142);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v140);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v135);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v139);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v138);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v137);
    v7 = v44;
    goto LABEL_135;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x27,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagenotification.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v134);
LABEL_135:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v165);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003584c  mov     [rsp-8+arg_10], rbx
0x180035851  push    rbp
0x180035852  push    rsi
0x180035853  push    rdi
0x180035854  push    r12
0x180035856  push    r13
0x180035858  push    r14
0x18003585a  push    r15
0x18003585c  lea     rbp, [rsp-570h]
0x180035864  sub     rsp, 670h
0x18003586b  mov     rax, cs:__security_cookie
0x180035872  xor     rax, rsp
0x180035875  mov     [rbp+5A0h+var_40], rax
0x18003587c  mov     r14, rdx
0x18003587f  mov     rsi, rcx
0x180035882  xor     r13d, r13d
0x180035885  test    rdx, rdx
0x180035888  jnz     short loc_180035894
0x18003588a  mov     eax, 80070057h
0x18003588f  jmp     loc_180036FE7
0x180035894  mov     [rbp+5A0h+var_530], r13
0x180035898  mov     [rbp+5A0h+var_508], r13
0x18003589f  mov     r9d, 31h ; '1'; unsigned int
0x1800358a5  lea     r8d, [r9+1]; unsigned int
0x1800358a9  lea     rdx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x1800358b0  lea     rcx, [rbp+5A0h+hstringHeader]; hstringHeader
0x1800358b7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800358bc  nop
0x1800358bd  mov     rbx, [rbp+5A0h+var_508]
0x1800358c4  lea     rcx, [rbp+5A0h+var_530]
0x1800358c8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800358cd  lea     r8, [rbp+5A0h+var_530]
0x1800358d1  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x1800358d8  mov     rcx, rbx
0x1800358db  call    cs:__imp_RoGetActivationFactory
0x1800358e1  mov     ebx, eax
0x1800358e3  mov     [rbp+5A0h+var_508], r13
0x1800358ea  test    eax, eax
0x1800358ec  jns     short loc_18003590E
0x1800358ee  mov     rcx, [rbp+5A8h]; this
0x1800358f5  mov     r9d, eax; char *
0x1800358f8  lea     r8, aOnecoreDrivers_24; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800358ff  mov     edx, 27h ; '''; void *
0x180035904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035909  jmp     loc_180036FDC
0x18003590e  mov     [rsp+6A0h+var_660], r13
0x180035913  mov     rdi, [rbp+5A0h+var_530]
0x180035917  mov     rax, [rdi]
0x18003591a  mov     rbx, [rax]
0x18003591d  lea     rcx, [rsp+6A0h+var_660]
0x180035922  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035927  lea     r8, [rsp+6A0h+var_660]
0x18003592c  lea     rdx, _GUID_8f993fd3_e516_45fb_8130_398e93fa52c3
0x180035933  mov     rcx, rdi
0x180035936  mov     rax, rbx
0x180035939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003593e  mov     ebx, eax
0x180035940  test    eax, eax
0x180035942  jns     short loc_18003596F
0x180035944  mov     rcx, [rbp+5A8h]; this
0x18003594b  mov     r9d, eax; char *
0x18003594e  lea     r8, aOnecoreDrivers_24; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180035955  mov     edx, 2Ah ; '*'; void *
0x18003595a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003595f  nop
0x180035960  lea     rcx, [rsp+6A0h+var_660]
0x180035965  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003596a  jmp     loc_180036FDC
0x18003596f  mov     [rsp+6A0h+var_658], r13
0x180035974  mov     rdi, [rsp+6A0h+var_660]
0x180035979  mov     rax, [rdi]
0x18003597c  mov     rbx, [rax+30h]
0x180035980  lea     rcx, [rsp+6A0h+var_658]
0x180035985  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003598a  lea     r8, [rsp+6A0h+var_658]
0x18003598f  mov     rdx, rsi
0x180035992  mov     rcx, rdi
0x180035995  mov     rax, rbx
0x180035998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003599d  mov     ebx, eax
0x18003599f  test    eax, eax
0x1800359a1  jns     short loc_1800359CB
0x1800359a3  mov     rcx, [rbp+5A8h]; this
0x1800359aa  mov     r9d, eax; char *
0x1800359ad  lea     r8, aOnecoreDrivers_24; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800359b4  mov     edx, 2Dh ; '-'; void *
0x1800359b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800359be  nop
0x1800359bf  lea     rcx, [rsp+6A0h+var_658]
0x1800359c4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800359c9  jmp     short loc_180035960
0x1800359cb  mov     [rsp+6A0h+var_650], r13
0x1800359d0  mov     rdi, [rsp+6A0h+var_658]
0x1800359d5  mov     rax, [rdi]
0x1800359d8  mov     rbx, [rax+38h]
0x1800359dc  lea     rcx, [rsp+6A0h+var_650]
0x1800359e1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800359e6  mov     rdx, r14
0x1800359e9  lea     rcx, [rbp+5A0h+var_1E0]
0x1800359f0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800359f5  nop
0x1800359f6  lea     r8, [rsp+6A0h+var_650]
0x1800359fb  mov     rdx, [rax+18h]
0x1800359ff  mov     rcx, rdi
0x180035a02  mov     rax, rbx
0x180035a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a0a  mov     ebx, eax
0x180035a0c  mov     [rbp+5A0h+var_1C8], r13
0x180035a13  test    eax, eax
0x180035a15  jns     short loc_180035A3F
0x180035a17  mov     rcx, [rbp+5A8h]; this
0x180035a1e  mov     r9d, eax; char *
0x180035a21  lea     r8, aOnecoreDrivers_24; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180035a28  mov     edx, 33h ; '3'; void *
0x180035a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a32  nop
0x180035a33  lea     rcx, [rsp+6A0h+var_650]
0x180035a38  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035a3d  jmp     short loc_1800359BF
0x180035a3f  mov     [rsp+6A0h+var_670], r13
0x180035a44  mov     rdi, [rbp+5A0h+var_530]
0x180035a48  mov     rax, [rdi]
0x180035a4b  mov     rbx, [rax+40h]
0x180035a4f  lea     rcx, [rsp+6A0h+var_670]
0x180035a54  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035a59  lea     r8, [rsp+6A0h+var_670]
0x180035a5e  mov     edx, 5
0x180035a63  mov     rcx, rdi
0x180035a66  mov     rax, rbx
0x180035a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a6e  mov     ebx, eax
0x180035a70  test    eax, eax
0x180035a72  jns     short loc_180035A9C
0x180035a74  mov     rcx, [rbp+5A8h]; this
0x180035a7b  mov     r9d, eax; char *
0x180035a7e  lea     r8, aOnecoreDrivers_24; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180035a85  mov     edx, 37h ; '7'; void *
0x180035a8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a8f  nop
0x180035a90  lea     rcx, [rsp+6A0h+var_670]
0x180035a95  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035a9a  jmp     short loc_180035A33
0x180035a9c  mov     [rsp+6A0h+var_648], r13
0x180035aa1  mov     [rsp+6A0h+var_638], r13
0x180035aa6  mov     [rsp+6A0h+var_640], r13
0x180035aab  mov     [rbp+5A0h+var_528], r13d
0x180035aaf  mov     rdi, [rsp+6A0h+var_670]
0x180035ab4  mov     rax, [rdi]
0x180035ab7  mov     rbx, [rax+80h]
0x180035abe  lea     rcx, [rsp+6A0h+var_648]
0x180035ac3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035ac8  mov     [rbp+5A0h+var_4E8], r13
0x180035acf  mov     r9d, 7; unsigned int
0x180035ad5  lea     r15d, [r9+1]
0x180035ad9  mov     r8d, r15d; unsigned int
0x180035adc  lea     rdx, aBinding; "binding"
0x180035ae3  lea     rcx, [rbp+5A0h+var_500]; hstringHeader
0x180035aea  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180035aef  nop
0x180035af0  lea     r8, [rsp+6A0h+var_648]
0x180035af5  mov     rdx, [rbp+5A0h+var_4E8]
0x180035afc  mov     rcx, rdi
0x180035aff  mov     rax, rbx
0x180035b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b07  mov     ebx, eax
0x180035b09  mov     [rbp+5A0h+var_4E8], r13
0x180035b10  test    eax, eax
0x180035b12  jns     short loc_180035B54
0x180035b14  lea     edx, [r15+37h]; void *
0x180035b18  mov     rcx, [rbp+5A8h]; this
0x180035b1f  mov     r9d, eax; char *
0x180035b22  lea     r8, aOnecoreDrivers_24; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180035b29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b2e  nop
0x180035b2f  lea     rcx, [rsp+6A0h+var_640]
0x180035b34  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035b39  nop
0x180035b3a  lea     rcx, [rsp+6A0h+var_638]
0x180035b3f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035b44  nop
0x180035b45  lea     rcx, [rsp+6A0h+var_648]
0x180035b4a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035b4f  jmp     loc_180035A90
0x180035b54  mov     rcx, [rsp+6A0h+var_648]
0x180035b59  mov     rax, [rcx]
0x180035b5c  lea     rdx, [rbp+5A0h+var_528]
0x180035b60  mov     rax, [rax+30h]
0x180035b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b69  mov     ebx, eax
0x180035b6b  test    eax, eax
0x180035b6d  jns     short loc_180035B76
0x180035b6f  mov     edx, 40h ; '@'
0x180035b74  jmp     short loc_180035B18
0x180035b76  mov     rdi, [rsp+6A0h+var_648]
0x180035b7b  mov     rax, [rdi]
0x180035b7e  mov     rbx, [rax+38h]
0x180035b82  lea     rcx, [rsp+6A0h+var_638]
0x180035b87  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035b8c  lea     r8, [rsp+6A0h+var_638]
0x180035b91  xor     edx, edx
0x180035b93  mov     rcx, rdi
0x180035b96  mov     rax, rbx
0x180035b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b9e  mov     ebx, eax
0x180035ba0  test    eax, eax
0x180035ba2  jns     short loc_180035BAE
0x180035ba4  mov     edx, 41h ; 'A'
0x180035ba9  jmp     loc_180035B18
0x180035bae  mov     rbx, [rsp+6A0h+var_638]
0x180035bb3  mov     rax, [rbx]
0x180035bb6  mov     rdi, [rax]
0x180035bb9  lea     rcx, [rsp+6A0h+var_640]
0x180035bbe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035bc3  lea     r8, [rsp+6A0h+var_640]
0x180035bc8  lea     rdx, _GUID_2dfb8a1f_6b10_4ef8_9f83_efcce8faec37
0x180035bcf  mov     rcx, rbx
0x180035bd2  mov     rax, rdi
0x180035bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bda  mov     ebx, eax
0x180035bdc  test    eax, eax
0x180035bde  jns     short loc_180035BEA
0x180035be0  mov     edx, 42h ; 'B'
0x180035be5  jmp     loc_180035B18
0x180035bea  mov     rsi, [rsp+6A0h+var_640]
0x180035bef  mov     rax, [rsi]
0x180035bf2  mov     rdi, [rax+40h]
0x180035bf6  mov     [rbp+5A0h+var_4A8], r13
0x180035bfd  mov     r9d, 0Ch; unsigned int
0x180035c03  lea     r8d, [r9+1]; unsigned int
0x180035c07  lea     rdx, aToastgeneric; "ToastGeneric"
0x180035c0e  lea     rcx, [rbp+5A0h+var_4C0]; hstringHeader
0x180035c15  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180035c1a  nop
0x180035c1b  mov     rbx, [rbp+5A0h+var_4A8]
0x180035c22  mov     [rbp+5A0h+var_4C8], r13
0x180035c29  mov     r9d, r15d; unsigned int
0x180035c2c  mov     r8d, 9; unsigned int
0x180035c32  lea     rdx, aTemplate; "template"
0x180035c39  lea     rcx, [rbp+5A0h+var_4E0]; hstringHeader
0x180035c40  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180035c45  nop
0x180035c46  mov     r8, rbx
0x180035c49  mov     rdx, [rbp+5A0h+var_4C8]
0x180035c50  mov     rcx, rsi
0x180035c53  mov     rax, rdi
0x180035c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c5b  mov     ebx, eax
0x180035c5d  mov     [rbp+5A0h+var_4C8], r13
0x180035c64  mov     [rbp+5A0h+var_4A8], r13
0x180035c6b  test    eax, eax
0x180035c6d  jns     short loc_180035C79
0x180035c6f  mov     edx, 43h ; 'C'
0x180035c74  jmp     loc_180035B18
0x180035c79  mov     [rbp+5A0h+var_5F8], r13
0x180035c7d  mov     [rsp+6A0h+var_628], r13
0x180035c82  mov     [rsp+6A0h+var_630], r13
0x180035c87  mov     [rbp+5A0h+var_618], r13
0x180035c8b  mov     [rbp+5A0h+var_600], r13
0x180035c8f  mov     [rbp+5A0h+var_5F0], r13
0x180035c93  mov     [rbp+5A0h+var_5D8], r13
0x180035c97  mov     [rsp+6A0h+var_668], r13
0x180035c9c  mov     [rbp+5A0h+var_608], r13
0x180035ca0  mov     [rbp+5A0h+var_610], r13
0x180035ca4  mov     [rbp+5A0h+var_620], r13
0x180035ca8  mov     [rbp+5A0h+var_5E0], r13
0x180035cac  mov     [rbp+5A0h+var_560], r13
0x180035cb0  mov     [rbp+5A0h+var_558], r13
0x180035cb4  mov     [rbp+5A0h+var_550], r13
0x180035cb8  mov     [rbp+5A0h+var_578], r13
0x180035cbc  mov     [rbp+5A0h+var_570], r13
0x180035cc0  mov     [rbp+5A0h+var_568], r13
0x180035cc4  mov     r15, r13
0x180035cc7  mov     [rbp+5A0h+var_590], r13
0x180035ccb  mov     [rbp+5A0h+var_588], r13
0x180035ccf  mov     [rbp+5A0h+var_580], r13
0x180035cd3  mov     r12, r13
0x180035cd6  mov     [rbp+5A0h+var_5A8], r13
0x180035cda  mov     [rbp+5A0h+var_5A0], r13
0x180035cde  mov     [rbp+5A0h+var_598], r13
0x180035ce2  mov     [rbp+5A0h+var_5C0], r13
0x180035ce6  mov     [rbp+5A0h+var_5B8], r13
0x180035cea  mov     [rbp+5A0h+var_5B0], r13
0x180035cee  mov     rdi, [rsp+6A0h+var_670]
0x180035cf3  mov     rax, [rdi]
0x180035cf6  mov     rbx, [rax+80h]
0x180035cfd  lea     rcx, [rbp+5A0h+var_5F8]
0x180035d01  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035d06  mov     [rbp+5A0h+var_488], r13
0x180035d0d  mov     r9d, 4; unsigned int
0x180035d13  lea     r8d, [r9+1]; unsigned int
0x180035d17  lea     rdx, aText; "text"
0x180035d1e  lea     rcx, [rbp+5A0h+var_4A0]; hstringHeader
0x180035d25  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180035d2a  nop
0x180035d2b  lea     r8, [rbp+5A0h+var_5F8]
0x180035d2f  mov     rdx, [rbp+5A0h+var_488]
0x180035d36  mov     rcx, rdi
0x180035d39  mov     rax, rbx
0x180035d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d41  mov     ebx, eax
  ... truncated ...
```
