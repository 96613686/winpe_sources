# CWorkspace::CreateStartMenuItemsAndResourceMap(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,TS_WORKSPACE_DOWNLOAD_INFO,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,TS_WORKSPACE_DOWNLOAD_INFO>>> &)

- ea: `0x18002b1a8`
- end: `0x18002caaf`
- name: `?CreateStartMenuItemsAndResourceMap@CWorkspace@@QEAAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTS_WORKSPACE_DOWNLOAD_INFO@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTS_WORKSPACE_DOWNLOAD_INFO@@@std@@@2@@std@@@Z`
- size: `6407`
- prototype: `__int64 __fastcall(CWorkspace *this, __int64)`
- caller_count: `1`
- callee_count: `63`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a840`

## callees

- `0x180002214`
- `0x180004970`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001b7e4`
- `0x18001e41c`
- `0x18001e5d8`
- `0x18001e610`
- `0x18001e92c`
- `0x18001e974`
- `0x18001eac4`
- `0x18001ead4`
- `0x1800208a8`
- `0x180020a68`
- `0x180020bf0`
- `0x180025950`
- `0x1800259d8`
- `0x1800276f4`
- `0x180027720`
- `0x180027810`
- `0x180027dc0`
- `0x18002830c`
- `0x180028354`
- `0x180028860`
- `0x180028920`
- `0x1800289f0`
- `0x180028a6c`
- `0x180028ca0`
- `0x180028d04`
- `0x180028dd8`
- `0x18002915c`
- `0x18002a9a4`
- `0x18002b1a8`
- `0x18002e6fc`
- `0x18002f29c`
- `0x18002fa8c`
- `0x18002fd30`
- `0x18003283c`
- `0x180034224`
- `0x180037b6c`
- `0x1800382c4`
- `0x18003add8`
- `0x18003c824`
- `0x18003c954`
- `0x18003cc8c`

## import_xrefs

- `KERNEL32!RegDeleteTreeW` at `0x18002b8bf`
- `KERNEL32!RegDeleteTreeW` at `0x18002b8bf`
- `SHLWAPI!PathFileExistsW` at `0x18002c385`
- `SHLWAPI!PathFileExistsW` at `0x18002c385`
- `SHELL32!SHChangeNotify` at `0x18002c8ff`
- `SHELL32!SHChangeNotify` at `0x18002c8ff`
- `SHELL32!SHCreateDirectoryExW` at `0x18002b666`
- `SHELL32!SHCreateDirectoryExW` at `0x18002b6e2`
- `SHELL32!SHCreateDirectoryExW` at `0x18002b666`
- `SHELL32!SHCreateDirectoryExW` at `0x18002b6e2`

## string_xrefs

