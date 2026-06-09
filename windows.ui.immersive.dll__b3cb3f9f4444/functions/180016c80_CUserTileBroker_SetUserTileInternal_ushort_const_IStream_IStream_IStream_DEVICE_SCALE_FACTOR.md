# CUserTileBroker::_SetUserTileInternal(ushort const *,IStream *,IStream *,IStream *,DEVICE_SCALE_FACTOR)

- ea: `0x180016c80`
- end: `0x18001754a`
- name: `?_SetUserTileInternal@CUserTileBroker@@AEAAJPEBGPEAUIStream@@11W4DEVICE_SCALE_FACTOR@@@Z`
- size: `2250`
- prototype: `__int64 __fastcall(CUserTileBroker *__hidden this, const unsigned __int16 *, struct IStream *, struct IStream *, struct IStream *, enum DEVICE_SCALE_FACTOR)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d1900`
- `0x1800d1930`

## callees

- `0x180016c80`
- `0x180018bf8`
- `0x1800343ec`
- `0x18003cf38`
- `0x18003ff34`
- `0x180040564`
- `0x180054130`
- `0x1800d1ae8`
- `0x1800d9530`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d30`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180016dca`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180016dca`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180016d8e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180016d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800174ea`

## string_xrefs

- `0x180016d4a`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180016e2e`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800174c2`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
__int64 __fastcall CUserTileBroker::_SetUserTileInternal(
        CUserTileBroker *this,
        const unsigned __int16 *a2,
        struct IStream *a3,
        struct IStream *a4,
        struct IStream *a5,
        enum DEVICE_SCALE_FACTOR a6)
{
  int inited; // edi
  int v10; // eax
  __int64 v11; // r9
  unsigned __int64 i; // rbx
  wil::details::in1diag3 *v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  unsigned __int64 j; // rsi
  __int64 v18; // rcx
  int DueTime; // [rsp+20h] [rbp-E0h]
  HANDLE *DueTimea; // [rsp+20h] [rbp-E0h]
  int v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  DWORD Parameter; // [rsp+60h] [rbp-A0h] BYREF
  char v27; // [rsp+64h] [rbp-9Ch]
  HRESULT v28; // [rsp+68h] [rbp-98h]
  void *phNewTimer; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  struct IStream *v31; // [rsp+88h] [rbp-78h]
  _QWORD v32[2]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A2h] [rbp-5Eh]
  __int16 v35; // [rsp+AAh] [rbp-56h]
  __int128 v36; // [rsp+ACh] [rbp-54h]
  __int128 v37; // [rsp+BCh] [rbp-44h]
  __int64 v38; // [rsp+CCh] [rbp-34h]
  LPVOID pv; // [rsp+D8h] [rbp-28h]
  int v40; // [rsp+E0h] [rbp-20h]
  int v41; // [rsp+E4h] [rbp-1Ch]
  struct IStream *v42; // [rsp+E8h] [rbp-18h]
  HANDLE v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  wchar_t v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+102h] [rbp+2h]
  __int16 v47; // [rsp+10Ah] [rbp+Ah]
  __int128 v48; // [rsp+10Ch] [rbp+Ch]
  wchar_t v49; // [rsp+11Ch] [rbp+1Ch]
  _BYTE v50[22]; // [rsp+11Eh] [rbp+1Eh] BYREF
  __int64 v51; // [rsp+138h] [rbp+38h]
  int v52; // [rsp+140h] [rbp+40h]
  int v53; // [rsp+144h] [rbp+44h]
  struct IStream *v54; // [rsp+148h] [rbp+48h]
  __int64 v55; // [rsp+150h] [rbp+50h]
  __int64 v56; // [rsp+158h] [rbp+58h]
  wchar_t v57; // [rsp+160h] [rbp+60h]
  __int64 v58; // [rsp+162h] [rbp+62h]
  __int16 v59; // [rsp+16Ah] [rbp+6Ah]
  __int128 v60; // [rsp+16Ch] [rbp+6Ch]
  wchar_t v61; // [rsp+17Ch] [rbp+7Ch]
  _BYTE v62[22]; // [rsp+17Eh] [rbp+7Eh] BYREF
  __int64 v63; // [rsp+198h] [rbp+98h]
  int v64; // [rsp+1A0h] [rbp+A0h]
  int v65; // [rsp+1A4h] [rbp+A4h]
  HANDLE v66; // [rsp+1A8h] [rbp+A8h]
  __int64 v67; // [rsp+1B0h] [rbp+B0h]
  __int64 v68; // [rsp+1B8h] [rbp+B8h]
  wchar_t v69; // [rsp+1C0h] [rbp+C0h]
  __int64 v70; // [rsp+1C2h] [rbp+C2h]
  __int16 v71; // [rsp+1CAh] [rbp+CAh]
  __int128 v72; // [rsp+1CCh] [rbp+CCh]
  __int128 v73; // [rsp+1DCh] [rbp+DCh]
  __int64 v74; // [rsp+1ECh] [rbp+ECh]
  __int64 v75; // [rsp+1F8h] [rbp+F8h]
  int v76; // [rsp+200h] [rbp+100h]
  int v77; // [rsp+204h] [rbp+104h]
  HANDLE v78; // [rsp+208h] [rbp+108h]
  __int64 v79; // [rsp+210h] [rbp+110h]
  __int64 v80; // [rsp+218h] [rbp+118h]
  wchar_t v81; // [rsp+220h] [rbp+120h]
  __int64 v82; // [rsp+222h] [rbp+122h]
  __int16 v83; // [rsp+22Ah] [rbp+12Ah]
  __int128 v84; // [rsp+22Ch] [rbp+12Ch]
  __int128 v85; // [rsp+23Ch] [rbp+13Ch]
  __int64 v86; // [rsp+24Ch] [rbp+14Ch]
  __int64 v87; // [rsp+258h] [rbp+158h]
  int v88; // [rsp+260h] [rbp+160h]
  int v89; // [rsp+264h] [rbp+164h]
  HANDLE v90; // [rsp+268h] [rbp+168h]
  __int64 v91; // [rsp+270h] [rbp+170h]
  __int64 v92; // [rsp+278h] [rbp+178h]
  wchar_t v93; // [rsp+280h] [rbp+180h]
  __int64 v94; // [rsp+282h] [rbp+182h]
  __int16 v95; // [rsp+28Ah] [rbp+18Ah]
  __int128 v96; // [rsp+28Ch] [rbp+18Ch]
  __int128 v97; // [rsp+29Ch] [rbp+19Ch]
  __int64 v98; // [rsp+2ACh] [rbp+1ACh]
  __int64 v99; // [rsp+2B8h] [rbp+1B8h]
  int v100; // [rsp+2C0h] [rbp+1C0h]
  int v101; // [rsp+2C4h] [rbp+1C4h]
  HANDLE v102; // [rsp+2C8h] [rbp+1C8h]
  __int64 v103; // [rsp+2D0h] [rbp+1D0h]
  __int64 v104; // [rsp+2D8h] [rbp+1D8h]
  wchar_t v105; // [rsp+2E0h] [rbp+1E0h]
  __int64 v106; // [rsp+2E2h] [rbp+1E2h]
  __int16 v107; // [rsp+2EAh] [rbp+1EAh]
  __int128 v108; // [rsp+2ECh] [rbp+1ECh]
  WCHAR v109; // [rsp+2FCh] [rbp+1FCh]
  _BYTE v110[22]; // [rsp+2FEh] [rbp+1FEh] BYREF
  __int64 v111; // [rsp+318h] [rbp+218h]
  int v112; // [rsp+320h] [rbp+220h]
  int v113; // [rsp+324h] [rbp+224h]
  struct IStream *v114; // [rsp+328h] [rbp+228h]
  __int64 v115; // [rsp+330h] [rbp+230h]
  __int64 v116; // [rsp+338h] [rbp+238h]
  wchar_t v117; // [rsp+340h] [rbp+240h]
  __int64 v118; // [rsp+342h] [rbp+242h]
  __int16 v119; // [rsp+34Ah] [rbp+24Ah]
  __int128 v120; // [rsp+34Ch] [rbp+24Ch]
  wchar_t v121; // [rsp+35Ch] [rbp+25Ch]
  _BYTE v122[22]; // [rsp+35Eh] [rbp+25Eh] BYREF
  __int64 v123; // [rsp+378h] [rbp+278h]
  int v124; // [rsp+380h] [rbp+280h]
  int v125; // [rsp+384h] [rbp+284h]
  HANDLE v126; // [rsp+388h] [rbp+288h]
  __int64 v127; // [rsp+390h] [rbp+290h]
  __int64 v128; // [rsp+398h] [rbp+298h]
  wchar_t v129; // [rsp+3A0h] [rbp+2A0h]
  __int64 v130; // [rsp+3A2h] [rbp+2A2h]
  __int16 v131; // [rsp+3AAh] [rbp+2AAh]
  __int128 v132; // [rsp+3ACh] [rbp+2ACh]
  wchar_t v133; // [rsp+3BCh] [rbp+2BCh]
  _BYTE v134[22]; // [rsp+3BEh] [rbp+2BEh] BYREF
  __int64 v135; // [rsp+3D8h] [rbp+2D8h]
  int v136; // [rsp+3E0h] [rbp+2E0h]
  int v137; // [rsp+3E4h] [rbp+2E4h]
  struct IStream *v138; // [rsp+3E8h] [rbp+2E8h]
  __int64 v139; // [rsp+3F0h] [rbp+2F0h]
  __int64 v140; // [rsp+3F8h] [rbp+2F8h]
  wchar_t v141; // [rsp+400h] [rbp+300h]
  __int64 v142; // [rsp+402h] [rbp+302h]
  __int16 v143; // [rsp+40Ah] [rbp+30Ah]
  __int128 v144; // [rsp+40Ch] [rbp+30Ch]
  wchar_t v145; // [rsp+41Ch] [rbp+31Ch]
  _BYTE v146[22]; // [rsp+41Eh] [rbp+31Eh] BYREF
  __int64 v147; // [rsp+438h] [rbp+338h]
  int v148; // [rsp+440h] [rbp+340h]
  int v149; // [rsp+444h] [rbp+344h]
  HANDLE v150; // [rsp+448h] [rbp+348h]
  __int64 v151; // [rsp+450h] [rbp+350h]
  __int64 v152; // [rsp+458h] [rbp+358h]
  wchar_t v153; // [rsp+460h] [rbp+360h]
  __int64 v154; // [rsp+462h] [rbp+362h]
  __int16 v155; // [rsp+46Ah] [rbp+36Ah]
  __int128 v156; // [rsp+46Ch] [rbp+36Ch]
  __int128 v157; // [rsp+47Ch] [rbp+37Ch]
  __int64 v158; // [rsp+48Ch] [rbp+38Ch]
  __int64 v159; // [rsp+498h] [rbp+398h]
  int v160; // [rsp+4A0h] [rbp+3A0h]
  int v161; // [rsp+4A4h] [rbp+3A4h]
  HANDLE v162; // [rsp+4A8h] [rbp+3A8h]
  __int64 v163; // [rsp+4B0h] [rbp+3B0h]
  __int64 v164; // [rsp+4B8h] [rbp+3B8h]
  wchar_t v165; // [rsp+4C0h] [rbp+3C0h]
  __int64 v166; // [rsp+4C2h] [rbp+3C2h]
  __int16 v167; // [rsp+4CAh] [rbp+3CAh]
  __int128 v168; // [rsp+4CCh] [rbp+3CCh]
  wchar_t v169; // [rsp+4DCh] [rbp+3DCh]
  _BYTE v170[22]; // [rsp+4DEh] [rbp+3DEh] BYREF
  __int64 v171; // [rsp+4F8h] [rbp+3F8h]
  int v172; // [rsp+500h] [rbp+400h]
  int v173; // [rsp+504h] [rbp+404h]
  HANDLE v174; // [rsp+508h] [rbp+408h]
  __int64 v175; // [rsp+510h] [rbp+410h]
  __int64 v176; // [rsp+518h] [rbp+418h]
  wchar_t v177; // [rsp+520h] [rbp+420h]
  __int64 v178; // [rsp+522h] [rbp+422h]
  __int16 v179; // [rsp+52Ah] [rbp+42Ah]
  __int128 v180; // [rsp+52Ch] [rbp+42Ch]
  wchar_t v181; // [rsp+53Ch] [rbp+43Ch]
  _BYTE v182[22]; // [rsp+53Eh] [rbp+43Eh] BYREF
  __int64 v183; // [rsp+558h] [rbp+458h]
  int v184; // [rsp+560h] [rbp+460h]
  int v185; // [rsp+564h] [rbp+464h]
  HANDLE v186; // [rsp+568h] [rbp+468h]
  __int64 v187; // [rsp+570h] [rbp+470h]
  __int64 v188; // [rsp+578h] [rbp+478h]
  wchar_t v189; // [rsp+580h] [rbp+480h]
  __int64 v190; // [rsp+582h] [rbp+482h]
  __int16 v191; // [rsp+58Ah] [rbp+48Ah]
  __int128 v192; // [rsp+58Ch] [rbp+48Ch]
  int v193; // [rsp+59Ch] [rbp+49Ch]
  __int128 v194; // [rsp+5A0h] [rbp+4A0h]
  int v195; // [rsp+5B0h] [rbp+4B0h]
  __int64 v196; // [rsp+5B8h] [rbp+4B8h]
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+508h]

  *(_QWORD *)v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22);
  *(_QWORD *)v22 = 0;
  hObject = 0;
  v24 = 0;
  inited = _InitRestrictedProcess(&hObject, &v24);
  if ( inited >= 0 )
  {
    inited = CreateInstanceInProcess(hObject, v22);
    CloseHandle(hObject);
    CloseHandle(v24);
  }
  if ( inited < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)inited,
      DueTime);
    goto LABEL_23;
  }
  Parameter = GetCurrentThreadId();
  v27 = 0;
  v28 = -2147467259;
  phNewTimer = 0;
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
  v28 = CoEnableCallCancellation(0);
  if ( v28 >= 0 )
    CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x1D4C0u, 0x3E8u, 0);
  v24 = 0;
  hObject = 0;
  v25 = 0;
  DueTimea = &v24;
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, struct IStream *, struct IStream *))(**(_QWORD **)v22 + 24LL))(
          *(_QWORD *)v22,
          a3,
          a4,
          a5);
  inited = v10;
  if ( v10 >= 0 )
  {
    v30 = 96;
    v31 = a3;
    v32[0] = v24;
    v32[1] = *(_QWORD *)L".jpg";
    LODWORD(v11) = aJpg[4];
    v33 = aJpg[4];
    v34 = 0;
    v35 = 0;
    v36 = *(_OWORD *)L"Image96";
    v37 = 0;
    v38 = 0;
    pv = 0;
    v40 = 448;
    v41 = 1;
    v42 = a4;
    v43 = hObject;
    v44 = *(_QWORD *)L".jpg";
    v45 = aJpg[4];
    v46 = 0;
    v47 = 0;
    v48 = *(_OWORD *)L"Image448";
    v49 = aImage448[8];
    memset(v50, 0, sizeof(v50));
    v51 = 0;
    v52 = 448;
    v53 = 2;
    v54 = a5;
    v55 = v25;
    v56 = *(_QWORD *)L".mp4";
    v57 = aMp4[4];
    v58 = 0;
    v59 = 0;
    v60 = *(_OWORD *)L"Video448";
    v61 = aVideo448[8];
    memset(v62, 0, sizeof(v62));
    v63 = 0;
    v64 = 32;
    v65 = 4;
    v66 = v24;
    v67 = 0;
    v68 = *(_QWORD *)L".jpg";
    v69 = aJpg[4];
    v70 = 0;
    v71 = 0;
    v72 = *(_OWORD *)L"Image32";
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 40;
    v77 = 5;
    v78 = v24;
    v79 = 0;
    v80 = *(_QWORD *)L".jpg";
    v81 = aJpg[4];
    v82 = 0;
    v83 = 0;
    v84 = *(_OWORD *)L"Image40";
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 48;
    v89 = 6;
    v90 = v24;
    v91 = 0;
    v92 = *(_QWORD *)L".jpg";
    v93 = aJpg[4];
    v94 = 0;
    v95 = 0;
    v96 = *(_OWORD *)L"Image48";
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v100 = 192;
    v101 = 7;
    v102 = hObject;
    v103 = 0;
    v104 = *(_QWORD *)L".jpg";
    v105 = aJpg[4];
    v106 = 0;
    v107 = 0;
    v108 = *(_OWORD *)L"Image192";
    v109 = aImage192[8];
    memset(v110, 0, sizeof(v110));
    v111 = 0;
    v112 = 192;
    v113 = 8;
    v114 = a5;
    v115 = 0;
    v116 = *(_QWORD *)L".mp4";
    v117 = aMp4[4];
    v118 = 0;
    v119 = 0;
    v120 = *(_OWORD *)L"Video192";
    v121 = aVideo192[8];
    memset(v122, 0, sizeof(v122));
    v123 = 0;
    v124 = 240;
    v125 = 9;
    v126 = hObject;
    v127 = 0;
    v128 = *(_QWORD *)L".jpg";
    v129 = aJpg[4];
    v130 = 0;
    v131 = 0;
    v132 = *(_OWORD *)L"Image240";
    v133 = aImage240[8];
    memset(v134, 0, sizeof(v134));
    v135 = 0;
    v136 = 240;
    v137 = 10;
    v138 = a5;
    v139 = 0;
    v140 = *(_QWORD *)L".mp4";
    v141 = aMp4[4];
    v142 = 0;
    v143 = 0;
    v144 = *(_OWORD *)L"Video240";
    v145 = aVideo240[8];
    memset(v146, 0, sizeof(v146));
    v147 = 0;
    v148 = 64;
    v149 = 11;
    v150 = v24;
    v151 = 0;
    v152 = *(_QWORD *)L".jpg";
    v153 = aJpg[4];
    v154 = 0;
    v155 = 0;
    v156 = *(_OWORD *)L"Image64";
    v157 = 0;
    v158 = 0;
    v159 = 0;
    v160 = 208;
    v161 = 12;
    v162 = hObject;
    v163 = 0;
    v164 = *(_QWORD *)L".jpg";
    v165 = aJpg[4];
    v166 = 0;
    v167 = 0;
    v168 = *(_OWORD *)L"Image208";
    v169 = aImage208[8];
    memset(v170, 0, sizeof(v170));
    v171 = 0;
    v172 = 424;
    v173 = 13;
    v174 = hObject;
    v175 = 0;
    v176 = *(_QWORD *)L".jpg";
    v177 = aJpg[4];
    v178 = 0;
    v179 = 0;
    v180 = *(_OWORD *)L"Image424";
    v181 = aImage424[8];
    memset(v182, 0, sizeof(v182));
    v183 = 0;
    v184 = 1080;
    v185 = 14;
    v186 = hObject;
    v187 = 0;
    v188 = *(_QWORD *)L".jpg";
    v189 = aJpg[4];
    v190 = 0;
    v191 = 0;
    v192 = *(_OWORD *)L"Image1080";
    v193 = *(_DWORD *)L"0";
    v194 = 0;
    v195 = 0;
    v196 = 0;
    if ( hObject )
    {
      for ( i = 3; i < 0xE; ++i )
      {
        if ( inited < 0 )
          break;
        v11 = v32[12 * i - 1];
        if ( v11 )
        {
          DueTimea = (HANDLE *)&v32[12 * i];
          inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v22 + 32LL))(
                     *(_QWORD *)v22,
                     *((unsigned int *)&v30 + 24 * i + 1),
                     (unsigned int)(int)(float)((float)((float)*((int *)&v30 + 24 * i) * (float)a6) / 100.0));
        }
      }
    }
    v13 = retaddr;
    if ( inited >= 0 )
    {
      v16 = CUserTileBroker::_SaveImages(retaddr, a2, (struct USERTILE_SIZE_MAPPING *)&v30, v11);
      inited = v16;
      v13 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_20;
      v14 = (unsigned int)v16;
      v15 = 543;
    }
    else
    {
      v14 = (unsigned int)inited;
      v15 = 540;
    }
    wil::details::in1diag3::_Log_Hr(
      v13,
      (void *)v15,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)v14,
      (int)DueTimea);
