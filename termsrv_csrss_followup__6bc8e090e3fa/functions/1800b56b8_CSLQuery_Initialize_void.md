# CSLQuery::Initialize(void)

- ea: `0x1800b56b8`
- end: `0x1800b7710`
- name: `?Initialize@CSLQuery@@SAJXZ`
- size: `8280`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a260`
- `0x1800a4044`
- `0x1800af148`
- `0x1800af20c`
- `0x1800b5520`
- `0x1800b7718`
- `0x1800b77d4`
- `0x1800b7890`
- `0x1800b7a6c`
- `0x1800bdcc0`
- `0x1800bdd80`

## callees

- `0x1800015c4`
- `0x18000255c`
- `0x18000256c`
- `0x180005314`
- `0x18000542c`
- `0x180012210`
- `0x18001ed70`
- `0x180033f60`
- `0x1800519e8`
- `0x180051c10`
- `0x1800b56b8`
- `0x1800ca374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b57c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b57c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800b570a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800b570a`

## string_xrefs

- `0x1800b5861`: `TerminalServices-RemoteConnectionManager-AllowRemoteConnections`
- `0x1800b5adc`: `TerminalServices-RemoteConnectionManager-AllowMultipleSessions`
- `0x1800b5d72`: `TerminalServices-RemoteConnectionManager-AllowAppServerMode`
- `0x1800b6011`: `TerminalServices-RemoteConnectionManager-AutomatedAppServerInstallation`
- `0x1800b61bd`: `CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAutomatedAppServerInstallation`
- `0x1800b609f`: `The SL policy for 'Automated App Server Installation' is not defined - assuming FALSE`
- `0x1800b628c`: `TerminalServices-RemoteConnectionManager-AllowMultimon`
- `0x1800b6507`: `TerminalServices-ADD-Licensing`
- `0x1800b6782`: `TerminalServices-RemoteConnectionManager-MaxUserSessions`
- `0x1800b69db`: `TerminalServices-RemoteConnectionManager-ce0ad219-4670-4988-98fb-89b14c2f072b-MaxSessions`
- `0x1800b6e8d`: `TerminalServices-RemoteConnectionManager-WVD-Enabled`
- `0x1800b752d`: `The SL policy for 'Max Agent Sessions' is not defined - assuming no limit to user sessions`
- `0x1800b749f`: `TerminalServices-RemoteConnectionManager-cd051c59-3fe7-499c-9b66-02d99dbd8d3b-MaxSessions`
- `0x1800b764b`: `CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxAgentSessions`

## pseudocode

```c
__int64 CSLQuery::Initialize(void)
{
  __int64 v0; // r8
  __int64 v1; // r8
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  int v24; // [rsp+40h] [rbp-758h]
  unsigned int v25; // [rsp+44h] [rbp-754h] BYREF
  char v26; // [rsp+48h] [rbp-750h]
  char v27; // [rsp+49h] [rbp-74Fh]
  char v28; // [rsp+4Ah] [rbp-74Eh]
  char v29; // [rsp+4Bh] [rbp-74Dh]
  char v30; // [rsp+4Ch] [rbp-74Ch]
  char v31; // [rsp+4Dh] [rbp-74Bh]
  char v32; // [rsp+4Eh] [rbp-74Ah]
  char v33; // [rsp+4Fh] [rbp-749h]
  char v34; // [rsp+50h] [rbp-748h]
  char v35; // [rsp+51h] [rbp-747h]
  char v36; // [rsp+52h] [rbp-746h]
  char v37; // [rsp+53h] [rbp-745h]
  char v38; // [rsp+54h] [rbp-744h]
  char v39; // [rsp+55h] [rbp-743h]
  char v40; // [rsp+56h] [rbp-742h]
  char v41; // [rsp+57h] [rbp-741h]
  char v42; // [rsp+58h] [rbp-740h]
  char v43; // [rsp+59h] [rbp-73Fh]
  char v44; // [rsp+5Ah] [rbp-73Eh]
  char v45; // [rsp+5Bh] [rbp-73Dh]
  bool v46; // [rsp+5Ch] [rbp-73Ch]
  bool v47; // [rsp+5Dh] [rbp-73Bh]
  __int64 *v48; // [rsp+60h] [rbp-738h]
  unsigned int v49; // [rsp+68h] [rbp-730h]
  unsigned int v50; // [rsp+6Ch] [rbp-72Ch]
  unsigned int v51; // [rsp+70h] [rbp-728h]
  unsigned int v52; // [rsp+74h] [rbp-724h]
  BOOL v53; // [rsp+78h] [rbp-720h]
  unsigned int v54; // [rsp+7Ch] [rbp-71Ch]
  unsigned int v55; // [rsp+80h] [rbp-718h]
  unsigned int v56; // [rsp+84h] [rbp-714h]
  BOOL v57; // [rsp+88h] [rbp-710h]
  unsigned int v58; // [rsp+8Ch] [rbp-70Ch]
  unsigned int v59; // [rsp+90h] [rbp-708h]
  BOOL v60; // [rsp+94h] [rbp-704h]
  unsigned int v61; // [rsp+98h] [rbp-700h]
  unsigned int v62; // [rsp+9Ch] [rbp-6FCh]
  BOOL v63; // [rsp+A0h] [rbp-6F8h]
  unsigned int v64; // [rsp+A4h] [rbp-6F4h]
  unsigned int v65; // [rsp+A8h] [rbp-6F0h]
  BOOL v66; // [rsp+ACh] [rbp-6ECh]
  unsigned int v67; // [rsp+B0h] [rbp-6E8h]
  unsigned int v68; // [rsp+B4h] [rbp-6E4h]
  BOOL v69; // [rsp+B8h] [rbp-6E0h]
  unsigned int v70; // [rsp+BCh] [rbp-6DCh]
  unsigned int v71; // [rsp+C0h] [rbp-6D8h]
  unsigned int v72; // [rsp+C4h] [rbp-6D4h]
  unsigned int v73; // [rsp+C8h] [rbp-6D0h]
  unsigned int v74; // [rsp+CCh] [rbp-6CCh]
  BOOL v75; // [rsp+D0h] [rbp-6C8h]
  unsigned int v76; // [rsp+D4h] [rbp-6C4h]
  unsigned int v77; // [rsp+D8h] [rbp-6C0h]
  BOOL v78; // [rsp+DCh] [rbp-6BCh]
  int v79; // [rsp+E0h] [rbp-6B8h]
  int v80; // [rsp+E4h] [rbp-6B4h]
  int v81; // [rsp+E8h] [rbp-6B0h]
  int v82; // [rsp+ECh] [rbp-6ACh]
  unsigned int v83; // [rsp+F0h] [rbp-6A8h]
  int v84; // [rsp+F4h] [rbp-6A4h]
  int v85; // [rsp+F8h] [rbp-6A0h]
  int v86; // [rsp+FCh] [rbp-69Ch]
  int v87; // [rsp+100h] [rbp-698h]
  BOOL v88; // [rsp+104h] [rbp-694h]
  unsigned int v89; // [rsp+108h] [rbp-690h]
  unsigned int v90; // [rsp+10Ch] [rbp-68Ch]
  int v91; // [rsp+110h] [rbp-688h]
  unsigned int v92; // [rsp+114h] [rbp-684h]
  DWORD LastError; // [rsp+118h] [rbp-680h] BYREF
  _BYTE v94[4]; // [rsp+11Ch] [rbp-67Ch] BYREF
  unsigned int v95; // [rsp+120h] [rbp-678h]
  unsigned int v96; // [rsp+124h] [rbp-674h]
  int v97; // [rsp+128h] [rbp-670h] BYREF
  _BYTE v98[4]; // [rsp+12Ch] [rbp-66Ch] BYREF
  unsigned int v99; // [rsp+130h] [rbp-668h]
  unsigned int v100; // [rsp+134h] [rbp-664h]
  int v101; // [rsp+138h] [rbp-660h] BYREF
  _BYTE v102[4]; // [rsp+13Ch] [rbp-65Ch] BYREF
  unsigned int v103; // [rsp+140h] [rbp-658h]
  int v104; // [rsp+144h] [rbp-654h]
  unsigned int v105; // [rsp+148h] [rbp-650h]
  int v106; // [rsp+14Ch] [rbp-64Ch] BYREF
  _BYTE v107[4]; // [rsp+150h] [rbp-648h] BYREF
  unsigned int v108; // [rsp+154h] [rbp-644h]
  unsigned int v109; // [rsp+158h] [rbp-640h]
  int v110; // [rsp+15Ch] [rbp-63Ch] BYREF
  _BYTE v111[4]; // [rsp+160h] [rbp-638h] BYREF
  unsigned int v112; // [rsp+164h] [rbp-634h]
  unsigned int v113; // [rsp+168h] [rbp-630h]
  int v114; // [rsp+16Ch] [rbp-62Ch] BYREF
  _BYTE v115[4]; // [rsp+170h] [rbp-628h] BYREF
  unsigned int v116; // [rsp+174h] [rbp-624h]
  unsigned int v117; // [rsp+178h] [rbp-620h]
  int v118; // [rsp+17Ch] [rbp-61Ch] BYREF
  _BYTE v119[4]; // [rsp+180h] [rbp-618h] BYREF
  unsigned int v120; // [rsp+184h] [rbp-614h]
  unsigned int v121; // [rsp+188h] [rbp-610h]
  int v122; // [rsp+18Ch] [rbp-60Ch] BYREF
  _BYTE v123[4]; // [rsp+190h] [rbp-608h] BYREF
  unsigned int v124; // [rsp+194h] [rbp-604h]
  unsigned int v125; // [rsp+198h] [rbp-600h]
  int v126; // [rsp+19Ch] [rbp-5FCh] BYREF
  _BYTE v127[4]; // [rsp+1A0h] [rbp-5F8h] BYREF
  unsigned int v128; // [rsp+1A4h] [rbp-5F4h]
  unsigned int v129; // [rsp+1A8h] [rbp-5F0h]
  int v130; // [rsp+1ACh] [rbp-5ECh] BYREF
  _BYTE v131[4]; // [rsp+1B0h] [rbp-5E8h] BYREF
  unsigned int v132; // [rsp+1B4h] [rbp-5E4h]
  unsigned int v133; // [rsp+1B8h] [rbp-5E0h]
  int v134; // [rsp+1BCh] [rbp-5DCh] BYREF
  _BYTE v135[4]; // [rsp+1C0h] [rbp-5D8h] BYREF
  unsigned int v136; // [rsp+1C4h] [rbp-5D4h]
  unsigned int v137; // [rsp+1C8h] [rbp-5D0h]
  int v138; // [rsp+1CCh] [rbp-5CCh] BYREF
  _BYTE v139[8]; // [rsp+1D0h] [rbp-5C8h] BYREF
  int *v140; // [rsp+1D8h] [rbp-5C0h]
  int *v141; // [rsp+1E0h] [rbp-5B8h]
  int *v142; // [rsp+1E8h] [rbp-5B0h]
  int *v143; // [rsp+1F0h] [rbp-5A8h]
  int *v144; // [rsp+1F8h] [rbp-5A0h]
  int *v145; // [rsp+200h] [rbp-598h]
  int *v146; // [rsp+208h] [rbp-590h]
  int *v147; // [rsp+210h] [rbp-588h]
  int *v148; // [rsp+218h] [rbp-580h]
  int *v149; // [rsp+220h] [rbp-578h]
  int *v150; // [rsp+228h] [rbp-570h]
  int *v151; // [rsp+230h] [rbp-568h]
  int *v152; // [rsp+238h] [rbp-560h]
  int *v153; // [rsp+240h] [rbp-558h]
  int *v154; // [rsp+248h] [rbp-550h]
  int *v155; // [rsp+250h] [rbp-548h]
  int *v156; // [rsp+258h] [rbp-540h]
  int *v157; // [rsp+260h] [rbp-538h]
  int *v158; // [rsp+268h] [rbp-530h]
  int *v159; // [rsp+270h] [rbp-528h]
  int *v160; // [rsp+278h] [rbp-520h]
  int *v161; // [rsp+280h] [rbp-518h]
  int *v162; // [rsp+288h] [rbp-510h]
  int *v163; // [rsp+290h] [rbp-508h]
  _BYTE *v164; // [rsp+298h] [rbp-500h]
  __int64 v165; // [rsp+2A0h] [rbp-4F8h]
  int *v166; // [rsp+2A8h] [rbp-4F0h]
  int *v167; // [rsp+2B0h] [rbp-4E8h]
  __int64 v168; // [rsp+2B8h] [rbp-4E0h]
  _BYTE *v169; // [rsp+2C0h] [rbp-4D8h]
  __int64 v170; // [rsp+2C8h] [rbp-4D0h]
  __int64 v171; // [rsp+2D0h] [rbp-4C8h]
  int *v172; // [rsp+2D8h] [rbp-4C0h]
  int *v173; // [rsp+2E0h] [rbp-4B8h]
  __int64 v174; // [rsp+2E8h] [rbp-4B0h]
  _BYTE *v175; // [rsp+2F0h] [rbp-4A8h]
  __int64 v176; // [rsp+2F8h] [rbp-4A0h]
  __int64 v177; // [rsp+300h] [rbp-498h]
  int *v178; // [rsp+308h] [rbp-490h]
  int *v179; // [rsp+310h] [rbp-488h]
  __int64 v180; // [rsp+318h] [rbp-480h]
  _BYTE *v181; // [rsp+320h] [rbp-478h]
  __int64 v182; // [rsp+328h] [rbp-470h]
  __int64 v183; // [rsp+330h] [rbp-468h]
  int *v184; // [rsp+338h] [rbp-460h]
  int *v185; // [rsp+340h] [rbp-458h]
  __int64 v186; // [rsp+348h] [rbp-450h]
  _BYTE *v187; // [rsp+350h] [rbp-448h]
  __int64 v188; // [rsp+358h] [rbp-440h]
  __int64 v189; // [rsp+360h] [rbp-438h]
  int *v190; // [rsp+368h] [rbp-430h]
  int *v191; // [rsp+370h] [rbp-428h]
  __int64 v192; // [rsp+378h] [rbp-420h]
  _BYTE *v193; // [rsp+380h] [rbp-418h]
  __int64 v194; // [rsp+388h] [rbp-410h]
  __int64 v195; // [rsp+390h] [rbp-408h]
  int *v196; // [rsp+398h] [rbp-400h]
  int *v197; // [rsp+3A0h] [rbp-3F8h]
  __int64 v198; // [rsp+3A8h] [rbp-3F0h]
  _BYTE *v199; // [rsp+3B0h] [rbp-3E8h]
  __int64 v200; // [rsp+3B8h] [rbp-3E0h]
  __int64 v201; // [rsp+3C0h] [rbp-3D8h]
  int *v202; // [rsp+3C8h] [rbp-3D0h]
  int *v203; // [rsp+3D0h] [rbp-3C8h]
  __int64 v204; // [rsp+3D8h] [rbp-3C0h]
  _BYTE *v205; // [rsp+3E0h] [rbp-3B8h]
  __int64 v206; // [rsp+3E8h] [rbp-3B0h]
  __int64 v207; // [rsp+3F0h] [rbp-3A8h]
  int *v208; // [rsp+3F8h] [rbp-3A0h]
  int *v209; // [rsp+400h] [rbp-398h]
  __int64 v210; // [rsp+408h] [rbp-390h]
  _BYTE *v211; // [rsp+410h] [rbp-388h]
  __int64 v212; // [rsp+418h] [rbp-380h]
  __int64 v213; // [rsp+420h] [rbp-378h]
  int *v214; // [rsp+428h] [rbp-370h]
  int *v215; // [rsp+430h] [rbp-368h]
  __int64 v216; // [rsp+438h] [rbp-360h]
  _BYTE *v217; // [rsp+440h] [rbp-358h]
  __int64 v218; // [rsp+448h] [rbp-350h]
  __int64 v219; // [rsp+450h] [rbp-348h]
  int *v220; // [rsp+458h] [rbp-340h]
  int *v221; // [rsp+460h] [rbp-338h]
  __int64 v222; // [rsp+468h] [rbp-330h]
  _BYTE *v223; // [rsp+470h] [rbp-328h]
  __int64 v224; // [rsp+478h] [rbp-320h]
  __int64 v225; // [rsp+480h] [rbp-318h]
  __int64 *v226; // [rsp+488h] [rbp-310h]
  int *v227; // [rsp+490h] [rbp-308h]
  int *v228; // [rsp+498h] [rbp-300h]
  __int64 v229; // [rsp+4A0h] [rbp-2F8h]
  _BYTE *v230; // [rsp+4A8h] [rbp-2F0h]
  __int64 v231; // [rsp+4B0h] [rbp-2E8h]
  __int64 v232; // [rsp+4B8h] [rbp-2E0h]
  _BYTE v233[8]; // [rsp+4C0h] [rbp-2D8h] BYREF
  _BYTE v234[8]; // [rsp+4C8h] [rbp-2D0h] BYREF
  _BYTE v235[8]; // [rsp+4D0h] [rbp-2C8h] BYREF
  _BYTE v236[8]; // [rsp+4D8h] [rbp-2C0h] BYREF
  _BYTE v237[8]; // [rsp+4E0h] [rbp-2B8h] BYREF
  _BYTE v238[8]; // [rsp+4E8h] [rbp-2B0h] BYREF
  _BYTE v239[8]; // [rsp+4F0h] [rbp-2A8h] BYREF
  _BYTE v240[8]; // [rsp+4F8h] [rbp-2A0h] BYREF
  _BYTE v241[8]; // [rsp+500h] [rbp-298h] BYREF
  _BYTE v242[8]; // [rsp+508h] [rbp-290h] BYREF
  _BYTE v243[8]; // [rsp+510h] [rbp-288h] BYREF
  _BYTE v244[8]; // [rsp+518h] [rbp-280h] BYREF
  _BYTE v245[8]; // [rsp+520h] [rbp-278h] BYREF
  _BYTE v246[8]; // [rsp+528h] [rbp-270h] BYREF
  _BYTE v247[8]; // [rsp+530h] [rbp-268h] BYREF
  _BYTE v248[8]; // [rsp+538h] [rbp-260h] BYREF
  _BYTE v249[8]; // [rsp+540h] [rbp-258h] BYREF
  _BYTE v250[8]; // [rsp+548h] [rbp-250h] BYREF
  _BYTE v251[8]; // [rsp+550h] [rbp-248h] BYREF
  _BYTE v252[8]; // [rsp+558h] [rbp-240h] BYREF
  _BYTE v253[8]; // [rsp+560h] [rbp-238h] BYREF
  _BYTE v254[8]; // [rsp+568h] [rbp-230h] BYREF
  _BYTE v255[8]; // [rsp+570h] [rbp-228h] BYREF
  _BYTE v256[8]; // [rsp+578h] [rbp-220h] BYREF
  _BYTE v257[8]; // [rsp+580h] [rbp-218h] BYREF
  _BYTE v258[8]; // [rsp+588h] [rbp-210h] BYREF
  _BYTE v259[8]; // [rsp+590h] [rbp-208h] BYREF
  _BYTE v260[8]; // [rsp+598h] [rbp-200h] BYREF
  _BYTE v261[8]; // [rsp+5A0h] [rbp-1F8h] BYREF
  _BYTE v262[8]; // [rsp+5A8h] [rbp-1F0h] BYREF
  _BYTE v263[8]; // [rsp+5B0h] [rbp-1E8h] BYREF
  _BYTE v264[8]; // [rsp+5B8h] [rbp-1E0h] BYREF
  _BYTE v265[8]; // [rsp+5C0h] [rbp-1D8h] BYREF
  _BYTE v266[8]; // [rsp+5C8h] [rbp-1D0h] BYREF
  _BYTE v267[8]; // [rsp+5D0h] [rbp-1C8h] BYREF
  _BYTE v268[8]; // [rsp+5D8h] [rbp-1C0h] BYREF
  _BYTE v269[8]; // [rsp+5E0h] [rbp-1B8h] BYREF
  _BYTE v270[8]; // [rsp+5E8h] [rbp-1B0h] BYREF
  _BYTE v271[8]; // [rsp+5F0h] [rbp-1A8h] BYREF
  _BYTE v272[8]; // [rsp+5F8h] [rbp-1A0h] BYREF
  _BYTE v273[8]; // [rsp+600h] [rbp-198h] BYREF
  __int64 *v274; // [rsp+608h] [rbp-190h]
  __int64 *v275; // [rsp+610h] [rbp-188h]
  __int64 *v276; // [rsp+628h] [rbp-170h]
  __int64 *v277; // [rsp+630h] [rbp-168h]
  __int64 *v278; // [rsp+638h] [rbp-160h]
  _BYTE v279[8]; // [rsp+640h] [rbp-158h] BYREF
  _BYTE v280[8]; // [rsp+648h] [rbp-150h] BYREF
  _BYTE v281[8]; // [rsp+650h] [rbp-148h] BYREF
  _BYTE v282[8]; // [rsp+658h] [rbp-140h] BYREF
  _BYTE VersionInformation[284]; // [rsp+660h] [rbp-138h] BYREF

  v25 = 0;
  memset(VersionInformation, 0, sizeof(VersionInformation));
  *(_DWORD *)VersionInformation = 284;
  if ( GetVersionExW((LPOSVERSIONINFOW)VersionInformation) )
  {
    v75 = VersionInformation[282] != 1;
    CSLQuery::bServerSku = v75;
  }
  else
  {
    v140 = g_ProviderToUse;
    v163 = g_ProviderToUse;
    v49 = 0;
    v49 = *g_ProviderToUse;
    v92 = v49;
    if ( v49 > 3 && (unsigned __int8)tlgKeywordOn(v140, 0, v0) )
    {
      LastError = GetLastError();
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v94, &LastError);
      v164 = v94;
      v165 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v233,
               "GetVersionEx FAILED");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v140,
        (unsigned int)&word_18011A45E,
        0,
        0,
        v165,
        (__int64)v164);
    }
  }
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowRemoteConnections", &v25);
  if ( v24 == -1073418222 )
  {
    v141 = g_ProviderToUse;
    v166 = g_ProviderToUse;
    v50 = 0;
    v50 = *g_ProviderToUse;
    v95 = v50;
    if ( v50 > 3 && (unsigned __int8)tlgKeywordOn(v141, 0, v1) )
    {
      v2 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             v234,
             "The SL policy for 'Allow Remote Connections' is not defined - assuming Reduced Functionality Mode");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v141,
        (unsigned int)&word_18011A9DE,
        0,
        0,
        v2);
    }
    v51 = CSLQuery::bServerSku != 0;
    v25 = v51;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v142 = g_ProviderToUse;
    v167 = g_ProviderToUse;
    v52 = 0;
    v52 = *g_ProviderToUse;
    v96 = v52;
    if ( v52 > 3 && (unsigned __int8)tlgKeywordOn(v142, 0, v1) )
    {
      v168 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v235,
               "Initialize");
      v97 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v98, &v97);
      v169 = v98;
      v170 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v236,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bRemoteConnAllowed");
      v171 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v237,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v142,
        (unsigned int)byte_18011A209,
        0,
        0,
        v171,
        v170,
        (__int64)v169,
        v168);
    }
    return (unsigned int)v24;
  }
  v53 = v25 != 0;
  CSLQuery::bRemoteConnAllowed = v53;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowMultipleSessions", &v25);
  if ( v24 == -1073418222 )
  {
    v143 = g_ProviderToUse;
    v172 = g_ProviderToUse;
    v54 = 0;
    v54 = *g_ProviderToUse;
    v99 = v54;
    if ( v54 > 3 && (unsigned __int8)tlgKeywordOn(v143, 0, v3) )
    {
      v4 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             v238,
             "The SL policy for 'Allow Multiple Sessions' is not defined - assuming Reduced Functionality Mode");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v143,
        (unsigned int)&word_18011A972,
        0,
        0,
        v4);
    }
    v55 = CSLQuery::bServerSku != 0;
    v25 = v55;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v144 = g_ProviderToUse;
    v173 = g_ProviderToUse;
    v56 = 0;
    v56 = *g_ProviderToUse;
    v100 = v56;
    if ( v56 > 3 && (unsigned __int8)tlgKeywordOn(v144, 0, v3) )
    {
      v174 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v239,
               "Initialize");
      v101 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v102, &v101);
      v175 = v102;
      v176 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v240,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bFUSEnabled");
      v177 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v241,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v144,
        (unsigned int)byte_18011A81D,
        0,
        0,
        v177,
        v176,
        (__int64)v175,
        v174);
    }
    return (unsigned int)v24;
  }
  v57 = v25 != 0;
  CSLQuery::bFUSEnabled = v57;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowAppServerMode", &v25);
  if ( v24 == -1073418222 )
  {
    v145 = g_ProviderToUse;
    v178 = g_ProviderToUse;
    v58 = 0;
    v58 = *g_ProviderToUse;
    v103 = v58;
    if ( v58 > 3 && (unsigned __int8)tlgKeywordOn(v145, 0, v5) )
    {
      v6 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             v242,
             "The SL policy for 'Allow Multiple Sessions' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v145,
        (unsigned int)&word_18011A5F6,
        0,
        0,
        v6);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v104 = 0;
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v146 = g_ProviderToUse;
    v179 = g_ProviderToUse;
    v59 = 0;
    v59 = *g_ProviderToUse;
    v105 = v59;
    if ( v59 > 3 && (unsigned __int8)tlgKeywordOn(v146, 0, v5) )
    {
      v180 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v243,
               "Initialize");
      v106 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v107, &v106);
      v181 = v107;
      v182 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v244,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAppServerAllowed");
      v183 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v245,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v146,
        (unsigned int)&byte_18011A4CF,
        0,
        0,
        v183,
        v182,
        (__int64)v181,
        v180);
    }
    return (unsigned int)v24;
  }
  v60 = v25 != 0;
  CSLQuery::bAppServerAllowed = v60;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-AutomatedAppServerInstallation",
          &v25);
  if ( v24 == -1073418222 )
  {
    v147 = g_ProviderToUse;
    v184 = g_ProviderToUse;
    v61 = 0;
    v61 = *g_ProviderToUse;
    v108 = v61;
    if ( v61 > 3 && (unsigned __int8)tlgKeywordOn(v147, 0, v7) )
    {
      v8 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             v246,
             "The SL policy for 'Automated App Server Installation' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v147,
        (unsigned int)byte_18011A0CC,
        0,
        0,
        v8);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v148 = g_ProviderToUse;
    v185 = g_ProviderToUse;
    v62 = 0;
    v62 = *g_ProviderToUse;
    v109 = v62;
    if ( v62 > 3 && (unsigned __int8)tlgKeywordOn(v148, 0, v7) )
    {
      v186 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v247,
               "Initialize");
      v110 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v111, &v110);
      v187 = v111;
      v188 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v248,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAutomatedAppServerInstallation");
      v189 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v249,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v148,
        (unsigned int)&byte_18011A9FF,
        0,
        0,
        v189,
        v188,
        (__int64)v187,
        v186);
    }
    return (unsigned int)v24;
  }
  v63 = v25 != 0;
  CSLQuery::bAutomatedAppServerInstallation = v63;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowMultimon", &v25);
  if ( v24 == -1073418222 )
  {
    v149 = g_ProviderToUse;
    v190 = g_ProviderToUse;
    v64 = 0;
    v64 = *g_ProviderToUse;
    v112 = v64;
    if ( v64 > 3 && (unsigned __int8)tlgKeywordOn(v149, 0, v9) )
    {
      v10 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v250,
              "The SL policy for 'Allow Multiple Monitors' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v149,
        (unsigned int)byte_18011A68D,
        0,
        0,
        v10);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v150 = g_ProviderToUse;
    v191 = g_ProviderToUse;
    v65 = 0;
    v65 = *g_ProviderToUse;
    v113 = v65;
    if ( v65 > 3 && (unsigned __int8)tlgKeywordOn(v150, 0, v9) )
    {
      v192 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v251,
               "Initialize");
      v114 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v115, &v114);
      v193 = v115;
      v194 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v252,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bMultimonAllowed");
      v195 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v253,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v150,
        (unsigned int)&word_18011A6AE,
        0,
        0,
        v195,
        v194,
        (__int64)v193,
        v192);
    }
    return (unsigned int)v24;
  }
  v66 = v25 != 0;
  CSLQuery::bMultimonAllowed = v66;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-ADD-Licensing", &v25);
  if ( v24 == -1073418222 )
  {
    v151 = g_ProviderToUse;
    v196 = g_ProviderToUse;
    v67 = 0;
    v67 = *g_ProviderToUse;
    v116 = v67;
    if ( v67 > 3 && (unsigned __int8)tlgKeywordOn(v151, 0, v11) )
    {
      v12 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v254,
              "The SL policy for 'Allow AAD Licensing' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v151,
        (unsigned int)byte_18011A000,
        0,
        0,
        v12);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v152 = g_ProviderToUse;
    v197 = g_ProviderToUse;
    v68 = 0;
    v68 = *g_ProviderToUse;
    v117 = v68;
    if ( v68 > 3 && (unsigned __int8)tlgKeywordOn(v152, 0, v11) )
    {
      v198 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v255,
               "Initialize");
      v118 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v119, &v118);
      v199 = v119;
      v200 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v256,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAllowAADLicensing");
      v201 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v257,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v152,
        (unsigned int)&word_18011A652,
        0,
        0,
        v201,
        v200,
        (__int64)v199,
        v198);
    }
    return (unsigned int)v24;
  }
  v69 = v25 != 0;
  CSLQuery::bAllowAADLicensing = v69;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-MaxUserSessions", &v25);
  if ( v24 == -1073418222 )
  {
    v153 = g_ProviderToUse;
    v202 = g_ProviderToUse;
    v70 = 0;
    v70 = *g_ProviderToUse;
    v120 = v70;
    if ( v70 > 3 && (unsigned __int8)tlgKeywordOn(v153, 0, v13) )
    {
      v14 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v258,
              "The SL policy for 'Max User Sessions' is not defined - assuming no limit to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v153,
        (unsigned int)byte_18011A0AB,
        0,
        0,
        v14);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v154 = g_ProviderToUse;
    v203 = g_ProviderToUse;
    v71 = 0;
    v71 = *g_ProviderToUse;
    v121 = v71;
    if ( v71 > 3 && (unsigned __int8)tlgKeywordOn(v154, 0, v13) )
    {
      v204 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v259,
               "Initialize");
      v122 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v123, &v122);
      v205 = v123;
      v206 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v260,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for lMaxUserSessions");
      v207 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v261,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v154,
        (unsigned int)&word_18011AA3A,
        0,
        0,
        v207,
        v206,
        (__int64)v205,
        v204);
    }
    return (unsigned int)v24;
  }
  CSLQuery::lMaxUserSessions = v25;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-ce0ad219-4670-4988-98fb-89b14c2f072b-MaxSessions",
          &v25);
  if ( v24 == -1073418222 )
  {
    v155 = g_ProviderToUse;
    v208 = g_ProviderToUse;
    v72 = 0;
    v72 = *g_ProviderToUse;
    v124 = v72;
    if ( v72 > 3 && (unsigned __int8)tlgKeywordOn(v155, 0, v15) )
    {
      v16 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v262,
              "The SL policy for 'Max Debug Sessions' is not defined - assuming no limit to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v155,
        (unsigned int)&word_18011A172,
        0,
        0,
        v16);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v156 = g_ProviderToUse;
    v209 = g_ProviderToUse;
    v73 = 0;
    v73 = *g_ProviderToUse;
    v125 = v73;
    if ( v73 > 3 && (unsigned __int8)tlgKeywordOn(v156, 0, v15) )
    {
      v210 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v263,
               "Initialize");
      v126 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v127, &v126);
      v211 = v127;
      v212 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v264,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxDebugSessions");
      v213 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v265,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v156,
        (unsigned int)&byte_18011A137,
        0,
        0,
        v213,
        v212,
        (__int64)v211,
        v210);
    }
    return (unsigned int)v24;
  }
  CSLQuery::ulMaxDebugSessions = v25;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"Kernel-OneCore-VailGuest", &v25);
  if ( v24 == -1073418222 )
  {
    v157 = g_ProviderToUse;
    v214 = g_ProviderToUse;
    v74 = 0;
    v74 = *g_ProviderToUse;
    v128 = v74;
    if ( v74 > 3 && (unsigned __int8)tlgKeywordOn(v157, 0, v17) )
    {
      v18 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v266,
              "The SL policy for 'VAIL Guest Policy' is not defined - assuming not in VAIL");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v157,
        (unsigned int)byte_18011A43D,
        0,
        0,
        v18);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v158 = g_ProviderToUse;
    v215 = g_ProviderToUse;
    v83 = 0;
    v83 = *g_ProviderToUse;
    v129 = v83;
    if ( v83 > 3 && (unsigned __int8)tlgKeywordOn(v158, 0, v17) )
    {
      v216 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v267,
               "Initialize");
      v130 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v131, &v130);
      v217 = v131;
      v218 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v268,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bVailGuest");
      v219 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v269,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v158,
        (unsigned int)&byte_18011A617,
        0,
        0,
        v219,
        v218,
        (__int64)v217,
        v216);
    }
    return (unsigned int)v24;
  }
  CSLQuery::bVailGuest = v25;
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-WVD-Enabled", &v25);
  if ( v24 == -1073418222 )
  {
    v159 = g_ProviderToUse;
    v220 = g_ProviderToUse;
    v76 = 0;
    v76 = *g_ProviderToUse;
    v132 = v76;
    if ( v76 > 3 && (unsigned __int8)tlgKeywordOn(v159, 0, v19) )
    {
      v20 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v270,
              "The SL policy for 'WVD Enabled' is not defined - assuming WVD is disabled");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v159,
        (unsigned int)byte_18011A858,
        0,
        0,
        v20);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 < 0 )
  {
    v160 = g_ProviderToUse;
    v221 = g_ProviderToUse;
    v77 = 0;
    v77 = *g_ProviderToUse;
    v133 = v77;
    if ( v77 > 3 && (unsigned __int8)tlgKeywordOn(v160, 0, v19) )
    {
      v222 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v271,
               "Initialize");
      v134 = v24;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v135, &v134);
      v223 = v135;
      v224 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v272,
               "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bWVDEnabled");
      v225 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               v273,
               "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v160,
        (unsigned int)byte_18011A330,
        0,
        0,
        v225,
        v224,
        (__int64)v223,
        v222);
    }
    return (unsigned int)v24;
  }
  v78 = v25 != 0;
  CSLQuery::bWVDEnabled = v78;
  v226 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v48 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v274 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v275 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl);
  v276 = v48;
  v277 = v48;
  v278 = v48;
  v26 = 1;
  v79 = 1;
  v27 = 1;
  v28 = 1;
  v29 = 1;
  v80 = 1;
  v30 = 1;
  v31 = 1;
  v81 = 1;
  v32 = 1;
  v33 = 1;
  v82 = 1;
  v34 = 1;
  v91 = 1;
  v35 = 1;
  v36 = 1;
  v84 = 1;
  v37 = 1;
  v38 = 1;
  v39 = 1;
  v40 = 1;
  v85 = 1;
  v41 = 1;
  v86 = 1;
  v42 = 1;
  v43 = 1;
  v87 = 1;
  v44 = 1;
  v45 = 1;
  v88 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(v48) != 0;
  v46 = v88;
  v47 = v88;
  if ( !v88 )
  {
LABEL_118:
    CSLQuery::bInitialized = 1;
    return (unsigned int)v24;
  }
  v25 = 0;
  v24 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-cd051c59-3fe7-499c-9b66-02d99dbd8d3b-MaxSessions",
          &v25);
  if ( v24 == -1073418222 )
  {
    v161 = g_ProviderToUse;
    v227 = g_ProviderToUse;
    v89 = 0;
    v89 = *g_ProviderToUse;
    v136 = v89;
    if ( v89 > 3 && (unsigned __int8)tlgKeywordOn(v161, 0, v21) )
    {
      v22 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              v279,
              "The SL policy for 'Max Agent Sessions' is not defined - assuming no limit to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v161,
        (unsigned int)&word_18011A08A,
        0,
        0,
        v22);
    }
    v25 = 0;
    v24 = 0;
  }
  if ( v24 >= 0 )
  {
    CSLQuery::ulMaxAgentSessions = v25;
    goto LABEL_118;
  }
  v162 = g_ProviderToUse;
  v228 = g_ProviderToUse;
  v90 = 0;
  v90 = *g_ProviderToUse;
  v137 = v90;
  if ( v90 > 3 && (unsigned __int8)tlgKeywordOn(v162, 0, v21) )
  {
    v229 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             v280,
             "Initialize");
    v138 = v24;
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v139, &v138);
    v230 = v139;
    v231 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             v281,
             "CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxAgentSessions");
    v232 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             v282,
             "Warning HResult failed");
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v162,
      (unsigned int)byte_18011A244,
      0,
      0,
      v232,
      v231,
      (__int64)v230,
      v229);
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800b56b8  push    rdi
0x1800b56ba  sub     rsp, 790h
0x1800b56c1  mov     rax, cs:__security_cookie
0x1800b56c8  xor     rax, rsp
0x1800b56cb  mov     [rsp+798h+var_18], rax
0x1800b56d3  mov     [rsp+798h+var_758], 80004001h
0x1800b56db  mov     [rsp+798h+var_754], 0
0x1800b56e3  lea     rax, [rsp+798h+VersionInformation]
0x1800b56eb  mov     rdi, rax
0x1800b56ee  xor     eax, eax
0x1800b56f0  mov     ecx, 11Ch
0x1800b56f5  rep stosb
0x1800b56f7  mov     [rsp+798h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800b5702  lea     rcx, [rsp+798h+VersionInformation]; lpVersionInformation
0x1800b570a  call    cs:__imp_GetVersionExW
0x1800b5711  nop     dword ptr [rax+rax+00h]
0x1800b5716  test    eax, eax
0x1800b5718  jz      short loc_1800B5751
0x1800b571a  movzx   eax, [rsp+798h+var_1E]
0x1800b5722  cmp     eax, 1
0x1800b5725  jnz     short loc_1800B5734
0x1800b5727  mov     [rsp+798h+var_6C8], 0
0x1800b5732  jmp     short loc_1800B573F
0x1800b5734  mov     [rsp+798h+var_6C8], 1
0x1800b573f  mov     eax, [rsp+798h+var_6C8]
0x1800b5746  mov     cs:?bServerSku@CSLQuery@@0HA, eax; int CSLQuery::bServerSku
0x1800b574c  jmp     loc_1800B5854
0x1800b5751  mov     rax, cs:g_ProviderToUse
0x1800b5758  mov     [rsp+798h+var_5C0], rax
0x1800b5760  mov     rax, [rsp+798h+var_5C0]
0x1800b5768  mov     [rsp+798h+var_508], rax
0x1800b5770  mov     [rsp+798h+var_730], 0
0x1800b5778  mov     rax, [rsp+798h+var_508]
0x1800b5780  mov     eax, [rax]
0x1800b5782  mov     [rsp+798h+var_730], eax
0x1800b5786  mov     eax, [rsp+798h+var_730]
0x1800b578a  mov     [rsp+798h+var_684], eax
0x1800b5791  mov     eax, [rsp+798h+var_684]
0x1800b5798  cmp     eax, 3
0x1800b579b  jbe     loc_1800B584A
0x1800b57a1  mov     rdx, cs:qword_18011A461
0x1800b57a8  mov     rcx, [rsp+798h+var_5C0]
0x1800b57b0  call    _tlgKeywordOn
0x1800b57b5  movzx   eax, al
0x1800b57b8  test    eax, eax
0x1800b57ba  jz      loc_1800B584A
0x1800b57c0  call    cs:__imp_GetLastError
0x1800b57c7  nop     dword ptr [rax+rax+00h]
0x1800b57cc  mov     [rsp+798h+var_680], eax
0x1800b57d3  lea     rdx, [rsp+798h+var_680]
0x1800b57db  lea     rcx, [rsp+798h+var_67C]
0x1800b57e3  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800b57e8  nop
0x1800b57e9  lea     rax, [rsp+798h+var_67C]
0x1800b57f1  mov     [rsp+798h+var_500], rax
0x1800b57f9  lea     rdx, aGetversionexFa; "GetVersionEx FAILED"
0x1800b5800  lea     rcx, [rsp+798h+var_2D8]
0x1800b5808  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b580d  mov     [rsp+798h+var_4F8], rax
0x1800b5815  mov     rax, [rsp+798h+var_500]
0x1800b581d  mov     [rsp+798h+var_770], rax
0x1800b5822  mov     rax, [rsp+798h+var_4F8]
0x1800b582a  mov     [rsp+798h+var_778], rax
0x1800b582f  xor     r9d, r9d
0x1800b5832  xor     r8d, r8d
0x1800b5835  lea     rdx, word_18011A45E
0x1800b583c  mov     rcx, [rsp+798h+var_5C0]
0x1800b5844  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b5849  nop
0x1800b584a  xor     eax, eax
0x1800b584c  test    eax, eax
0x1800b584e  jnz     loc_1800B5751
0x1800b5854  mov     [rsp+798h+var_754], 0
0x1800b585c  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x1800b5861  lea     rcx, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x1800b5868  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
0x1800b586d  mov     [rsp+798h+var_758], eax
0x1800b5871  cmp     [rsp+798h+var_758], 0C004F012h
0x1800b5879  jnz     loc_1800B594F
0x1800b587f  mov     rax, cs:g_ProviderToUse
0x1800b5886  mov     [rsp+798h+var_5B8], rax
0x1800b588e  mov     rax, [rsp+798h+var_5B8]
0x1800b5896  mov     [rsp+798h+var_4F0], rax
0x1800b589e  mov     [rsp+798h+var_72C], 0
0x1800b58a6  mov     rax, [rsp+798h+var_4F0]
0x1800b58ae  mov     eax, [rax]
0x1800b58b0  mov     [rsp+798h+var_72C], eax
0x1800b58b4  mov     eax, [rsp+798h+var_72C]
0x1800b58b8  mov     [rsp+798h+var_678], eax
0x1800b58bf  mov     eax, [rsp+798h+var_678]
0x1800b58c6  cmp     eax, 3
0x1800b58c9  jbe     short loc_1800B591A
0x1800b58cb  mov     rdx, cs:qword_18011A9E1
0x1800b58d2  mov     rcx, [rsp+798h+var_5B8]
0x1800b58da  call    _tlgKeywordOn
0x1800b58df  movzx   eax, al
0x1800b58e2  test    eax, eax
0x1800b58e4  jz      short loc_1800B591A
0x1800b58e6  lea     rdx, aTheSlPolicyFor_3; "The SL policy for 'Allow Remote Connect"...
0x1800b58ed  lea     rcx, [rsp+798h+var_2D0]
0x1800b58f5  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b58fa  mov     [rsp+798h+var_778], rax
0x1800b58ff  xor     r9d, r9d
0x1800b5902  xor     r8d, r8d
0x1800b5905  lea     rdx, word_18011A9DE
0x1800b590c  mov     rcx, [rsp+798h+var_5B8]
0x1800b5914  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800b5919  nop
0x1800b591a  xor     eax, eax
0x1800b591c  test    eax, eax
0x1800b591e  jnz     loc_1800B587F
0x1800b5924  cmp     cs:?bServerSku@CSLQuery@@0HA, 0; int CSLQuery::bServerSku
0x1800b592b  jz      short loc_1800B5937
0x1800b592d  mov     [rsp+798h+var_728], 1
0x1800b5935  jmp     short loc_1800B593F
0x1800b5937  mov     [rsp+798h+var_728], 0
0x1800b593f  mov     eax, [rsp+798h+var_728]
0x1800b5943  mov     [rsp+798h+var_754], eax
0x1800b5947  mov     [rsp+798h+var_758], 0
0x1800b594f  cmp     [rsp+798h+var_758], 0
0x1800b5954  jge     loc_1800B5AAC
0x1800b595a  mov     rax, cs:g_ProviderToUse
0x1800b5961  mov     [rsp+798h+var_5B0], rax
0x1800b5969  mov     rax, [rsp+798h+var_5B0]
0x1800b5971  mov     [rsp+798h+var_4E8], rax
0x1800b5979  mov     [rsp+798h+var_724], 0
0x1800b5981  mov     rax, [rsp+798h+var_4E8]
0x1800b5989  mov     eax, [rax]
0x1800b598b  mov     [rsp+798h+var_724], eax
0x1800b598f  mov     eax, [rsp+798h+var_724]
0x1800b5993  mov     [rsp+798h+var_674], eax
0x1800b599a  mov     eax, [rsp+798h+var_674]
0x1800b59a1  cmp     eax, 3
0x1800b59a4  jbe     loc_1800B5A9D
0x1800b59aa  mov     rdx, cs:qword_18011A20C
0x1800b59b1  mov     rcx, [rsp+798h+var_5B0]
0x1800b59b9  call    _tlgKeywordOn
0x1800b59be  movzx   eax, al
0x1800b59c1  test    eax, eax
0x1800b59c3  jz      loc_1800B5A9D
0x1800b59c9  lea     rdx, aInitialize; "Initialize"
0x1800b59d0  lea     rcx, [rsp+798h+var_2C8]
0x1800b59d8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b59dd  mov     [rsp+798h+var_4E0], rax
0x1800b59e5  mov     eax, [rsp+798h+var_758]
0x1800b59e9  mov     [rsp+798h+var_670], eax
0x1800b59f0  lea     rdx, [rsp+798h+var_670]
0x1800b59f8  lea     rcx, [rsp+798h+var_66C]
0x1800b5a00  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800b5a05  nop
0x1800b5a06  lea     rax, [rsp+798h+var_66C]
0x1800b5a0e  mov     [rsp+798h+var_4D8], rax
0x1800b5a16  lea     rdx, aCslqueryInitia_2; "CSLQuery::Initialize - SLGetWindowsInfo"...
0x1800b5a1d  lea     rcx, [rsp+798h+var_2C0]
0x1800b5a25  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b5a2a  mov     [rsp+798h+var_4D0], rax
0x1800b5a32  lea     rdx, aWarningHresult; "Warning HResult failed"
0x1800b5a39  lea     rcx, [rsp+798h+var_2B8]
0x1800b5a41  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b5a46  mov     [rsp+798h+var_4C8], rax
0x1800b5a4e  mov     rax, [rsp+798h+var_4E0]
0x1800b5a56  mov     [rsp+798h+var_760], rax
0x1800b5a5b  mov     rax, [rsp+798h+var_4D8]
0x1800b5a63  mov     [rsp+798h+var_768], rax
0x1800b5a68  mov     rax, [rsp+798h+var_4D0]
0x1800b5a70  mov     [rsp+798h+var_770], rax
0x1800b5a75  mov     rax, [rsp+798h+var_4C8]
0x1800b5a7d  mov     [rsp+798h+var_778], rax
0x1800b5a82  xor     r9d, r9d
0x1800b5a85  xor     r8d, r8d
0x1800b5a88  lea     rdx, byte_18011A209
0x1800b5a8f  mov     rcx, [rsp+798h+var_5B0]
0x1800b5a97  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800b5a9c  nop
0x1800b5a9d  xor     eax, eax
0x1800b5a9f  test    eax, eax
0x1800b5aa1  jnz     loc_1800B595A
0x1800b5aa7  jmp     loc_1800B76F2
0x1800b5aac  cmp     [rsp+798h+var_754], 0
0x1800b5ab1  jz      short loc_1800B5ABD
0x1800b5ab3  mov     [rsp+798h+var_720], 1
0x1800b5abb  jmp     short loc_1800B5AC5
0x1800b5abd  mov     [rsp+798h+var_720], 0
0x1800b5ac5  mov     eax, [rsp+798h+var_720]
0x1800b5ac9  mov     cs:?bRemoteConnAllowed@CSLQuery@@0HA, eax; int CSLQuery::bRemoteConnAllowed
0x1800b5acf  mov     [rsp+798h+var_754], 0
0x1800b5ad7  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x1800b5adc  lea     rcx, aTerminalservic_4; "TerminalServices-RemoteConnectionManage"...
0x1800b5ae3  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
0x1800b5ae8  mov     [rsp+798h+var_758], eax
0x1800b5aec  cmp     [rsp+798h+var_758], 0C004F012h
0x1800b5af4  jnz     loc_1800B5BD3
0x1800b5afa  mov     rax, cs:g_ProviderToUse
0x1800b5b01  mov     [rsp+798h+var_5A8], rax
0x1800b5b09  mov     rax, [rsp+798h+var_5A8]
0x1800b5b11  mov     [rsp+798h+var_4C0], rax
0x1800b5b19  mov     [rsp+798h+var_71C], 0
0x1800b5b21  mov     rax, [rsp+798h+var_4C0]
0x1800b5b29  mov     eax, [rax]
0x1800b5b2b  mov     [rsp+798h+var_71C], eax
0x1800b5b2f  mov     eax, [rsp+798h+var_71C]
0x1800b5b33  mov     [rsp+798h+var_668], eax
0x1800b5b3a  mov     eax, [rsp+798h+var_668]
0x1800b5b41  cmp     eax, 3
0x1800b5b44  jbe     short loc_1800B5B95
0x1800b5b46  mov     rdx, cs:qword_18011A975
0x1800b5b4d  mov     rcx, [rsp+798h+var_5A8]
0x1800b5b55  call    _tlgKeywordOn
0x1800b5b5a  movzx   eax, al
0x1800b5b5d  test    eax, eax
0x1800b5b5f  jz      short loc_1800B5B95
0x1800b5b61  lea     rdx, aTheSlPolicyFor_2; "The SL policy for 'Allow Multiple Sessi"...
0x1800b5b68  lea     rcx, [rsp+798h+var_2B0]
0x1800b5b70  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b5b75  mov     [rsp+798h+var_778], rax
0x1800b5b7a  xor     r9d, r9d
0x1800b5b7d  xor     r8d, r8d
0x1800b5b80  lea     rdx, word_18011A972
0x1800b5b87  mov     rcx, [rsp+798h+var_5A8]
0x1800b5b8f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800b5b94  nop
0x1800b5b95  xor     eax, eax
0x1800b5b97  test    eax, eax
0x1800b5b99  jnz     loc_1800B5AFA
0x1800b5b9f  cmp     cs:?bServerSku@CSLQuery@@0HA, 0; int CSLQuery::bServerSku
0x1800b5ba6  jz      short loc_1800B5BB5
0x1800b5ba8  mov     [rsp+798h+var_718], 1
0x1800b5bb3  jmp     short loc_1800B5BC0
0x1800b5bb5  mov     [rsp+798h+var_718], 0
0x1800b5bc0  mov     eax, [rsp+798h+var_718]
0x1800b5bc7  mov     [rsp+798h+var_754], eax
0x1800b5bcb  mov     [rsp+798h+var_758], 0
0x1800b5bd3  cmp     [rsp+798h+var_758], 0
0x1800b5bd8  jge     loc_1800B5D39
0x1800b5bde  mov     rax, cs:g_ProviderToUse
0x1800b5be5  mov     [rsp+798h+var_5A0], rax
0x1800b5bed  mov     rax, [rsp+798h+var_5A0]
0x1800b5bf5  mov     [rsp+798h+var_4B8], rax
0x1800b5bfd  mov     [rsp+798h+var_714], 0
0x1800b5c08  mov     rax, [rsp+798h+var_4B8]
0x1800b5c10  mov     eax, [rax]
0x1800b5c12  mov     [rsp+798h+var_714], eax
0x1800b5c19  mov     eax, [rsp+798h+var_714]
0x1800b5c20  mov     [rsp+798h+var_664], eax
0x1800b5c27  mov     eax, [rsp+798h+var_664]
0x1800b5c2e  cmp     eax, 3
0x1800b5c31  jbe     loc_1800B5D2A
0x1800b5c37  mov     rdx, cs:qword_18011A820
0x1800b5c3e  mov     rcx, [rsp+798h+var_5A0]
0x1800b5c46  call    _tlgKeywordOn
0x1800b5c4b  movzx   eax, al
0x1800b5c4e  test    eax, eax
0x1800b5c50  jz      loc_1800B5D2A
0x1800b5c56  lea     rdx, aInitialize; "Initialize"
0x1800b5c5d  lea     rcx, [rsp+798h+var_2A8]
0x1800b5c65  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b5c6a  mov     [rsp+798h+var_4B0], rax
0x1800b5c72  mov     eax, [rsp+798h+var_758]
0x1800b5c76  mov     [rsp+798h+var_660], eax
0x1800b5c7d  lea     rdx, [rsp+798h+var_660]
0x1800b5c85  lea     rcx, [rsp+798h+var_65C]
0x1800b5c8d  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800b5c92  nop
0x1800b5c93  lea     rax, [rsp+798h+var_65C]
0x1800b5c9b  mov     [rsp+798h+var_4A8], rax
0x1800b5ca3  lea     rdx, aCslqueryInitia_4; "CSLQuery::Initialize - SLGetWindowsInfo"...
0x1800b5caa  lea     rcx, [rsp+798h+var_2A0]
0x1800b5cb2  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b5cb7  mov     [rsp+798h+var_4A0], rax
0x1800b5cbf  lea     rdx, aWarningHresult; "Warning HResult failed"
0x1800b5cc6  lea     rcx, [rsp+798h+var_298]
0x1800b5cce  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b5cd3  mov     [rsp+798h+var_498], rax
0x1800b5cdb  mov     rax, [rsp+798h+var_4B0]
0x1800b5ce3  mov     [rsp+798h+var_760], rax
0x1800b5ce8  mov     rax, [rsp+798h+var_4A8]
0x1800b5cf0  mov     [rsp+798h+var_768], rax
0x1800b5cf5  mov     rax, [rsp+798h+var_4A0]
0x1800b5cfd  mov     [rsp+798h+var_770], rax
0x1800b5d02  mov     rax, [rsp+798h+var_498]
0x1800b5d0a  mov     [rsp+798h+var_778], rax
0x1800b5d0f  xor     r9d, r9d
0x1800b5d12  xor     r8d, r8d
0x1800b5d15  lea     rdx, byte_18011A81D
0x1800b5d1c  mov     rcx, [rsp+798h+var_5A0]
0x1800b5d24  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800b5d29  nop
0x1800b5d2a  xor     eax, eax
0x1800b5d2c  test    eax, eax
0x1800b5d2e  jnz     loc_1800B5BDE
0x1800b5d34  jmp     loc_1800B76F2
0x1800b5d39  cmp     [rsp+798h+var_754], 0
0x1800b5d3e  jz      short loc_1800B5D4D
0x1800b5d40  mov     [rsp+798h+var_710], 1
0x1800b5d4b  jmp     short loc_1800B5D58
0x1800b5d4d  mov     [rsp+798h+var_710], 0
0x1800b5d58  mov     eax, [rsp+798h+var_710]
0x1800b5d5f  mov     cs:?bFUSEnabled@CSLQuery@@0HA, eax; int CSLQuery::bFUSEnabled
0x1800b5d65  mov     [rsp+798h+var_754], 0
0x1800b5d6d  lea     rdx, [rsp+798h+var_754]; unsigned int *
  ... truncated ...
```