- `0x18002b2f2`: `GetCombinedResourceTypeMap failed`
- `0x18002ba18`: `%systemroot%\system32\mstsc.exe`
- `0x18002ba32`: `%systemroot%\system32\mstsc.exe`
- `0x18002bf54`: `%systemroot%\system32\mstsc.exe`
- `0x18002c046`: `CWorkspaceTaskbarPin::Initialize failed`
- `0x18002c93d`: `CWorkspace::ApplyTaskbarPinRules failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CWorkspace::CreateStartMenuItemsAndResourceMap(CWorkspace *this, __int64 a2)
{
  CWorkspace *v2; // rsi
  int v3; // r14d
  int CombinedResourceTypeMap; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // eax
  const unsigned __int16 *v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rbx
  unsigned int v16; // eax
  const WCHAR *v17; // rax
  __int64 v18; // rbx
  unsigned int v19; // eax
  const WCHAR *v20; // rax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  const WCHAR *v27; // rax
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r11
  __int64 v34; // rbx
  __int64 v35; // rbx
  unsigned int v36; // eax
  int v37; // edx
  __int64 v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rbx
  unsigned int v46; // eax
  CWorkspaceAppID *v47; // rax
  __int64 v48; // r14
  __int64 v49; // rsi
  CWorkspaceAppID *v50; // rbx
  __int64 FinalAppID; // rax
  __int64 v52; // r14
  CWorkspaceAppID *v53; // rbx
  __int64 v54; // rbx
  unsigned int v55; // eax
  __int64 v56; // r14
  __int64 v57; // rsi
  __int64 v58; // rax
  __int64 v59; // rdi
  __int64 v60; // rbx
  __int64 v61; // rdi
  CWorkspaceTaskbarPin *v62; // rax
  CWorkspaceTaskbarPin *v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rbx
  unsigned int v67; // eax
  __int64 v68; // rcx
  __int64 v69; // rbx
  unsigned int v70; // eax
  __int64 v71; // rcx
  __int64 v72; // rbx
  __int64 v73; // rax
  unsigned int v74; // eax
  __int64 v75; // rax
  __int64 v76; // rax
  int v77; // eax
  unsigned int v78; // eax
  __int64 v79; // rax
  unsigned int v80; // eax
  unsigned int v81; // ebx
  __int64 v82; // rax
  unsigned int v83; // eax
  __int64 v84; // rax
  int Shortcut; // ebx
  unsigned int v86; // eax
  __int64 v87; // rax
  void *v88; // rax
  __int64 v89; // rax
  __int64 v90; // r8
  __int64 v91; // rbx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rbx
  __int64 v95; // rax
  __int64 v96; // rax
  _WORD *v97; // rax
  __int64 v98; // r14
  __int64 v99; // rsi
  __int64 v100; // rdi
  __int64 v101; // rbx
  __int64 v102; // rax
  __int64 v103; // rax
  int v104; // ebx
  unsigned int v105; // eax
  __int64 v106; // rax
  __int64 v107; // rbx
  unsigned int v108; // eax
  unsigned int v109; // eax
  unsigned int v110; // eax
  unsigned int v111; // eax
  __int64 v113; // [rsp+20h] [rbp-A18h]
  __int64 v114; // [rsp+20h] [rbp-A18h]
  __int64 v115; // [rsp+28h] [rbp-A10h]
  __int64 v116; // [rsp+40h] [rbp-9F8h] BYREF
  int v117; // [rsp+48h] [rbp-9F0h]
  __int64 v118; // [rsp+50h] [rbp-9E8h] BYREF
  CWorkspaceAppID *v119; // [rsp+58h] [rbp-9E0h] BYREF
  int v120; // [rsp+60h] [rbp-9D8h]
  __int64 v121; // [rsp+68h] [rbp-9D0h]
  __int64 v122; // [rsp+70h] [rbp-9C8h]
  __int64 v123; // [rsp+78h] [rbp-9C0h]
  unsigned int v124; // [rsp+80h] [rbp-9B8h]
  __int64 v125; // [rsp+88h] [rbp-9B0h] BYREF
  __int64 i; // [rsp+90h] [rbp-9A8h] BYREF
  CWorkspace *v127; // [rsp+98h] [rbp-9A0h]
  __int64 v128; // [rsp+A0h] [rbp-998h] BYREF
  __int64 v129; // [rsp+A8h] [rbp-990h] BYREF
  _QWORD v130[2]; // [rsp+B0h] [rbp-988h] BYREF
  _BYTE v131[16]; // [rsp+C0h] [rbp-978h] BYREF
  int v132; // [rsp+D0h] [rbp-968h]
  int v133; // [rsp+D4h] [rbp-964h]
  _BYTE v134[16]; // [rsp+D8h] [rbp-960h] BYREF
  char v135[8]; // [rsp+E8h] [rbp-950h] BYREF
  char v136[8]; // [rsp+F0h] [rbp-948h] BYREF
  char v137[8]; // [rsp+F8h] [rbp-940h] BYREF
  char v138[8]; // [rsp+100h] [rbp-938h] BYREF
  _BYTE *v139; // [rsp+108h] [rbp-930h]
  CWorkspaceAppID *v140; // [rsp+110h] [rbp-928h]
  _BYTE *v141; // [rsp+118h] [rbp-920h]
  _BYTE *v142; // [rsp+120h] [rbp-918h]
  _BYTE *v143; // [rsp+128h] [rbp-910h]
  _BYTE *v144; // [rsp+130h] [rbp-908h]
  _BYTE *v145; // [rsp+138h] [rbp-900h]
  _BYTE *v146; // [rsp+140h] [rbp-8F8h]
  _BYTE *v147; // [rsp+148h] [rbp-8F0h]
  _BYTE *v148; // [rsp+150h] [rbp-8E8h]
  _BYTE *v149; // [rsp+158h] [rbp-8E0h]
  _BYTE *v150; // [rsp+160h] [rbp-8D8h]
  CWorkspaceTaskbarPin *v151; // [rsp+168h] [rbp-8D0h]
  _BYTE *v152; // [rsp+170h] [rbp-8C8h]
  char v153[8]; // [rsp+178h] [rbp-8C0h] BYREF
  char v154[8]; // [rsp+180h] [rbp-8B8h] BYREF
  char v155[8]; // [rsp+188h] [rbp-8B0h] BYREF
  char v156[8]; // [rsp+190h] [rbp-8A8h] BYREF
  char v157[8]; // [rsp+198h] [rbp-8A0h] BYREF
  _BYTE *v158; // [rsp+1A0h] [rbp-898h]
  _BYTE *v159; // [rsp+1A8h] [rbp-890h]
  _BYTE *v160; // [rsp+1B0h] [rbp-888h]
  _BYTE *v161; // [rsp+1B8h] [rbp-880h]
  _BYTE *v162; // [rsp+1C0h] [rbp-878h]
  char v163[8]; // [rsp+1C8h] [rbp-870h] BYREF
  __int64 v164; // [rsp+1D0h] [rbp-868h]
  char v165[8]; // [rsp+1D8h] [rbp-860h] BYREF
  _BYTE v166[32]; // [rsp+1E0h] [rbp-858h] BYREF
  _BYTE v167[32]; // [rsp+200h] [rbp-838h] BYREF
  _BYTE v168[32]; // [rsp+220h] [rbp-818h] BYREF
  _BYTE v169[32]; // [rsp+240h] [rbp-7F8h] BYREF
  _BYTE v170[32]; // [rsp+260h] [rbp-7D8h] BYREF
  _BYTE v171[32]; // [rsp+280h] [rbp-7B8h] BYREF
  _BYTE v172[32]; // [rsp+2A0h] [rbp-798h] BYREF
  _BYTE v173[32]; // [rsp+2C0h] [rbp-778h] BYREF
  _BYTE v174[32]; // [rsp+2E0h] [rbp-758h] BYREF
  _BYTE v175[32]; // [rsp+300h] [rbp-738h] BYREF
  _BYTE v176[32]; // [rsp+320h] [rbp-718h] BYREF
  _BYTE v177[32]; // [rsp+340h] [rbp-6F8h] BYREF
  _BYTE v178[32]; // [rsp+360h] [rbp-6D8h] BYREF
  _BYTE v179[32]; // [rsp+380h] [rbp-6B8h] BYREF
  _BYTE v180[32]; // [rsp+3A0h] [rbp-698h] BYREF
  _BYTE v181[32]; // [rsp+3C0h] [rbp-678h] BYREF
  _BYTE v182[32]; // [rsp+3E0h] [rbp-658h] BYREF
  _BYTE v183[16]; // [rsp+400h] [rbp-638h] BYREF
  __int64 v184; // [rsp+410h] [rbp-628h]
  _BYTE v185[32]; // [rsp+420h] [rbp-618h] BYREF
  _BYTE v186[32]; // [rsp+440h] [rbp-5F8h] BYREF
  _BYTE v187[32]; // [rsp+460h] [rbp-5D8h] BYREF
  _BYTE v188[32]; // [rsp+480h] [rbp-5B8h] BYREF
  _BYTE v189[32]; // [rsp+4A0h] [rbp-598h] BYREF
  _BYTE v190[32]; // [rsp+4C0h] [rbp-578h] BYREF
  _BYTE v191[32]; // [rsp+4E0h] [rbp-558h] BYREF
  _BYTE v192[32]; // [rsp+500h] [rbp-538h] BYREF
  _BYTE v193[32]; // [rsp+520h] [rbp-518h] BYREF
  int v194; // [rsp+540h] [rbp-4F8h] BYREF
  int v195; // [rsp+544h] [rbp-4F4h]
  char v196[32]; // [rsp+550h] [rbp-4E8h] BYREF
  char v197[32]; // [rsp+570h] [rbp-4C8h] BYREF
  char v198[32]; // [rsp+590h] [rbp-4A8h] BYREF
  char v199[32]; // [rsp+5B0h] [rbp-488h] BYREF
  char v200[16]; // [rsp+5D0h] [rbp-468h] BYREF
  _BYTE v201[32]; // [rsp+5E0h] [rbp-458h] BYREF
  _BYTE v202[32]; // [rsp+600h] [rbp-438h] BYREF
  _BYTE v203[32]; // [rsp+620h] [rbp-418h] BYREF
  _BYTE v204[32]; // [rsp+640h] [rbp-3F8h] BYREF
  _BYTE v205[32]; // [rsp+660h] [rbp-3D8h] BYREF
  _BYTE v206[32]; // [rsp+680h] [rbp-3B8h] BYREF
  _BYTE v207[32]; // [rsp+6A0h] [rbp-398h] BYREF
  _BYTE v208[32]; // [rsp+6C0h] [rbp-378h] BYREF
  _BYTE v209[32]; // [rsp+6E0h] [rbp-358h] BYREF
  _BYTE v210[240]; // [rsp+700h] [rbp-338h] BYREF
  WCHAR pszPath[268]; // [rsp+7F0h] [rbp-248h] BYREF

  v164 = -2;
  v123 = a2;
  v2 = this;
  v127 = this;
  v130[1] = this;
  v3 = 0;
  v117 = 0;
  v120 = 0;
  std::wstring::wstring(v193);
  std::wstring::wstring(v183);
  std::wstring::wstring(v192);
  std::wstring::wstring(v185);
  std::wstring::wstring(v191);
  std::wstring::wstring(v187);
  std::wstring::wstring(v188);
  std::wstring::wstring(v190);
  std::map<std::wstring,ResourceTypeInfo>::map<std::wstring,ResourceTypeInfo>(v131);
  ResourceMapNode::ResourceMapNode((ResourceMapNode *)&v194);
  std::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(v134);
  *((_DWORD *)v2 + 150) = 0;
  *((_DWORD *)v2 + 151) = 0;
  CombinedResourceTypeMap = CResourceTypeManager::GetCombinedResourceTypeMap(v131);
  LODWORD(v116) = CombinedResourceTypeMap;
  if ( CombinedResourceTypeMap < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        125,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"GetCombinedResourceTypeMap failed",
        CombinedResourceTypeMap);
    }
    goto LABEL_212;
  }
  CombinedResourceTypeMap = CWorkspace::GetUniquePublisherName(v2, pszPath, 0x104u);
  LODWORD(v116) = CombinedResourceTypeMap;
  if ( CombinedResourceTypeMap < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v6,
        (__int64)"GetUniquePublisherName failed",
        CombinedResourceTypeMap);
    }
    goto LABEL_212;
  }
  std::wstring::assign(v190, pszPath);
  CombinedResourceTypeMap = CWorkspaceManager::GetStartMenuBaseFolder(v193);
  LODWORD(v116) = CombinedResourceTypeMap;
  if ( CombinedResourceTypeMap < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        127,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v7,
        (__int64)"GetStartMenuBaseFolder failed",
        CombinedResourceTypeMap);
    }
    goto LABEL_212;
  }
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v190);
  CombinedResourceTypeMap = TSWFormatString(g_hinst, 0x3B73u, pszPath, 0x104u, v8);
  LODWORD(v116) = CombinedResourceTypeMap;
  if ( CombinedResourceTypeMap < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        128,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v9,
        (__int64)"TSWFormatString failed",
        CombinedResourceTypeMap);
    }
    goto LABEL_212;
  }
  v10 = std::operator+<unsigned short>(v203, v193, L"\\");
  v11 = std::operator+<unsigned short>(v206, v10, pszPath);
  std::wstring::operator=(v183, v11);
  std::wstring::~wstring(v206);
  std::wstring::~wstring(v203);
  if ( (unsigned __int64)(260 - v184) <= 0xA )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v12,
        -2147220989);
    }
    CombinedResourceTypeMap = -2147220989;
    LODWORD(v116) = -2147220989;
    goto LABEL_213;
  }
  v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v183);
  if ( !(unsigned int)IsPathCanonical(v13) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v14,
        -2147220989);
    }
    CombinedResourceTypeMap = -2147220989;
    LODWORD(v116) = -2147220989;
    goto LABEL_213;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v183);
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      v16,
      v15);
  }
  v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v183);
  CombinedResourceTypeMap = SHCreateDirectoryExW(0, v17, 0);
  if ( CombinedResourceTypeMap == 183 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v183);
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        CombinedResourceTypeMap - 51,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v19,
        v18);
    }
    WipeoutFolder(v183);
    v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v183);
    CombinedResourceTypeMap = SHCreateDirectoryExW(0, v20, 0);
  }
  if ( CombinedResourceTypeMap )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( CombinedResourceTypeMap > 0 )
        v21 = (unsigned __int16)CombinedResourceTypeMap | 0x80070000;
      else
        v21 = CombinedResourceTypeMap;
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v22, v21);
    }
    if ( CombinedResourceTypeMap > 0 )
      CombinedResourceTypeMap = (unsigned __int16)CombinedResourceTypeMap | 0x80070000;
    LODWORD(v116) = CombinedResourceTypeMap;
    goto LABEL_212;
  }
  CombinedResourceTypeMap = CWorkspace::SetStartMenuFolder(v2, v183);
  LODWORD(v116) = CombinedResourceTypeMap;
  if ( CombinedResourceTypeMap < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v23,
        (__int64)"SetStartMenuLocation failed",
        CombinedResourceTypeMap);
    }
LABEL_212:
    if ( CombinedResourceTypeMap < 0 )
      goto LABEL_213;
    goto LABEL_214;
  }
  if ( *((_DWORD *)v2 + 191) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        135,
        WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v24,
        -2147467259);
    }
    CombinedResourceTypeMap = -2147467259;
    LODWORD(v116) = -2147467259;
    goto LABEL_213;
  }
  if ( *((_DWORD *)v2 + 213) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        136,
        WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v25,
        -2147467259);
    }
    CombinedResourceTypeMap = -2147467259;
    LODWORD(v116) = -2147467259;
    goto LABEL_213;
  }
  v26 = std::operator+<unsigned short>(v204, (char *)v2 + 488, L"\\");
  std::operator+<unsigned short>(v186, v26, L"AppIds");
  std::wstring::~wstring(v204);
  v27 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v186);
  v28 = RegDeleteTreeW(HKEY_CURRENT_USER, v27);
  if ( v28 > 0 )
    v28 = (unsigned __int16)v28 | 0x80070000;
  LODWORD(v116) = v28;
  v118 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
                      v123,
                      &v119,
                      v123);
  while ( 1 )
  {
    v30 = std::vector<unsigned int>::begin(v29, v165);
    if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                             &v118,
                             v30) )
      break;
    v32 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v118);
    v34 = v32;
    v121 = v32;
    if ( *(_DWORD *)(v32 + 36) )
      goto LABEL_192;
    if ( *(int *)(v32 + 208) >= 0 )
    {
      v38 = v32 + 112;
      std::wstring::operator=(v192, v32 + 112);
      v128 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,TS_WORKSPACE_DOWNLOAD_INFO,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>,0>>::find(
                          v123,
                          v135,
                          v34 + 216);
      v39 = std::vector<unsigned int>::begin(v123, v136);
      if ( (unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                              &v128,
                              v39)
        && (v40 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v128),
            *(int *)(v40 + 208) >= 0) )
      {
        std::wstring::operator=(v185, v40 + 112);
      }
      else
      {
        std::wstring::assign(v185, L"%systemroot%\\system32\\mstsc.exe");
      }
      if ( *(_DWORD *)(v34 + 40) )
      {
        std::wstring::assign(v191, L"%systemroot%\\system32\\mstsc.exe");
        goto LABEL_94;
      }
      v129 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::find(
                          v131,
                          v137,
                          v34 + 176);
      v41 = std::vector<unsigned int>::begin(v131, v138);
      if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ResourceTypeInfo>>>>::operator==(
                               v41,
                               &v129) )
      {
        v42 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v129);
        std::wstring::operator=(v191, v42 + 64);
LABEL_94:
        BYTE4(v116) = 0;
        if ( *(_DWORD *)(v34 + 40)
          && (v139 = v169,
              v43 = std::wstring::wstring(v169, v38),
              CWorkspace::GetAppID(v44, v43, (char *)&v116 + 4, v187),
              BYTE4(v116)) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34 + 280);
            v46 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              139,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v46,
              v45);
            v34 = v121;
          }
          v47 = (CWorkspaceAppID *)operator new(0xE8u);
          v140 = v47;
          if ( v47 )
            v119 = CWorkspaceAppID::CWorkspaceAppID(v47);
          else
            v119 = 0;
          v141 = v170;
          v48 = std::wstring::wstring(v170, (char *)v2 + 64);
          v142 = v171;
          v49 = std::wstring::wstring(v171, v38);
          v143 = v166;
          std::wstring::wstring(v166, v185);
          v144 = v167;
          v122 = v34 + 144;
          std::wstring::wstring(v167, v34 + 144);
          v145 = v168;
          std::wstring::wstring(v168, v187);
          v50 = v119;
          CWorkspaceAppID::Initialize(v119, v49, v48);
          v2 = v127;
          (*(void (__fastcall **)(char *, CWorkspaceAppID *))(*((_QWORD *)v127 + 97) + 8LL))((char *)v127 + 776, v50);
          FinalAppID = CWorkspaceAppID::GetFinalAppID(v50, v205);
          std::wstring::operator=(v187, FinalAppID);
          std::wstring::~wstring(v205);
          v52 = v121;
          v53 = (CWorkspaceAppID *)(v121 + 280);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34 + 280);
            v55 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              140,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v55,
              v54);
            v34 = v121;
          }
          CWorkspaceAppID::CWorkspaceAppID((CWorkspaceAppID *)v210);
          v146 = v172;
          v56 = std::wstring::wstring(v172, (char *)v2 + 64);
          v147 = v173;
          v57 = std::wstring::wstring(v173, v38);
          v148 = v174;
          std::wstring::wstring(v174, v185);
          v149 = v175;
          v122 = v34 + 144;
          std::wstring::wstring(v175, v34 + 144);
          v150 = v176;
          v119 = (CWorkspaceAppID *)(v121 + 280);
          std::wstring::wstring(v176, v121 + 280);
          CWorkspaceAppID::Initialize((CWorkspaceAppID *)v210, v57, v56);
          v58 = CWorkspaceAppID::GetFinalAppID(v210, v207);
          std::wstring::operator=(v187, v58);
          std::wstring::~wstring(v207);
          CWorkspaceAppID::~CWorkspaceAppID((CWorkspaceAppID *)v210);
          v2 = v127;
          v52 = v121;
          v53 = v119;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v59 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v187);
          v60 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v60, v59);
        }
        if ( *(_QWORD *)(v52 + 360) )
        {
          v62 = (CWorkspaceTaskbarPin *)operator new(0xB8u);
          v151 = v62;
          if ( v62 )
            v63 = CWorkspaceTaskbarPin::CWorkspaceTaskbarPin(v62);
          else
            v63 = 0;
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v125, v63);
          std::wstring::wstring(v189, L"%systemroot%\\system32\\mstsc.exe");
          v64 = std::operator+<unsigned short>(v209, L" \"", v52 + 112);
          v65 = std::operator+<unsigned short>(v208, v64, L"\"");
          std::wstring::append(v189, v65, 0, -1);
          std::wstring::~wstring(v208);
          std::wstring::~wstring(v209);
          v66 = v125;
          v122 = v52 + 144;
          CombinedResourceTypeMap = CWorkspaceTaskbarPin::Initialize(
                                      v125,
                                      (int)v52 + 344,
                                      (int)v52 + 144,
                                      (unsigned int)v185,
                                      (__int64)v189,
                                      *(_QWORD *)(v52 + 392) != 0);
          LODWORD(v116) = CombinedResourceTypeMap;
          if ( CombinedResourceTypeMap < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v67 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(v115) = CombinedResourceTypeMap;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                142,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v67,
                (__int64)"CWorkspaceTaskbarPin::Initialize failed",
                v115);
            }
            std::wstring::~wstring(v189);
            if ( v66 )
              std::default_delete<CWorkspaceTaskbarPin>::operator()(v68, v66);
LABEL_125:
            std::wstring::~wstring(v186);
            goto LABEL_212;
          }
          std::vector<std::unique_ptr<CWorkspaceTaskbarPin>>::push_back((char *)v2 + 808, &v125);
          v61 = v52 + 280;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v69 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52 + 280);
            v70 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              143,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v70,
              v69);
          }
          std::wstring::~wstring(v189);
          if ( v125 )
            std::default_delete<CWorkspaceTaskbarPin>::operator()(v71, v125);
        }
        else
        {
          v61 = v52 + 280;
        }
        v72 = v122;
        v194 = *(_DWORD *)(v52 + 40);
        std::wstring::operator=(v196, v52 + 176);
        std::wstring::operator=(v197, v52 + 112);
        std::wstring::operator=(v198, v185);
        std::wstring::operator=(v199, v61);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::operator=(
          v200,
          v52 + 432);
        v195 = *(_DWORD *)(v52 + 44);
        v73 = std::map<std::wstring,ResourceMapNode>::operator[]((char *)v2 + 872, v72);
        ResourceMapNode::operator=(v73, &v194);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v74 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            144,
            WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
            v74,
            v195);
        }
        std::wstring::operator=(v188, v183);
        v75 = std::operator+<unsigned short>(v201, L"\\", v72);
        std::wstring::append(v188, v75, 0, -1);
        std::wstring::~wstring(v201);
        v76 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v188);
        v77 = StringCchPrintfW(pszPath, 0x104u, L"%s.lnk", v76);
        CombinedResourceTypeMap = v77;
        LODWORD(v116) = v77;
        if ( v77 < 0 )
        {
          if ( v77 != -2147024774 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v78 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                145,
                WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v78,
                CombinedResourceTypeMap);
            }
            LODWORD(v116) = CombinedResourceTypeMap;
            std::wstring::~wstring(v186);
            goto LABEL_212;
          }
          v79 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v188);
          CombinedResourceTypeMap = StringCchPrintfW(pszPath, 0x104u, L"%.252s....lnk", v79);
          LODWORD(v116) = CombinedResourceTypeMap;
          if ( CombinedResourceTypeMap < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v80 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(v115) = CombinedResourceTypeMap;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                146,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v80,
                (__int64)"StringCchPrintfW failed",
                v115);
            }
            goto LABEL_125;
          }
        }
        v81 = 0;
        v124 = 0;
        while ( 1 )
        {
          if ( v81 >= 0xA )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v106 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v118);
              v107 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v106 + 144);
              v108 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                148,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v108,
                v107);
            }
            goto LABEL_191;
          }
          if ( !PathFileExistsW(pszPath) )
            break;
          v124 = ++v81;
          v82 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v188);
          LODWORD(v113) = v81;
          CombinedResourceTypeMap = StringCchPrintfW(pszPath, 0x104u, L"%.249s...[%.1d].lnk", v82, v113);
          LODWORD(v116) = CombinedResourceTypeMap;
          if ( CombinedResourceTypeMap < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v83 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(v115) = CombinedResourceTypeMap;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                147,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v83,
                (__int64)"StringCchPrintfW failed",
                v115);
            }
            goto LABEL_125;
          }
        }
        v84 = std::wstring::wstring(v202, pszPath);
        Shortcut = CWorkspace::CreateShortcut(
                     (__int64)v2,
                     v84,
                     (__int64)v192,
                     (__int64)v185,
                     (__int64)v191,
                     (__int64)v187);
        LODWORD(v116) = Shortcut;
        std::wstring::~wstring(v202);
        if ( Shortcut < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v86 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              149,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v86,
              Shortcut);
          }
LABEL_191:
          v3 = v117;
          goto LABEL_192;
        }
        if ( !v120 )
        {
          v87 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v118);
          if ( *(_DWORD *)(v87 + 40) )
          {
            v152 = v177;
            v88 = (void *)std::wstring::wstring(v177, v87 + 112);
            CWorkspace::SetupSSOInformation(v2, v88);
            v120 = 1;
            v132 = 1;
          }
        }
        v89 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v118);
        if ( *(_DWORD *)(v89 + 40) )
        {
          for ( i = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
                                 v89 + 416,
                                 v153,
                                 v90);
                ;
                std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(
                  &i,
                  v157) )
          {
            v91 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v118);
            v119 = (CWorkspaceAppID *)(v91 + 416);
            v92 = std::vector<unsigned int>::begin(v91 + 416, v154);
            if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                                     &i,
                                     v92) )
              break;
            v93 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&i);
            v94 = v93;
            if ( *(_QWORD *)(v93 + 88) )
            {
              v130[0] = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,TS_WORKSPACE_DOWNLOAD_INFO,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>,0>>::find(
                                     v123,
                                     v155,
                                     v93 + 72);
              v95 = std::vector<unsigned int>::begin(v123, v156);
              if ( (unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                                      v130,
                                      v95)
                && (v96 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(v130),
                    *(int *)(v96 + 208) >= 0) )
              {
                std::wstring::operator=(v94 + 104, v96 + 112);
              }
              else
              {
                v97 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94 + 104);
                *(_QWORD *)(v94 + 120) = 0;
                *v97 = 0;
              }
            }
          }
          v158 = v178;
          v98 = std::wstring::wstring(v178, v192);
          v159 = v179;
          v99 = std::wstring::wstring(v179, v185);
          v160 = v180;
          v100 = std::wstring::wstring(v180, v91 + 144);
          v161 = v181;
          v101 = std::wstring::wstring(v181, v91 + 280);
          v162 = v182;
          v102 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v190);
          v103 = std::wstring::wstring(v182, v102);
          v114 = v99;
          v2 = v127;
          v104 = CWorkspace::RegisterAppFileAssociations(v127, v103, v101, v100, v114, v119, v98, v134, v116);
          LODWORD(v116) = v104;
          if ( v104 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v105 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              150,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v105,
              v104);
          }
          if ( v117 || v104 != 1 )
          {
            v3 = 1;
            v117 = 1;
          }
          else
          {
            v3 = 0;
            v117 = 0;
          }
          v133 = v3;
        }
        else
        {
          v3 = v117;
        }
        if ( *(_DWORD *)(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v118)
                       + 32) == 1 )
          ++*((_DWORD *)v2 + 150);
        else
          ++*((_DWORD *)v2 + 151);
        goto LABEL_192;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34 + 144);
        v36 = RdpWppGetCurrentThreadActivityIdPrefix();
        v37 = 138;
        goto LABEL_81;
      }
    }
    else if ( (PVOID *)v33 != &WPP_GLOBAL_Control && (*(_BYTE *)(v33 + 28) & 1) != 0 && *(_BYTE *)(v33 + 25) >= 2u )
    {
      v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32 + 144);
      v36 = RdpWppGetCurrentThreadActivityIdPrefix();
      v37 = 137;
LABEL_81:
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v37,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v36,
        v35);
    }
LABEL_192:
    std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(
      &v118,
      v163);
    v29 = v123;
  }
  CWorkspace::LogFileAssociationCollisions(v31, v134);
  if ( !*((_DWORD *)v2 + 147) || *((_DWORD *)v2 + 150) + *((_DWORD *)v2 + 151) )
  {
    if ( v3 )
      SHChangeNotify(0x8000000, 0, 0, 0);
    CombinedResourceTypeMap = CWorkspace::ApplyTaskbarPinRules(v2);
    LODWORD(v116) = CombinedResourceTypeMap;
    if ( CombinedResourceTypeMap < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v110 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v115) = CombinedResourceTypeMap;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          152,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v110,
          (__int64)"CWorkspace::ApplyTaskbarPinRules failed",
          v115);
      }
      goto LABEL_125;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v111 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v111);
    }
    CombinedResourceTypeMap = 0;
    LODWORD(v116) = 0;
    std::wstring::~wstring(v186);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v109 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v109);
    }
    CombinedResourceTypeMap = -2147467259;
    LODWORD(v116) = -2147467259;
    std::wstring::~wstring(v186);
LABEL_213:
    CWorkspace::DeleteStartMenuItems(v2);
  }
LABEL_214:
  std::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::~map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(v134);
  ResourceMapNode::~ResourceMapNode((ResourceMapNode *)&v194);
  std::map<std::wstring,ResourceTypeInfo>::~map<std::wstring,ResourceTypeInfo>(v131);
  std::wstring::~wstring(v190);
  std::wstring::~wstring(v188);
  std::wstring::~wstring(v187);
  std::wstring::~wstring(v191);
  std::wstring::~wstring(v185);
  std::wstring::~wstring(v192);
  std::wstring::~wstring(v183);
  std::wstring::~wstring(v193);
  return (unsigned int)CombinedResourceTypeMap;
}

```