LABEL_20:
    for ( j = 0; j < 0xE; ++j )
    {
      SafeRelease<IPopupCommand>(&v32[12 * j]);
      CoTaskMemFree(*(&pv + 12 * j));
    }
    goto LABEL_22;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1F9,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
    (const char *)(unsigned int)v10,
    (int)&v24);
LABEL_22:
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
LABEL_23:
  v18 = *(_QWORD *)v22;
  if ( *(_QWORD *)v22 )
  {
    *(_QWORD *)v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180016c80  push    rbp
0x180016c82  push    rbx
0x180016c83  push    rsi
0x180016c84  push    rdi
0x180016c85  push    r12
0x180016c87  push    r14
0x180016c89  push    r15
0x180016c8b  lea     rbp, [rsp-4D0h]
0x180016c93  sub     rsp, 5D0h
0x180016c9a  mov     rax, cs:__security_cookie
0x180016ca1  xor     rax, rsp
0x180016ca4  mov     [rbp+500h+var_40], rax
0x180016cab  mov     r14, r9
0x180016cae  mov     rsi, r8
0x180016cb1  mov     r15, rdx
0x180016cb4  mov     rbx, [rbp+500h+arg_20]
0x180016cbb  xor     r12d, r12d
0x180016cbe  mov     qword ptr [rsp+600h+var_5C0], r12
0x180016cc3  lea     rcx, [rsp+600h+var_5C0]
0x180016cc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016ccd  mov     qword ptr [rsp+600h+var_5C0], r12
0x180016cd2  mov     [rsp+600h+hObject], r12
0x180016cd7  mov     [rsp+600h+var_5B0], r12
0x180016cdc  lea     rdx, [rsp+600h+var_5B0]; void **
0x180016ce1  lea     rcx, [rsp+600h+hObject]; void **
0x180016ce6  call    ?_InitRestrictedProcess@@YAJPEAPEAX0@Z; _InitRestrictedProcess(void * *,void * *)
0x180016ceb  mov     edi, eax
0x180016ced  test    eax, eax
0x180016cef  js      short loc_180016D3C
0x180016cf1  lea     rax, [rsp+600h+var_5C0]
0x180016cf6  mov     qword ptr [rsp+600h+DueTime], rax; int
0x180016cfb  lea     r9, _GUID_0406e498_0916_49c2_a1c4_10db7bf76766
0x180016d02  lea     r8, CLSID_UserTileValidator
0x180016d09  mov     rdx, [rsp+600h+var_5B0]
0x180016d0e  mov     rcx, [rsp+600h+hObject]; ProcessHandle
0x180016d13  call    _CreateInstanceInProcess
0x180016d18  mov     edi, eax
0x180016d1a  mov     rcx, [rsp+600h+hObject]; hObject
0x180016d1f  call    cs:__imp_CloseHandle
0x180016d26  nop     dword ptr [rax+rax+00h]
0x180016d2b  mov     rcx, [rsp+600h+var_5B0]; hObject
0x180016d30  call    cs:__imp_CloseHandle
0x180016d37  nop     dword ptr [rax+rax+00h]
0x180016d3c  mov     rcx, [rbp+508h]; this
0x180016d43  test    edi, edi
0x180016d45  jns     short loc_180016D60
0x180016d47  mov     r9d, edi; char *
0x180016d4a  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180016d51  mov     edx, 1F3h; void *
0x180016d56  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016d5b  jmp     loc_18001750A
0x180016d60  call    cs:__imp_GetCurrentThreadId
0x180016d67  nop     dword ptr [rax+rax+00h]
0x180016d6c  mov     [rsp+600h+Parameter], eax
0x180016d70  mov     [rsp+600h+var_59C], r12b
0x180016d75  mov     [rsp+600h+var_598], 80004005h
0x180016d7d  mov     [rsp+600h+phNewTimer], r12
0x180016d82  lea     rcx, [rsp+600h+Parameter]; this
0x180016d87  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180016d8c  xor     ecx, ecx; pReserved
0x180016d8e  call    cs:__imp_CoEnableCallCancellation
0x180016d95  nop     dword ptr [rax+rax+00h]
0x180016d9a  mov     [rsp+600h+var_598], eax
0x180016d9e  test    eax, eax
0x180016da0  js      short loc_180016DD7
0x180016da2  mov     [rsp+600h+Flags], r12d; Flags
0x180016da7  mov     [rsp+600h+Period], 3E8h; Period
0x180016daf  mov     [rsp+600h+DueTime], 1D4C0h; DueTime
0x180016db7  lea     r9, [rsp+600h+Parameter]; Parameter
0x180016dbc  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180016dc3  xor     edx, edx; TimerQueue
0x180016dc5  lea     rcx, [rsp+600h+phNewTimer]; phNewTimer
0x180016dca  call    cs:__imp_CreateTimerQueueTimer
0x180016dd1  nop     dword ptr [rax+rax+00h]
0x180016dd6  nop
0x180016dd7  mov     [rsp+600h+var_5B0], r12
0x180016ddc  mov     [rsp+600h+hObject], r12
0x180016de1  mov     [rsp+600h+var_5A8], r12
0x180016de6  mov     rcx, qword ptr [rsp+600h+var_5C0]
0x180016deb  mov     rax, [rcx]
0x180016dee  lea     rdx, [rsp+600h+var_5A8]
0x180016df3  mov     qword ptr [rsp+600h+Flags], rdx
0x180016df8  lea     rdx, [rsp+600h+hObject]
0x180016dfd  mov     qword ptr [rsp+600h+Period], rdx
0x180016e02  lea     rdx, [rsp+600h+var_5B0]
0x180016e07  mov     qword ptr [rsp+600h+DueTime], rdx; int
0x180016e0c  mov     r9, rbx
0x180016e0f  mov     r8, r14
0x180016e12  mov     rdx, rsi
0x180016e15  mov     rax, [rax+18h]
0x180016e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e1e  mov     edi, eax
0x180016e20  mov     rcx, [rbp+508h]; this
0x180016e27  test    eax, eax
0x180016e29  jns     short loc_180016E44
0x180016e2b  mov     r9d, eax; char *
0x180016e2e  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180016e35  mov     edx, 1F9h; void *
0x180016e3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016e3f  jmp     loc_1800174FF
0x180016e44  mov     [rbp+500h+var_580], 60h ; '`'
0x180016e4c  mov     [rbp+500h+var_578], rsi
0x180016e50  mov     rdx, [rsp+600h+var_5B0]
0x180016e55  mov     [rbp+500h+var_570], rdx
0x180016e59  movsd   xmm3, qword ptr cs:aJpg; ".jpg"
0x180016e61  movsd   [rbp+500h+var_568], xmm3
0x180016e66  movzx   r9d, word ptr cs:aJpg+8; ""
0x180016e6e  mov     [rbp+500h+var_560], r9w
0x180016e73  xor     eax, eax
0x180016e75  mov     [rbp+500h+var_55E], rax
0x180016e79  mov     [rbp+500h+var_556], ax
0x180016e7d  movups  xmm0, xmmword ptr cs:aImage96; "Image96"
0x180016e84  movdqu  [rbp+500h+var_554], xmm0
0x180016e89  xorps   xmm1, xmm1
0x180016e8c  movups  [rbp+500h+var_544], xmm1
0x180016e90  mov     [rbp+500h+var_534], rax
0x180016e94  mov     [rbp+500h+pv], r12
0x180016e98  mov     ecx, 1C0h
0x180016e9d  mov     [rbp+500h+var_520], ecx
0x180016ea0  mov     [rbp+500h+var_51C], 1
0x180016ea7  mov     [rbp+500h+var_518], r14
0x180016eab  mov     r8, [rsp+600h+hObject]
0x180016eb0  mov     [rbp+500h+var_510], r8
0x180016eb4  movsd   [rbp+500h+var_508], xmm3
0x180016eb9  mov     [rbp+500h+var_500], r9w
0x180016ebe  mov     [rbp+500h+var_4FE], rax
0x180016ec2  mov     [rbp+500h+var_4F6], ax
0x180016ec6  movups  xmm0, xmmword ptr cs:aImage448; "Image448"
0x180016ecd  movups  [rbp+500h+var_4F4], xmm0
0x180016ed1  movzx   eax, word ptr cs:aImage448+10h; ""
0x180016ed8  mov     [rbp+500h+var_4E4], ax
0x180016edc  xorps   xmm0, xmm0
0x180016edf  xor     eax, eax
0x180016ee1  movups  xmmword ptr [rbp+500h+var_4E2], xmm0
0x180016ee5  mov     qword ptr [rbp+500h+var_4E2+0Eh], rax
0x180016ee9  mov     [rbp+500h+var_4C8], r12
0x180016eed  mov     [rbp+500h+var_4C0], ecx
0x180016ef0  mov     [rbp+500h+var_4BC], 2
0x180016ef7  mov     [rbp+500h+var_4B8], rbx
0x180016efb  mov     rax, [rsp+600h+var_5A8]
0x180016f00  mov     [rbp+500h+var_4B0], rax
0x180016f04  movsd   xmm2, qword ptr cs:aMp4; ".mp4"
0x180016f0c  movsd   [rbp+500h+var_4A8], xmm2
0x180016f11  movzx   ecx, word ptr cs:aMp4+8; ""
0x180016f18  mov     [rbp+500h+var_4A0], cx
0x180016f1c  xor     eax, eax
0x180016f1e  mov     [rbp+500h+var_49E], rax
0x180016f22  mov     [rbp+500h+var_496], ax
0x180016f26  movups  xmm0, xmmword ptr cs:aVideo448; "Video448"
0x180016f2d  movups  [rbp+500h+var_494], xmm0
0x180016f31  movzx   eax, word ptr cs:aVideo448+10h; ""
0x180016f38  mov     [rbp+500h+var_484], ax
0x180016f3c  xorps   xmm0, xmm0
0x180016f3f  xor     eax, eax
0x180016f41  movups  xmmword ptr [rbp+500h+var_482], xmm0
0x180016f45  mov     qword ptr [rbp+500h+var_482+0Eh], rax
0x180016f4c  mov     [rbp+500h+var_468], r12
0x180016f53  mov     [rbp+500h+var_460], 20h ; ' '
0x180016f5d  mov     [rbp+500h+var_45C], 4
0x180016f67  mov     [rbp+500h+var_458], rdx
0x180016f6e  mov     [rbp+500h+var_450], r12
0x180016f75  movsd   [rbp+500h+var_448], xmm3
0x180016f7d  mov     [rbp+500h+var_440], r9w
0x180016f85  mov     [rbp+500h+var_43E], rax
0x180016f8c  mov     [rbp+500h+var_436], ax
0x180016f93  movups  xmm0, xmmword ptr cs:aImage32; "Image32"
0x180016f9a  movdqu  [rbp+500h+var_434], xmm0
0x180016fa2  movups  [rbp+500h+var_424], xmm1
0x180016fa9  mov     [rbp+500h+var_414], rax
0x180016fb0  mov     [rbp+500h+var_408], r12
0x180016fb7  mov     [rbp+500h+var_400], 28h ; '('
0x180016fc1  mov     [rbp+500h+var_3FC], 5
0x180016fcb  mov     [rbp+500h+var_3F8], rdx
0x180016fd2  mov     [rbp+500h+var_3F0], r12
0x180016fd9  movsd   [rbp+500h+var_3E8], xmm3
0x180016fe1  mov     [rbp+500h+var_3E0], r9w
0x180016fe9  mov     [rbp+500h+var_3DE], rax
0x180016ff0  mov     [rbp+500h+var_3D6], ax
0x180016ff7  movups  xmm0, xmmword ptr cs:aImage40; "Image40"
0x180016ffe  movdqu  [rbp+500h+var_3D4], xmm0
0x180017006  movups  [rbp+500h+var_3C4], xmm1
0x18001700d  mov     [rbp+500h+var_3B4], rax
0x180017014  mov     [rbp+500h+var_3A8], r12
0x18001701b  mov     [rbp+500h+var_3A0], 30h ; '0'
0x180017025  mov     [rbp+500h+var_39C], 6
0x18001702f  mov     [rbp+500h+var_398], rdx
0x180017036  mov     [rbp+500h+var_390], r12
0x18001703d  movsd   [rbp+500h+var_388], xmm3
0x180017045  mov     [rbp+500h+var_380], r9w
0x18001704d  mov     [rbp+500h+var_37E], rax
0x180017054  mov     [rbp+500h+var_376], ax
0x18001705b  movups  xmm0, xmmword ptr cs:aImage48; "Image48"
0x180017062  movdqu  [rbp+500h+var_374], xmm0
0x18001706a  movups  [rbp+500h+var_364], xmm1
0x180017071  mov     [rbp+500h+var_354], rax
0x180017078  mov     [rbp+500h+var_348], r12
0x18001707f  mov     r10d, 0C0h
0x180017085  mov     [rbp+500h+var_340], r10d
0x18001708c  mov     [rbp+500h+var_33C], 7
0x180017096  mov     [rbp+500h+var_338], r8
0x18001709d  mov     [rbp+500h+var_330], r12
0x1800170a4  movsd   [rbp+500h+var_328], xmm3
0x1800170ac  mov     [rbp+500h+var_320], r9w
0x1800170b4  mov     [rbp+500h+var_31E], rax
0x1800170bb  mov     [rbp+500h+var_316], ax
0x1800170c2  movups  xmm0, xmmword ptr cs:aImage192; "Image192"
0x1800170c9  movups  [rbp+500h+var_314], xmm0
0x1800170d0  movzx   eax, word ptr cs:aImage192+10h; ""
0x1800170d7  mov     [rbp+500h+var_304], ax
0x1800170de  xorps   xmm0, xmm0
0x1800170e1  xor     eax, eax
0x1800170e3  movups  xmmword ptr [rbp+500h+var_302], xmm0
0x1800170ea  mov     qword ptr [rbp+500h+var_302+0Eh], rax
0x1800170f1  mov     [rbp+500h+var_2E8], r12
0x1800170f8  mov     [rbp+500h+var_2E0], r10d
0x1800170ff  mov     [rbp+500h+var_2DC], 8
0x180017109  mov     [rbp+500h+var_2D8], rbx
0x180017110  mov     [rbp+500h+var_2D0], r12
0x180017117  movsd   [rbp+500h+var_2C8], xmm2
0x18001711f  mov     [rbp+500h+var_2C0], cx
0x180017126  mov     [rbp+500h+var_2BE], rax
0x18001712d  mov     [rbp+500h+var_2B6], ax
0x180017134  movups  xmm0, xmmword ptr cs:aVideo192; "Video192"
0x18001713b  movups  [rbp+500h+var_2B4], xmm0
0x180017142  movzx   eax, word ptr cs:aVideo192+10h; ""
0x180017149  mov     [rbp+500h+var_2A4], ax
0x180017150  xorps   xmm0, xmm0
0x180017153  xor     eax, eax
0x180017155  movups  xmmword ptr [rbp+500h+var_2A2], xmm0
0x18001715c  mov     qword ptr [rbp+500h+var_2A2+0Eh], rax
0x180017163  mov     [rbp+500h+var_288], r12
0x18001716a  mov     r10d, 0F0h
0x180017170  mov     [rbp+500h+var_280], r10d
0x180017177  mov     [rbp+500h+var_27C], 9
0x180017181  mov     [rbp+500h+var_278], r8
0x180017188  mov     [rbp+500h+var_270], r12
0x18001718f  movsd   [rbp+500h+var_268], xmm3
0x180017197  mov     [rbp+500h+var_260], r9w
0x18001719f  mov     [rbp+500h+var_25E], rax
0x1800171a6  mov     [rbp+500h+var_256], ax
0x1800171ad  movups  xmm0, xmmword ptr cs:aImage240; "Image240"
0x1800171b4  movups  [rbp+500h+var_254], xmm0
0x1800171bb  movzx   eax, word ptr cs:aImage240+10h; ""
0x1800171c2  mov     [rbp+500h+var_244], ax
0x1800171c9  xorps   xmm0, xmm0
0x1800171cc  xor     eax, eax
0x1800171ce  movups  xmmword ptr [rbp+500h+var_242], xmm0
0x1800171d5  mov     qword ptr [rbp+500h+var_242+0Eh], rax
0x1800171dc  mov     [rbp+500h+var_228], r12
0x1800171e3  mov     [rbp+500h+var_220], r10d
0x1800171ea  mov     [rbp+500h+var_21C], 0Ah
0x1800171f4  mov     [rbp+500h+var_218], rbx
0x1800171fb  mov     [rbp+500h+var_210], r12
0x180017202  movsd   [rbp+500h+var_208], xmm2
0x18001720a  mov     [rbp+500h+var_200], cx
0x180017211  mov     [rbp+500h+var_1FE], rax
0x180017218  mov     [rbp+500h+var_1F6], ax
0x18001721f  movups  xmm0, xmmword ptr cs:aVideo240; "Video240"
0x180017226  movups  [rbp+500h+var_1F4], xmm0
0x18001722d  movzx   eax, word ptr cs:aVideo240+10h; ""
0x180017234  mov     [rbp+500h+var_1E4], ax
0x18001723b  xorps   xmm0, xmm0
0x18001723e  xor     eax, eax
0x180017240  movups  xmmword ptr [rbp+500h+var_1E2], xmm0
0x180017247  mov     qword ptr [rbp+500h+var_1E2+0Eh], rax
0x18001724e  mov     [rbp+500h+var_1C8], r12
0x180017255  mov     [rbp+500h+var_1C0], 40h ; '@'
0x18001725f  mov     [rbp+500h+var_1BC], 0Bh
0x180017269  mov     [rbp+500h+var_1B8], rdx
0x180017270  mov     [rbp+500h+var_1B0], r12
0x180017277  movsd   [rbp+500h+var_1A8], xmm3
0x18001727f  mov     [rbp+500h+var_1A0], r9w
0x180017287  mov     [rbp+500h+var_19E], rax
0x18001728e  mov     [rbp+500h+var_196], ax
0x180017295  movups  xmm0, xmmword ptr cs:aImage64; "Image64"
0x18001729c  movdqu  [rbp+500h+var_194], xmm0
0x1800172a4  movups  [rbp+500h+var_184], xmm1
0x1800172ab  mov     [rbp+500h+var_174], rax
0x1800172b2  mov     [rbp+500h+var_168], r12
0x1800172b9  mov     [rbp+500h+var_160], 0D0h
0x1800172c3  mov     [rbp+500h+var_15C], 0Ch
0x1800172cd  mov     [rbp+500h+var_158], r8
0x1800172d4  mov     [rbp+500h+var_150], r12
0x1800172db  movsd   [rbp+500h+var_148], xmm3
0x1800172e3  mov     [rbp+500h+var_140], r9w
0x1800172eb  mov     [rbp+500h+var_13E], rax
0x1800172f2  mov     [rbp+500h+var_136], ax
0x1800172f9  movups  xmm0, xmmword ptr cs:aImage208; "Image208"
0x180017300  movups  [rbp+500h+var_134], xmm0
0x180017307  movzx   eax, word ptr cs:aImage208+10h; ""
0x18001730e  mov     [rbp+500h+var_124], ax
0x180017315  xorps   xmm0, xmm0
0x180017318  xor     eax, eax
0x18001731a  movups  xmmword ptr [rbp+500h+var_122], xmm0
0x180017321  mov     qword ptr [rbp+500h+var_122+0Eh], rax
0x180017328  mov     [rbp+500h+var_108], r12
0x18001732f  mov     [rbp+500h+var_100], 1A8h
0x180017339  mov     [rbp+500h+var_FC], 0Dh
0x180017343  mov     [rbp+500h+var_F8], r8
0x18001734a  mov     [rbp+500h+var_F0], r12
  ... truncated ...
```
