# CSLQuery::Initialize(void)

- ea: `0x1800af3a4`
- end: `0x1800b13ef`
- name: `?Initialize@CSLQuery@@SAJXZ`
- size: `8267`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800195c0`
- `0x18009ebfc`
- `0x1800a9328`
- `0x1800a93ec`
- `0x1800af21c`
- `0x1800b13f8`
- `0x1800b14b4`
- `0x1800b1570`
- `0x1800b1748`
- `0x1800b74b4`
- `0x1800b7574`

## callees

- `0x1800015a4`
- `0x180002534`
- `0x180002544`
- `0x1800052d0`
- `0x1800053e4`
- `0x180011a80`
- `0x18001df00`
- `0x1800321f0`
- `0x18004f340`
- `0x18004f570`
- `0x1800af3a4`
- `0x1800c4290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af4a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af4a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800af3f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800af3f6`

## string_xrefs

- `0x1800af541`: `TerminalServices-RemoteConnectionManager-AllowRemoteConnections`
- `0x1800af7bc`: `TerminalServices-RemoteConnectionManager-AllowMultipleSessions`
- `0x1800afa52`: `TerminalServices-RemoteConnectionManager-AllowAppServerMode`
- `0x1800afcf1`: `TerminalServices-RemoteConnectionManager-AutomatedAppServerInstallation`
- `0x1800afe9d`: `CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAutomatedAppServerInstallation`
- `0x1800afd7f`: `The SL policy for 'Automated App Server Installation' is not defined - assuming FALSE`
- `0x1800aff6c`: `TerminalServices-RemoteConnectionManager-AllowMultimon`
- `0x1800b01e7`: `TerminalServices-ADD-Licensing`
- `0x1800b0462`: `TerminalServices-RemoteConnectionManager-MaxUserSessions`
- `0x1800b06bb`: `TerminalServices-RemoteConnectionManager-ce0ad219-4670-4988-98fb-89b14c2f072b-MaxSessions`
- `0x1800b0b6d`: `TerminalServices-RemoteConnectionManager-WVD-Enabled`
- `0x1800b120d`: `The SL policy for 'Max Agent Sessions' is not defined - assuming no limit to user sessions`
- `0x1800b117f`: `TerminalServices-RemoteConnectionManager-cd051c59-3fe7-499c-9b66-02d99dbd8d3b-MaxSessions`
- `0x1800b132b`: `CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxAgentSessions`

## pseudocode

```c
__int64 CSLQuery::Initialize(void)
{
  const unsigned __int16 **v0; // rax
  const unsigned __int16 **v1; // rax
  const unsigned __int16 **v2; // rax
  const unsigned __int16 **v3; // rax
  const unsigned __int16 **v4; // rax
  const unsigned __int16 **v5; // rax
  const unsigned __int16 **v6; // rax
  const unsigned __int16 **v7; // rax
  const unsigned __int16 **v8; // rax
  const unsigned __int16 **v9; // rax
  const unsigned __int16 **v10; // rax
  int v12; // [rsp+40h] [rbp-758h]
  unsigned int v13; // [rsp+44h] [rbp-754h] BYREF
  char v14; // [rsp+48h] [rbp-750h]
  char v15; // [rsp+49h] [rbp-74Fh]
  char v16; // [rsp+4Ah] [rbp-74Eh]
  char v17; // [rsp+4Bh] [rbp-74Dh]
  char v18; // [rsp+4Ch] [rbp-74Ch]
  char v19; // [rsp+4Dh] [rbp-74Bh]
  char v20; // [rsp+4Eh] [rbp-74Ah]
  char v21; // [rsp+4Fh] [rbp-749h]
  char v22; // [rsp+50h] [rbp-748h]
  char v23; // [rsp+51h] [rbp-747h]
  char v24; // [rsp+52h] [rbp-746h]
  char v25; // [rsp+53h] [rbp-745h]
  char v26; // [rsp+54h] [rbp-744h]
  char v27; // [rsp+55h] [rbp-743h]
  char v28; // [rsp+56h] [rbp-742h]
  char v29; // [rsp+57h] [rbp-741h]
  char v30; // [rsp+58h] [rbp-740h]
  char v31; // [rsp+59h] [rbp-73Fh]
  char v32; // [rsp+5Ah] [rbp-73Eh]
  char v33; // [rsp+5Bh] [rbp-73Dh]
  bool v34; // [rsp+5Ch] [rbp-73Ch]
  bool v35; // [rsp+5Dh] [rbp-73Bh]
  __int64 *v36; // [rsp+60h] [rbp-738h]
  unsigned int v37; // [rsp+68h] [rbp-730h]
  unsigned int v38; // [rsp+6Ch] [rbp-72Ch]
  unsigned int v39; // [rsp+70h] [rbp-728h]
  unsigned int v40; // [rsp+74h] [rbp-724h]
  BOOL v41; // [rsp+78h] [rbp-720h]
  unsigned int v42; // [rsp+7Ch] [rbp-71Ch]
  unsigned int v43; // [rsp+80h] [rbp-718h]
  unsigned int v44; // [rsp+84h] [rbp-714h]
  BOOL v45; // [rsp+88h] [rbp-710h]
  unsigned int v46; // [rsp+8Ch] [rbp-70Ch]
  unsigned int v47; // [rsp+90h] [rbp-708h]
  BOOL v48; // [rsp+94h] [rbp-704h]
  unsigned int v49; // [rsp+98h] [rbp-700h]
  unsigned int v50; // [rsp+9Ch] [rbp-6FCh]
  BOOL v51; // [rsp+A0h] [rbp-6F8h]
  unsigned int v52; // [rsp+A4h] [rbp-6F4h]
  unsigned int v53; // [rsp+A8h] [rbp-6F0h]
  BOOL v54; // [rsp+ACh] [rbp-6ECh]
  unsigned int v55; // [rsp+B0h] [rbp-6E8h]
  unsigned int v56; // [rsp+B4h] [rbp-6E4h]
  BOOL v57; // [rsp+B8h] [rbp-6E0h]
  unsigned int v58; // [rsp+BCh] [rbp-6DCh]
  unsigned int v59; // [rsp+C0h] [rbp-6D8h]
  unsigned int v60; // [rsp+C4h] [rbp-6D4h]
  unsigned int v61; // [rsp+C8h] [rbp-6D0h]
  unsigned int v62; // [rsp+CCh] [rbp-6CCh]
  BOOL v63; // [rsp+D0h] [rbp-6C8h]
  unsigned int v64; // [rsp+D4h] [rbp-6C4h]
  unsigned int v65; // [rsp+D8h] [rbp-6C0h]
  BOOL v66; // [rsp+DCh] [rbp-6BCh]
  int v67; // [rsp+E0h] [rbp-6B8h]
  int v68; // [rsp+E4h] [rbp-6B4h]
  int v69; // [rsp+E8h] [rbp-6B0h]
  int v70; // [rsp+ECh] [rbp-6ACh]
  unsigned int v71; // [rsp+F0h] [rbp-6A8h]
  int v72; // [rsp+F4h] [rbp-6A4h]
  int v73; // [rsp+F8h] [rbp-6A0h]
  int v74; // [rsp+FCh] [rbp-69Ch]
  int v75; // [rsp+100h] [rbp-698h]
  BOOL v76; // [rsp+104h] [rbp-694h]
  unsigned int v77; // [rsp+108h] [rbp-690h]
  unsigned int v78; // [rsp+10Ch] [rbp-68Ch]
  int v79; // [rsp+110h] [rbp-688h]
  unsigned int v80; // [rsp+114h] [rbp-684h]
  DWORD LastError; // [rsp+118h] [rbp-680h] BYREF
  _BYTE v82[4]; // [rsp+11Ch] [rbp-67Ch] BYREF
  unsigned int v83; // [rsp+120h] [rbp-678h]
  unsigned int v84; // [rsp+124h] [rbp-674h]
  int v85; // [rsp+128h] [rbp-670h] BYREF
  _BYTE v86[4]; // [rsp+12Ch] [rbp-66Ch] BYREF
  unsigned int v87; // [rsp+130h] [rbp-668h]
  unsigned int v88; // [rsp+134h] [rbp-664h]
  int v89; // [rsp+138h] [rbp-660h] BYREF
  _BYTE v90[4]; // [rsp+13Ch] [rbp-65Ch] BYREF
  unsigned int v91; // [rsp+140h] [rbp-658h]
  int v92; // [rsp+144h] [rbp-654h]
  unsigned int v93; // [rsp+148h] [rbp-650h]
  int v94; // [rsp+14Ch] [rbp-64Ch] BYREF
  _BYTE v95[4]; // [rsp+150h] [rbp-648h] BYREF
  unsigned int v96; // [rsp+154h] [rbp-644h]
  unsigned int v97; // [rsp+158h] [rbp-640h]
  int v98; // [rsp+15Ch] [rbp-63Ch] BYREF
  _BYTE v99[4]; // [rsp+160h] [rbp-638h] BYREF
  unsigned int v100; // [rsp+164h] [rbp-634h]
  unsigned int v101; // [rsp+168h] [rbp-630h]
  int v102; // [rsp+16Ch] [rbp-62Ch] BYREF
  _BYTE v103[4]; // [rsp+170h] [rbp-628h] BYREF
  unsigned int v104; // [rsp+174h] [rbp-624h]
  unsigned int v105; // [rsp+178h] [rbp-620h]
  int v106; // [rsp+17Ch] [rbp-61Ch] BYREF
  _BYTE v107[4]; // [rsp+180h] [rbp-618h] BYREF
  unsigned int v108; // [rsp+184h] [rbp-614h]
  unsigned int v109; // [rsp+188h] [rbp-610h]
  int v110; // [rsp+18Ch] [rbp-60Ch] BYREF
  _BYTE v111[4]; // [rsp+190h] [rbp-608h] BYREF
  unsigned int v112; // [rsp+194h] [rbp-604h]
  unsigned int v113; // [rsp+198h] [rbp-600h]
  int v114; // [rsp+19Ch] [rbp-5FCh] BYREF
  _BYTE v115[4]; // [rsp+1A0h] [rbp-5F8h] BYREF
  unsigned int v116; // [rsp+1A4h] [rbp-5F4h]
  unsigned int v117; // [rsp+1A8h] [rbp-5F0h]
  int v118; // [rsp+1ACh] [rbp-5ECh] BYREF
  _BYTE v119[4]; // [rsp+1B0h] [rbp-5E8h] BYREF
  unsigned int v120; // [rsp+1B4h] [rbp-5E4h]
  unsigned int v121; // [rsp+1B8h] [rbp-5E0h]
  int v122; // [rsp+1BCh] [rbp-5DCh] BYREF
  _BYTE v123[4]; // [rsp+1C0h] [rbp-5D8h] BYREF
  unsigned int v124; // [rsp+1C4h] [rbp-5D4h]
  unsigned int v125; // [rsp+1C8h] [rbp-5D0h]
  int v126; // [rsp+1CCh] [rbp-5CCh] BYREF
  _BYTE v127[8]; // [rsp+1D0h] [rbp-5C8h] BYREF
  int *v128; // [rsp+1D8h] [rbp-5C0h]
  int *v129; // [rsp+1E0h] [rbp-5B8h]
  int *v130; // [rsp+1E8h] [rbp-5B0h]
  int *v131; // [rsp+1F0h] [rbp-5A8h]
  int *v132; // [rsp+1F8h] [rbp-5A0h]
  int *v133; // [rsp+200h] [rbp-598h]
  int *v134; // [rsp+208h] [rbp-590h]
  int *v135; // [rsp+210h] [rbp-588h]
  int *v136; // [rsp+218h] [rbp-580h]
  int *v137; // [rsp+220h] [rbp-578h]
  int *v138; // [rsp+228h] [rbp-570h]
  int *v139; // [rsp+230h] [rbp-568h]
  int *v140; // [rsp+238h] [rbp-560h]
  int *v141; // [rsp+240h] [rbp-558h]
  int *v142; // [rsp+248h] [rbp-550h]
  int *v143; // [rsp+250h] [rbp-548h]
  int *v144; // [rsp+258h] [rbp-540h]
  int *v145; // [rsp+260h] [rbp-538h]
  int *v146; // [rsp+268h] [rbp-530h]
  int *v147; // [rsp+270h] [rbp-528h]
  int *v148; // [rsp+278h] [rbp-520h]
  int *v149; // [rsp+280h] [rbp-518h]
  int *v150; // [rsp+288h] [rbp-510h]
  int *v151; // [rsp+290h] [rbp-508h]
  _BYTE *v152; // [rsp+298h] [rbp-500h]
  const unsigned __int16 **v153; // [rsp+2A0h] [rbp-4F8h]
  int *v154; // [rsp+2A8h] [rbp-4F0h]
  int *v155; // [rsp+2B0h] [rbp-4E8h]
  const unsigned __int16 **v156; // [rsp+2B8h] [rbp-4E0h]
  _BYTE *v157; // [rsp+2C0h] [rbp-4D8h]
  const unsigned __int16 **v158; // [rsp+2C8h] [rbp-4D0h]
  const unsigned __int16 **v159; // [rsp+2D0h] [rbp-4C8h]
  int *v160; // [rsp+2D8h] [rbp-4C0h]
  int *v161; // [rsp+2E0h] [rbp-4B8h]
  const unsigned __int16 **v162; // [rsp+2E8h] [rbp-4B0h]
  _BYTE *v163; // [rsp+2F0h] [rbp-4A8h]
  const unsigned __int16 **v164; // [rsp+2F8h] [rbp-4A0h]
  const unsigned __int16 **v165; // [rsp+300h] [rbp-498h]
  int *v166; // [rsp+308h] [rbp-490h]
  int *v167; // [rsp+310h] [rbp-488h]
  const unsigned __int16 **v168; // [rsp+318h] [rbp-480h]
  _BYTE *v169; // [rsp+320h] [rbp-478h]
  const unsigned __int16 **v170; // [rsp+328h] [rbp-470h]
  const unsigned __int16 **v171; // [rsp+330h] [rbp-468h]
  int *v172; // [rsp+338h] [rbp-460h]
  int *v173; // [rsp+340h] [rbp-458h]
  const unsigned __int16 **v174; // [rsp+348h] [rbp-450h]
  _BYTE *v175; // [rsp+350h] [rbp-448h]
  const unsigned __int16 **v176; // [rsp+358h] [rbp-440h]
  const unsigned __int16 **v177; // [rsp+360h] [rbp-438h]
  int *v178; // [rsp+368h] [rbp-430h]
  int *v179; // [rsp+370h] [rbp-428h]
  const unsigned __int16 **v180; // [rsp+378h] [rbp-420h]
  _BYTE *v181; // [rsp+380h] [rbp-418h]
  const unsigned __int16 **v182; // [rsp+388h] [rbp-410h]
  const unsigned __int16 **v183; // [rsp+390h] [rbp-408h]
  int *v184; // [rsp+398h] [rbp-400h]
  int *v185; // [rsp+3A0h] [rbp-3F8h]
  const unsigned __int16 **v186; // [rsp+3A8h] [rbp-3F0h]
  _BYTE *v187; // [rsp+3B0h] [rbp-3E8h]
  const unsigned __int16 **v188; // [rsp+3B8h] [rbp-3E0h]
  const unsigned __int16 **v189; // [rsp+3C0h] [rbp-3D8h]
  int *v190; // [rsp+3C8h] [rbp-3D0h]
  int *v191; // [rsp+3D0h] [rbp-3C8h]
  const unsigned __int16 **v192; // [rsp+3D8h] [rbp-3C0h]
  _BYTE *v193; // [rsp+3E0h] [rbp-3B8h]
  const unsigned __int16 **v194; // [rsp+3E8h] [rbp-3B0h]
  const unsigned __int16 **v195; // [rsp+3F0h] [rbp-3A8h]
  int *v196; // [rsp+3F8h] [rbp-3A0h]
  int *v197; // [rsp+400h] [rbp-398h]
  const unsigned __int16 **v198; // [rsp+408h] [rbp-390h]
  _BYTE *v199; // [rsp+410h] [rbp-388h]
  const unsigned __int16 **v200; // [rsp+418h] [rbp-380h]
  const unsigned __int16 **v201; // [rsp+420h] [rbp-378h]
  int *v202; // [rsp+428h] [rbp-370h]
  int *v203; // [rsp+430h] [rbp-368h]
  const unsigned __int16 **v204; // [rsp+438h] [rbp-360h]
  _BYTE *v205; // [rsp+440h] [rbp-358h]
  const unsigned __int16 **v206; // [rsp+448h] [rbp-350h]
  const unsigned __int16 **v207; // [rsp+450h] [rbp-348h]
  int *v208; // [rsp+458h] [rbp-340h]
  int *v209; // [rsp+460h] [rbp-338h]
  const unsigned __int16 **v210; // [rsp+468h] [rbp-330h]
  _BYTE *v211; // [rsp+470h] [rbp-328h]
  const unsigned __int16 **v212; // [rsp+478h] [rbp-320h]
  const unsigned __int16 **v213; // [rsp+480h] [rbp-318h]
  __int64 *v214; // [rsp+488h] [rbp-310h]
  int *v215; // [rsp+490h] [rbp-308h]
  int *v216; // [rsp+498h] [rbp-300h]
  const unsigned __int16 **v217; // [rsp+4A0h] [rbp-2F8h]
  _BYTE *v218; // [rsp+4A8h] [rbp-2F0h]
  const unsigned __int16 **v219; // [rsp+4B0h] [rbp-2E8h]
  const unsigned __int16 **v220; // [rsp+4B8h] [rbp-2E0h]
  __int64 v221; // [rsp+4C0h] [rbp-2D8h] BYREF
  __int64 v222; // [rsp+4C8h] [rbp-2D0h] BYREF
  __int64 v223; // [rsp+4D0h] [rbp-2C8h] BYREF
  __int64 v224; // [rsp+4D8h] [rbp-2C0h] BYREF
  __int64 v225; // [rsp+4E0h] [rbp-2B8h] BYREF
  __int64 v226; // [rsp+4E8h] [rbp-2B0h] BYREF
  __int64 v227; // [rsp+4F0h] [rbp-2A8h] BYREF
  __int64 v228; // [rsp+4F8h] [rbp-2A0h] BYREF
  __int64 v229; // [rsp+500h] [rbp-298h] BYREF
  __int64 v230; // [rsp+508h] [rbp-290h] BYREF
  __int64 v231; // [rsp+510h] [rbp-288h] BYREF
  __int64 v232; // [rsp+518h] [rbp-280h] BYREF
  __int64 v233; // [rsp+520h] [rbp-278h] BYREF
  __int64 v234; // [rsp+528h] [rbp-270h] BYREF
  __int64 v235; // [rsp+530h] [rbp-268h] BYREF
  __int64 v236; // [rsp+538h] [rbp-260h] BYREF
  __int64 v237; // [rsp+540h] [rbp-258h] BYREF
  __int64 v238; // [rsp+548h] [rbp-250h] BYREF
  __int64 v239; // [rsp+550h] [rbp-248h] BYREF
  __int64 v240; // [rsp+558h] [rbp-240h] BYREF
  __int64 v241; // [rsp+560h] [rbp-238h] BYREF
  __int64 v242; // [rsp+568h] [rbp-230h] BYREF
  __int64 v243; // [rsp+570h] [rbp-228h] BYREF
  __int64 v244; // [rsp+578h] [rbp-220h] BYREF
  __int64 v245; // [rsp+580h] [rbp-218h] BYREF
  __int64 v246; // [rsp+588h] [rbp-210h] BYREF
  __int64 v247; // [rsp+590h] [rbp-208h] BYREF
  __int64 v248; // [rsp+598h] [rbp-200h] BYREF
  __int64 v249; // [rsp+5A0h] [rbp-1F8h] BYREF
  __int64 v250; // [rsp+5A8h] [rbp-1F0h] BYREF
  __int64 v251; // [rsp+5B0h] [rbp-1E8h] BYREF
  __int64 v252; // [rsp+5B8h] [rbp-1E0h] BYREF
  __int64 v253; // [rsp+5C0h] [rbp-1D8h] BYREF
  __int64 v254; // [rsp+5C8h] [rbp-1D0h] BYREF
  __int64 v255; // [rsp+5D0h] [rbp-1C8h] BYREF
  __int64 v256; // [rsp+5D8h] [rbp-1C0h] BYREF
  __int64 v257; // [rsp+5E0h] [rbp-1B8h] BYREF
  __int64 v258; // [rsp+5E8h] [rbp-1B0h] BYREF
  __int64 v259; // [rsp+5F0h] [rbp-1A8h] BYREF
  __int64 v260; // [rsp+5F8h] [rbp-1A0h] BYREF
  _QWORD v261[8]; // [rsp+600h] [rbp-198h] BYREF
  __int64 v262; // [rsp+640h] [rbp-158h] BYREF
  __int64 v263; // [rsp+648h] [rbp-150h] BYREF
  __int64 v264; // [rsp+650h] [rbp-148h] BYREF
  __int64 v265; // [rsp+658h] [rbp-140h] BYREF
  _BYTE VersionInformation[284]; // [rsp+660h] [rbp-138h] BYREF

  v13 = 0;
  memset(VersionInformation, 0, sizeof(VersionInformation));
  *(_DWORD *)VersionInformation = 284;
  if ( GetVersionExW((LPOSVERSIONINFOW)VersionInformation) )
  {
    v63 = VersionInformation[282] != 1;
    CSLQuery::bServerSku = v63;
  }
  else
  {
    v128 = g_ProviderToUse;
    v151 = g_ProviderToUse;
    v37 = 0;
    v37 = *g_ProviderToUse;
    v80 = v37;
    if ( v37 > 3 && (unsigned __int8)tlgKeywordOn(v128, 0) )
    {
      LastError = GetLastError();
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v82, &LastError);
      v152 = v82;
      v153 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v221,
                                          (__int64)"GetVersionEx FAILED");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)v128,
        (__int64)&word_1801143DE,
        0,
        0,
        v153,
        (__int64)v152);
    }
  }
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowRemoteConnections", &v13);
  if ( v12 == -1073418222 )
  {
    v129 = g_ProviderToUse;
    v154 = g_ProviderToUse;
    v38 = 0;
    v38 = *g_ProviderToUse;
    v83 = v38;
    if ( v38 > 3 && (unsigned __int8)tlgKeywordOn(v129, 0) )
    {
      v0 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v222,
                                        (__int64)"The SL policy for 'Allow Remote Connections' is not defined - assuming "
                                                 "Reduced Functionality Mode");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v129,
        (unsigned __int8 *)&word_18011495E,
        0,
        0,
        v0);
    }
    v39 = CSLQuery::bServerSku != 0;
    v13 = v39;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v130 = g_ProviderToUse;
    v155 = g_ProviderToUse;
    v40 = 0;
    v40 = *g_ProviderToUse;
    v84 = v40;
    if ( v40 > 3 && (unsigned __int8)tlgKeywordOn(v130, 0) )
    {
      v156 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v223,
                                          (__int64)"Initialize");
      v85 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v86, &v85);
      v157 = v86;
      v158 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v224,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bRemoteConnAllowed");
      v159 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v225,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v130,
        (__int64)byte_180114189,
        0,
        0,
        v159,
        v158,
        (__int64)v157,
        v156);
    }
    return (unsigned int)v12;
  }
  v41 = v13 != 0;
  CSLQuery::bRemoteConnAllowed = v41;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowMultipleSessions", &v13);
  if ( v12 == -1073418222 )
  {
    v131 = g_ProviderToUse;
    v160 = g_ProviderToUse;
    v42 = 0;
    v42 = *g_ProviderToUse;
    v87 = v42;
    if ( v42 > 3 && (unsigned __int8)tlgKeywordOn(v131, 0) )
    {
      v1 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v226,
                                        (__int64)"The SL policy for 'Allow Multiple Sessions' is not defined - assuming R"
                                                 "educed Functionality Mode");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v131,
        (unsigned __int8 *)&word_1801148F2,
        0,
        0,
        v1);
    }
    v43 = CSLQuery::bServerSku != 0;
    v13 = v43;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v132 = g_ProviderToUse;
    v161 = g_ProviderToUse;
    v44 = 0;
    v44 = *g_ProviderToUse;
    v88 = v44;
    if ( v44 > 3 && (unsigned __int8)tlgKeywordOn(v132, 0) )
    {
      v162 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v227,
                                          (__int64)"Initialize");
      v89 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v90, &v89);
      v163 = v90;
      v164 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v228,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bFUSEnabled");
      v165 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v229,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v132,
        (__int64)byte_18011479D,
        0,
        0,
        v165,
        v164,
        (__int64)v163,
        v162);
    }
    return (unsigned int)v12;
  }
  v45 = v13 != 0;
  CSLQuery::bFUSEnabled = v45;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowAppServerMode", &v13);
  if ( v12 == -1073418222 )
  {
    v133 = g_ProviderToUse;
    v166 = g_ProviderToUse;
    v46 = 0;
    v46 = *g_ProviderToUse;
    v91 = v46;
    if ( v46 > 3 && (unsigned __int8)tlgKeywordOn(v133, 0) )
    {
      v2 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v230,
                                        (__int64)"The SL policy for 'Allow Multiple Sessions' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v133,
        (unsigned __int8 *)&word_180114576,
        0,
        0,
        v2);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v92 = 0;
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v134 = g_ProviderToUse;
    v167 = g_ProviderToUse;
    v47 = 0;
    v47 = *g_ProviderToUse;
    v93 = v47;
    if ( v47 > 3 && (unsigned __int8)tlgKeywordOn(v134, 0) )
    {
      v168 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v231,
                                          (__int64)"Initialize");
      v94 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v95, &v94);
      v169 = v95;
      v170 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v232,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAppServerAllowed");
      v171 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v233,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v134,
        (__int64)byte_180114403,
        0,
        0,
        v171,
        v170,
        (__int64)v169,
        v168);
    }
    return (unsigned int)v12;
  }
  v48 = v13 != 0;
  CSLQuery::bAppServerAllowed = v48;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-AutomatedAppServerInstallation",
          &v13);
  if ( v12 == -1073418222 )
  {
    v135 = g_ProviderToUse;
    v172 = g_ProviderToUse;
    v49 = 0;
    v49 = *g_ProviderToUse;
    v96 = v49;
    if ( v49 > 3 && (unsigned __int8)tlgKeywordOn(v135, 0) )
    {
      v3 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v234,
                                        (__int64)"The SL policy for 'Automated App Server Installation' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v135,
        (unsigned __int8 *)byte_18011404C,
        0,
        0,
        v3);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v136 = g_ProviderToUse;
    v173 = g_ProviderToUse;
    v50 = 0;
    v50 = *g_ProviderToUse;
    v97 = v50;
    if ( v50 > 3 && (unsigned __int8)tlgKeywordOn(v136, 0) )
    {
      v174 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v235,
                                          (__int64)"Initialize");
      v98 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v99, &v98);
      v175 = v99;
      v176 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v236,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAutomatedApp"
                                                   "ServerInstallation");
      v177 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v237,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v136,
        (__int64)&byte_18011497F,
        0,
        0,
        v177,
        v176,
        (__int64)v175,
        v174);
    }
    return (unsigned int)v12;
  }
  v51 = v13 != 0;
  CSLQuery::bAutomatedAppServerInstallation = v51;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowMultimon", &v13);
  if ( v12 == -1073418222 )
  {
    v137 = g_ProviderToUse;
    v178 = g_ProviderToUse;
    v52 = 0;
    v52 = *g_ProviderToUse;
    v100 = v52;
    if ( v52 > 3 && (unsigned __int8)tlgKeywordOn(v137, 0) )
    {
      v4 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v238,
                                        (__int64)"The SL policy for 'Allow Multiple Monitors' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v137,
        (unsigned __int8 *)byte_18011460D,
        0,
        0,
        v4);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v138 = g_ProviderToUse;
    v179 = g_ProviderToUse;
    v53 = 0;
    v53 = *g_ProviderToUse;
    v101 = v53;
    if ( v53 > 3 && (unsigned __int8)tlgKeywordOn(v138, 0) )
    {
      v180 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v239,
                                          (__int64)"Initialize");
      v102 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v103, &v102);
      v181 = v103;
      v182 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v240,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bMultimonAllowed");
      v183 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v241,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v138,
        (__int64)&word_18011462E,
        0,
        0,
        v183,
        v182,
        (__int64)v181,
        v180);
    }
    return (unsigned int)v12;
  }
  v54 = v13 != 0;
  CSLQuery::bMultimonAllowed = v54;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-ADD-Licensing", &v13);
  if ( v12 == -1073418222 )
  {
    v139 = g_ProviderToUse;
    v184 = g_ProviderToUse;
    v55 = 0;
    v55 = *g_ProviderToUse;
    v104 = v55;
    if ( v55 > 3 && (unsigned __int8)tlgKeywordOn(v139, 0) )
    {
      v5 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v242,
                                        (__int64)"The SL policy for 'Allow AAD Licensing' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v139,
        (unsigned __int8 *)byte_180113F80,
        0,
        0,
        v5);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v140 = g_ProviderToUse;
    v185 = g_ProviderToUse;
    v56 = 0;
    v56 = *g_ProviderToUse;
    v105 = v56;
    if ( v56 > 3 && (unsigned __int8)tlgKeywordOn(v140, 0) )
    {
      v186 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v243,
                                          (__int64)"Initialize");
      v106 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v107, &v106);
      v187 = v107;
      v188 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v244,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAllowAADLicensing");
      v189 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v245,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v140,
        (__int64)&word_1801145D2,
        0,
        0,
        v189,
        v188,
        (__int64)v187,
        v186);
    }
    return (unsigned int)v12;
  }
  v57 = v13 != 0;
  CSLQuery::bAllowAADLicensing = v57;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-MaxUserSessions", &v13);
  if ( v12 == -1073418222 )
  {
    v141 = g_ProviderToUse;
    v190 = g_ProviderToUse;
    v58 = 0;
    v58 = *g_ProviderToUse;
    v108 = v58;
    if ( v58 > 3 && (unsigned __int8)tlgKeywordOn(v141, 0) )
    {
      v6 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v246,
                                        (__int64)"The SL policy for 'Max User Sessions' is not defined - assuming no limi"
                                                 "t to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v141,
        (unsigned __int8 *)byte_18011402B,
        0,
        0,
        v6);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v142 = g_ProviderToUse;
    v191 = g_ProviderToUse;
    v59 = 0;
    v59 = *g_ProviderToUse;
    v109 = v59;
    if ( v59 > 3 && (unsigned __int8)tlgKeywordOn(v142, 0) )
    {
      v192 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v247,
                                          (__int64)"Initialize");
      v110 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v111, &v110);
      v193 = v111;
      v194 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v248,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for lMaxUserSessions");
      v195 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v249,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v142,
        (__int64)&word_1801149BA,
        0,
        0,
        v195,
        v194,
        (__int64)v193,
        v192);
    }
    return (unsigned int)v12;
  }
  CSLQuery::lMaxUserSessions = v13;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-ce0ad219-4670-4988-98fb-89b14c2f072b-MaxSessions",
          &v13);
  if ( v12 == -1073418222 )
  {
    v143 = g_ProviderToUse;
    v196 = g_ProviderToUse;
    v60 = 0;
    v60 = *g_ProviderToUse;
    v112 = v60;
    if ( v60 > 3 && (unsigned __int8)tlgKeywordOn(v143, 0) )
    {
      v7 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v250,
                                        (__int64)"The SL policy for 'Max Debug Sessions' is not defined - assuming no lim"
                                                 "it to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v143,
        (unsigned __int8 *)&word_1801140F2,
        0,
        0,
        v7);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v144 = g_ProviderToUse;
    v197 = g_ProviderToUse;
    v61 = 0;
    v61 = *g_ProviderToUse;
    v113 = v61;
    if ( v61 > 3 && (unsigned __int8)tlgKeywordOn(v144, 0) )
    {
      v198 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v251,
                                          (__int64)"Initialize");
      v114 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v115, &v114);
      v199 = v115;
      v200 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v252,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxDebugSessions");
      v201 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v253,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v144,
        (__int64)&byte_1801140B7,
        0,
        0,
        v201,
        v200,
        (__int64)v199,
        v198);
    }
    return (unsigned int)v12;
  }
  CSLQuery::ulMaxDebugSessions = v13;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"Kernel-OneCore-VailGuest", &v13);
  if ( v12 == -1073418222 )
  {
    v145 = g_ProviderToUse;
    v202 = g_ProviderToUse;
    v62 = 0;
    v62 = *g_ProviderToUse;
    v116 = v62;
    if ( v62 > 3 && (unsigned __int8)tlgKeywordOn(v145, 0) )
    {
      v8 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v254,
                                        (__int64)"The SL policy for 'VAIL Guest Policy' is not defined - assuming not in VAIL");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v145,
        (unsigned __int8 *)byte_1801143BD,
        0,
        0,
        v8);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v146 = g_ProviderToUse;
    v203 = g_ProviderToUse;
    v71 = 0;
    v71 = *g_ProviderToUse;
    v117 = v71;
    if ( v71 > 3 && (unsigned __int8)tlgKeywordOn(v146, 0) )
    {
      v204 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v255,
                                          (__int64)"Initialize");
      v118 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v119, &v118);
      v205 = v119;
      v206 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v256,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bVailGuest");
      v207 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v257,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v146,
        (__int64)&byte_180114597,
        0,
        0,
        v207,
        v206,
        (__int64)v205,
        v204);
    }
    return (unsigned int)v12;
  }
  CSLQuery::bVailGuest = v13;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-WVD-Enabled", &v13);
  if ( v12 == -1073418222 )
  {
    v147 = g_ProviderToUse;
    v208 = g_ProviderToUse;
    v64 = 0;
    v64 = *g_ProviderToUse;
    v120 = v64;
    if ( v64 > 3 && (unsigned __int8)tlgKeywordOn(v147, 0) )
    {
      v9 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v258,
                                        (__int64)"The SL policy for 'WVD Enabled' is not defined - assuming WVD is disabled");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v147,
        (unsigned __int8 *)byte_180114820,
        0,
        0,
        v9);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v148 = g_ProviderToUse;
    v209 = g_ProviderToUse;
    v65 = 0;
    v65 = *g_ProviderToUse;
    v121 = v65;
    if ( v65 > 3 && (unsigned __int8)tlgKeywordOn(v148, 0) )
    {
      v210 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v259,
                                          (__int64)"Initialize");
      v122 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v123, &v122);
      v211 = v123;
      v212 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          &v260,
                                          (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for bWVDEnabled");
      v213 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                          v261,
                                          (__int64)"Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v148,
        (__int64)byte_1801142B0,
        0,
        0,
        v213,
        v212,
        (__int64)v211,
        v210);
    }
    return (unsigned int)v12;
  }
  v66 = v13 != 0;
  CSLQuery::bWVDEnabled = v66;
  v214 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v36 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v261[1] = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v261[2] = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  _scrt_stub_for_acrt_uninitialize_critical(`wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl);
  v261[5] = v36;
  v261[6] = v36;
  v261[7] = v36;
  v14 = 1;
  v67 = 1;
  v15 = 1;
  v16 = 1;
  v17 = 1;
  v68 = 1;
  v18 = 1;
  v19 = 1;
  v69 = 1;
  v20 = 1;
  v21 = 1;
  v70 = 1;
  v22 = 1;
  v79 = 1;
  v23 = 1;
  v24 = 1;
  v72 = 1;
  v25 = 1;
  v26 = 1;
  v27 = 1;
  v28 = 1;
  v73 = 1;
  v29 = 1;
  v74 = 1;
  v30 = 1;
  v31 = 1;
  v75 = 1;
  v32 = 1;
  v33 = 1;
  v76 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(v36) != 0;
  v34 = v76;
  v35 = v76;
  if ( !v76 )
  {
LABEL_118:
    CSLQuery::bInitialized = 1;
    return (unsigned int)v12;
  }
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-cd051c59-3fe7-499c-9b66-02d99dbd8d3b-MaxSessions",
          &v13);
  if ( v12 == -1073418222 )
  {
    v149 = g_ProviderToUse;
    v215 = g_ProviderToUse;
    v77 = 0;
    v77 = *g_ProviderToUse;
    v124 = v77;
    if ( v77 > 3 && (unsigned __int8)tlgKeywordOn(v149, 0) )
    {
      v10 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                         &v262,
                                         (__int64)"The SL policy for 'Max Agent Sessions' is not defined - assuming no li"
                                                  "mit to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v149,
        (unsigned __int8 *)&word_18011400A,
        0,
        0,
        v10);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 >= 0 )
  {
    CSLQuery::ulMaxAgentSessions = v13;
    goto LABEL_118;
  }
  v150 = g_ProviderToUse;
  v216 = g_ProviderToUse;
  v78 = 0;
  v78 = *g_ProviderToUse;
  v125 = v78;
  if ( v78 > 3 && (unsigned __int8)tlgKeywordOn(v150, 0) )
  {
    v217 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v263,
                                        (__int64)"Initialize");
    v126 = v12;
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v127, &v126);
    v218 = v127;
    v219 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v264,
                                        (__int64)"CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxAgentSessions");
    v220 = (const unsigned __int16 **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                        &v265,
                                        (__int64)"Warning HResult failed");
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)v150,
      (__int64)byte_1801141C4,
      0,
      0,
      v220,
      v219,
      (__int64)v218,
      v217);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800af3a4  push    rdi
0x1800af3a6  sub     rsp, 790h
0x1800af3ad  mov     rax, cs:__security_cookie
0x1800af3b4  xor     rax, rsp
0x1800af3b7  mov     [rsp+798h+var_18], rax
0x1800af3bf  mov     [rsp+798h+var_758], 80004001h
0x1800af3c7  mov     [rsp+798h+var_754], 0
0x1800af3cf  lea     rax, [rsp+798h+VersionInformation]
0x1800af3d7  mov     rdi, rax
0x1800af3da  xor     eax, eax
0x1800af3dc  mov     ecx, 11Ch
0x1800af3e1  rep stosb
0x1800af3e3  mov     [rsp+798h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800af3ee  lea     rcx, [rsp+798h+VersionInformation]; lpVersionInformation
0x1800af3f6  call    cs:__imp_GetVersionExW
0x1800af3fc  test    eax, eax
0x1800af3fe  jz      short loc_1800AF437
0x1800af400  movzx   eax, [rsp+798h+var_1E]
0x1800af408  cmp     eax, 1
0x1800af40b  jnz     short loc_1800AF41A
0x1800af40d  mov     [rsp+798h+var_6C8], 0
0x1800af418  jmp     short loc_1800AF425
0x1800af41a  mov     [rsp+798h+var_6C8], 1
0x1800af425  mov     eax, [rsp+798h+var_6C8]
0x1800af42c  mov     cs:?bServerSku@CSLQuery@@0HA, eax; int CSLQuery::bServerSku
0x1800af432  jmp     loc_1800AF534
0x1800af437  mov     rax, cs:g_ProviderToUse
0x1800af43e  mov     [rsp+798h+var_5C0], rax
0x1800af446  mov     rax, [rsp+798h+var_5C0]
0x1800af44e  mov     [rsp+798h+var_508], rax
0x1800af456  mov     [rsp+798h+var_730], 0
0x1800af45e  mov     rax, [rsp+798h+var_508]
0x1800af466  mov     eax, [rax]
0x1800af468  mov     [rsp+798h+var_730], eax
0x1800af46c  mov     eax, [rsp+798h+var_730]
0x1800af470  mov     [rsp+798h+var_684], eax
0x1800af477  mov     eax, [rsp+798h+var_684]
0x1800af47e  cmp     eax, 3
0x1800af481  jbe     loc_1800AF52A
0x1800af487  mov     rdx, cs:qword_1801143E1
0x1800af48e  mov     rcx, [rsp+798h+var_5C0]
0x1800af496  call    _tlgKeywordOn
0x1800af49b  movzx   eax, al
0x1800af49e  test    eax, eax
0x1800af4a0  jz      loc_1800AF52A
0x1800af4a6  call    cs:__imp_GetLastError
0x1800af4ac  mov     [rsp+798h+var_680], eax
0x1800af4b3  lea     rdx, [rsp+798h+var_680]
0x1800af4bb  lea     rcx, [rsp+798h+var_67C]
0x1800af4c3  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800af4c8  nop
0x1800af4c9  lea     rax, [rsp+798h+var_67C]
0x1800af4d1  mov     [rsp+798h+var_500], rax
0x1800af4d9  lea     rdx, aGetversionexFa; "GetVersionEx FAILED"
0x1800af4e0  lea     rcx, [rsp+798h+var_2D8]
0x1800af4e8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af4ed  mov     [rsp+798h+var_4F8], rax
0x1800af4f5  mov     rax, [rsp+798h+var_500]
0x1800af4fd  mov     [rsp+798h+var_770], rax
0x1800af502  mov     rax, [rsp+798h+var_4F8]
0x1800af50a  mov     [rsp+798h+var_778], rax
0x1800af50f  xor     r9d, r9d
0x1800af512  xor     r8d, r8d
0x1800af515  lea     rdx, word_1801143DE
0x1800af51c  mov     rcx, [rsp+798h+var_5C0]
0x1800af524  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800af529  nop
0x1800af52a  xor     eax, eax
0x1800af52c  test    eax, eax
0x1800af52e  jnz     loc_1800AF437
0x1800af534  mov     [rsp+798h+var_754], 0
0x1800af53c  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x1800af541  lea     rcx, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x1800af548  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
0x1800af54d  mov     [rsp+798h+var_758], eax
0x1800af551  cmp     [rsp+798h+var_758], 0C004F012h
0x1800af559  jnz     loc_1800AF62F
0x1800af55f  mov     rax, cs:g_ProviderToUse
0x1800af566  mov     [rsp+798h+var_5B8], rax
0x1800af56e  mov     rax, [rsp+798h+var_5B8]
0x1800af576  mov     [rsp+798h+var_4F0], rax
0x1800af57e  mov     [rsp+798h+var_72C], 0
0x1800af586  mov     rax, [rsp+798h+var_4F0]
0x1800af58e  mov     eax, [rax]
0x1800af590  mov     [rsp+798h+var_72C], eax
0x1800af594  mov     eax, [rsp+798h+var_72C]
0x1800af598  mov     [rsp+798h+var_678], eax
0x1800af59f  mov     eax, [rsp+798h+var_678]
0x1800af5a6  cmp     eax, 3
0x1800af5a9  jbe     short loc_1800AF5FA
0x1800af5ab  mov     rdx, cs:qword_180114961
0x1800af5b2  mov     rcx, [rsp+798h+var_5B8]
0x1800af5ba  call    _tlgKeywordOn
0x1800af5bf  movzx   eax, al
0x1800af5c2  test    eax, eax
0x1800af5c4  jz      short loc_1800AF5FA
0x1800af5c6  lea     rdx, aTheSlPolicyFor_3; "The SL policy for 'Allow Remote Connect"...
0x1800af5cd  lea     rcx, [rsp+798h+var_2D0]
0x1800af5d5  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af5da  mov     [rsp+798h+var_778], rax
0x1800af5df  xor     r9d, r9d
0x1800af5e2  xor     r8d, r8d
0x1800af5e5  lea     rdx, word_18011495E
0x1800af5ec  mov     rcx, [rsp+798h+var_5B8]
0x1800af5f4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800af5f9  nop
0x1800af5fa  xor     eax, eax
0x1800af5fc  test    eax, eax
0x1800af5fe  jnz     loc_1800AF55F
0x1800af604  cmp     cs:?bServerSku@CSLQuery@@0HA, 0; int CSLQuery::bServerSku
0x1800af60b  jz      short loc_1800AF617
0x1800af60d  mov     [rsp+798h+var_728], 1
0x1800af615  jmp     short loc_1800AF61F
0x1800af617  mov     [rsp+798h+var_728], 0
0x1800af61f  mov     eax, [rsp+798h+var_728]
0x1800af623  mov     [rsp+798h+var_754], eax
0x1800af627  mov     [rsp+798h+var_758], 0
0x1800af62f  cmp     [rsp+798h+var_758], 0
0x1800af634  jge     loc_1800AF78C
0x1800af63a  mov     rax, cs:g_ProviderToUse
0x1800af641  mov     [rsp+798h+var_5B0], rax
0x1800af649  mov     rax, [rsp+798h+var_5B0]
0x1800af651  mov     [rsp+798h+var_4E8], rax
0x1800af659  mov     [rsp+798h+var_724], 0
0x1800af661  mov     rax, [rsp+798h+var_4E8]
0x1800af669  mov     eax, [rax]
0x1800af66b  mov     [rsp+798h+var_724], eax
0x1800af66f  mov     eax, [rsp+798h+var_724]
0x1800af673  mov     [rsp+798h+var_674], eax
0x1800af67a  mov     eax, [rsp+798h+var_674]
0x1800af681  cmp     eax, 3
0x1800af684  jbe     loc_1800AF77D
0x1800af68a  mov     rdx, cs:qword_18011418C
0x1800af691  mov     rcx, [rsp+798h+var_5B0]
0x1800af699  call    _tlgKeywordOn
0x1800af69e  movzx   eax, al
0x1800af6a1  test    eax, eax
0x1800af6a3  jz      loc_1800AF77D
0x1800af6a9  lea     rdx, aInitialize; "Initialize"
0x1800af6b0  lea     rcx, [rsp+798h+var_2C8]
0x1800af6b8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af6bd  mov     [rsp+798h+var_4E0], rax
0x1800af6c5  mov     eax, [rsp+798h+var_758]
0x1800af6c9  mov     [rsp+798h+var_670], eax
0x1800af6d0  lea     rdx, [rsp+798h+var_670]
0x1800af6d8  lea     rcx, [rsp+798h+var_66C]
0x1800af6e0  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800af6e5  nop
0x1800af6e6  lea     rax, [rsp+798h+var_66C]
0x1800af6ee  mov     [rsp+798h+var_4D8], rax
0x1800af6f6  lea     rdx, aCslqueryInitia_2; "CSLQuery::Initialize - SLGetWindowsInfo"...
0x1800af6fd  lea     rcx, [rsp+798h+var_2C0]
0x1800af705  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af70a  mov     [rsp+798h+var_4D0], rax
0x1800af712  lea     rdx, aWarningHresult; "Warning HResult failed"
0x1800af719  lea     rcx, [rsp+798h+var_2B8]
0x1800af721  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af726  mov     [rsp+798h+var_4C8], rax
0x1800af72e  mov     rax, [rsp+798h+var_4E0]
0x1800af736  mov     [rsp+798h+var_760], rax
0x1800af73b  mov     rax, [rsp+798h+var_4D8]
0x1800af743  mov     [rsp+798h+var_768], rax
0x1800af748  mov     rax, [rsp+798h+var_4D0]
0x1800af750  mov     [rsp+798h+var_770], rax
0x1800af755  mov     rax, [rsp+798h+var_4C8]
0x1800af75d  mov     [rsp+798h+var_778], rax
0x1800af762  xor     r9d, r9d
0x1800af765  xor     r8d, r8d
0x1800af768  lea     rdx, byte_180114189
0x1800af76f  mov     rcx, [rsp+798h+var_5B0]
0x1800af777  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800af77c  nop
0x1800af77d  xor     eax, eax
0x1800af77f  test    eax, eax
0x1800af781  jnz     loc_1800AF63A
0x1800af787  jmp     loc_1800B13D2
0x1800af78c  cmp     [rsp+798h+var_754], 0
0x1800af791  jz      short loc_1800AF79D
0x1800af793  mov     [rsp+798h+var_720], 1
0x1800af79b  jmp     short loc_1800AF7A5
0x1800af79d  mov     [rsp+798h+var_720], 0
0x1800af7a5  mov     eax, [rsp+798h+var_720]
0x1800af7a9  mov     cs:?bRemoteConnAllowed@CSLQuery@@0HA, eax; int CSLQuery::bRemoteConnAllowed
0x1800af7af  mov     [rsp+798h+var_754], 0
0x1800af7b7  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x1800af7bc  lea     rcx, aTerminalservic_4; "TerminalServices-RemoteConnectionManage"...
0x1800af7c3  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
0x1800af7c8  mov     [rsp+798h+var_758], eax
0x1800af7cc  cmp     [rsp+798h+var_758], 0C004F012h
0x1800af7d4  jnz     loc_1800AF8B3
0x1800af7da  mov     rax, cs:g_ProviderToUse
0x1800af7e1  mov     [rsp+798h+var_5A8], rax
0x1800af7e9  mov     rax, [rsp+798h+var_5A8]
0x1800af7f1  mov     [rsp+798h+var_4C0], rax
0x1800af7f9  mov     [rsp+798h+var_71C], 0
0x1800af801  mov     rax, [rsp+798h+var_4C0]
0x1800af809  mov     eax, [rax]
0x1800af80b  mov     [rsp+798h+var_71C], eax
0x1800af80f  mov     eax, [rsp+798h+var_71C]
0x1800af813  mov     [rsp+798h+var_668], eax
0x1800af81a  mov     eax, [rsp+798h+var_668]
0x1800af821  cmp     eax, 3
0x1800af824  jbe     short loc_1800AF875
0x1800af826  mov     rdx, cs:qword_1801148F5
0x1800af82d  mov     rcx, [rsp+798h+var_5A8]
0x1800af835  call    _tlgKeywordOn
0x1800af83a  movzx   eax, al
0x1800af83d  test    eax, eax
0x1800af83f  jz      short loc_1800AF875
0x1800af841  lea     rdx, aTheSlPolicyFor_2; "The SL policy for 'Allow Multiple Sessi"...
0x1800af848  lea     rcx, [rsp+798h+var_2B0]
0x1800af850  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af855  mov     [rsp+798h+var_778], rax
0x1800af85a  xor     r9d, r9d
0x1800af85d  xor     r8d, r8d
0x1800af860  lea     rdx, word_1801148F2
0x1800af867  mov     rcx, [rsp+798h+var_5A8]
0x1800af86f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800af874  nop
0x1800af875  xor     eax, eax
0x1800af877  test    eax, eax
0x1800af879  jnz     loc_1800AF7DA
0x1800af87f  cmp     cs:?bServerSku@CSLQuery@@0HA, 0; int CSLQuery::bServerSku
0x1800af886  jz      short loc_1800AF895
0x1800af888  mov     [rsp+798h+var_718], 1
0x1800af893  jmp     short loc_1800AF8A0
0x1800af895  mov     [rsp+798h+var_718], 0
0x1800af8a0  mov     eax, [rsp+798h+var_718]
0x1800af8a7  mov     [rsp+798h+var_754], eax
0x1800af8ab  mov     [rsp+798h+var_758], 0
0x1800af8b3  cmp     [rsp+798h+var_758], 0
0x1800af8b8  jge     loc_1800AFA19
0x1800af8be  mov     rax, cs:g_ProviderToUse
0x1800af8c5  mov     [rsp+798h+var_5A0], rax
0x1800af8cd  mov     rax, [rsp+798h+var_5A0]
0x1800af8d5  mov     [rsp+798h+var_4B8], rax
0x1800af8dd  mov     [rsp+798h+var_714], 0
0x1800af8e8  mov     rax, [rsp+798h+var_4B8]
0x1800af8f0  mov     eax, [rax]
0x1800af8f2  mov     [rsp+798h+var_714], eax
0x1800af8f9  mov     eax, [rsp+798h+var_714]
0x1800af900  mov     [rsp+798h+var_664], eax
0x1800af907  mov     eax, [rsp+798h+var_664]
0x1800af90e  cmp     eax, 3
0x1800af911  jbe     loc_1800AFA0A
0x1800af917  mov     rdx, cs:qword_1801147A0
0x1800af91e  mov     rcx, [rsp+798h+var_5A0]
0x1800af926  call    _tlgKeywordOn
0x1800af92b  movzx   eax, al
0x1800af92e  test    eax, eax
0x1800af930  jz      loc_1800AFA0A
0x1800af936  lea     rdx, aInitialize; "Initialize"
0x1800af93d  lea     rcx, [rsp+798h+var_2A8]
0x1800af945  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af94a  mov     [rsp+798h+var_4B0], rax
0x1800af952  mov     eax, [rsp+798h+var_758]
0x1800af956  mov     [rsp+798h+var_660], eax
0x1800af95d  lea     rdx, [rsp+798h+var_660]
0x1800af965  lea     rcx, [rsp+798h+var_65C]
0x1800af96d  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800af972  nop
0x1800af973  lea     rax, [rsp+798h+var_65C]
0x1800af97b  mov     [rsp+798h+var_4A8], rax
0x1800af983  lea     rdx, aCslqueryInitia_4; "CSLQuery::Initialize - SLGetWindowsInfo"...
0x1800af98a  lea     rcx, [rsp+798h+var_2A0]
0x1800af992  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af997  mov     [rsp+798h+var_4A0], rax
0x1800af99f  lea     rdx, aWarningHresult; "Warning HResult failed"
0x1800af9a6  lea     rcx, [rsp+798h+var_298]
0x1800af9ae  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af9b3  mov     [rsp+798h+var_498], rax
0x1800af9bb  mov     rax, [rsp+798h+var_4B0]
0x1800af9c3  mov     [rsp+798h+var_760], rax
0x1800af9c8  mov     rax, [rsp+798h+var_4A8]
0x1800af9d0  mov     [rsp+798h+var_768], rax
0x1800af9d5  mov     rax, [rsp+798h+var_4A0]
0x1800af9dd  mov     [rsp+798h+var_770], rax
0x1800af9e2  mov     rax, [rsp+798h+var_498]
0x1800af9ea  mov     [rsp+798h+var_778], rax
0x1800af9ef  xor     r9d, r9d
0x1800af9f2  xor     r8d, r8d
0x1800af9f5  lea     rdx, byte_18011479D
0x1800af9fc  mov     rcx, [rsp+798h+var_5A0]
0x1800afa04  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800afa09  nop
0x1800afa0a  xor     eax, eax
0x1800afa0c  test    eax, eax
0x1800afa0e  jnz     loc_1800AF8BE
0x1800afa14  jmp     loc_1800B13D2
0x1800afa19  cmp     [rsp+798h+var_754], 0
0x1800afa1e  jz      short loc_1800AFA2D
0x1800afa20  mov     [rsp+798h+var_710], 1
0x1800afa2b  jmp     short loc_1800AFA38
0x1800afa2d  mov     [rsp+798h+var_710], 0
0x1800afa38  mov     eax, [rsp+798h+var_710]
0x1800afa3f  mov     cs:?bFUSEnabled@CSLQuery@@0HA, eax; int CSLQuery::bFUSEnabled
0x1800afa45  mov     [rsp+798h+var_754], 0
0x1800afa4d  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x1800afa52  lea     rcx, aTerminalservic_9; "TerminalServices-RemoteConnectionManage"...
0x1800afa59  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
  ... truncated ...
```