## disassembly

```asm
0x18002b1a8  mov     r11, rsp
0x18002b1ab  push    rdi
0x18002b1ac  push    r12
0x18002b1ae  push    r13
0x18002b1b0  push    r14
0x18002b1b2  push    r15
0x18002b1b4  sub     rsp, 0A10h
0x18002b1bb  mov     qword ptr [r11-868h], 0FFFFFFFFFFFFFFFEh
0x18002b1c6  mov     [r11+18h], rbx
0x18002b1ca  mov     [r11+20h], rsi
0x18002b1ce  mov     rax, cs:__security_cookie
0x18002b1d5  xor     rax, rsp
0x18002b1d8  mov     [rsp+0A38h+var_30], rax
0x18002b1e0  mov     [rsp+0A38h+var_9C0], rdx
0x18002b1e5  mov     rsi, rcx
0x18002b1e8  mov     [rsp+0A38h+var_9A0], rcx
0x18002b1f0  mov     [rsp+0A38h+var_980], rcx
0x18002b1f8  xor     r15d, r15d
0x18002b1fb  mov     r14d, r15d
0x18002b1fe  mov     [rsp+0A38h+var_9F0], r15d
0x18002b203  mov     [rsp+0A38h+var_9D8], r15d
0x18002b208  lea     rcx, [r11-518h]
0x18002b20f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b214  nop
0x18002b215  lea     rcx, [rsp+0A38h+var_638]
0x18002b21d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b222  nop
0x18002b223  lea     rcx, [rsp+0A38h+var_538]
0x18002b22b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b230  nop
0x18002b231  lea     rcx, [rsp+0A38h+var_618]
0x18002b239  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b23e  nop
0x18002b23f  lea     rcx, [rsp+0A38h+var_558]
0x18002b247  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b24c  nop
0x18002b24d  lea     rcx, [rsp+0A38h+var_5D8]
0x18002b255  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b25a  nop
0x18002b25b  lea     rcx, [rsp+0A38h+var_5B8]
0x18002b263  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b268  nop
0x18002b269  lea     rcx, [rsp+0A38h+var_578]
0x18002b271  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b276  nop
0x18002b277  lea     rcx, [rsp+0A38h+var_978]
0x18002b27f  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,ResourceTypeInfo>::map<std::wstring,ResourceTypeInfo>(void)
0x18002b284  nop
0x18002b285  lea     rcx, [rsp+0A38h+var_4F8]; this
0x18002b28d  call    ??0ResourceMapNode@@QEAA@XZ; ResourceMapNode::ResourceMapNode(void)
0x18002b292  nop
0x18002b293  lea     rcx, [rsp+0A38h+var_960]
0x18002b29b  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UKeyCompareLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(void)
0x18002b2a0  nop
0x18002b2a1  mov     [rsi+258h], r15d
0x18002b2a8  mov     [rsi+25Ch], r15d
0x18002b2af  lea     rcx, [rsp+0A38h+var_978]
0x18002b2b7  call    ?GetCombinedResourceTypeMap@CResourceTypeManager@@SAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@@std@@@Z; CResourceTypeManager::GetCombinedResourceTypeMap(std::map<std::wstring,ResourceTypeInfo> &)
0x18002b2bc  mov     edi, eax
0x18002b2be  mov     [rsp+0A38h+var_9F8], eax
0x18002b2c2  test    eax, eax
0x18002b2c4  jns     short loc_18002B31E
0x18002b2c6  lea     r12, WPP_GLOBAL_Control
0x18002b2cd  mov     rax, cs:WPP_GLOBAL_Control
0x18002b2d4  cmp     rax, r12
0x18002b2d7  jz      short loc_18002B319
0x18002b2d9  test    byte ptr [rax+1Ch], 8
0x18002b2dd  jz      short loc_18002B319
0x18002b2df  cmp     byte ptr [rax+19h], 2
0x18002b2e3  jb      short loc_18002B319
0x18002b2e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b2ea  lea     edx, [r15+7Dh]
0x18002b2ee  mov     dword ptr [rsp+0A38h+var_A10], edi
0x18002b2f2  lea     rcx, aGetcombinedres; "GetCombinedResourceTypeMap failed"
0x18002b2f9  mov     [rsp+0A38h+var_A18], rcx
0x18002b2fe  mov     r9d, eax
0x18002b301  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b308  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b30f  mov     rcx, [rcx+10h]
0x18002b313  call    WPP_SF_DsD
0x18002b318  nop
0x18002b319  jmp     loc_18002C9DA
0x18002b31e  mov     ebx, 104h
0x18002b323  mov     r8d, ebx; unsigned int
0x18002b326  lea     rdx, [rsp+0A38h+pszPath]; unsigned __int16 *
0x18002b32e  mov     rcx, rsi; this
0x18002b331  call    ?GetUniquePublisherName@CWorkspace@@QEAAJPEAGK@Z; CWorkspace::GetUniquePublisherName(ushort *,ulong)
0x18002b336  mov     edi, eax
0x18002b338  mov     [rsp+0A38h+var_9F8], eax
0x18002b33c  test    eax, eax
0x18002b33e  jns     short loc_18002B399
0x18002b340  lea     r12, WPP_GLOBAL_Control
0x18002b347  mov     rax, cs:WPP_GLOBAL_Control
0x18002b34e  cmp     rax, r12
0x18002b351  jz      short loc_18002B394
0x18002b353  test    byte ptr [rax+1Ch], 8
0x18002b357  jz      short loc_18002B394
0x18002b359  cmp     byte ptr [rax+19h], 2
0x18002b35d  jb      short loc_18002B394
0x18002b35f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b364  mov     edx, 7Eh ; '~'
0x18002b369  mov     dword ptr [rsp+0A38h+var_A10], edi
0x18002b36d  lea     rcx, aGetuniquepubli; "GetUniquePublisherName failed"
0x18002b374  mov     [rsp+0A38h+var_A18], rcx
0x18002b379  mov     r9d, eax
0x18002b37c  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b383  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b38a  mov     rcx, [rcx+10h]
0x18002b38e  call    WPP_SF_DsD
0x18002b393  nop
0x18002b394  jmp     loc_18002C9DA
0x18002b399  lea     rdx, [rsp+0A38h+pszPath]
0x18002b3a1  lea     rcx, [rsp+0A38h+var_578]
0x18002b3a9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002b3ae  lea     rcx, [rsp+0A38h+var_518]
0x18002b3b6  call    ?GetStartMenuBaseFolder@CWorkspaceManager@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CWorkspaceManager::GetStartMenuBaseFolder(std::wstring &)
0x18002b3bb  mov     edi, eax
0x18002b3bd  mov     [rsp+0A38h+var_9F8], eax
0x18002b3c1  test    eax, eax
0x18002b3c3  jns     short loc_18002B41E
0x18002b3c5  lea     r12, WPP_GLOBAL_Control
0x18002b3cc  mov     rax, cs:WPP_GLOBAL_Control
0x18002b3d3  cmp     rax, r12
0x18002b3d6  jz      short loc_18002B419
0x18002b3d8  test    byte ptr [rax+1Ch], 8
0x18002b3dc  jz      short loc_18002B419
0x18002b3de  cmp     byte ptr [rax+19h], 2
0x18002b3e2  jb      short loc_18002B419
0x18002b3e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b3e9  mov     edx, 7Fh
0x18002b3ee  mov     dword ptr [rsp+0A38h+var_A10], edi
0x18002b3f2  lea     rcx, aGetstartmenuba; "GetStartMenuBaseFolder failed"
0x18002b3f9  mov     [rsp+0A38h+var_A18], rcx
0x18002b3fe  mov     r9d, eax
0x18002b401  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b408  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b40f  mov     rcx, [rcx+10h]
0x18002b413  call    WPP_SF_DsD
0x18002b418  nop
0x18002b419  jmp     loc_18002C9DA
0x18002b41e  lea     rcx, [rsp+0A38h+var_578]
0x18002b426  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b42b  mov     [rsp+0A38h+var_A18], rax
0x18002b430  mov     r9, rbx; unsigned __int64
0x18002b433  lea     r8, [rsp+0A38h+pszPath]; unsigned __int16 *
0x18002b43b  mov     edx, 3B73h; uID
0x18002b440  mov     rcx, cs:g_hinst; hInstance
0x18002b447  call    ?TSWFormatString@@YAJPEAUHINSTANCE__@@HPEAG_KZZ; TSWFormatString(HINSTANCE__ *,int,ushort *,unsigned __int64,...)
0x18002b44c  mov     edi, eax
0x18002b44e  mov     [rsp+0A38h+var_9F8], eax
0x18002b452  test    eax, eax
0x18002b454  jns     short loc_18002B4AF
0x18002b456  lea     r12, WPP_GLOBAL_Control
0x18002b45d  mov     rax, cs:WPP_GLOBAL_Control
0x18002b464  cmp     rax, r12
0x18002b467  jz      short loc_18002B4AA
0x18002b469  test    byte ptr [rax+1Ch], 8
0x18002b46d  jz      short loc_18002B4AA
0x18002b46f  cmp     byte ptr [rax+19h], 2
0x18002b473  jb      short loc_18002B4AA
0x18002b475  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b47a  mov     edx, 80h
0x18002b47f  mov     dword ptr [rsp+0A38h+var_A10], edi
0x18002b483  lea     rcx, aTswformatstrin; "TSWFormatString failed"
0x18002b48a  mov     [rsp+0A38h+var_A18], rcx
0x18002b48f  mov     r9d, eax
0x18002b492  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b499  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4a0  mov     rcx, [rcx+10h]
0x18002b4a4  call    WPP_SF_DsD
0x18002b4a9  nop
0x18002b4aa  jmp     loc_18002C9DA
0x18002b4af  lea     r8, SubStr; "\\"
0x18002b4b6  lea     rdx, [rsp+0A38h+var_518]
0x18002b4be  lea     rcx, [rsp+0A38h+var_418]
0x18002b4c6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002b4cb  nop
0x18002b4cc  lea     r8, [rsp+0A38h+pszPath]
0x18002b4d4  mov     rdx, rax
0x18002b4d7  lea     rcx, [rsp+0A38h+var_3B8]
0x18002b4df  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002b4e4  nop
0x18002b4e5  mov     rdx, rax
0x18002b4e8  lea     rcx, [rsp+0A38h+var_638]
0x18002b4f0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b4f5  nop
0x18002b4f6  lea     rcx, [rsp+0A38h+var_3B8]; void *
0x18002b4fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b503  nop
0x18002b504  lea     rcx, [rsp+0A38h+var_418]; void *
0x18002b50c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b511  mov     rax, rbx
0x18002b514  sub     rax, [rsp+0A38h+var_628]
0x18002b51c  cmp     rax, 0Ah
0x18002b520  ja      short loc_18002B57B
0x18002b522  lea     r12, WPP_GLOBAL_Control
0x18002b529  mov     rax, cs:WPP_GLOBAL_Control
0x18002b530  cmp     rax, r12
0x18002b533  jz      short loc_18002B56D
0x18002b535  test    byte ptr [rax+1Ch], 8
0x18002b539  jz      short loc_18002B56D
0x18002b53b  cmp     byte ptr [rax+19h], 2
0x18002b53f  jb      short loc_18002B56D
0x18002b541  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b546  mov     edx, 81h
0x18002b54b  mov     dword ptr [rsp+0A38h+var_A18], 80040203h
0x18002b553  mov     r9d, eax
0x18002b556  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b55d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b564  mov     rcx, [rcx+10h]
0x18002b568  call    WPP_SF_Dd
0x18002b56d  mov     edi, 80040203h
0x18002b572  mov     [rsp+0A38h+var_9F8], edi
0x18002b576  jmp     loc_18002C9DE
0x18002b57b  lea     rcx, [rsp+0A38h+var_638]
0x18002b583  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b588  mov     rcx, rax; unsigned __int16 *
0x18002b58b  call    ?IsPathCanonical@@YAHPEBG@Z; IsPathCanonical(ushort const *)
0x18002b590  test    eax, eax
0x18002b592  jnz     short loc_18002B5ED
0x18002b594  lea     r12, WPP_GLOBAL_Control
0x18002b59b  mov     rax, cs:WPP_GLOBAL_Control
0x18002b5a2  cmp     rax, r12
0x18002b5a5  jz      short loc_18002B5DF
0x18002b5a7  test    byte ptr [rax+1Ch], 8
0x18002b5ab  jz      short loc_18002B5DF
0x18002b5ad  cmp     byte ptr [rax+19h], 2
0x18002b5b1  jb      short loc_18002B5DF
0x18002b5b3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b5b8  mov     edx, 82h
0x18002b5bd  mov     dword ptr [rsp+0A38h+var_A18], 80040203h
0x18002b5c5  mov     r9d, eax
0x18002b5c8  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b5cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5d6  mov     rcx, [rcx+10h]
0x18002b5da  call    WPP_SF_Dd
0x18002b5df  mov     edi, 80040203h
0x18002b5e4  mov     [rsp+0A38h+var_9F8], edi
0x18002b5e8  jmp     loc_18002C9DE
0x18002b5ed  lea     r12, WPP_GLOBAL_Control
0x18002b5f4  mov     rax, cs:WPP_GLOBAL_Control
0x18002b5fb  cmp     rax, r12
0x18002b5fe  jz      short loc_18002B64A
0x18002b600  test    byte ptr [rax+1Ch], 1
0x18002b604  jz      short loc_18002B64A
0x18002b606  cmp     byte ptr [rax+19h], 4
0x18002b60a  jb      short loc_18002B64A
0x18002b60c  lea     rcx, [rsp+0A38h+var_638]
0x18002b614  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b619  mov     rbx, rax
0x18002b61c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b621  mov     edx, 83h
0x18002b626  mov     [rsp+0A38h+var_A18], rbx
0x18002b62b  mov     r9d, eax
0x18002b62e  lea     r13, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b635  mov     r8, r13
0x18002b638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b63f  mov     rcx, [rcx+10h]
0x18002b643  call    WPP_SF_DS
0x18002b648  jmp     short loc_18002B651
0x18002b64a  lea     r13, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002b651  lea     rcx, [rsp+0A38h+var_638]
0x18002b659  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b65e  mov     rdx, rax; pszPath
0x18002b661  xor     r8d, r8d; psa
0x18002b664  xor     ecx, ecx; hwnd
0x18002b666  call    cs:__imp_SHCreateDirectoryExW
0x18002b66c  mov     edi, eax
0x18002b66e  cmp     eax, 0B7h
0x18002b673  jnz     short loc_18002B6EA
0x18002b675  mov     rax, cs:WPP_GLOBAL_Control
0x18002b67c  cmp     rax, r12
0x18002b67f  jz      short loc_18002B6C0
0x18002b681  test    byte ptr [rax+1Ch], 1
0x18002b685  jz      short loc_18002B6C0
0x18002b687  cmp     byte ptr [rax+19h], 4
0x18002b68b  jb      short loc_18002B6C0
0x18002b68d  lea     rcx, [rsp+0A38h+var_638]
0x18002b695  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b69a  mov     rbx, rax
0x18002b69d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b6a2  lea     edx, [rdi-33h]
0x18002b6a5  mov     [rsp+0A38h+var_A18], rbx
0x18002b6aa  mov     r9d, eax
0x18002b6ad  mov     r8, r13
0x18002b6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6b7  mov     rcx, [rcx+10h]
0x18002b6bb  call    WPP_SF_DS
0x18002b6c0  lea     rcx, [rsp+0A38h+var_638]
0x18002b6c8  call    ?WipeoutFolder@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WipeoutFolder(std::wstring &)
0x18002b6cd  lea     rcx, [rsp+0A38h+var_638]
0x18002b6d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b6da  mov     rdx, rax; pszPath
0x18002b6dd  xor     r8d, r8d; psa
0x18002b6e0  xor     ecx, ecx; hwnd
0x18002b6e2  call    cs:__imp_SHCreateDirectoryExW
0x18002b6e8  mov     edi, eax
0x18002b6ea  test    edi, edi
0x18002b6ec  jz      short loc_18002B751
0x18002b6ee  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
