# CWorkspace::SaveRegistryEntries(int)

- ea: `0x180034ffc`
- end: `0x18003622b`
- name: `?SaveRegistryEntries@CWorkspace@@QEAAJH@Z`
- size: `4655`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this, int)`
- caller_count: `6`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a548`
- `0x18004a840`
- `0x18004bd50`
- `0x18007525c`
- `0x180075d30`
- `0x1800761c0`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e41c`
- `0x18001e610`
- `0x18001e92c`
- `0x180025824`
- `0x180025950`
- `0x180034ffc`
- `0x180036234`
- `0x180036c9c`
- `0x18003708c`
- `0x180039a58`
- `0x18003ce1c`
- `0x180053648`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180035b39`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180035dd2`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180035b39`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180035dd2`
- `ADVAPI32!RegCloseKey` at `0x180035fa2`
- `ADVAPI32!RegCloseKey` at `0x1800361d7`
- `ADVAPI32!RegCloseKey` at `0x1800361e7`
- `ADVAPI32!RegCloseKey` at `0x180035fa2`
- `ADVAPI32!RegCloseKey` at `0x1800361d7`
- `ADVAPI32!RegCloseKey` at `0x1800361e7`
- `ADVAPI32!RegSetValueExW` at `0x180035c8b`
- `ADVAPI32!RegSetValueExW` at `0x180035c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003513b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003619d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003513b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003619d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800361f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800361f6`
- `KERNEL32!RegDeleteTreeW` at `0x180035e6a`
- `KERNEL32!RegDeleteTreeW` at `0x180035e6a`
- `ktmw32!CreateTransaction` at `0x1800350cf`
- `ktmw32!CreateTransaction` at `0x1800350cf`
- `ktmw32!CommitTransaction` at `0x180036142`
- `ktmw32!CommitTransaction` at `0x180036142`

## string_xrefs

- `0x1800353d4`: `EnableAutoUpdate`
- `0x180035723`: `NumStartMenuComputers`
- `0x18003575f`: `LastSuccessfulUpdateTimeHigh`
- `0x18003579b`: `LastSuccessfulUpdateTimeLow`
- `0x1800357d7`: `LastAttemptTimeHigh`
- `0x180035813`: `LastAttemptTimeLow`
- `0x18003544c`: `CreatedTimeHigh`
- `0x180035488`: `CreatedTimeLow`
- `0x1800358c7`: `LastAttemptStatus`
- `0x180035903`: `LastAttemptTitle`
- `0x180035950`: `LastAttemptDetail`
- `0x180035a26`: `RDWebServiceURL`
- `0x180035a73`: `CreatedThroughSSP`
- `0x1800350ad`: `Saving workspace registry data`
- `0x180035f69`: `CWorkspaceFileAssociation::BackupToRegistry failed`
- `0x180035fef`: `CWorkspaceTaskbarPin::SaveTaskbarPinPropertiesRegistry failed`
- `0x180036066`: `CWorkspace::SaveResourceMapRegistry failed`
- `0x1800360d8`: `CWorkspace::SaveSSPInstalledAppsRegistry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CWorkspace::SaveRegistryEntries(CWorkspace *this, int a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE hTransaction; // r15
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  signed int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  char *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rbx
  const WCHAR *v16; // rax
  unsigned int v17; // edi
  unsigned int v18; // eax
  int v19; // r9d
  unsigned int v20; // eax
  unsigned int v21; // r8d
  DWORD v22; // r9d
  const BYTE *v23; // rcx
  unsigned int v24; // edi
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  const WCHAR *v29; // rax
  unsigned int v30; // edi
  unsigned int v31; // eax
  unsigned int v32; // edi
  unsigned int v33; // eax
  char *v34; // rbx
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  signed int v40; // eax
  unsigned int v41; // ebx
  unsigned int v42; // eax
  signed int v43; // eax
  DWORD Timeout[2]; // [rsp+28h] [rbp-640h]
  DWORD dwDisposition; // [rsp+68h] [rbp-600h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-5F8h] BYREF
  unsigned int v49; // [rsp+78h] [rbp-5F0h]
  HKEY hKey; // [rsp+80h] [rbp-5E8h] BYREF
  __int64 v51; // [rsp+88h] [rbp-5E0h]
  CWorkspaceFileAssociation *v52[2]; // [rsp+90h] [rbp-5D8h] BYREF
  _BYTE v53[32]; // [rsp+A0h] [rbp-5C8h] BYREF
  _BYTE v54[32]; // [rsp+C0h] [rbp-5A8h] BYREF
  _BYTE v55[32]; // [rsp+E0h] [rbp-588h] BYREF
  LPCWSTR lpValueName; // [rsp+100h] [rbp-568h]
  DWORD dwType[2]; // [rsp+108h] [rbp-560h]
  __int64 v58; // [rsp+110h] [rbp-558h]
  int v59; // [rsp+118h] [rbp-550h] BYREF
  DWORD cbData; // [rsp+11Ch] [rbp-54Ch]
  _DWORD v61[2]; // [rsp+120h] [rbp-548h]
  const unsigned __int16 *v62; // [rsp+128h] [rbp-540h]
  int v63; // [rsp+130h] [rbp-538h]
  __int64 v64; // [rsp+138h] [rbp-530h]
  int v65; // [rsp+140h] [rbp-528h]
  int v66; // [rsp+144h] [rbp-524h]
  int v67; // [rsp+148h] [rbp-520h]
  const wchar_t *v68; // [rsp+150h] [rbp-518h]
  int v69; // [rsp+158h] [rbp-510h]
  __int64 v70; // [rsp+160h] [rbp-508h]
  int v71; // [rsp+168h] [rbp-500h]
  int v72; // [rsp+16Ch] [rbp-4FCh]
  int v73; // [rsp+170h] [rbp-4F8h]
  const wchar_t *v74; // [rsp+178h] [rbp-4F0h]
  int v75; // [rsp+180h] [rbp-4E8h]
  __int64 v76; // [rsp+188h] [rbp-4E0h]
  int v77; // [rsp+190h] [rbp-4D8h]
  int v78; // [rsp+194h] [rbp-4D4h]
  int v79; // [rsp+198h] [rbp-4D0h]
  const unsigned __int16 *v80; // [rsp+1A0h] [rbp-4C8h]
  int v81; // [rsp+1A8h] [rbp-4C0h]
  __int64 v82; // [rsp+1B0h] [rbp-4B8h]
  int v83; // [rsp+1B8h] [rbp-4B0h]
  int v84; // [rsp+1BCh] [rbp-4ACh]
  int v85; // [rsp+1C0h] [rbp-4A8h]
  const wchar_t *v86; // [rsp+1C8h] [rbp-4A0h]
  int v87; // [rsp+1D0h] [rbp-498h]
  __int64 v88; // [rsp+1D8h] [rbp-490h]
  int v89; // [rsp+1E0h] [rbp-488h]
  int v90; // [rsp+1E4h] [rbp-484h]
  int v91; // [rsp+1E8h] [rbp-480h]
  const wchar_t *v92; // [rsp+1F0h] [rbp-478h]
  int v93; // [rsp+1F8h] [rbp-470h]
  __int64 v94; // [rsp+200h] [rbp-468h]
  int v95; // [rsp+208h] [rbp-460h]
  int v96; // [rsp+20Ch] [rbp-45Ch]
  int v97; // [rsp+210h] [rbp-458h]
  const wchar_t *v98; // [rsp+218h] [rbp-450h]
  int v99; // [rsp+220h] [rbp-448h]
  __int64 v100; // [rsp+228h] [rbp-440h]
  int v101; // [rsp+230h] [rbp-438h]
  int v102; // [rsp+234h] [rbp-434h]
  int v103; // [rsp+238h] [rbp-430h]
  const wchar_t *v104; // [rsp+240h] [rbp-428h]
  int v105; // [rsp+248h] [rbp-420h]
  __int64 v106; // [rsp+250h] [rbp-418h]
  int v107; // [rsp+258h] [rbp-410h]
  int v108; // [rsp+25Ch] [rbp-40Ch]
  int v109; // [rsp+260h] [rbp-408h]
  const wchar_t *v110; // [rsp+268h] [rbp-400h]
  int v111; // [rsp+270h] [rbp-3F8h]
  __int64 v112; // [rsp+278h] [rbp-3F0h]
  int v113; // [rsp+280h] [rbp-3E8h]
  int v114; // [rsp+284h] [rbp-3E4h]
  int v115; // [rsp+288h] [rbp-3E0h]
  const wchar_t *v116; // [rsp+290h] [rbp-3D8h]
  int v117; // [rsp+298h] [rbp-3D0h]
  __int64 v118; // [rsp+2A0h] [rbp-3C8h]
  int v119; // [rsp+2A8h] [rbp-3C0h]
  int v120; // [rsp+2ACh] [rbp-3BCh]
  int v121; // [rsp+2B0h] [rbp-3B8h]
  const wchar_t *v122; // [rsp+2B8h] [rbp-3B0h]
  int v123; // [rsp+2C0h] [rbp-3A8h]
  __int64 v124; // [rsp+2C8h] [rbp-3A0h]
  int v125; // [rsp+2D0h] [rbp-398h]
  int v126; // [rsp+2D4h] [rbp-394h]
  int v127; // [rsp+2D8h] [rbp-390h]
  const wchar_t *v128; // [rsp+2E0h] [rbp-388h]
  int v129; // [rsp+2E8h] [rbp-380h]
  __int64 v130; // [rsp+2F0h] [rbp-378h]
  int v131; // [rsp+2F8h] [rbp-370h]
  int v132; // [rsp+2FCh] [rbp-36Ch]
  int v133; // [rsp+300h] [rbp-368h]
  const wchar_t *v134; // [rsp+308h] [rbp-360h]
  int v135; // [rsp+310h] [rbp-358h]
  __int64 v136; // [rsp+318h] [rbp-350h]
  int v137; // [rsp+320h] [rbp-348h]
  int v138; // [rsp+324h] [rbp-344h]
  int v139; // [rsp+328h] [rbp-340h]
  const wchar_t *v140; // [rsp+330h] [rbp-338h]
  int v141; // [rsp+338h] [rbp-330h]
  __int64 v142; // [rsp+340h] [rbp-328h]
  int v143; // [rsp+348h] [rbp-320h]
  int v144; // [rsp+34Ch] [rbp-31Ch]
  int v145; // [rsp+350h] [rbp-318h]
  const wchar_t *v146; // [rsp+358h] [rbp-310h]
  int v147; // [rsp+360h] [rbp-308h]
  __int64 v148; // [rsp+368h] [rbp-300h]
  int v149; // [rsp+370h] [rbp-2F8h]
  int v150; // [rsp+374h] [rbp-2F4h]
  int v151; // [rsp+378h] [rbp-2F0h]
  const wchar_t *v152; // [rsp+380h] [rbp-2E8h]
  int v153; // [rsp+388h] [rbp-2E0h]
  __int64 v154; // [rsp+390h] [rbp-2D8h]
  int v155; // [rsp+398h] [rbp-2D0h]
  int v156; // [rsp+39Ch] [rbp-2CCh]
  int v157; // [rsp+3A0h] [rbp-2C8h]
  const wchar_t *v158; // [rsp+3A8h] [rbp-2C0h]
  int v159; // [rsp+3B0h] [rbp-2B8h]
  __int64 v160; // [rsp+3B8h] [rbp-2B0h]
  int v161; // [rsp+3C0h] [rbp-2A8h]
  int v162; // [rsp+3C4h] [rbp-2A4h]
  int v163; // [rsp+3C8h] [rbp-2A0h]
  const wchar_t *v164; // [rsp+3D0h] [rbp-298h]
  int v165; // [rsp+3D8h] [rbp-290h]
  __int64 v166; // [rsp+3E0h] [rbp-288h]
  int v167; // [rsp+3E8h] [rbp-280h]
  int v168; // [rsp+3ECh] [rbp-27Ch]
  int v169; // [rsp+3F0h] [rbp-278h]
  const wchar_t *v170; // [rsp+3F8h] [rbp-270h]
  int v171; // [rsp+400h] [rbp-268h]
  __int64 v172; // [rsp+408h] [rbp-260h]
  int v173; // [rsp+410h] [rbp-258h]
  int v174; // [rsp+414h] [rbp-254h]
  int v175; // [rsp+418h] [rbp-250h]
  const wchar_t *v176; // [rsp+420h] [rbp-248h]
  int v177; // [rsp+428h] [rbp-240h]
  __int64 v178; // [rsp+430h] [rbp-238h]
  int v179; // [rsp+438h] [rbp-230h]
  int v180; // [rsp+43Ch] [rbp-22Ch]
  int v181; // [rsp+440h] [rbp-228h]
  const wchar_t *v182; // [rsp+448h] [rbp-220h]
  int v183; // [rsp+450h] [rbp-218h]
  __int64 v184; // [rsp+458h] [rbp-210h]
  int v185; // [rsp+460h] [rbp-208h]
  int v186; // [rsp+464h] [rbp-204h]
  int v187; // [rsp+468h] [rbp-200h]
  const wchar_t *v188; // [rsp+470h] [rbp-1F8h]
  int v189; // [rsp+478h] [rbp-1F0h]
  __int64 v190; // [rsp+480h] [rbp-1E8h]
  int v191; // [rsp+488h] [rbp-1E0h]
  int v192; // [rsp+48Ch] [rbp-1DCh]
  int v193; // [rsp+490h] [rbp-1D8h]
  const wchar_t *v194; // [rsp+498h] [rbp-1D0h]
  int v195; // [rsp+4A0h] [rbp-1C8h]
  __int64 v196; // [rsp+4A8h] [rbp-1C0h]
  int v197; // [rsp+4B0h] [rbp-1B8h]
  int v198; // [rsp+4B4h] [rbp-1B4h]
  int v199; // [rsp+4B8h] [rbp-1B0h]
  const wchar_t *v200; // [rsp+4C0h] [rbp-1A8h]
  int v201; // [rsp+4C8h] [rbp-1A0h]
  __int64 v202; // [rsp+4D0h] [rbp-198h]
  int v203; // [rsp+4D8h] [rbp-190h]
  int v204; // [rsp+4DCh] [rbp-18Ch]
  int v205; // [rsp+4E0h] [rbp-188h]
  const wchar_t *v206; // [rsp+4E8h] [rbp-180h]
  int v207; // [rsp+4F0h] [rbp-178h]
  __int64 v208; // [rsp+4F8h] [rbp-170h]
  int v209; // [rsp+500h] [rbp-168h]
  int v210; // [rsp+504h] [rbp-164h]
  int v211; // [rsp+508h] [rbp-160h]
  const wchar_t *v212; // [rsp+510h] [rbp-158h]
  int v213; // [rsp+518h] [rbp-150h]
  __int64 v214; // [rsp+520h] [rbp-148h]
  int v215; // [rsp+528h] [rbp-140h]
  int v216; // [rsp+52Ch] [rbp-13Ch]
  int v217; // [rsp+530h] [rbp-138h]
  const wchar_t *v218; // [rsp+538h] [rbp-130h]
  int v219; // [rsp+540h] [rbp-128h]
  __int64 v220; // [rsp+548h] [rbp-120h]
  int v221; // [rsp+550h] [rbp-118h]
  int v222; // [rsp+554h] [rbp-114h]
  int v223; // [rsp+558h] [rbp-110h]
  const wchar_t *v224; // [rsp+560h] [rbp-108h]
  int v225; // [rsp+568h] [rbp-100h]
  __int64 v226; // [rsp+570h] [rbp-F8h]
  int v227; // [rsp+578h] [rbp-F0h]
  int v228; // [rsp+57Ch] [rbp-ECh]
  int v229; // [rsp+580h] [rbp-E8h]
  const wchar_t *v230; // [rsp+588h] [rbp-E0h]
  int v231; // [rsp+590h] [rbp-D8h]
  __int64 v232; // [rsp+598h] [rbp-D0h]
  int v233; // [rsp+5A0h] [rbp-C8h]
  int v234; // [rsp+5A4h] [rbp-C4h]
  int v235; // [rsp+5A8h] [rbp-C0h]
  const wchar_t *v236; // [rsp+5B0h] [rbp-B8h]
  int v237; // [rsp+5B8h] [rbp-B0h]
  __int64 v238; // [rsp+5C0h] [rbp-A8h]
  int v239; // [rsp+5C8h] [rbp-A0h]
  int v240; // [rsp+5CCh] [rbp-9Ch]
  int v241; // [rsp+5D0h] [rbp-98h]
  const WCHAR *v242; // [rsp+5D8h] [rbp-90h]
  int v243; // [rsp+5E0h] [rbp-88h]
  __int64 v244; // [rsp+5E8h] [rbp-80h]
  int v245; // [rsp+5F0h] [rbp-78h]
  int v246; // [rsp+5F4h] [rbp-74h]
  int v247; // [rsp+5F8h] [rbp-70h]
  const wchar_t *v248; // [rsp+600h] [rbp-68h]
  int v249; // [rsp+608h] [rbp-60h]
  __int64 v250; // [rsp+610h] [rbp-58h]
  int v251; // [rsp+618h] [rbp-50h]
  int v252; // [rsp+61Ch] [rbp-4Ch]
  int v253; // [rsp+620h] [rbp-48h]

  v52[1] = (CWorkspaceFileAssociation *)-2LL;
  phkResult = 0;
  hKey = 0;
  dwDisposition = 0;
  v51 = -1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      194,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  hTransaction = CreateTransaction(0, 0, 1u, 0, 0, 0x2710u, (LPWSTR)L"Saving workspace registry data");
  v51 = (__int64)hTransaction;
  if ( hTransaction == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v7, v6);
    }
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
  else
  {
    v10 = std::wstring::wstring(v54, L"Software\\Microsoft\\Workspaces\\Feeds");
    v11 = std::operator+<unsigned short>(v53, v10, L"\\");
    v12 = (char *)this + 64;
    v13 = std::operator+<unsigned short>(v55, v11, (char *)this + 64);
    std::wstring::operator=((char *)this + 488, v13);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v53);
    std::wstring::~wstring(v54);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 296);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 488);
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v14);
      v12 = (char *)this + 64;
    }
    if ( !a2 && *((_DWORD *)this + 24) )
      CWorkspaceManager::WriteDefaultWorkspaceGUID(v12);
    lpValueName = L"Id";
    dwType[0] = 1;
    v58 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
    v59 = 0;
    cbData = 2 * *((_DWORD *)this + 20) + 2;
    v61[0] = 0;
    v62 = L"URL";
    v63 = 1;
    v64 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 296);
    v65 = 0;
    v66 = 2 * *((_DWORD *)this + 78) + 2;
    v67 = 0;
    v68 = L"FeedDiscoveryURL";
    v69 = 1;
    v70 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 328);
    v71 = 0;
    v72 = 2 * *((_DWORD *)this + 86) + 2;
    v73 = 0;
    v74 = L"ClaimsHint";
    v75 = 1;
    v76 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 360);
    v77 = 0;
    v78 = 2 * *((_DWORD *)this + 94) + 2;
    v79 = 0;
    v80 = L"UserName";
    v81 = 1;
    v82 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 552);
    v83 = 0;
    v84 = 2 * *((_DWORD *)this + 142) + 2;
    v85 = 0;
    v86 = L"EnableAutoUpdate";
    v87 = 4;
    v88 = 0;
    v89 = *((_DWORD *)this + 42);
    v90 = 4;
    v91 = 0;
    v92 = L"UseClaimsAuth";
    v93 = 4;
    v94 = 0;
    v95 = *((_DWORD *)this + 43);
    v96 = 4;
    v97 = 0;
    v98 = L"CreatedTimeHigh";
    v99 = 4;
    v100 = 0;
    v101 = *((_DWORD *)this + 153);
    v102 = 4;
    v103 = 0;
    v104 = L"CreatedTimeLow";
    v105 = 4;
    v106 = 0;
    v107 = *((_DWORD *)this + 152);
    v108 = 4;
    v109 = 0;
    v110 = L"Publisher";
    v111 = 1;
    v112 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 104);
    v113 = 0;
    v114 = 2 * *((_DWORD *)this + 30) + 2;
    v115 = 1;
    v116 = L"WorkspaceId";
    v117 = 1;
    v118 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 136);
    v119 = 0;
    v120 = 2 * *((_DWORD *)this + 38) + 2;
    v121 = 1;
    v122 = L"PublisherNameSuffix";
    v123 = 4;
    v124 = 0;
    v125 = *((_DWORD *)this + 72);
    v126 = 4;
    v127 = 1;
    v128 = L"WorkspaceFolder";
    v129 = 2;
    v130 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 424);
    v131 = 0;
    v132 = 2 * *((_DWORD *)this + 110) + 2;
    v133 = 1;
    v134 = L"StartMenuRoot";
    v135 = 2;
    v136 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 456);
    v137 = 0;
    v138 = 2 * *((_DWORD *)this + 118) + 2;
    v139 = 1;
    v140 = L"NumPublishedResources";
    v141 = 4;
    v142 = 0;
    v143 = *((_DWORD *)this + 146);
    v144 = 4;
    v145 = 1;
    v146 = L"NumDownloadedResourceFiles";
    v147 = 4;
    v148 = 0;
    v149 = *((_DWORD *)this + 147);
    v150 = 4;
    v151 = 1;
    v152 = L"NumDownloadedIcons";
    v153 = 4;
    v154 = 0;
    v155 = *((_DWORD *)this + 148);
    v156 = 4;
    v157 = 1;
    v158 = L"NumStartMenuPrograms";
    v159 = 4;
    v160 = 0;
    v161 = *((_DWORD *)this + 150);
    v162 = 4;
    v163 = 1;
    v164 = L"NumStartMenuComputers";
    v165 = 4;
    v166 = 0;
    v167 = *((_DWORD *)this + 151);
    v168 = 4;
    v169 = 1;
    v170 = L"LastSuccessfulUpdateTimeHigh";
    v171 = 4;
    v172 = 0;
    v173 = *((_DWORD *)this + 155);
    v174 = 4;
    v175 = 1;
    v176 = L"LastSuccessfulUpdateTimeLow";
    v177 = 4;
    v178 = 0;
    v179 = *((_DWORD *)this + 154);
    v180 = 4;
    v181 = 1;
    v182 = L"LastAttemptTimeHigh";
    v183 = 4;
    v184 = 0;
    v185 = *((_DWORD *)this + 157);
    v186 = 4;
    v187 = 1;
    v188 = L"LastAttemptTimeLow";
    v189 = 4;
    v190 = 0;
    v191 = *((_DWORD *)this + 156);
    v192 = 4;
    v193 = 1;
    v194 = L"FirstFailureTimeHigh";
    v195 = 4;
    v196 = 0;
    v197 = *((_DWORD *)this + 159);
    v198 = 4;
    v199 = 1;
    v200 = L"FirstFailureTimeLow";
    v201 = 4;
    v202 = 0;
    v203 = *((_DWORD *)this + 158);
    v204 = 4;
    v205 = 1;
    v206 = L"LastAttemptStatus";
    v207 = 4;
    v208 = 0;
    v209 = *((_DWORD *)this + 160);
    v210 = 4;
    v211 = 1;
    v212 = L"LastAttemptTitle";
    v213 = 1;
    v214 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 648);
    v215 = 0;
    v216 = 2 * *((_DWORD *)this + 166) + 2;
    v217 = 1;
    v218 = L"LastAttemptDetail";
    v219 = 1;
    v220 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 680);
    v221 = 0;
    v222 = 2 * *((_DWORD *)this + 174) + 2;
    v223 = 1;
    v224 = L"LoginCookie";
    v225 = 1;
    v226 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 712);
    v227 = 0;
    v228 = 2 * *((_DWORD *)this + 182) + 2;
    v229 = 1;
    v230 = L"EnableFileAssociations";
    v231 = 4;
    v232 = 0;
    v233 = *((_DWORD *)this + 216);
    v234 = 4;
    v235 = 1;
    v236 = L"RDWebServiceURL";
    v237 = 1;
    v238 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 392);
    v239 = 0;
    v240 = 2 * *((_DWORD *)this + 102) + 2;
    v241 = 0;
    v242 = L"CreatedThroughSSP";
    v243 = 4;
    v244 = 0;
    v245 = *((_DWORD *)this + 66);
    v246 = 4;
    v247 = 1;
    v248 = L"SuppressReconnect";
    v249 = 4;
    v250 = 0;
    v251 = *((_DWORD *)this + 46);
    v252 = 4;
    v253 = 1;
    v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 488);
    v9 = RegCreateKeyTransactedW(HKEY_CURRENT_USER, v16, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition, hTransaction, 0);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v9 > 0 )
          v17 = (unsigned __int16)v9 | 0x80070000;
        else
          v17 = v9;
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v18, v17);
      }
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v19 = a2;
      if ( !a2 || dwDisposition == 2 )
      {
        v21 = 0;
        v49 = 0;
        while ( v21 < 0x21 )
        {
          if ( !v19 || v61[10 * v21] )
          {
            v22 = dwType[10 * v21];
            if ( v22 == 4 )
              v23 = (const BYTE *)(&v59 + 10 * v21);
            else
              v23 = (const BYTE *)*(&v58 + 5 * v21);
            v9 = RegSetValueExW(hKey, *(LPCWSTR *)&dwType[10 * v21 - 2], 0, v22, v23, v61[10 * v21 - 1]);
            if ( v9 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                if ( v9 > 0 )
                  v24 = (unsigned __int16)v9 | 0x80070000;
                else
                  v24 = v9;
                v25 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  199,
                  WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                  v25,
                  v24);
              }
              if ( v9 > 0 )
                v9 = (unsigned __int16)v9 | 0x80070000;
              goto LABEL_118;
            }
            v21 = v49;
            v19 = a2;
          }
          v49 = ++v21;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v26);
        }
        v27 = std::operator+<unsigned short>(v53, (char *)this + 488, L"\\");
        v28 = std::operator+<unsigned short>(v54, v27, L"ProgIds");
        v29 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
        v9 = RegCreateKeyTransactedW(
               HKEY_CURRENT_USER,
               v29,
               0,
               0,
               0,
               0x2001Fu,
               0,
               &phkResult,
               &dwDisposition,
               hTransaction,
               0);
        std::wstring::~wstring(v54);
        std::wstring::~wstring(v53);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v30 = (unsigned __int16)v9 | 0x80070000;
            else
              v30 = v9;
            v31 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              201,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v31,
              v30);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          v9 = RegDeleteTreeW(phkResult, 0);
          if ( v9 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              if ( v9 > 0 )
                v32 = (unsigned __int16)v9 | 0x80070000;
              else
                v32 = v9;
              v33 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                202,
                WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v33,
                v32);
            }
            if ( v9 > 0 )
              v9 = (unsigned __int16)v9 | 0x80070000;
          }
          else
          {
            v34 = (char *)this + 744;
            (*(void (__fastcall **)(char *))(*((_QWORD *)this + 93) + 64LL))((char *)this + 744);
            v52[0] = 0;
            while ( (*(unsigned int (__fastcall **)(char *, CWorkspaceFileAssociation **))(*(_QWORD *)v34 + 72LL))(
                      v34,
                      v52) )
            {
              v9 = CWorkspaceFileAssociation::BackupToRegistry(v52[0], hTransaction, phkResult);
              if ( v9 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v35 = RdpWppGetCurrentThreadActivityIdPrefix();
                  Timeout[0] = v9;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    203,
                    (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                    v35,
                    (__int64)"CWorkspaceFileAssociation::BackupToRegistry failed",
                    *(_QWORD *)Timeout);
                }
                goto LABEL_118;
              }
              v34 = (char *)this + 744;
            }
            RegCloseKey(phkResult);
            phkResult = 0;
            v9 = CWorkspace::SaveTaskbarPinPropertiesRegistry(this, hTransaction);
            if ( v9 >= 0 )
            {
              v9 = CWorkspace::SaveResourceMapRegistry(this, hKey, hTransaction, a2);
              if ( v9 >= 0 )
              {
                v9 = CWorkspace::SaveSSPInstalledAppsRegistry(this, hKey, hTransaction);
                if ( v9 >= 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    v39 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      207,
                      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                      v39);
                  }
                  if ( CommitTransaction(hTransaction) )
                  {
                    v9 = 0;
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v40 = GetLastError();
                      v41 = v40;
                      if ( v40 > 0 )
                        v41 = (unsigned __int16)v40 | 0x80070000;
                      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        208,
                        WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                        v42,
                        v41);
                    }
                    v43 = GetLastError();
                    v9 = v43;
                    if ( v43 > 0 )
                      v9 = (unsigned __int16)v43 | 0x80070000;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                  Timeout[0] = v9;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    206,
                    (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                    v38,
                    (__int64)"CWorkspace::SaveSSPInstalledAppsRegistry failed",
                    *(_QWORD *)Timeout);
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v37 = RdpWppGetCurrentThreadActivityIdPrefix();
                Timeout[0] = v9;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  205,
                  (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                  v37,
                  (__int64)"CWorkspace::SaveResourceMapRegistry failed",
                  *(_QWORD *)Timeout);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v36 = RdpWppGetCurrentThreadActivityIdPrefix();
              Timeout[0] = v9;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                204,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v36,
                (__int64)"CWorkspaceTaskbarPin::SaveTaskbarPinPropertiesRegistry failed",
                *(_QWORD *)Timeout);
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            198,
            WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
            v20,
            -2147024809);
        }
        v9 = -2147024809;
      }
    }
  }
