# CWorkspace::CreateStartMenuItemsForSSPApps(void)

- ea: `0x18002cab8`
- end: `0x18002d6e6`
- name: `?CreateStartMenuItemsForSSPApps@CWorkspace@@QEAAJXZ`
- size: `3118`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `3`
- callee_count: `43`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004a840`
- `0x18007525c`
- `0x180075d30`

## callees

- `0x180002214`
- `0x180004970`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001b7e4`
- `0x18001e5d8`
- `0x18001e610`
- `0x18001e92c`
- `0x18001e974`
- `0x18001eac4`
- `0x18001ead4`
- `0x1800208a8`
- `0x180020a68`
- `0x180020bf0`
- `0x1800259d8`
- `0x1800276f4`
- `0x180027720`
- `0x180027dc0`
- `0x18002830c`
- `0x180028354`
- `0x180028860`
- `0x180028ca0`
- `0x180028d04`
- `0x18002a9a4`
- `0x18002cab8`
- `0x18002f29c`
- `0x18003234c`
- `0x1800382c4`
- `0x18003add8`
- `0x18003c824`
- `0x18003ce1c`
- `0x1800465e4`
- `0x18005701c`
- `0x1800570dc`
- `0x1800571c8`
- `0x180057700`
- `0x18007bb28`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18002d3c7`
- `SHLWAPI!PathFileExistsW` at `0x18002d3c7`
- `SHELL32!SHCreateDirectoryExW` at `0x18002cc91`
- `SHELL32!SHCreateDirectoryExW` at `0x18002cc91`

## string_xrefs

- `0x18002cbe7`: `GetCombinedResourceTypeMap failed`
- `0x18002cda8`: `%systemroot%\system32\mstsc.exe`
- `0x18002cdba`: `%systemroot%\system32\mstsc.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=29 #try_helpers=1
__int64 __fastcall CWorkspace::CreateStartMenuItemsForSSPApps(CWorkspace *this)
{
  CWorkspace *v1; // rsi
  int CombinedResourceTypeMap; // ebx
  unsigned int v3; // eax
  __int64 v4; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const WCHAR *v6; // rax
  unsigned int v7; // edi
  unsigned int v8; // eax
  char *v9; // r8
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdi
  const unsigned __int16 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rbx
  unsigned int v21; // eax
  CWorkspaceAppID *v22; // rax
  __int64 v23; // r14
  __int64 v24; // rsi
  CWorkspaceAppID *v25; // rbx
  __int64 FinalAppID; // rax
  __int64 v27; // rbx
  unsigned int v28; // eax
  __int64 v29; // r14
  __int64 v30; // rsi
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rax
  int v36; // eax
  unsigned int v37; // eax
  __int64 v38; // rax
  unsigned int v39; // eax
  unsigned int v40; // edi
  __int64 v41; // rax
  unsigned int v42; // eax
  __int64 v43; // rax
  int Shortcut; // ebx
  unsigned int v45; // eax
  __int64 v46; // rax
  void *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rbx
  unsigned int v50; // eax
  __int64 v52; // [rsp+20h] [rbp-718h]
  __int64 v53; // [rsp+28h] [rbp-710h]
  _BYTE v54[4]; // [rsp+30h] [rbp-708h] BYREF
  int v55; // [rsp+34h] [rbp-704h]
  int v56; // [rsp+38h] [rbp-700h]
  int v57; // [rsp+3Ch] [rbp-6FCh]
  __int64 v58; // [rsp+40h] [rbp-6F8h] BYREF
  unsigned int v59; // [rsp+48h] [rbp-6F0h]
  __int64 v60; // [rsp+50h] [rbp-6E8h] BYREF
  __int64 v61; // [rsp+58h] [rbp-6E0h]
  __int64 v62; // [rsp+60h] [rbp-6D8h] BYREF
  CWorkspaceAppID *v63; // [rsp+68h] [rbp-6D0h]
  CWorkspace *v64; // [rsp+70h] [rbp-6C8h]
  CWorkspace *v65; // [rsp+78h] [rbp-6C0h]
  _BYTE v66[16]; // [rsp+80h] [rbp-6B8h] BYREF
  int v67; // [rsp+90h] [rbp-6A8h]
  int v68; // [rsp+94h] [rbp-6A4h]
  _BYTE v69[32]; // [rsp+98h] [rbp-6A0h] BYREF
  _BYTE v70[32]; // [rsp+B8h] [rbp-680h] BYREF
  _BYTE v71[8]; // [rsp+D8h] [rbp-660h] BYREF
  _BYTE *v72; // [rsp+E0h] [rbp-658h]
  CWorkspaceAppID *v73; // [rsp+E8h] [rbp-650h]
  _BYTE *v74; // [rsp+F0h] [rbp-648h]
  _BYTE *v75; // [rsp+F8h] [rbp-640h]
  _BYTE *v76; // [rsp+100h] [rbp-638h]
  _BYTE *v77; // [rsp+108h] [rbp-630h]
  _BYTE *v78; // [rsp+110h] [rbp-628h]
  _BYTE *v79; // [rsp+118h] [rbp-620h]
  _BYTE *v80; // [rsp+120h] [rbp-618h]
  _BYTE *v81; // [rsp+128h] [rbp-610h]
  _BYTE *v82; // [rsp+130h] [rbp-608h]
  _BYTE *v83; // [rsp+138h] [rbp-600h]
  _BYTE *v84; // [rsp+140h] [rbp-5F8h]
  _BYTE v85[8]; // [rsp+148h] [rbp-5F0h] BYREF
  __int64 v86; // [rsp+150h] [rbp-5E8h]
  _BYTE v87[16]; // [rsp+158h] [rbp-5E0h] BYREF
  _BYTE v88[8]; // [rsp+168h] [rbp-5D0h] BYREF
  _BYTE v89[32]; // [rsp+170h] [rbp-5C8h] BYREF
  _BYTE v90[32]; // [rsp+190h] [rbp-5A8h] BYREF
  _BYTE v91[32]; // [rsp+1B0h] [rbp-588h] BYREF
  _BYTE v92[8]; // [rsp+1D0h] [rbp-568h] BYREF
  _BYTE v93[32]; // [rsp+1D8h] [rbp-560h] BYREF
  _BYTE v94[32]; // [rsp+1F8h] [rbp-540h] BYREF
  _BYTE v95[32]; // [rsp+218h] [rbp-520h] BYREF
  _BYTE v96[32]; // [rsp+238h] [rbp-500h] BYREF
  _BYTE v97[32]; // [rsp+258h] [rbp-4E0h] BYREF
  _BYTE v98[32]; // [rsp+278h] [rbp-4C0h] BYREF
  _BYTE v99[32]; // [rsp+298h] [rbp-4A0h] BYREF
  _BYTE v100[32]; // [rsp+2B8h] [rbp-480h] BYREF
  _BYTE v101[32]; // [rsp+2D8h] [rbp-460h] BYREF
  _BYTE v102[32]; // [rsp+2F8h] [rbp-440h] BYREF
  _BYTE v103[32]; // [rsp+318h] [rbp-420h] BYREF
  _BYTE v104[40]; // [rsp+338h] [rbp-400h] BYREF
  _BYTE v105[240]; // [rsp+360h] [rbp-3D8h] BYREF
  _BYTE v106[160]; // [rsp+450h] [rbp-2E8h] BYREF
  WCHAR pszPath[268]; // [rsp+4F0h] [rbp-248h] BYREF

  v86 = -2;
  v1 = this;
  v64 = this;
  v65 = this;
  v56 = 0;
  v57 = 0;
  std::wstring::wstring(v104);
  std::wstring::wstring(v103);
  std::wstring::wstring(v97);
  std::wstring::wstring(v95);
  std::wstring::wstring(v96);
  std::wstring::wstring(v93);
  std::wstring::wstring(v94);
  std::wstring::wstring(v102);
  std::map<std::wstring,ResourceTypeInfo>::map<std::wstring,ResourceTypeInfo>(v66);
  ResourceMapNode::ResourceMapNode((ResourceMapNode *)v106);
  std::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(v87);
  CombinedResourceTypeMap = CResourceTypeManager::GetCombinedResourceTypeMap(v66);
  v55 = CombinedResourceTypeMap;
  if ( CombinedResourceTypeMap >= 0 )
  {
    WipeoutFolder((char *)v1 + 456);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v1 + 456);
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        168,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        v4);
    }
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v1 + 456);
    CombinedResourceTypeMap = SHCreateDirectoryExW(0, v6, 0);
    if ( CombinedResourceTypeMap )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( CombinedResourceTypeMap > 0 )
          v7 = (unsigned __int16)CombinedResourceTypeMap | 0x80070000;
        else
          v7 = CombinedResourceTypeMap;
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v8, v7);
      }
      if ( CombinedResourceTypeMap > 0 )
        CombinedResourceTypeMap = (unsigned __int16)CombinedResourceTypeMap | 0x80070000;
      v55 = CombinedResourceTypeMap;
      goto LABEL_89;
    }
    v58 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
                       (char *)v1 + 872,
                       &v60,
                       (char *)v1 + 872);
    while ( 1 )
    {
      v10 = std::vector<unsigned int>::begin(v9, v88);
      if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                               &v58,
                               v10) )
      {
        CombinedResourceTypeMap = 0;
        v55 = 0;
        goto LABEL_91;
      }
      v11 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v58);
      v61 = v11;
      v12 = v11 + 144;
      v60 = v11 + 144;
      v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11 + 144);
      if ( CWorkspace::IsSSPAppInstalled(v1, v13) )
      {
        std::wstring::operator=(v97, v11 + 80);
        if ( *(_QWORD *)(v11 + 128) )
          std::wstring::operator=(v95, v11 + 112);
        else
          std::wstring::assign(v95, L"%systemroot%\\system32\\mstsc.exe");
        if ( *(_DWORD *)(v11 + 32) )
        {
          std::wstring::assign(v96, L"%systemroot%\\system32\\mstsc.exe");
        }
        else
        {
          v62 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::find(
                             v66,
                             v92,
                             v11 + 48);
          v14 = std::vector<unsigned int>::begin(v66, v71);
          if ( (unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ResourceTypeInfo>>>>::operator==(
                                  v14,
                                  &v62) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
              v16 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                170,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v16,
                v15);
            }
            goto LABEL_87;
          }
          v17 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v62);
          std::wstring::operator=(v96, v17 + 64);
        }
        v54[0] = 0;
        if ( *(_DWORD *)(v11 + 32)
          && (v72 = v69, v18 = std::wstring::wstring(v69, v11 + 80), CWorkspace::GetAppID(v19, v18, v54, v93), v54[0]) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
            v21 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              171,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v21,
              v20);
            v11 = v61;
          }
          v22 = (CWorkspaceAppID *)operator new(0xE8u);
          v73 = v22;
          if ( v22 )
            v63 = CWorkspaceAppID::CWorkspaceAppID(v22);
          else
            v63 = 0;
          v74 = v69;
          v23 = std::wstring::wstring(v69, (char *)v1 + 64);
          v75 = v89;
          v24 = std::wstring::wstring(v89, v11 + 80);
          v76 = v90;
          std::wstring::wstring(v90, v95);
          v77 = v91;
          std::wstring::wstring(v91, v11);
          v78 = v70;
          std::wstring::wstring(v70, v93);
          v25 = v63;
          CWorkspaceAppID::Initialize(v63, v24, v23);
          v1 = v64;
          (*(void (__fastcall **)(char *, CWorkspaceAppID *))(*((_QWORD *)v64 + 97) + 8LL))((char *)v64 + 776, v25);
          FinalAppID = CWorkspaceAppID::GetFinalAppID(v25, v98);
          std::wstring::operator=(v93, FinalAppID);
          std::wstring::~wstring(v98);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
            v28 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              172,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v28,
              v27);
            v11 = v61;
          }
          CWorkspaceAppID::CWorkspaceAppID((CWorkspaceAppID *)v105);
          v79 = v70;
          v29 = std::wstring::wstring(v70, (char *)v1 + 64);
          v80 = v91;
          v30 = std::wstring::wstring(v91, v11 + 80);
          v81 = v90;
          std::wstring::wstring(v90, v95);
          v82 = v89;
          std::wstring::wstring(v89, v11);
          v83 = v69;
          std::wstring::wstring(v69, v60);
          CWorkspaceAppID::Initialize((CWorkspaceAppID *)v105, v30, v29);
          v31 = CWorkspaceAppID::GetFinalAppID(v105, v99);
          std::wstring::operator=(v93, v31);
          std::wstring::~wstring(v99);
          CWorkspaceAppID::~CWorkspaceAppID((CWorkspaceAppID *)v105);
          v1 = v64;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v93);
          v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, v32);
        }
        std::wstring::operator=(v94, (char *)v1 + 456);
        v34 = std::operator+<unsigned short>(v100, L"\\", v61);
        std::wstring::append(v94, v34, 0, -1);
        std::wstring::~wstring(v100);
        v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        v36 = StringCchPrintfW(pszPath, 0x104u, L"%s.lnk", v35);
        CombinedResourceTypeMap = v36;
        v55 = v36;
        if ( v36 < 0 )
        {
          if ( v36 != -2147024774 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v37 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                174,
                WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v37,
                CombinedResourceTypeMap);
            }
            v55 = CombinedResourceTypeMap;
            goto LABEL_89;
          }
          v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
          CombinedResourceTypeMap = StringCchPrintfW(pszPath, 0x104u, L"%.252s....lnk", v38);
          v55 = CombinedResourceTypeMap;
          if ( CombinedResourceTypeMap < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v39 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(v53) = CombinedResourceTypeMap;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                175,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v39,
                (__int64)"StringCchPrintfW failed",
                v53);
            }
            goto LABEL_89;
          }
        }
        v40 = 0;
        v59 = 0;
        while ( v40 < 0xA )
        {
          if ( !PathFileExistsW(pszPath) )
          {
            v43 = std::wstring::wstring(v101, pszPath);
            Shortcut = CWorkspace::CreateShortcut(
                         (__int64)v1,
                         v43,
                         (__int64)v97,
                         (__int64)v95,
                         (__int64)v96,
                         (__int64)v93);
            v55 = Shortcut;
            std::wstring::~wstring(v101);
            if ( Shortcut >= 0 )
            {
              if ( !v56 )
              {
                v46 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v58);
                if ( *(_DWORD *)(v46 + 32) )
                {
                  v84 = v70;
                  v47 = (void *)std::wstring::wstring(v70, v46 + 80);
                  CWorkspace::SetupSSOInformation(v1, v47);
                  v56 = 1;
                  v67 = 1;
                }
              }
              v68 = ++v57;
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v45 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                178,
                WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v45,
                Shortcut);
            }
            goto LABEL_87;
          }
          v59 = ++v40;
          v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
          LODWORD(v52) = v40;
          CombinedResourceTypeMap = StringCchPrintfW(pszPath, 0x104u, L"%.249s...[%.1d].lnk", v41, v52);
          v55 = CombinedResourceTypeMap;
          if ( CombinedResourceTypeMap < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v42 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(v53) = CombinedResourceTypeMap;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                176,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v42,
                (__int64)"StringCchPrintfW failed",
                v53);
            }
            goto LABEL_89;
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v48 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v58);
          v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
          v50 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            177,
            (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
            v50,
            v49);
        }
      }
