# CWorkspace::RegisterAppFileAssociations(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,TS_WORKSPACE_FILE_ASSOC_INFO,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,TS_WORKSPACE_FILE_ASSOC_INFO>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,KeyCompareLess,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>> &)

- ea: `0x180034224`
- end: `0x180034ca0`
- name: `?RegisterAppFileAssociations@CWorkspace@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTS_WORKSPACE_FILE_ASSOC_INFO@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTS_WORKSPACE_FILE_ASSOC_INFO@@@std@@@2@@3@0AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UKeyCompareLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@3@@Z`
- size: `2684`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b1a8`

## callees

- `0x180005500`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000c3a0`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000fed8`
- `0x18001e5d8`
- `0x18001ead4`
- `0x180020a68`
- `0x180020bf0`
- `0x180027f80`
- `0x180028ca0`
- `0x180028d04`
- `0x180034224`
- `0x18003add8`
- `0x1800512e8`
- `0x180051630`
- `0x180051968`
- `0x180053c00`
- `0x180053cfc`
- `0x180054b64`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034742`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034c1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034c1f`
- `ktmw32!CreateTransaction` at `0x1800343f9`
- `ktmw32!CreateTransaction` at `0x1800343f9`
- `ktmw32!CommitTransaction` at `0x1800346d8`
- `ktmw32!CommitTransaction` at `0x1800346d8`

## string_xrefs

- `0x1800344c4`: `CWorkspaceFtaAppRegistration::CreateInstance failed`
- `0x180034869`: `CWorkspaceFileAssociation::CreateInstance failed`
- `0x18003469a`: `CWorkspaceFtaAppRegistration::Install failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 __fastcall CWorkspace::RegisterAppFileAssociations(
        __int64 a1,
        void *a2,
        void *a3,
        void *a4,
        void *a5,
        __int64 a6,
        void *a7,
        __int64 a8)
{
  void *v8; // rsi
  void *v9; // r13
  void *v10; // r15
  void *v12; // r14
  __int64 v13; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v15; // rbx
  unsigned int v16; // eax
  int v17; // ebx
  HANDLE Transaction; // r12
  signed int LastError; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  signed int v22; // eax
  unsigned int v23; // eax
  struct CWorkspaceFtaAppRegistration *v24; // r15
  __int64 v25; // r14
  __int64 v26; // rsi
  __int64 v27; // rdi
  __int64 v28; // rbx
  __int64 v29; // rax
  unsigned int v30; // eax
  __int64 v31; // rdi
  unsigned int v32; // eax
  signed int v33; // eax
  unsigned int v34; // ebx
  unsigned int v35; // eax
  signed int v36; // eax
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rdi
  __int64 v40; // rdx
  unsigned int v41; // eax
  __int64 v42; // r13
  __int64 v43; // r12
  void *v44; // r15
  void *v45; // r14
  void *v46; // rsi
  int v47; // edi
  int v48; // ebx
  int v49; // eax
  unsigned int v50; // eax
  __int64 v51; // rdi
  int v52; // ebx
  unsigned int v53; // eax
  DWORD Timeout[2]; // [rsp+28h] [rbp-2D0h]
  DWORD Timeouta[2]; // [rsp+28h] [rbp-2D0h]
  struct CWorkspaceFileAssociation *v57; // [rsp+58h] [rbp-2A0h] BYREF
  void *v58; // [rsp+60h] [rbp-298h]
  void *v59; // [rsp+68h] [rbp-290h]
  void *v60; // [rsp+70h] [rbp-288h]
  struct CWorkspaceFtaAppRegistration *v61; // [rsp+78h] [rbp-280h] BYREF
  __int64 v62; // [rsp+80h] [rbp-278h]
  void *v63; // [rsp+88h] [rbp-270h]
  _BYTE *v64; // [rsp+90h] [rbp-268h] BYREF
  void *v65; // [rsp+98h] [rbp-260h]
  int v66[2]; // [rsp+A0h] [rbp-258h]
  __int64 v67; // [rsp+A8h] [rbp-250h]
  int v68[2]; // [rsp+B0h] [rbp-248h]
  __int64 v69; // [rsp+B8h] [rbp-240h]
  _BYTE *v70; // [rsp+C0h] [rbp-238h] BYREF
  _BYTE *v71; // [rsp+C8h] [rbp-230h]
  __int64 v72; // [rsp+D0h] [rbp-228h]
  _QWORD v73[3]; // [rsp+D8h] [rbp-220h] BYREF
  int v74; // [rsp+F0h] [rbp-208h]
  _BYTE v75[32]; // [rsp+F8h] [rbp-200h] BYREF
  _BYTE v76[32]; // [rsp+118h] [rbp-1E0h] BYREF
  __int64 v77; // [rsp+138h] [rbp-1C0h]
  _BYTE *v78; // [rsp+140h] [rbp-1B8h]
  _BYTE *v79; // [rsp+148h] [rbp-1B0h]
  _BYTE *v80; // [rsp+150h] [rbp-1A8h]
  _BYTE *v81; // [rsp+158h] [rbp-1A0h]
  _BYTE *v82; // [rsp+160h] [rbp-198h]
  _BYTE *v83; // [rsp+168h] [rbp-190h]
  _BYTE *v84; // [rsp+170h] [rbp-188h]
  char v85[8]; // [rsp+178h] [rbp-180h] BYREF
  _BYTE v86[32]; // [rsp+180h] [rbp-178h] BYREF
  _BYTE v87[32]; // [rsp+1A0h] [rbp-158h] BYREF
  _BYTE v88[32]; // [rsp+1C0h] [rbp-138h] BYREF
  _BYTE v89[32]; // [rsp+1E0h] [rbp-118h] BYREF
  _BYTE v90[32]; // [rsp+200h] [rbp-F8h] BYREF
  _BYTE v91[32]; // [rsp+220h] [rbp-D8h] BYREF
  void *v92; // [rsp+240h] [rbp-B8h]
  void *v93; // [rsp+248h] [rbp-B0h]
  void *v94; // [rsp+250h] [rbp-A8h]
  void *v95; // [rsp+258h] [rbp-A0h]
  void *v96; // [rsp+260h] [rbp-98h]
  _BYTE v97[32]; // [rsp+268h] [rbp-90h] BYREF
  _BYTE v98[40]; // [rsp+288h] [rbp-70h] BYREF

  v77 = -2;
  v8 = a4;
  v58 = a4;
  v9 = a3;
  v65 = a3;
  v10 = a2;
  v60 = a2;
  v67 = a1;
  v92 = a2;
  v93 = a3;
  v96 = a4;
  v12 = a5;
  v59 = a5;
  v94 = a5;
  v63 = a7;
  v95 = a7;
  v69 = a8;
  v62 = -1;
  v73[1] = 0;
  v73[2] = 0;
  v74 = 0;
  v73[0] = &CTSSimpleComPtrArray<CWorkspaceFtaAppRegistration>::`vftable';
  v57 = 0;
  v61 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      266,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix,
      v13);
  }
  if ( *(_QWORD *)(a6 + 8) )
  {
    Transaction = CreateTransaction(
                    0,
                    0,
                    1u,
                    0,
                    0,
                    0x2710u,
                    (LPWSTR)L"Registering per-app File Association information");
    v62 = (__int64)Transaction;
    if ( Transaction == (HANDLE)-1LL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v20 = LastError;
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v21, v20);
      }
      v22 = GetLastError();
      v17 = v22;
      if ( v22 > 0 )
        v17 = (unsigned __int16)v22 | 0x80070000;
    }
    else
    {
      v17 = CWorkspaceFtaAppRegistration::CreateInstance(&v61);
      if ( v17 >= 0 )
      {
        v24 = v61;
        *(_QWORD *)v68 = v98;
        v25 = std::wstring::wstring(v98, a1 + 296);
        v64 = v97;
        v26 = std::wstring::wstring(v97, a1 + 104);
        *(_QWORD *)v66 = v86;
        v72 = a1 + 64;
        v27 = std::wstring::wstring(v86, a1 + 64);
        v71 = v75;
        v28 = std::wstring::wstring(v75, v58);
        v70 = v76;
        v29 = std::wstring::wstring(v76, v9);
        v17 = CWorkspaceFtaAppRegistration::Initialize(v24, v29, v28, v27, v26, v25);
        if ( v17 >= 0 )
        {
          v31 = v67;
          v17 = CWorkspaceFtaAppRegistration::Install(v61, Transaction, *(_DWORD *)(v67 + 864) != 0);
          if ( v17 >= 0 )
          {
            if ( CommitTransaction(Transaction) )
            {
              (*(void (__fastcall **)(__int64, struct CWorkspaceFtaAppRegistration *))(*(_QWORD *)(v31 + 832) + 8LL))(
                v31 + 832,
                v61);
              std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
                a6,
                &v64,
                a6);
              while ( 1 )
              {
                v38 = std::vector<unsigned int>::begin(v37, &v70);
                if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                                         &v64,
                                         v38) )
                {
                  v17 = 0;
                  v8 = v58;
                  v12 = v59;
                  v10 = v60;
                  goto LABEL_73;
                }
                v39 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v64);
                std::wstring::wstring(v98, v39);
                v12 = v59;
                v40 = (__int64)v59;
                if ( *(_QWORD *)(v39 + 120) )
                  v40 = v39 + 104;
                std::wstring::wstring(v97, v40);
                if ( v57 )
                {
                  TCntPtr<CConfigManager>::SafeRelease(&v57);
                  v57 = 0;
                  TCntPtr<CConfigManager>::SafeAddRef(&v57);
                }
                v17 = CWorkspaceFileAssociation::CreateInstance(&v57);
                if ( v17 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v41 = RdpWppGetCurrentThreadActivityIdPrefix();
                    Timeouta[0] = v17;
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      273,
                      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                      v41,
                      (__int64)"CWorkspaceFileAssociation::CreateInstance failed",
                      *(_QWORD *)Timeouta);
                  }
                  std::wstring::~wstring(v97);
                  std::wstring::~wstring(v98);
                  v8 = v58;
                  v10 = v60;
                  goto LABEL_73;
                }
                *(_QWORD *)v68 = v57;
                v66[0] = *(_DWORD *)(v39 + 64);
                v71 = v76;
                v42 = std::wstring::wstring(v76, v60);
                v79 = v75;
                v43 = std::wstring::wstring(v75, v72);
                v80 = v86;
                v44 = (void *)std::wstring::wstring(v86, v97);
                v81 = v87;
                v45 = (void *)std::wstring::wstring(v87, v12);
                v78 = v88;
                v46 = (void *)std::wstring::wstring(v88, v63);
                v82 = v89;
                v47 = std::wstring::wstring(v89, v58);
                v83 = v90;
                v48 = std::wstring::wstring(v90, v65);
                v84 = v91;
                v49 = std::wstring::wstring(v91, v98);
                v17 = CWorkspaceFileAssociation::Initialize(v68[0], v49, v48, v47, v46, v45, v44, v43, v42, v66[0]);
                if ( v17 < 0 )
                  break;
                v51 = v67;
                if ( *(_DWORD *)(v67 + 864) )
                {
                  v52 = CWorkspaceFileAssociation::Install(v57, (__int64)v61, v69);
                  if ( v52 < 0
                    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v53 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      275,
                      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                      v53,
                      v52);
                  }
                }
                (*(void (__fastcall **)(__int64, struct CWorkspaceFileAssociation *))(*(_QWORD *)(v51 + 744) + 8LL))(
                  v51 + 744,
                  v57);
                std::wstring::~wstring(v97);
                std::wstring::~wstring(v98);
                std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(
                  &v64,
                  v85);
                Transaction = (HANDLE)v62;
                v9 = v65;
                v37 = a6;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v50 = RdpWppGetCurrentThreadActivityIdPrefix();
                Timeouta[0] = v17;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  274,
                  (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                  v50,
                  (__int64)"CWorkspaceFileAssociation::Initialize failed",
                  *(_QWORD *)Timeouta);
              }
              std::wstring::~wstring(v97);
              std::wstring::~wstring(v98);
              Transaction = (HANDLE)v62;
              v9 = v65;
              v8 = v58;
              v12 = v59;
              v10 = v60;
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v33 = GetLastError();
                v34 = v33;
                if ( v33 > 0 )
                  v34 = (unsigned __int16)v33 | 0x80070000;
                v35 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  272,
                  WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                  v35,
                  v34);
              }
              v36 = GetLastError();
              v17 = v36;
              if ( v36 > 0 )
                v17 = (unsigned __int16)v36 | 0x80070000;
              v8 = v58;
              v12 = v59;
              v10 = v60;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v32 = RdpWppGetCurrentThreadActivityIdPrefix();
              Timeouta[0] = v17;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                271,
                (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v32,
                (__int64)"CWorkspaceFtaAppRegistration::Install failed",
                *(_QWORD *)Timeouta);
            }
            v8 = v58;
            v12 = v59;
            v10 = v60;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v30 = RdpWppGetCurrentThreadActivityIdPrefix();
            Timeouta[0] = v17;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              270,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v30,
              (__int64)"CWorkspaceFtaAppRegistration::Initialize failed",
              *(_QWORD *)Timeouta);
          }
          v8 = v58;
          v12 = v59;
          v10 = v60;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        Timeout[0] = v17;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          269,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v23,
          (__int64)"CWorkspaceFtaAppRegistration::CreateInstance failed",
          *(_QWORD *)Timeout);
      }
LABEL_73:
      if ( Transaction != (HANDLE)-1LL )
        CloseHandle(Transaction);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        267,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v16,
        v15);
    }
    v17 = 1;
  }
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v61);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v57);
  CTSSimpleComPtrArray<CWorkspaceFtaAppRegistration>::~CTSSimpleComPtrArray<CWorkspaceFtaAppRegistration>(v73);
  std::wstring::~wstring(v10);
  std::wstring::~wstring(v9);
  std::wstring::~wstring(v8);
  std::wstring::~wstring(v12);
  std::wstring::~wstring(v63);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180034224  mov     r11, rsp
0x180034227  push    rbx
0x180034228  push    rsi
0x180034229  push    rdi
0x18003422a  push    r12
0x18003422c  push    r13
0x18003422e  push    r14
0x180034230  push    r15
0x180034232  sub     rsp, 2C0h
0x180034239  mov     qword ptr [r11-1C0h], 0FFFFFFFFFFFFFFFEh
0x180034244  mov     rax, cs:__security_cookie
0x18003424b  xor     rax, rsp
0x18003424e  mov     [rsp+2F8h+var_48], rax
0x180034256  mov     rsi, r9
0x180034259  mov     [rsp+2F8h+var_298], r9
0x18003425e  mov     r13, r8
0x180034261  mov     [r11-260h], r8
0x180034268  mov     r15, rdx
0x18003426b  mov     [rsp+2F8h+var_288], rdx
0x180034270  mov     rdi, rcx
0x180034273  mov     [rsp+2F8h+var_250], rcx
0x18003427b  mov     [r11-0B8h], rdx
0x180034282  mov     [r11-0B0h], r8
0x180034289  mov     [r11-98h], r9
0x180034290  mov     r14, [rsp+2F8h+arg_20]
0x180034298  mov     [rsp+2F8h+var_290], r14
0x18003429d  mov     [r11-0A8h], r14
0x1800342a4  mov     rax, [rsp+2F8h+arg_30]
0x1800342ac  mov     [r11-270h], rax
0x1800342b3  mov     [r11-0A0h], rax
0x1800342ba  mov     rax, [rsp+2F8h+arg_38]
0x1800342c2  mov     [rsp+2F8h+var_240], rax
0x1800342ca  mov     qword ptr [r11-278h], 0FFFFFFFFFFFFFFFFh
0x1800342d5  lea     rax, ??_7?$CTSSimpleArray@PEAVCWorkspaceFtaAppRegistration@@$0BA@@@6B@; const CTSSimpleArray<CWorkspaceFtaAppRegistration *,16>::`vftable'
0x1800342dc  mov     [r11-220h], rax
0x1800342e3  xor     ecx, ecx
0x1800342e5  mov     [r11-218h], rcx
0x1800342ec  mov     [r11-210h], rcx
0x1800342f3  mov     [rsp+2F8h+var_208], ecx
0x1800342fa  lea     rax, ??_7?$CTSSimpleComPtrArray@VCWorkspaceFtaAppRegistration@@@@6B@; const CTSSimpleComPtrArray<CWorkspaceFtaAppRegistration>::`vftable'
0x180034301  mov     [r11-220h], rax
0x180034308  mov     [rsp+2F8h+var_2A0], rcx
0x18003430d  mov     [rsp+2F8h+var_280], rcx
0x180034312  lea     rbx, WPP_GLOBAL_Control
0x180034319  mov     rax, cs:WPP_GLOBAL_Control
0x180034320  cmp     rax, rbx
0x180034323  jz      short loc_18003436E
0x180034325  test    byte ptr [rax+1Ch], 1
0x180034329  jz      short loc_18003436E
0x18003432b  cmp     byte ptr [rax+19h], 4
0x18003432f  jb      short loc_18003436E
0x180034331  mov     rcx, r8
0x180034334  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034339  mov     rbx, rax
0x18003433c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180034341  mov     edx, 10Ah
0x180034346  mov     qword ptr [rsp+2F8h+IsolationFlags], rbx
0x18003434b  mov     r9d, eax
0x18003434e  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180034355  mov     rcx, cs:WPP_GLOBAL_Control
0x18003435c  mov     rcx, [rcx+10h]
0x180034360  call    WPP_SF_DS
0x180034365  xor     ecx, ecx
0x180034367  lea     rbx, WPP_GLOBAL_Control
0x18003436e  mov     rax, [rsp+2F8h+arg_28]
0x180034376  cmp     [rax+8], rcx
0x18003437a  jnz     short loc_1800343D6
0x18003437c  mov     rax, cs:WPP_GLOBAL_Control
0x180034383  cmp     rax, rbx
0x180034386  jz      short loc_1800343C8
0x180034388  test    byte ptr [rax+1Ch], 1
0x18003438c  jz      short loc_1800343C8
0x18003438e  cmp     byte ptr [rax+19h], 4
0x180034392  jb      short loc_1800343C8
0x180034394  mov     rcx, r13
0x180034397  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003439c  mov     rbx, rax
0x18003439f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800343a4  mov     edx, 10Bh
0x1800343a9  mov     qword ptr [rsp+2F8h+IsolationFlags], rbx
0x1800343ae  mov     r9d, eax
0x1800343b1  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800343b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343bf  mov     rcx, [rcx+10h]
0x1800343c3  call    WPP_SF_DS
0x1800343c8  mov     ebx, 1
0x1800343cd  mov     [rsp+2F8h+var_2A8], ebx
0x1800343d1  jmp     loc_180034C26
0x1800343d6  lea     rax, Description; "Registering per-app File Association in"...
0x1800343dd  mov     [rsp+2F8h+Description], rax; Description
0x1800343e2  mov     [rsp+2F8h+Timeout], 2710h; Timeout
0x1800343ea  mov     [rsp+2F8h+IsolationFlags], ecx; IsolationFlags
0x1800343ee  xor     r9d, r9d; IsolationLevel
0x1800343f1  xor     edx, edx; UOW
0x1800343f3  xor     ecx, ecx; lpTransactionAttributes
0x1800343f5  lea     r8d, [r9+1]; CreateOptions
0x1800343f9  call    cs:__imp_CreateTransaction
0x1800343ff  mov     r12, rax
0x180034402  mov     [rsp+2F8h+var_278], rax
0x18003440a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003440e  jnz     short loc_180034483
0x180034410  mov     rax, cs:WPP_GLOBAL_Control
0x180034417  cmp     rax, rbx
0x18003441a  jz      short loc_180034465
0x18003441c  test    byte ptr [rax+1Ch], 8
0x180034420  jz      short loc_180034465
0x180034422  cmp     byte ptr [rax+19h], 2
0x180034426  jb      short loc_180034465
0x180034428  call    cs:__imp_GetLastError
0x18003442e  mov     ebx, eax
0x180034430  test    eax, eax
0x180034432  jle     short loc_18003443D
0x180034434  movzx   ebx, ax
0x180034437  or      ebx, 80070000h
0x18003443d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180034442  mov     edx, 10Ch
0x180034447  mov     [rsp+2F8h+IsolationFlags], ebx
0x18003444b  mov     r9d, eax
0x18003444e  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180034455  mov     rcx, cs:WPP_GLOBAL_Control
0x18003445c  mov     rcx, [rcx+10h]
0x180034460  call    WPP_SF_Dd
0x180034465  call    cs:__imp_GetLastError
0x18003446b  mov     ebx, eax
0x18003446d  test    eax, eax
0x18003446f  jle     short loc_18003447A
0x180034471  movzx   ebx, ax
0x180034474  or      ebx, 80070000h
0x18003447a  mov     [rsp+2F8h+var_2A8], ebx
0x18003447e  jmp     loc_180034C26
0x180034483  lea     rcx, [rsp+2F8h+var_280]; struct CWorkspaceFtaAppRegistration **
0x180034488  call    ?CreateInstance@CWorkspaceFtaAppRegistration@@SAJPEAPEAV1@@Z; CWorkspaceFtaAppRegistration::CreateInstance(CWorkspaceFtaAppRegistration * *)
0x18003448d  mov     ebx, eax
0x18003448f  mov     [rsp+2F8h+var_2A8], eax
0x180034493  test    eax, eax
0x180034495  jns     short loc_1800344F0
0x180034497  mov     rax, cs:WPP_GLOBAL_Control
0x18003449e  lea     rcx, WPP_GLOBAL_Control
0x1800344a5  cmp     rax, rcx
0x1800344a8  jz      short loc_1800344EB
0x1800344aa  test    byte ptr [rax+1Ch], 8
0x1800344ae  jz      short loc_1800344EB
0x1800344b0  cmp     byte ptr [rax+19h], 2
0x1800344b4  jb      short loc_1800344EB
0x1800344b6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800344bb  mov     edx, 10Dh
0x1800344c0  mov     [rsp+2F8h+Timeout], ebx
0x1800344c4  lea     rcx, aCworkspaceftaa_1; "CWorkspaceFtaAppRegistration::CreateIns"...
0x1800344cb  mov     qword ptr [rsp+2F8h+IsolationFlags], rcx
0x1800344d0  mov     r9d, eax
0x1800344d3  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800344da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344e1  mov     rcx, [rcx+10h]
0x1800344e5  call    WPP_SF_DsD
0x1800344ea  nop
0x1800344eb  jmp     loc_180034C16
0x1800344f0  mov     r15, [rsp+2F8h+var_280]
0x1800344f5  lea     rax, [rsp+2F8h+var_70]
0x1800344fd  mov     qword ptr [rsp+2F8h+var_248], rax
0x180034505  lea     rdx, [rdi+128h]
0x18003450c  lea     rcx, [rsp+2F8h+var_70]
0x180034514  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034519  mov     r14, rax
0x18003451c  lea     rax, [rsp+2F8h+var_90]
0x180034524  mov     [rsp+2F8h+var_268], rax
0x18003452c  lea     rdx, [rdi+68h]
0x180034530  lea     rcx, [rsp+2F8h+var_90]
0x180034538  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003453d  mov     rsi, rax
0x180034540  lea     rax, [rsp+2F8h+var_178]
0x180034548  mov     qword ptr [rsp+2F8h+var_258], rax
0x180034550  lea     rax, [rdi+40h]
0x180034554  mov     [rsp+2F8h+var_228], rax
0x18003455c  mov     rdx, rax
0x18003455f  lea     rcx, [rsp+2F8h+var_178]
0x180034567  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003456c  mov     rdi, rax
0x18003456f  lea     rax, [rsp+2F8h+var_200]
0x180034577  mov     [rsp+2F8h+var_230], rax
0x18003457f  mov     rdx, [rsp+2F8h+var_298]
0x180034584  lea     rcx, [rsp+2F8h+var_200]
0x18003458c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034591  mov     rbx, rax
0x180034594  lea     rax, [rsp+2F8h+var_1E0]
0x18003459c  mov     [rsp+2F8h+var_238], rax
0x1800345a4  mov     rdx, r13
0x1800345a7  lea     rcx, [rsp+2F8h+var_1E0]
0x1800345af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800345b4  nop
0x1800345b5  mov     qword ptr [rsp+2F8h+Timeout], r14
0x1800345ba  mov     qword ptr [rsp+2F8h+IsolationFlags], rsi
0x1800345bf  mov     r9, rdi
0x1800345c2  mov     r8, rbx
0x1800345c5  mov     rdx, rax
0x1800345c8  mov     rcx, r15
0x1800345cb  call    ?Initialize@CWorkspaceFtaAppRegistration@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0000@Z; CWorkspaceFtaAppRegistration::Initialize(std::wstring,std::wstring,std::wstring,std::wstring,std::wstring)
0x1800345d0  mov     ebx, eax
0x1800345d2  mov     [rsp+2F8h+var_2A8], eax
0x1800345d6  xor     esi, esi
0x1800345d8  test    eax, eax
0x1800345da  jns     short loc_180034644
0x1800345dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800345e3  lea     rcx, WPP_GLOBAL_Control
0x1800345ea  cmp     rax, rcx
0x1800345ed  jz      short loc_180034630
0x1800345ef  test    byte ptr [rax+1Ch], 8
0x1800345f3  jz      short loc_180034630
0x1800345f5  cmp     byte ptr [rax+19h], 2
0x1800345f9  jb      short loc_180034630
0x1800345fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180034600  mov     edx, 10Eh
0x180034605  mov     [rsp+2F8h+Timeout], ebx
0x180034609  lea     rcx, aCworkspaceftaa_3; "CWorkspaceFtaAppRegistration::Initializ"...
0x180034610  mov     qword ptr [rsp+2F8h+IsolationFlags], rcx
0x180034615  mov     r9d, eax
0x180034618  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18003461f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034626  mov     rcx, [rcx+10h]
0x18003462a  call    WPP_SF_DsD
0x18003462f  nop
0x180034630  mov     rsi, [rsp+2F8h+var_298]
0x180034635  mov     r14, [rsp+2F8h+var_290]
0x18003463a  mov     r15, [rsp+2F8h+var_288]
0x18003463f  jmp     loc_180034C16
0x180034644  mov     rdi, [rsp+2F8h+var_250]
0x18003464c  cmp     [rdi+360h], esi
0x180034652  setnz   r8b; bool
0x180034656  mov     rdx, r12; void *
0x180034659  mov     rcx, [rsp+2F8h+var_280]; this
0x18003465e  call    ?Install@CWorkspaceFtaAppRegistration@@QEAAJPEAX_N@Z; CWorkspaceFtaAppRegistration::Install(void *,bool)
0x180034663  mov     ebx, eax
0x180034665  mov     [rsp+2F8h+var_2A8], eax
0x180034669  test    eax, eax
0x18003466b  jns     short loc_1800346D5
0x18003466d  mov     rax, cs:WPP_GLOBAL_Control
0x180034674  lea     rcx, WPP_GLOBAL_Control
0x18003467b  cmp     rax, rcx
0x18003467e  jz      short loc_1800346C1
0x180034680  test    byte ptr [rax+1Ch], 8
0x180034684  jz      short loc_1800346C1
0x180034686  cmp     byte ptr [rax+19h], 2
0x18003468a  jb      short loc_1800346C1
0x18003468c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180034691  mov     edx, 10Fh
0x180034696  mov     [rsp+2F8h+Timeout], ebx
0x18003469a  lea     rcx, aCworkspaceftaa_0; "CWorkspaceFtaAppRegistration::Install f"...
0x1800346a1  mov     qword ptr [rsp+2F8h+IsolationFlags], rcx
0x1800346a6  mov     r9d, eax
0x1800346a9  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800346b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800346b7  mov     rcx, [rcx+10h]
0x1800346bb  call    WPP_SF_DsD
0x1800346c0  nop
0x1800346c1  mov     rsi, [rsp+2F8h+var_298]
0x1800346c6  mov     r14, [rsp+2F8h+var_290]
0x1800346cb  mov     r15, [rsp+2F8h+var_288]
0x1800346d0  jmp     loc_180034C16
0x1800346d5  mov     rcx, r12; TransactionHandle
0x1800346d8  call    cs:__imp_CommitTransaction
0x1800346de  test    eax, eax
0x1800346e0  jnz     loc_18003476F
0x1800346e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800346ed  lea     rcx, WPP_GLOBAL_Control
0x1800346f4  cmp     rax, rcx
0x1800346f7  jz      short loc_180034742
0x1800346f9  test    byte ptr [rax+1Ch], 8
0x1800346fd  jz      short loc_180034742
0x1800346ff  cmp     byte ptr [rax+19h], 2
0x180034703  jb      short loc_180034742
0x180034705  call    cs:__imp_GetLastError
0x18003470b  mov     ebx, eax
0x18003470d  test    eax, eax
0x18003470f  jle     short loc_18003471A
0x180034711  movzx   ebx, ax
0x180034714  or      ebx, 80070000h
0x18003471a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003471f  mov     edx, 110h
0x180034724  mov     [rsp+2F8h+IsolationFlags], ebx
0x180034728  mov     r9d, eax
0x18003472b  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180034732  mov     rcx, cs:WPP_GLOBAL_Control
0x180034739  mov     rcx, [rcx+10h]
0x18003473d  call    WPP_SF_Dd
0x180034742  call    cs:__imp_GetLastError
0x180034748  mov     ebx, eax
0x18003474a  test    eax, eax
0x18003474c  jle     short loc_180034757
0x18003474e  movzx   ebx, ax
0x180034751  or      ebx, 80070000h
0x180034757  mov     [rsp+2F8h+var_2A8], ebx
0x18003475b  mov     rsi, [rsp+2F8h+var_298]
0x180034760  mov     r14, [rsp+2F8h+var_290]
0x180034765  mov     r15, [rsp+2F8h+var_288]
0x18003476a  jmp     loc_180034C16
0x18003476f  lea     rcx, [rdi+340h]
0x180034776  mov     rax, [rcx]
0x180034779  mov     rdx, [rsp+2F8h+var_280]
0x18003477e  mov     rax, [rax+8]
0x180034782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034787  lea     rdx, [rsp+2F8h+var_268]
  ... truncated ...
```