LABEL_118:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hTransaction != (HANDLE)-1LL )
    CloseHandle(hTransaction);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180034ffc  mov     r11, rsp
0x180034fff  push    rdi
0x180035000  push    r12
0x180035002  push    r13
0x180035004  push    r14
0x180035006  push    r15
0x180035008  sub     rsp, 640h
0x18003500f  mov     qword ptr [r11-5D0h], 0FFFFFFFFFFFFFFFEh
0x18003501a  mov     [r11+18h], rbx
0x18003501e  mov     [r11+20h], rsi
0x180035022  mov     rax, cs:__security_cookie
0x180035029  xor     rax, rsp
0x18003502c  mov     [rsp+668h+var_30], rax
0x180035034  mov     [rsp+668h+var_604], edx
0x180035038  mov     r13, rcx
0x18003503b  xor     esi, esi
0x18003503d  mov     [rsp+668h+var_5F8], rsi
0x180035042  mov     [r11-5E8h], rsi
0x180035049  mov     [rsp+668h+dwDisposition], esi
0x18003504d  mov     qword ptr [r11-5E0h], 0FFFFFFFFFFFFFFFFh
0x180035058  lea     rdi, WPP_GLOBAL_Control
0x18003505f  mov     rax, cs:WPP_GLOBAL_Control
0x180035066  lea     ebx, [rsi+1]
0x180035069  lea     r12d, [rsi+4]
0x18003506d  cmp     rax, rdi
0x180035070  jz      short loc_1800350A6
0x180035072  test    [rax+1Ch], bl
0x180035075  jz      short loc_1800350A6
0x180035077  cmp     [rax+19h], r12b
0x18003507b  jb      short loc_1800350A6
0x18003507d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180035082  mov     edx, 0C2h
0x180035087  mov     r9d, eax
0x18003508a  lea     r14, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180035091  mov     r8, r14
0x180035094  mov     rcx, cs:WPP_GLOBAL_Control
0x18003509b  mov     rcx, [rcx+10h]
0x18003509f  call    WPP_SF_D
0x1800350a4  jmp     short loc_1800350AD
0x1800350a6  lea     r14, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800350ad  lea     rax, aSavingWorkspac; "Saving workspace registry data"
0x1800350b4  mov     [rsp+668h+Description], rax; Description
0x1800350b9  mov     [rsp+668h+Timeout], 2710h; Timeout
0x1800350c1  mov     [rsp+668h+IsolationFlags], esi; IsolationFlags
0x1800350c5  xor     r9d, r9d; IsolationLevel
0x1800350c8  mov     r8d, ebx; CreateOptions
0x1800350cb  xor     edx, edx; UOW
0x1800350cd  xor     ecx, ecx; lpTransactionAttributes
0x1800350cf  call    cs:__imp_CreateTransaction
0x1800350d5  mov     r15, rax
0x1800350d8  mov     [rsp+668h+var_5E0], rax
0x1800350e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800350e4  jnz     short loc_180035159
0x1800350e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800350ed  cmp     rax, rdi
0x1800350f0  jz      short loc_18003513B
0x1800350f2  test    byte ptr [rax+1Ch], 8
0x1800350f6  jz      short loc_18003513B
0x1800350f8  lea     edi, [r15+3]
0x1800350fc  cmp     [rax+19h], dil
0x180035100  jb      short loc_18003513B
0x180035102  call    cs:__imp_GetLastError
0x180035108  mov     ebx, eax
0x18003510a  test    eax, eax
0x18003510c  jle     short loc_180035117
0x18003510e  movzx   ebx, ax
0x180035111  or      ebx, 80070000h
0x180035117  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003511c  mov     edx, 0C3h
0x180035121  mov     [rsp+668h+IsolationFlags], ebx
0x180035125  mov     r9d, eax
0x180035128  mov     r8, r14
0x18003512b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035132  mov     rcx, [rcx+10h]
0x180035136  call    WPP_SF_Dd
0x18003513b  call    cs:__imp_GetLastError
0x180035141  mov     ebx, eax
0x180035143  test    eax, eax
0x180035145  jle     short loc_180035150
0x180035147  movzx   ebx, ax
0x18003514a  or      ebx, 80070000h
0x180035150  mov     [rsp+668h+var_608], ebx
0x180035154  jmp     loc_1800361CA
0x180035159  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Workspaces\\Feeds"
0x180035160  lea     rcx, [rsp+668h+var_5A8]
0x180035168  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18003516d  nop
0x18003516e  lea     r8, SubStr; "\\"
0x180035175  mov     rdx, rax
0x180035178  lea     rcx, [rsp+668h+var_5C8]
0x180035180  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180035185  nop
0x180035186  lea     rdi, [r13+40h]
0x18003518a  mov     r8, rdi
0x18003518d  mov     rdx, rax
0x180035190  lea     rcx, [rsp+668h+var_588]
0x180035198  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18003519d  nop
0x18003519e  lea     rcx, [r13+1E8h]
0x1800351a5  mov     rdx, rax
0x1800351a8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800351ad  nop
0x1800351ae  lea     rcx, [rsp+668h+var_588]; void *
0x1800351b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800351bb  nop
0x1800351bc  lea     rcx, [rsp+668h+var_5C8]; void *
0x1800351c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800351c9  nop
0x1800351ca  lea     rcx, [rsp+668h+var_5A8]; void *
0x1800351d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800351d7  mov     rax, cs:WPP_GLOBAL_Control
0x1800351de  lea     rcx, WPP_GLOBAL_Control
0x1800351e5  cmp     rax, rcx
0x1800351e8  jz      short loc_180035246
0x1800351ea  test    [rax+1Ch], bl
0x1800351ed  jz      short loc_180035246
0x1800351ef  cmp     [rax+19h], r12b
0x1800351f3  jb      short loc_180035246
0x1800351f5  lea     rcx, [r13+128h]
0x1800351fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035201  mov     rdi, rax
0x180035204  lea     rcx, [r13+1E8h]
0x18003520b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035210  mov     rbx, rax
0x180035213  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180035218  mov     edx, 0C4h
0x18003521d  mov     qword ptr [rsp+668h+Timeout], rdi; __int64
0x180035222  mov     qword ptr [rsp+668h+IsolationFlags], rbx; __int64
0x180035227  mov     r9d, eax
0x18003522a  mov     r8, r14
0x18003522d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035234  mov     rcx, [rcx+10h]; LoggerHandle
0x180035238  call    WPP_SF_DSS
0x18003523d  mov     ebx, 1
0x180035242  lea     rdi, [r13+40h]
0x180035246  cmp     [rsp+668h+var_604], esi
0x18003524a  jnz     short loc_18003525A
0x18003524c  cmp     [r13+60h], esi
0x180035250  jz      short loc_18003525A
0x180035252  mov     rcx, rdi
0x180035255  call    ?WriteDefaultWorkspaceGUID@CWorkspaceManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CWorkspaceManager::WriteDefaultWorkspaceGUID(std::wstring const &)
0x18003525a  lea     rax, aId; "Id"
0x180035261  mov     [rsp+668h+lpValueName], rax
0x180035269  mov     [rsp+668h+dwType], ebx
0x180035270  mov     rcx, rdi
0x180035273  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035278  mov     [rsp+668h+var_558], rax
0x180035280  mov     [rsp+668h+var_550], esi
0x180035287  mov     eax, [r13+50h]
0x18003528b  lea     eax, ds:2[rax*2]
0x180035292  mov     [rsp+668h+cbData], eax
0x180035299  mov     [rsp+668h+var_548], esi
0x1800352a0  lea     rax, aUrl; "URL"
0x1800352a7  mov     [rsp+668h+var_540], rax
0x1800352af  mov     [rsp+668h+var_538], ebx
0x1800352b6  lea     rcx, [r13+128h]
0x1800352bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800352c2  mov     [rsp+668h+var_530], rax
0x1800352ca  mov     [rsp+668h+var_528], esi
0x1800352d1  mov     eax, [r13+138h]
0x1800352d8  lea     eax, ds:2[rax*2]
0x1800352df  mov     [rsp+668h+var_524], eax
0x1800352e6  mov     [rsp+668h+var_520], esi
0x1800352ed  lea     rax, aFeeddiscoveryu; "FeedDiscoveryURL"
0x1800352f4  mov     [rsp+668h+var_518], rax
0x1800352fc  mov     [rsp+668h+var_510], ebx
0x180035303  lea     rcx, [r13+148h]
0x18003530a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003530f  mov     [rsp+668h+var_508], rax
0x180035317  mov     [rsp+668h+var_500], esi
0x18003531e  mov     eax, [r13+158h]
0x180035325  lea     eax, ds:2[rax*2]
0x18003532c  mov     [rsp+668h+var_4FC], eax
0x180035333  mov     [rsp+668h+var_4F8], esi
0x18003533a  lea     rax, aClaimshint; "ClaimsHint"
0x180035341  mov     [rsp+668h+var_4F0], rax
0x180035349  mov     [rsp+668h+var_4E8], ebx
0x180035350  lea     rcx, [r13+168h]
0x180035357  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003535c  mov     [rsp+668h+var_4E0], rax
0x180035364  mov     [rsp+668h+var_4D8], esi
0x18003536b  mov     eax, [r13+178h]
0x180035372  lea     eax, ds:2[rax*2]
0x180035379  mov     [rsp+668h+var_4D4], eax
0x180035380  mov     [rsp+668h+var_4D0], esi
0x180035387  lea     rax, aUsername; "UserName"
0x18003538e  mov     [rsp+668h+var_4C8], rax
0x180035396  mov     [rsp+668h+var_4C0], ebx
0x18003539d  lea     rcx, [r13+228h]
0x1800353a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800353a9  mov     [rsp+668h+var_4B8], rax
0x1800353b1  mov     [rsp+668h+var_4B0], esi
0x1800353b8  mov     eax, [r13+238h]
0x1800353bf  lea     eax, ds:2[rax*2]
0x1800353c6  mov     [rsp+668h+var_4AC], eax
0x1800353cd  mov     [rsp+668h+var_4A8], esi
0x1800353d4  lea     rax, aEnableautoupda; "EnableAutoUpdate"
0x1800353db  mov     [rsp+668h+var_4A0], rax
0x1800353e3  mov     [rsp+668h+var_498], r12d
0x1800353eb  mov     [rsp+668h+var_490], rsi
0x1800353f3  mov     eax, [r13+0A8h]
0x1800353fa  mov     [rsp+668h+var_488], eax
0x180035401  mov     [rsp+668h+var_484], r12d
0x180035409  mov     [rsp+668h+var_480], esi
0x180035410  lea     rax, aUseclaimsauth; "UseClaimsAuth"
0x180035417  mov     [rsp+668h+var_478], rax
0x18003541f  mov     [rsp+668h+var_470], r12d
0x180035427  mov     [rsp+668h+var_468], rsi
0x18003542f  mov     eax, [r13+0ACh]
0x180035436  mov     [rsp+668h+var_460], eax
0x18003543d  mov     [rsp+668h+var_45C], r12d
0x180035445  mov     [rsp+668h+var_458], esi
0x18003544c  lea     rax, aCreatedtimehig; "CreatedTimeHigh"
0x180035453  mov     [rsp+668h+var_450], rax
0x18003545b  mov     [rsp+668h+var_448], r12d
0x180035463  mov     [rsp+668h+var_440], rsi
0x18003546b  mov     eax, [r13+264h]
0x180035472  mov     [rsp+668h+var_438], eax
0x180035479  mov     [rsp+668h+var_434], r12d
0x180035481  mov     [rsp+668h+var_430], esi
0x180035488  lea     rax, aCreatedtimelow; "CreatedTimeLow"
0x18003548f  mov     [rsp+668h+var_428], rax
0x180035497  mov     [rsp+668h+var_420], r12d
0x18003549f  mov     [rsp+668h+var_418], rsi
0x1800354a7  mov     eax, [r13+260h]
0x1800354ae  mov     [rsp+668h+var_410], eax
0x1800354b5  mov     [rsp+668h+var_40C], r12d
0x1800354bd  mov     [rsp+668h+var_408], esi
0x1800354c4  lea     rax, aPublisher; "Publisher"
0x1800354cb  mov     [rsp+668h+var_400], rax
0x1800354d3  mov     [rsp+668h+var_3F8], ebx
0x1800354da  lea     rcx, [r13+68h]
0x1800354de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800354e3  mov     [rsp+668h+var_3F0], rax
0x1800354eb  mov     [rsp+668h+var_3E8], esi
0x1800354f2  mov     eax, [r13+78h]
0x1800354f6  lea     eax, ds:2[rax*2]
0x1800354fd  mov     [rsp+668h+var_3E4], eax
0x180035504  mov     [rsp+668h+var_3E0], ebx
0x18003550b  lea     rax, aWorkspaceid; "WorkspaceId"
0x180035512  mov     [rsp+668h+var_3D8], rax
0x18003551a  mov     [rsp+668h+var_3D0], ebx
0x180035521  lea     rcx, [r13+88h]
0x180035528  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003552d  mov     [rsp+668h+var_3C8], rax
0x180035535  mov     [rsp+668h+var_3C0], esi
0x18003553c  mov     eax, [r13+98h]
0x180035543  lea     eax, ds:2[rax*2]
0x18003554a  mov     [rsp+668h+var_3BC], eax
0x180035551  mov     [rsp+668h+var_3B8], ebx
0x180035558  lea     rax, aPublishernames; "PublisherNameSuffix"
0x18003555f  mov     [rsp+668h+var_3B0], rax
0x180035567  mov     [rsp+668h+var_3A8], r12d
0x18003556f  mov     [rsp+668h+var_3A0], rsi
0x180035577  mov     eax, [r13+120h]
0x18003557e  mov     [rsp+668h+var_398], eax
0x180035585  mov     [rsp+668h+var_394], r12d
0x18003558d  mov     [rsp+668h+var_390], ebx
0x180035594  lea     rax, aWorkspacefolde; "WorkspaceFolder"
0x18003559b  mov     [rsp+668h+var_388], rax
0x1800355a3  mov     edi, 2
0x1800355a8  mov     [rsp+668h+var_380], edi
0x1800355af  lea     rcx, [r13+1A8h]
0x1800355b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800355bb  mov     [rsp+668h+var_378], rax
0x1800355c3  mov     [rsp+668h+var_370], esi
0x1800355ca  mov     eax, [r13+1B8h]
0x1800355d1  lea     eax, ds:2[rax*2]
0x1800355d8  mov     [rsp+668h+var_36C], eax
0x1800355df  mov     [rsp+668h+var_368], ebx
0x1800355e6  lea     rax, aStartmenuroot; "StartMenuRoot"
0x1800355ed  mov     [rsp+668h+var_360], rax
0x1800355f5  mov     [rsp+668h+var_358], edi
0x1800355fc  lea     rcx, [r13+1C8h]
0x180035603  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035608  mov     [rsp+668h+var_350], rax
0x180035610  mov     [rsp+668h+var_348], esi
0x180035617  mov     eax, [r13+1D8h]
0x18003561e  lea     eax, ds:2[rax*2]
0x180035625  mov     [rsp+668h+var_344], eax
0x18003562c  mov     [rsp+668h+var_340], ebx
0x180035633  lea     rax, aNumpublishedre; "NumPublishedResources"
0x18003563a  mov     [rsp+668h+var_338], rax
0x180035642  mov     [rsp+668h+var_330], r12d
0x18003564a  mov     [rsp+668h+var_328], rsi
0x180035652  mov     eax, [r13+248h]
0x180035659  mov     [rsp+668h+var_320], eax
0x180035660  mov     [rsp+668h+var_31C], r12d
0x180035668  mov     [rsp+668h+var_318], ebx
0x18003566f  lea     rax, aNumdownloadedr; "NumDownloadedResourceFiles"
0x180035676  mov     [rsp+668h+var_310], rax
0x18003567e  mov     [rsp+668h+var_308], r12d
0x180035686  mov     [rsp+668h+var_300], rsi
0x18003568e  mov     eax, [r13+24Ch]
0x180035695  mov     [rsp+668h+var_2F8], eax
0x18003569c  mov     [rsp+668h+var_2F4], r12d
0x1800356a4  mov     [rsp+668h+var_2F0], ebx
0x1800356ab  lea     rax, aNumdownloadedi; "NumDownloadedIcons"
0x1800356b2  mov     [rsp+668h+var_2E8], rax
0x1800356ba  mov     [rsp+668h+var_2E0], r12d
  ... truncated ...
```