LABEL_87:
      std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(
        &v58,
        v85);
      v9 = (char *)v1 + 872;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      167,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      v3,
      (__int64)"GetCombinedResourceTypeMap failed",
      CombinedResourceTypeMap);
  }
LABEL_89:
  if ( CombinedResourceTypeMap < 0 )
    WipeoutFolder((char *)v1 + 456);
LABEL_91:
  std::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::~map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(v87);
  ResourceMapNode::~ResourceMapNode((ResourceMapNode *)v106);
  std::map<std::wstring,ResourceTypeInfo>::~map<std::wstring,ResourceTypeInfo>(v66);
  std::wstring::~wstring(v102);
  std::wstring::~wstring(v94);
  std::wstring::~wstring(v93);
  std::wstring::~wstring(v96);
  std::wstring::~wstring(v95);
  std::wstring::~wstring(v97);
  std::wstring::~wstring(v103);
  std::wstring::~wstring(v104);
  return (unsigned int)CombinedResourceTypeMap;
}

```

## disassembly

```asm
0x18002cab8  mov     r11, rsp
0x18002cabb  push    rdi
0x18002cabc  push    r12
0x18002cabe  push    r13
0x18002cac0  push    r14
0x18002cac2  push    r15
0x18002cac4  sub     rsp, 710h
0x18002cacb  mov     qword ptr [r11-5E8h], 0FFFFFFFFFFFFFFFEh
0x18002cad6  mov     [r11+10h], rbx
0x18002cada  mov     [r11+18h], rsi
0x18002cade  mov     rax, cs:__security_cookie
0x18002cae5  xor     rax, rsp
0x18002cae8  mov     [rsp+738h+var_30], rax
0x18002caf0  mov     rsi, rcx
0x18002caf3  mov     [rsp+738h+var_6C8], rcx
0x18002caf8  mov     [rsp+738h+var_6C0], rcx
0x18002cafd  xor     r15d, r15d
0x18002cb00  mov     [rsp+738h+var_700], r15d
0x18002cb05  mov     [rsp+738h+var_6FC], r15d
0x18002cb0a  lea     rcx, [r11-400h]
0x18002cb11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb16  nop
0x18002cb17  lea     rcx, [rsp+738h+var_420]
0x18002cb1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb24  nop
0x18002cb25  lea     rcx, [rsp+738h+var_4E0]
0x18002cb2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb32  nop
0x18002cb33  lea     rcx, [rsp+738h+var_520]
0x18002cb3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb40  nop
0x18002cb41  lea     rcx, [rsp+738h+var_500]
0x18002cb49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb4e  nop
0x18002cb4f  lea     rcx, [rsp+738h+var_560]
0x18002cb57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb5c  nop
0x18002cb5d  lea     rcx, [rsp+738h+var_540]
0x18002cb65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb6a  nop
0x18002cb6b  lea     rcx, [rsp+738h+var_440]
0x18002cb73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb78  nop
0x18002cb79  lea     rcx, [rsp+738h+var_6B8]
0x18002cb81  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,ResourceTypeInfo>::map<std::wstring,ResourceTypeInfo>(void)
0x18002cb86  nop
0x18002cb87  lea     rcx, [rsp+738h+var_2E8]; this
0x18002cb8f  call    ??0ResourceMapNode@@QEAA@XZ; ResourceMapNode::ResourceMapNode(void)
0x18002cb94  nop
0x18002cb95  lea     rcx, [rsp+738h+var_5E0]
0x18002cb9d  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UKeyCompareLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,KeyCompareLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(void)
0x18002cba2  nop
0x18002cba3  lea     rcx, [rsp+738h+var_6B8]
0x18002cbab  call    ?GetCombinedResourceTypeMap@CResourceTypeManager@@SAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@@std@@@Z; CResourceTypeManager::GetCombinedResourceTypeMap(std::map<std::wstring,ResourceTypeInfo> &)
0x18002cbb0  mov     ebx, eax
0x18002cbb2  mov     [rsp+738h+var_704], eax
0x18002cbb6  test    eax, eax
0x18002cbb8  jns     short loc_18002CC13
0x18002cbba  lea     r13, WPP_GLOBAL_Control
0x18002cbc1  mov     rax, cs:WPP_GLOBAL_Control
0x18002cbc8  cmp     rax, r13
0x18002cbcb  jz      short loc_18002CC0E
0x18002cbcd  test    byte ptr [rax+1Ch], 8
0x18002cbd1  jz      short loc_18002CC0E
0x18002cbd3  cmp     byte ptr [rax+19h], 2
0x18002cbd7  jb      short loc_18002CC0E
0x18002cbd9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002cbde  mov     edx, 0A7h
0x18002cbe3  mov     dword ptr [rsp+738h+var_710], ebx
0x18002cbe7  lea     rcx, aGetcombinedres; "GetCombinedResourceTypeMap failed"
0x18002cbee  mov     [rsp+738h+var_718], rcx
0x18002cbf3  mov     r9d, eax
0x18002cbf6  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002cbfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc04  mov     rcx, [rcx+10h]
0x18002cc08  call    WPP_SF_DsD
0x18002cc0d  nop
0x18002cc0e  jmp     loc_18002D60D
0x18002cc13  lea     rdi, [rsi+1C8h]
0x18002cc1a  mov     rcx, rdi
0x18002cc1d  call    ?WipeoutFolder@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WipeoutFolder(std::wstring &)
0x18002cc22  lea     r13, WPP_GLOBAL_Control
0x18002cc29  mov     rax, cs:WPP_GLOBAL_Control
0x18002cc30  cmp     rax, r13
0x18002cc33  jz      short loc_18002CC7A
0x18002cc35  test    byte ptr [rax+1Ch], 1
0x18002cc39  jz      short loc_18002CC7A
0x18002cc3b  cmp     byte ptr [rax+19h], 4
0x18002cc3f  jb      short loc_18002CC7A
0x18002cc41  mov     rcx, rdi
0x18002cc44  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cc49  mov     rbx, rax
0x18002cc4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002cc51  mov     edx, 0A8h
0x18002cc56  mov     [rsp+738h+var_718], rbx
0x18002cc5b  mov     r9d, eax
0x18002cc5e  lea     r12, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002cc65  mov     r8, r12
0x18002cc68  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc6f  mov     rcx, [rcx+10h]
0x18002cc73  call    WPP_SF_DS
0x18002cc78  jmp     short loc_18002CC81
0x18002cc7a  lea     r12, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002cc81  mov     rcx, rdi
0x18002cc84  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cc89  xor     r8d, r8d; psa
0x18002cc8c  mov     rdx, rax; pszPath
0x18002cc8f  xor     ecx, ecx; hwnd
0x18002cc91  call    cs:__imp_SHCreateDirectoryExW
0x18002cc97  mov     ebx, eax
0x18002cc99  test    eax, eax
0x18002cc9b  jz      short loc_18002CD00
0x18002cc9d  mov     rax, cs:WPP_GLOBAL_Control
0x18002cca4  cmp     rax, r13
0x18002cca7  jz      short loc_18002CCEA
0x18002cca9  test    byte ptr [rax+1Ch], 8
0x18002ccad  jz      short loc_18002CCEA
0x18002ccaf  cmp     byte ptr [rax+19h], 2
0x18002ccb3  jb      short loc_18002CCEA
0x18002ccb5  test    ebx, ebx
0x18002ccb7  jg      short loc_18002CCBD
0x18002ccb9  mov     edi, ebx
0x18002ccbb  jmp     short loc_18002CCC6
0x18002ccbd  movzx   edi, bx
0x18002ccc0  or      edi, 80070000h
0x18002ccc6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002cccb  mov     edx, 0A9h
0x18002ccd0  mov     dword ptr [rsp+738h+var_718], edi
0x18002ccd4  mov     r9d, eax
0x18002ccd7  mov     r8, r12
0x18002ccda  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cce1  mov     rcx, [rcx+10h]
0x18002cce5  call    WPP_SF_Dd
0x18002ccea  test    ebx, ebx
0x18002ccec  jle     short loc_18002CCF7
0x18002ccee  movzx   ebx, bx
0x18002ccf1  or      ebx, 80070000h
0x18002ccf7  mov     [rsp+738h+var_704], ebx
0x18002ccfb  jmp     loc_18002D60D
0x18002cd00  lea     r8, [rsi+368h]
0x18002cd07  lea     rdx, [rsp+738h+var_6E8]
0x18002cd0c  mov     rcx, r8
0x18002cd0f  call    ?begin@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(void)
0x18002cd14  mov     rcx, [rax]
0x18002cd17  mov     [rsp+738h+var_6F8], rcx
0x18002cd1c  lea     rdx, [rsp+738h+var_5D0]
0x18002cd24  mov     rcx, r8
0x18002cd27  call    ?begin@?$vector@IV?$allocator@_N@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@XZ; std::vector<uint>::begin(void)
0x18002cd2c  mov     rdx, rax
0x18002cd2f  lea     rcx, [rsp+738h+var_6F8]
0x18002cd34  call    ??9?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>> const &)
0x18002cd39  test    al, al
0x18002cd3b  jz      loc_18002D5F0
0x18002cd41  lea     rcx, [rsp+738h+var_6F8]
0x18002cd46  call    ??C?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEBAPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(void)
0x18002cd4b  mov     rbx, rax
0x18002cd4e  mov     [rsp+738h+var_6E0], rax
0x18002cd53  lea     rdi, [rax+90h]
0x18002cd5a  mov     [rsp+738h+var_6E8], rdi
0x18002cd5f  mov     rcx, rdi
0x18002cd62  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cd67  mov     rdx, rax; unsigned __int16 *
0x18002cd6a  mov     rcx, rsi; this
0x18002cd6d  call    ?IsSSPAppInstalled@CWorkspace@@QEAA_NPEBG@Z; CWorkspace::IsSSPAppInstalled(ushort const *)
0x18002cd72  test    al, al
0x18002cd74  jnz     short loc_18002CD7B
0x18002cd76  jmp     loc_18002D5D2
0x18002cd7b  lea     rdx, [rbx+50h]
0x18002cd7f  lea     rcx, [rsp+738h+var_4E0]
0x18002cd87  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002cd8c  lea     rcx, [rsp+738h+var_520]
0x18002cd94  cmp     [rbx+80h], r15
0x18002cd9b  jbe     short loc_18002CDA8
0x18002cd9d  lea     rdx, [rbx+70h]
0x18002cda1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002cda6  jmp     short loc_18002CDB4
0x18002cda8  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\mstsc.exe"
0x18002cdaf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002cdb4  cmp     [rbx+20h], r15d
0x18002cdb8  jz      short loc_18002CDD3
0x18002cdba  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\mstsc.exe"
0x18002cdc1  lea     rcx, [rsp+738h+var_500]
0x18002cdc9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002cdce  jmp     loc_18002CE8E
0x18002cdd3  lea     r8, [rbx+30h]
0x18002cdd7  lea     rdx, [rsp+738h+var_568]
0x18002cddf  lea     rcx, [rsp+738h+var_6B8]
0x18002cde7  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::find(std::wstring const &)
0x18002cdec  mov     rcx, [rax]
0x18002cdef  mov     [rsp+738h+var_6D8], rcx
0x18002cdf4  lea     rdx, [rsp+738h+var_660]
0x18002cdfc  lea     rcx, [rsp+738h+var_6B8]
0x18002ce04  call    ?begin@?$vector@IV?$allocator@_N@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@XZ; std::vector<uint>::begin(void)
0x18002ce09  lea     rdx, [rsp+738h+var_6D8]
0x18002ce0e  mov     rcx, rax
0x18002ce11  call    ??8?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ResourceTypeInfo>>>>::operator==(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ResourceTypeInfo>>>> const &)
0x18002ce16  test    al, al
0x18002ce18  jz      short loc_18002CE73
0x18002ce1a  mov     rax, cs:WPP_GLOBAL_Control
0x18002ce21  cmp     rax, r13
0x18002ce24  jz      loc_18002CD76
0x18002ce2a  test    byte ptr [rax+1Ch], 1
0x18002ce2e  jz      loc_18002CD76
0x18002ce34  cmp     byte ptr [rax+19h], 2
0x18002ce38  jb      loc_18002CD76
0x18002ce3e  mov     rcx, rbx
0x18002ce41  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ce46  mov     rbx, rax
0x18002ce49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ce4e  mov     edx, 0AAh
0x18002ce53  mov     [rsp+738h+var_718], rbx
0x18002ce58  mov     r9d, eax
0x18002ce5b  mov     r8, r12
0x18002ce5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce65  mov     rcx, [rcx+10h]
0x18002ce69  call    WPP_SF_DS
0x18002ce6e  jmp     loc_18002CD76
0x18002ce73  lea     rcx, [rsp+738h+var_6D8]
0x18002ce78  call    ??C?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEBAPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(void)
0x18002ce7d  lea     rdx, [rax+40h]
0x18002ce81  lea     rcx, [rsp+738h+var_500]
0x18002ce89  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002ce8e  mov     [rsp+738h+var_708], r15b
0x18002ce93  cmp     [rbx+20h], r15d
0x18002ce97  jz      loc_18002D07F
0x18002ce9d  lea     rax, [rsp+738h+var_6A0]
0x18002cea5  mov     [rsp+738h+var_658], rax
0x18002cead  lea     rdx, [rbx+50h]
0x18002ceb1  lea     rcx, [rsp+738h+var_6A0]
0x18002ceb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cebe  nop
0x18002cebf  lea     r9, [rsp+738h+var_560]
0x18002cec7  lea     r8, [rsp+738h+var_708]
0x18002cecc  mov     rdx, rax
0x18002cecf  call    ?GetAppID@CWorkspace@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_NAEAV23@@Z; CWorkspace::GetAppID(std::wstring,bool *,std::wstring &)
0x18002ced4  cmp     [rsp+738h+var_708], r15b
0x18002ced9  jz      loc_18002D07F
0x18002cedf  mov     rax, cs:WPP_GLOBAL_Control
0x18002cee6  cmp     rax, r13
0x18002cee9  jz      short loc_18002CF2C
0x18002ceeb  test    byte ptr [rax+1Ch], 1
0x18002ceef  jz      short loc_18002CF2C
0x18002cef1  cmp     byte ptr [rax+19h], 5
0x18002cef5  jb      short loc_18002CF2C
0x18002cef7  mov     rcx, rdi
0x18002cefa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ceff  mov     rbx, rax
0x18002cf02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002cf07  mov     edx, 0ABh
0x18002cf0c  mov     [rsp+738h+var_718], rbx
0x18002cf11  mov     r9d, eax
0x18002cf14  mov     r8, r12
0x18002cf17  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf1e  mov     rcx, [rcx+10h]
0x18002cf22  call    WPP_SF_DS
0x18002cf27  mov     rbx, [rsp+738h+var_6E0]
0x18002cf2c  mov     ecx, 0E8h; Size
0x18002cf31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cf36  mov     [rsp+738h+var_650], rax
0x18002cf3e  test    rax, rax
0x18002cf41  jz      short loc_18002CF52
0x18002cf43  mov     rcx, rax; this
0x18002cf46  call    ??0CWorkspaceAppID@@QEAA@XZ; CWorkspaceAppID::CWorkspaceAppID(void)
0x18002cf4b  mov     [rsp+738h+var_6D0], rax
0x18002cf50  jmp     short loc_18002CF57
0x18002cf52  mov     [rsp+738h+var_6D0], r15
0x18002cf57  lea     rax, [rsp+738h+var_6A0]
0x18002cf5f  mov     [rsp+738h+var_648], rax
0x18002cf67  lea     rdx, [rsi+40h]
0x18002cf6b  lea     rcx, [rsp+738h+var_6A0]
0x18002cf73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cf78  mov     r14, rax
0x18002cf7b  lea     rax, [rsp+738h+var_5C8]
0x18002cf83  mov     [rsp+738h+var_640], rax
0x18002cf8b  lea     rdx, [rbx+50h]
0x18002cf8f  lea     rcx, [rsp+738h+var_5C8]
0x18002cf97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cf9c  mov     rsi, rax
0x18002cf9f  lea     rax, [rsp+738h+var_5A8]
0x18002cfa7  mov     [rsp+738h+var_638], rax
0x18002cfaf  lea     rdx, [rsp+738h+var_520]
0x18002cfb7  lea     rcx, [rsp+738h+var_5A8]
0x18002cfbf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cfc4  mov     rdi, rax
0x18002cfc7  lea     rax, [rsp+738h+var_588]
0x18002cfcf  mov     [rsp+738h+var_630], rax
0x18002cfd7  mov     rdx, rbx
0x18002cfda  lea     rcx, [rsp+738h+var_588]
0x18002cfe2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cfe7  mov     rbx, rax
0x18002cfea  lea     rax, [rsp+738h+var_680]
0x18002cff2  mov     [rsp+738h+var_628], rax
0x18002cffa  lea     rdx, [rsp+738h+var_560]
0x18002d002  lea     rcx, [rsp+738h+var_680]
0x18002d00a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002d00f  nop
0x18002d010  mov     [rsp+738h+var_710], r14; __int64
0x18002d015  mov     [rsp+738h+var_718], rsi; __int64
0x18002d01a  mov     r9, rdi
0x18002d01d  mov     r8, rbx
  ... truncated ...
```
