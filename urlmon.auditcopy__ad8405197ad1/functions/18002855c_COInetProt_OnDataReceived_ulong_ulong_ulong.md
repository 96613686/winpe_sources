# COInetProt::OnDataReceived(ulong *,ulong *,ulong *)

- ea: `0x18002855c`
- end: `0x180029859`
- name: `?OnDataReceived@COInetProt@@QEAAJPEAK00@Z`
- size: `4861`
- prototype: `__int64 __fastcall(COInetProt *__hidden this, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180061a30`

## callees

- `0x180008b2c`
- `0x18001db50`
- `0x180023130`
- `0x180024ea0`
- `0x180026810`
- `0x180028410`
- `0x180028510`
- `0x18002855c`
- `0x18002f2c0`
- `0x18002fee0`
- `0x180031480`
- `0x180033858`
- `0x18003e100`
- `0x180045310`
- `0x18004ee30`
- `0x1800531b0`
- `0x180053228`
- `0x18005789c`
- `0x18005b29c`
- `0x18006218c`
- `0x18006c5dc`
- `0x180072260`
- `0x180074dc4`
- `0x18007536c`
- `0x18008390c`
- `0x180084cf8`
- `0x180088604`
- `0x18008af40`
- `0x1800940e4`
- `0x1800a34c4`
- `0x1800ac8ec`
- `0x1800ac95c`
- `0x1800fd768`
- `0x1800ffd4c`
- `0x1800ffef0`
- `0x1801285e6`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800292b0`
- `msvcrt!memcpy_s` at `0x1800292b0`
- `iertutil!CreateUri` at `0x180028e05`
- `iertutil!CreateUri` at `0x180028e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028a69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028a69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b2a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180028cbd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180028cbd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ca2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ca2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029030`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800290cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029030`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800290cf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002866a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002866a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029800`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002922f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800294cf`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002922f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800294cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800293ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800293ec`

## pseudocode

```c
__int64 __fastcall COInetProt::OnDataReceived(COInetProt *this, unsigned int *a2, unsigned int *a3, unsigned int *a4)
{
  int v4; // eax
  unsigned int *v5; // r13
  int v8; // ecx
  HRESULT Uri; // esi
  __int64 v10; // rdx
  int v11; // r15d
  HRESULT v12; // eax
  int v13; // edx
  int v14; // r14d
  unsigned int v15; // r14d
  int v16; // eax
  _QWORD *v17; // r15
  BOOL v18; // ebx
  unsigned int *v19; // r9
  unsigned int v20; // r11d
  unsigned int v21; // r14d
  bool v22; // al
  int v23; // ecx
  __int64 v24; // rsi
  CFeatureCache *v25; // rcx
  int v26; // ebx
  char v27; // r15
  __int64 v28; // rsi
  unsigned int v29; // eax
  int IsFeatureEnabledInternal; // eax
  bool v31; // zf
  __int64 v32; // rdx
  const WCHAR *v33; // rax
  int v34; // ecx
  const unsigned __int16 *v35; // r14
  const WCHAR *v36; // r13
  int v37; // r12d
  WCHAR *v38; // rcx
  OLECHAR *v39; // rbx
  int v40; // r12d
  int v41; // r15d
  const unsigned __int16 *MimeFromData; // rax
  __int64 v43; // rbx
  int v44; // eax
  bool v45; // zf
  wchar_t *v46; // r12
  int v47; // r14d
  COInetProt *v48; // rcx
  const unsigned __int16 *v49; // rdx
  void (__fastcall ***v50)(_QWORD, GUID *, STRSAFE_PCNZWCH *); // rcx
  int v51; // eax
  __int64 v52; // rdx
  STRSAFE_PCNZWCH v53; // rcx
  unsigned int *v54; // rbx
  unsigned int v55; // eax
  LPWSTR ExtensionW; // rax
  unsigned int v58; // ecx
  unsigned int v59; // edx
  _QWORD *ThreadLocalStoragePointer; // rax
  BOOL v61; // ebx
  int v62; // eax
  char *v63; // r14
  int v64; // eax
  wchar_t *v65; // r12
  unsigned __int16 *v66; // r13
  const unsigned __int16 *v67; // rcx
  const unsigned __int16 **v68; // rbx
  BOOL v69; // eax
  int v70; // ecx
  int v71; // eax
  unsigned int v72; // ecx
  unsigned int v73; // edx
  unsigned int v74; // ebx
  int v75; // eax
  int v76; // r14d
  bool v77; // sf
  unsigned int cchCount2; // eax
  const wchar_t *v79; // r14
  int v80; // eax
  int v81; // r15d
  __int64 v82; // rdx
  unsigned int v83; // eax
  char v84; // bl
  STRSAFE_PCNZWCH v85; // rcx
  void *v86; // rcx
  unsigned int v87; // ebx
  void *v88; // rax
  void *v89; // r14
  HRESULT v90; // eax
  int v91; // ecx
  int v92; // edx
  unsigned int v93; // edx
  unsigned int v94; // eax
  char v95; // al
  rsize_t v96; // rdx
  void *v97; // rcx
  const unsigned __int16 **v98; // rbx
  void *v99; // rcx
  const unsigned __int16 *v100; // r8
  const unsigned __int16 *v101; // r8
  unsigned __int16 *v102; // rdx
  int v103; // eax
  __int64 v104; // r8
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rax
  int v108; // eax
  __int64 v109; // r15
  unsigned __int16 *v110; // rax
  unsigned __int16 *v111; // rbx
  unsigned __int16 *v112; // r8
  unsigned int v113; // edx
  bool v114[4]; // [rsp+60h] [rbp-A0h] BYREF
  int cchCount1; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v116; // [rsp+68h] [rbp-98h] BYREF
  int v117; // [rsp+6Ch] [rbp-94h]
  unsigned int v118; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v119; // [rsp+74h] [rbp-8Ch] BYREF
  int v120; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v121; // [rsp+80h] [rbp-80h]
  unsigned int *v122; // [rsp+88h] [rbp-78h]
  int v123; // [rsp+90h] [rbp-70h] BYREF
  int v124; // [rsp+94h] [rbp-6Ch] BYREF
  void **v125; // [rsp+98h] [rbp-68h] BYREF
  WCHAR *v126; // [rsp+A0h] [rbp-60h]
  int v127; // [rsp+A8h] [rbp-58h]
  BSTR bstrString[2]; // [rsp+B0h] [rbp-50h]
  int v129; // [rsp+C0h] [rbp-40h]
  STRSAFE_PCNZWCH psz[2]; // [rsp+C8h] [rbp-38h] BYREF
  IUri *ppURI[2]; // [rsp+D8h] [rbp-28h] BYREF
  BINDINFO pbindinfo; // [rsp+F0h] [rbp-10h] BYREF
  CHAR MultiByteStr[16]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v134; // [rsp+180h] [rbp+80h]
  __int64 v135; // [rsp+190h] [rbp+90h]
  char v136; // [rsp+198h] [rbp+98h]
  int v137; // [rsp+1B0h] [rbp+B0h]
  __int128 v138; // [rsp+1B4h] [rbp+B4h]
  __int128 v139; // [rsp+1C4h] [rbp+C4h]
  __int128 v140; // [rsp+1D4h] [rbp+D4h]
  int v141; // [rsp+1E4h] [rbp+E4h]

  v4 = *((_DWORD *)this + 46);
  v5 = a3;
  v121 = a4;
  v122 = a3;
  if ( (v4 & 0x100) != 0 )
  {
    Uri = 2;
    goto LABEL_84;
  }
  v8 = *((_DWORD *)this + 37);
  Uri = 0;
  if ( (v8 & 0x230) != 0 && ((v4 & 2) == 0 || (v4 & 0x40) != 0) || (v8 & 0x200) != 0 && (v4 & 0x200) == 0 )
  {
    v10 = *((unsigned int *)this + 42);
    v11 = 0;
    v117 = 0;
    v120 = 0;
    if ( (unsigned int)v10 >= *((_DWORD *)this + 43) )
      goto LABEL_79;
    do
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 14) + 72LL))(
              *((_QWORD *)this + 14),
              *((_QWORD *)this + 19) + v10,
              (unsigned int)(*((_DWORD *)this + 40) - v10),
              &v120);
      v13 = v120;
      Uri = v12;
      v14 = *((_DWORD *)this + 42);
      *((_DWORD *)this + 41) += v120;
      v15 = v13 + v14;
      *((_DWORD *)this + 45) += v13;
      *((_DWORD *)this + 42) = v15;
      if ( v12 )
        break;
      v10 = v15;
    }
    while ( v15 < *((_DWORD *)this + 43) );
    v16 = *((_DWORD *)this + 46);
    if ( (v16 & 1) == 0 )
    {
      v17 = (_QWORD *)*((_QWORD *)this + 19);
      v18 = 0;
      InitOnceExecuteOnce(&stru_18016BB00, (PINIT_ONCE_FN)InitOnceDeviceFamily, 0, 0);
      if ( !byte_18016AF34 && v15 )
        v18 = IsDocFile(v17, v15) == 0;
      *((_DWORD *)this + 46) &= ~1u;
      *((_DWORD *)this + 46) |= v18;
      v16 = *((_DWORD *)this + 46);
    }
    v19 = v121;
    v20 = *v121;
    if ( *v121 )
    {
      if ( v20 <= *((_DWORD *)this + 40) )
        goto LABEL_15;
      v21 = *v121;
    }
    else
    {
      v21 = 0;
    }
    if ( (v16 & 1) != 0 )
    {
      v87 = 4096;
    }
    else
    {
      v22 = IsXmlProlog(*((_QWORD *)this + 19), *((_DWORD *)this + 42));
      v19 = v121;
      if ( !v22 )
        goto LABEL_15;
      v87 = 512;
      v20 = v21;
    }
    if ( *((_DWORD *)this + 40) < v87 )
    {
      v88 = operator new(v87);
      v89 = v88;
      if ( v88 )
      {
        memcpy_s(v88, v87, *((const void *const *)this + 19), *((unsigned int *)this + 42));
        operator delete(*((void **)this + 19));
        *((_QWORD *)this + 19) = v89;
        *((_DWORD *)this + 40) = v87;
        if ( !Uri )
        {
          do
          {
            v90 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 14) + 72LL))(
                    *((_QWORD *)this + 14),
                    *((_QWORD *)this + 19) + *((unsigned int *)this + 42),
                    v87 - *((_DWORD *)this + 42),
                    &v120);
            v91 = v120;
            Uri = v90;
            v92 = *((_DWORD *)this + 42);
            *((_DWORD *)this + 41) += v120;
            v93 = v91 + v92;
            *((_DWORD *)this + 45) += v91;
            *((_DWORD *)this + 42) = v93;
            if ( v90 )
              break;
            v87 = *((_DWORD *)this + 40);
          }
          while ( v93 < v87 );
        }
      }
      v19 = v121;
      v94 = *v121;
      if ( !*v121 || v94 >= *((_DWORD *)this + 40) )
        v94 = *((_DWORD *)this + 40);
      *((_DWORD *)this + 43) = v94;
      v20 = *v19;
    }
LABEL_15:
    v5 = v122;
    if ( Uri == -2147483638 )
    {
      if ( *((_DWORD *)this + 42) < *((_DWORD *)this + 43) )
      {
        Uri = 2;
        goto LABEL_18;
      }
    }
    else if ( Uri )
    {
      if ( Uri == 1 )
      {
        *a2 |= 0xCu;
        v11 = 1;
        v83 = *((_DWORD *)this + 41);
        *v19 = v83;
        *v5 = v83;
        v117 = 1;
        goto LABEL_19;
      }
LABEL_18:
      v11 = v117;
LABEL_19:
      v23 = *((_DWORD *)this + 46);
      if ( (v23 & 2) != 0 || *v5 < *((_DWORD *)this + 43) && Uri != 1 )
        goto LABEL_79;
      v24 = *((_QWORD *)this + 17);
      v25 = (CFeatureCache *)(v23 | 2u);
      v31 = *((_QWORD *)this + 24) == 0;
      *((_DWORD *)this + 46) = (_DWORD)v25;
      v26 = v31;
      psz[0] = 0;
      v124 = 0;
      v119 = 0;
      v123 = 0;
      if ( v24 )
      {
        memset_0(&pbindinfo.cbSize + 1, 0, 0x7Cu);
        pbindinfo.cbSize = 128;
        if ( (*(int (__fastcall **)(__int64, int *, BINDINFO *, unsigned int *, int *))(*(_QWORD *)(v24 + 16) + 40LL))(
               v24 + 16,
               &v124,
               &pbindinfo,
               &v119,
               &v123) >= 0 )
        {
          ReleaseBindInfo(&pbindinfo);
          if ( *((_QWORD *)this + 26) )
          {
            if ( (v119 & 0x80000000) == 0 )
              v26 |= 8u;
          }
        }
      }
      v27 = 3;
      v28 = *((_QWORD *)this + 28);
      v116 = 3;
      if ( g_pFeatureCache )
      {
        if ( !CFeatureCache::IsFeatureEnabled(v25, 3u) )
        {
LABEL_24:
          v29 = 0;
LABEL_25:
          v116 = v29;
LABEL_32:
          v31 = (v29 & 0xF) == 0;
          goto LABEL_33;
        }
      }
      else
      {
        IsFeatureEnabledInternal = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING);
        if ( IsFeatureEnabledInternal < 0 )
          goto LABEL_116;
        if ( IsFeatureEnabledInternal == 1 )
          goto LABEL_24;
      }
      if ( !v28 )
      {
        v29 = 3;
        goto LABEL_25;
      }
      if ( (int)EnsureSecurityManager() >= 0
        && ((int (__fastcall *)(struct IInternetSecurityManagerEx2 *, __int64, __int64, unsigned int *, int, _QWORD, _DWORD, int, _QWORD, _QWORD))g_pInternetSecurityManagerEx2->lpVtbl->ProcessUrlActionEx2)(
             g_pInternetSecurityManagerEx2,
             v28,
             8448,
             &v116,
             4,
             0,
             0,
             1,
             0,
             0) >= 0 )
      {
        LOBYTE(v29) = v116;
        goto LABEL_32;
      }
      v116 = 3;
LABEL_116:
      v31 = (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING) == 1;
LABEL_33:
      if ( v31 )
        v26 |= 2u;
      if ( (v119 & 0x2000000) != 0 )
      {
        v26 |= 0x10u;
      }
      else if ( (v26 & 2) == 0 )
      {
        v26 |= 4u;
      }
      v32 = *((unsigned int *)this + 46);
      v33 = (const WCHAR *)*((_QWORD *)this + 19);
      v34 = v26 | 0x40;
      v118 = 0;
      v35 = (const unsigned __int16 *)*((_QWORD *)this + 24);
      v36 = v33;
      if ( (v32 & 0x10) == 0 )
        v34 = v26;
      v37 = v34 | 0x80;
      if ( (v32 & 0x20) == 0 )
        v37 = v34;
      v38 = 0;
      cchCount1 = v37;
      if ( v35 || (v35 = (const unsigned __int16 *)*((_QWORD *)this + 33)) != 0 || v33 )
      {
        v39 = (OLECHAR *)*((_QWORD *)this + 25);
        if ( v33 || v39 )
        {
          v40 = *((_DWORD *)this + 42);
          Uri = -2147467259;
          ppURI[0] = 0;
          if ( v39 )
          {
            v41 = _AllocString<CTCoAllocPolicy>(0, v32, v39, ppURI);
            if ( v41 >= 0 )
              v39 = (OLECHAR *)ppURI[0];
          }
          else
          {
            v41 = -2147467259;
          }
          v135 = 0;
          v136 = 0;
          v141 = 0;
          v137 = 0;
          *(_OWORD *)MultiByteStr = 0;
          v134 = 0;
          v138 = 0;
          v139 = 0;
          v140 = 0;
          MimeFromData = CContentAnalyzer::FindMimeFromData(
                           (CContentAnalyzer *)MultiByteStr,
                           v35,
                           v36,
                           v40,
                           v39,
                           cchCount1,
                           &v118);
          if ( MimeFromData )
          {
            psz[0] = OLESTRDuplicate(MimeFromData);
            Uri = psz[0] == 0 ? 0x8007000E : 0;
          }
          if ( v41 >= 0 )
            CoTaskMemFree(v39);
          LOBYTE(v37) = cchCount1;
          v27 = 3;
        }
        else
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          cchCount1 = 260;
          if ( dword_180172680 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
          {
            Init_thread_header(&dword_180172680);
            if ( dword_180172680 == -1 )
            {
              dwFlags = HelperAddUriDefaultFlags(50342784, 5u);
              Init_thread_footer(&dword_180172680);
            }
          }
          v125 = &CUString::`vftable';
          ppURI[0] = 0;
          v126 = 0;
          v129 = 0;
          v127 = 11;
          *(_OWORD *)bstrString = 0;
          Uri = CreateUri(v35, dwFlags, 0, ppURI);
          if ( Uri >= 0 )
          {
            Uri = !(unsigned int)CUString::Set((CUString *)&v125, ppURI[0], 4u) && bstrString[1]
                ? GetMimeFromExt(bstrString[1], (unsigned __int16 *)MultiByteStr, (unsigned int *)&cchCount1)
                : -2147467259;
            ((void (__fastcall *)(IUri *))ppURI[0]->lpVtbl->Release)(ppURI[0]);
            if ( Uri >= 0 )
            {
              psz[0] = OLESTRDuplicate((const unsigned __int16 *)MultiByteStr);
              if ( psz[0] )
              {
                v118 = 2;
                Uri = 0;
              }
              else
              {
                Uri = -2147024882;
              }
            }
          }
          v38 = v126;
          v125 = &CUString::`vftable';
          v61 = v126 != 0;
          if ( v126 || v127 != 11 )
          {
            if ( bstrString[0] )
            {
              SysFreeString(bstrString[0]);
              v38 = v126;
              bstrString[0] = 0;
            }
            bstrString[1] = 0;
            v129 = 0;
            if ( v61 && v38 )
            {
              (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v38 + 16LL))(v38);
              v126 = 0;
            }
          }
          v127 = 11;
        }
        if ( !Uri && v118 == 4 )
        {
          if ( *((_QWORD *)this + 17) )
          {
            if ( *((_QWORD *)this + 24) )
            {
              if ( (v37 & 0x10) != 0 )
              {
                v38 = (WCHAR *)*((_QWORD *)this + 25);
                if ( v38 )
                {
                  if ( !StrCmpICW(v38, L"text/plain") )
                  {
                    ExtensionW = PathFindExtensionW(*((LPCWSTR *)this + 24));
                    if ( ExtensionW )
                    {
                      if ( *ExtensionW == 46 && !(unsigned int)StrCmpNIIW(ExtensionW, L".txt", 4u) )
                      {
                        v114[0] = 0;
                        COInetProt::SafeReportProgressToProtocolSink(this, 0x3Eu, 0, v114);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        Uri = -2147024809;
      }
      v43 = *((_QWORD *)this + 28);
      cchCount1 = 3;
      if ( g_pFeatureCache )
      {
        if ( !CFeatureCache::IsFeatureEnabled((CFeatureCache *)v38, 3u) )
        {
LABEL_55:
          v27 = 0;
LABEL_62:
          v45 = (v27 & 0xF) == 0;
LABEL_63:
          v46 = (wchar_t *)psz[0];
          if ( !v45 && psz[0] )
          {
            v74 = 10;
            psz[0] = 0;
            ppURI[0] = 0;
            cchCount1 = 0;
            v116 = 0;
            if ( StringLengthWorkerW(v46, 0xAu, (size_t *)psz) < 0
              || (v75 = LongLongToULong((unsigned __int64)psz[0], (unsigned int *)&cchCount1), v76 = cchCount1, v75 < 0) )
            {
              v76 = 10;
            }
            if ( StringLengthWorkerW(L"text/plain", 0xAu, (size_t *)ppURI) < 0
              || (v77 = (int)LongLongToULong((unsigned __int64)ppURI[0], &v116) < 0, cchCount2 = v116, v77) )
            {
              cchCount2 = 10;
            }
            if ( CompareStringW(0x7Fu, 0x1001u, v46, v76, L"text/plain", cchCount2) != 2 )
            {
              v79 = (const wchar_t *)*((_QWORD *)this + 25);
              if ( v79 )
              {
                psz[0] = 0;
                ppURI[0] = 0;
                cchCount1 = 0;
                v116 = 0;
                if ( StringLengthWorkerW(v79, 0xAu, (size_t *)psz) < 0
                  || (v80 = LongLongToULong((unsigned __int64)psz[0], (unsigned int *)&cchCount1),
                      v81 = cchCount1,
                      v80 < 0) )
                {
                  v81 = 10;
                }
                if ( StringLengthWorkerW(L"text/plain", 0xAu, (size_t *)ppURI) >= 0
                  && (int)LongLongToULong((unsigned __int64)ppURI[0], &v116) >= 0 )
                {
                  v74 = v116;
                }
                if ( CompareStringW(0x7Fu, 0x1001u, v79, v81, L"text/plain", v74) == 2 )
                {
                  v82 = *((_QWORD *)this + 17);
                  if ( v82 )
                  {
                    v95 = *(_BYTE *)(v82 + 440);
                    if ( (v95 & 1) != 0 )
                    {
                      *(_BYTE *)(v82 + 440) = v95 & 0xFE;
                    }
                    else
                    {
                      operator delete(v46);
                      v46 = OLESTRDuplicate(*((const unsigned __int16 **)this + 25));
                      v114[0] = 0;
                      *(_BYTE *)(*((_QWORD *)this + 17) + 440LL) |= 2u;
                      COInetProt::SafeReportProgressToProtocolSink(this, 0x32u, v46, v114);
                    }
                  }
                  else
                  {
                    operator delete(v46);
                    v46 = OLESTRDuplicate(*((const unsigned __int16 **)this + 25));
                  }
                }
              }
            }
          }
          v47 = 0;
          if ( COInetProt::ShouldCheckCacheExtension(this) )
          {
            v49 = v46;
            if ( *((_QWORD *)this + 26) )
              v49 = (const unsigned __int16 *)*((_QWORD *)this + 26);
            v47 = COInetProt::CheckCacheExtension(v48, v49, v118);
          }
          psz[0] = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
          v50 = (void (__fastcall ***)(_QWORD, GUID *, STRSAFE_PCNZWCH *))*((_QWORD *)this + 15);
          if ( v50 )
            (**v50)(v50, &GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b, psz);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
          v51 = *((_DWORD *)this + 46);
          v52 = 0x8000;
          if ( v47 || (v51 & 0x8000) == 0 )
          {
            v53 = psz[0];
            if ( !psz[0] )
            {
LABEL_76:
              if ( v46 )
              {
                psz[0] = 0;
                v84 = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)psz);
                if ( !(unsigned int)COInetProt::GetProtocolSink(this, (struct IInternetProtocolSink **)psz) )
                {
                  v84 = 1;
                  (*(void (__fastcall **)(STRSAFE_PCNZWCH, __int64, wchar_t *))(*(_QWORD *)psz[0] + 32LL))(
                    psz[0],
                    13,
                    v46);
                }
                v85 = psz[0];
                if ( psz[0] )
                {
                  psz[0] = 0;
                  (*(void (__fastcall **)(STRSAFE_PCNZWCH))(*(_QWORD *)v85 + 16LL))(v85);
                }
                if ( v84 )
                  *((_DWORD *)this + 46) |= 4u;
                v86 = (void *)*((_QWORD *)this + 25);
                if ( v86 )
                  CoTaskMemFree(v86);
                *((_QWORD *)this + 25) = v46;
              }
              if ( (*((_BYTE *)this + 184) & 1) == 0 )
                goto LABEL_78;
              if ( (*((_BYTE *)this + 148) & 0x20) == 0 )
                goto LABEL_78;
              v96 = *((unsigned int *)this + 42);
              v97 = (void *)*((_QWORD *)this + 19);
              *(_OWORD *)psz = 0;
              if ( (unsigned int)GetClassDocFileBuffer(v97, v96, (struct _GUID *)psz) )
                goto LABEL_78;
              v98 = (const unsigned __int16 **)((char *)this + 216);
              v99 = (void *)*((_QWORD *)this + 27);
              if ( v99 )
              {
                operator delete(v99);
                *v98 = 0;
              }
              StringFromCLSID((const IID *const)psz, (LPOLESTR *)this + 27);
              v100 = *v98;
              if ( *v98 )
              {
                v114[0] = 0;
                COInetProt::SafeReportProgressToProtocolSink(this, 0xCu, v100, v114);
                v5 = v122;
                v11 = v117;
                if ( v114[0] )
                  *((_DWORD *)this + 46) |= 0x400u;
              }
              else
              {
LABEL_78:
                v11 = v117;
                v5 = v122;
              }
LABEL_79:
              if ( (*((_DWORD *)this + 37) & 0x200) == 0 || (v62 = *((_DWORD *)this + 46), (v62 & 0x80u) != 0) )
              {
                v54 = v121;
LABEL_81:
                v55 = *v54;
                if ( *v54 && v55 < *v5 )
                  *v5 = v55;
                if ( Uri == 1 )
                  Uri = 0;
                goto LABEL_84;
              }
              v63 = (char *)*((_QWORD *)this + 26);
              if ( !v63 )
                v63 = (char *)*((_QWORD *)this + 25);
              v64 = v62 | 0x200;
              v118 = 0;
              *((_DWORD *)this + 46) = v64;
              v119 = 0;
              v65 = 0;
              psz[0] = 0;
              v66 = 0;
              *(_OWORD *)ppURI = 0;
              if ( (v64 & 0x400) == 0 )
              {
                v101 = (const unsigned __int16 *)*((_QWORD *)this + 27);
                if ( v101 )
                {
                  v114[0] = 0;
                  COInetProt::SafeReportProgressToProtocolSink(this, 0xCu, v101, v114);
                  if ( v114[0] )
                    *((_DWORD *)this + 46) |= 0x400u;
                }
              }
              v67 = (const unsigned __int16 *)*((_QWORD *)this + 24);
              v68 = (const unsigned __int16 **)((char *)this + 264);
              if ( !v67 )
                v67 = *v68;
              v69 = IsHandlerAvailable(
                      v67,
                      v63,
                      (struct _GUID *)ppURI,
                      *((unsigned __int8 **)this + 19),
                      *((_DWORD *)this + 42));
              v70 = *((_DWORD *)this + 46);
              if ( !v69 )
              {
                v70 |= 0x80u;
                *((_DWORD *)this + 46) = v70;
                goto LABEL_141;
              }
              if ( (v70 & 1) == 0 )
              {
LABEL_141:
                if ( (v70 & 0x40) != 0 || (v70 & 0x80u) != 0 || (v70 & 1) == 0 )
                {
LABEL_142:
                  if ( v65 )
                    CoTaskMemFree(v65);
                  goto LABEL_144;
                }
                if ( !v65 )
                {
LABEL_144:
                  if ( v66 )
                    operator delete(v66);
                  v71 = *((_DWORD *)this + 46);
                  v54 = v121;
                  if ( (v71 & 1) != 0 && (v71 & 0x80u) != 0 )
                  {
                    v113 = 2048;
                    if ( *v121 - 1 <= 0x7FE )
                      v113 = *v121;
                    *((_DWORD *)this + 43) = v113;
                    if ( *((_DWORD *)this + 42) >= v113 )
                      COInetProt::ReportCacheFileName(this, 0);
                  }
                  v72 = *((_DWORD *)this + 41);
                  v5 = v122;
                  v73 = *v122;
                  if ( *v122 <= v72 )
                    v73 = v72 + 1;
                  *v122 = v73;
                  goto LABEL_81;
                }
                psz[0] = 0;
                if ( !memcmp_0(ppURI, &GUID_NULL, 0x10u) )
                {
                  if ( v63 && !(unsigned int)StrCmpNIIW((PCNZWCH)v63, L"application/octet-stream", 0x18u) )
                    *((_DWORD *)this + 46) |= 0x80u;
                }
                else
                {
                  StringFromCLSID((const IID *const)ppURI, (LPOLESTR *)psz);
                }
                if ( *((char *)this + 184) < 0 || !psz[0] && !v63 )
                  goto LABEL_276;
                if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_RESTRICT_CDL) != 1 )
                {
                  if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
                    IECompatLogCDLRestrictions(0, 0, 1);
                  goto LABEL_276;
                }
                v104 = -1;
                do
                  ++v104;
                while ( v65[v104] );
                if ( psz[0] )
                {
                  v105 = -1;
                  do
                    ++v105;
                  while ( psz[0][v105] );
                }
                else
                {
                  LODWORD(v105) = 0;
                }
                if ( v63 )
                {
                  v106 = -1;
                  do
                    ++v106;
                  while ( *(_WORD *)&v63[2 * v106] );
                }
                else
                {
                  LODWORD(v106) = 0;
                }
                if ( v66 )
                {
                  v107 = -1;
                  do
                    ++v107;
                  while ( v66[v107] );
                  v108 = v107 + 1;
                }
                else
                {
                  v108 = 0;
                }
                v109 = (int)v105 + (int)v106 + (int)v104 + v108 + 3LL;
                v110 = (unsigned __int16 *)operator new(saturated_mul(v109, 2u));
                v111 = v110;
                if ( !v110 )
                {
LABEL_276:
                  operator delete((void *)psz[0]);
                  goto LABEL_142;
                }
                *v110 = 0;
                if ( *v65 )
                  StringCchCopyW(v110, v109, v65);
                StringCchCatW(v111, v109, L"?");
                v112 = (unsigned __int16 *)psz[0];
                if ( !psz[0] )
                {
                  if ( !v63 )
                  {
LABEL_273:
                    if ( v66 )
                    {
                      StringCchCatW(v111, v109, L"?");
                      StringCchCatW(v111, v109, v66);
                    }
                    (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)this + 17) + 32LL))(
                      *((_QWORD *)this + 17),
                      23,
                      v111);
                    operator delete(v111);
                    *((_DWORD *)this + 46) |= 0x1C0u;
                    Uri = 2;
                    goto LABEL_276;
                  }
                  v112 = (unsigned __int16 *)v63;
                }
                StringCchCatW(v111, v109, v112);
                goto LABEL_273;
              }
              if ( (int)GetCodeBaseFromDocFile(
                          *((unsigned __int8 **)this + 19),
                          *((_DWORD *)this + 42),
                          (unsigned __int16 **)psz,
                          *v68,
                          &v118,
                          &v119) < 0 )
              {
                if ( *((_DWORD *)this + 42) < *((_DWORD *)this + 43) )
                {
                  v103 = 64;
                  if ( !v11 )
                    goto LABEL_234;
                }
              }
              else if ( v118 || v119 )
              {
                StringCchPrintfA(MultiByteStr, 0x104u, "%ld,%ld", v118, v119);
                v66 = WzA2WDynamic(MultiByteStr, v102);
              }
              v103 = 0;
LABEL_234:
              *((_DWORD *)this + 46) &= ~0x40u;
              *((_DWORD *)this + 46) |= v103;
              v70 = *((_DWORD *)this + 46);
              v65 = (wchar_t *)psz[0];
              goto LABEL_141;
            }
            if ( !*((_QWORD *)this + 24) )
            {
LABEL_74:
              if ( v53 )
              {
                psz[0] = 0;
                (*(void (__fastcall **)(STRSAFE_PCNZWCH, __int64))(*(_QWORD *)v53 + 16LL))(v53, v52);
              }
              goto LABEL_76;
            }
            *((_DWORD *)this + 46) = v51 | 0x8000;
            (*(void (__fastcall **)(STRSAFE_PCNZWCH, __int64))(*(_QWORD *)v53 + 32LL))(v53, 14);
          }
          v53 = psz[0];
          goto LABEL_74;
        }
      }
      else
      {
        v44 = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING);
        if ( v44 < 0 )
          goto LABEL_118;
        if ( v44 == 1 )
          goto LABEL_55;
      }
      if ( !v43 )
        goto LABEL_62;
      if ( (int)EnsureSecurityManager() >= 0
        && ((int (__fastcall *)(struct IInternetSecurityManagerEx2 *, __int64, __int64, int *, int, _QWORD, _DWORD, int, _QWORD, _QWORD))g_pInternetSecurityManagerEx2->lpVtbl->ProcessUrlActionEx2)(
             g_pInternetSecurityManagerEx2,
             v43,
             8448,
             &cchCount1,
             4,
             0,
             0,
             1,
             0,
             0) >= 0 )
      {
        v27 = cchCount1;
        goto LABEL_62;
      }
      cchCount1 = 3;
LABEL_118:
      v45 = (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING) == 1;
      goto LABEL_63;
    }
    v58 = *((_DWORD *)this + 41);
    v59 = *v122;
    if ( *v122 <= v58 )
      v59 = v58 + 1;
    if ( v20 && v59 > v20 )
      v59 = v20;
    *v122 = v59;
    goto LABEL_18;
  }
LABEL_84:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *((_DWORD *)this + 44) = *v5;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x18002855c  push    rbp
0x18002855e  push    rbx
0x18002855f  push    rsi
0x180028560  push    rdi
0x180028561  push    r12
0x180028563  push    r13
0x180028565  push    r14
0x180028567  push    r15
0x180028569  lea     rbp, [rsp-298h]
0x180028571  sub     rsp, 398h
0x180028578  mov     rax, cs:__security_cookie
0x18002857f  xor     rax, rsp
0x180028582  mov     [rbp+2D0h+var_50], rax
0x180028589  mov     eax, [rcx+0B8h]
0x18002858f  mov     r13, r8
0x180028592  mov     [rbp+2D0h+var_350], r9
0x180028596  mov     r12, rdx
0x180028599  mov     [rbp+2D0h+var_348], r8
0x18002859d  mov     rdi, rcx
0x1800285a0  bt      eax, 8
0x1800285a4  jb      loc_180029240
0x1800285aa  mov     ecx, [rcx+94h]
0x1800285b0  xor     r14d, r14d
0x1800285b3  mov     esi, r14d
0x1800285b6  test    ecx, 230h
0x1800285bc  jz      loc_180029252
0x1800285c2  test    al, 2
0x1800285c4  jnz     loc_18002924A
0x1800285ca  mov     edx, [rdi+0A8h]
0x1800285d0  mov     r15d, r14d
0x1800285d3  mov     ebx, 1
0x1800285d8  mov     [rsp+3D0h+var_364], r14d
0x1800285dd  mov     [rsp+3D0h+var_358], r14d
0x1800285e2  cmp     edx, [rdi+0ACh]
0x1800285e8  jnb     loc_180028AFA
0x1800285ee  xor     r13d, r13d
0x1800285f1  mov     rcx, [rdi+70h]
0x1800285f5  lea     r9, [rsp+3D0h+var_358]
0x1800285fa  mov     r8d, [rdi+0A0h]
0x180028601  sub     r8d, edx
0x180028604  add     rdx, [rdi+98h]
0x18002860b  mov     rax, [rcx]
0x18002860e  mov     rax, [rax+48h]
0x180028612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028617  mov     edx, [rsp+3D0h+var_358]
0x18002861b  mov     esi, eax
0x18002861d  mov     r14d, [rdi+0A8h]
0x180028624  add     [rdi+0A4h], edx
0x18002862a  add     r14d, edx
0x18002862d  add     [rdi+0B4h], edx
0x180028633  mov     [rdi+0A8h], r14d
0x18002863a  test    eax, eax
0x18002863c  jz      loc_180028C47
0x180028642  mov     eax, [rdi+0B8h]
0x180028648  test    bl, al
0x18002864a  jnz     short loc_1800286B1
0x18002864c  mov     r15, [rdi+98h]
0x180028653  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002865a  xor     r9d, r9d; Context
0x18002865d  lea     rcx, stru_18016BB00; InitOnce
0x180028664  xor     r8d, r8d; Parameter
0x180028667  mov     ebx, r13d
0x18002866a  call    cs:__imp_InitOnceExecuteOnce
0x180028671  nop     dword ptr [rax+rax+00h]
0x180028676  cmp     cs:byte_18016AF34, r13b
0x18002867d  jnz     short loc_180028699
0x18002867f  test    r14d, r14d
0x180028682  jz      short loc_180028699
0x180028684  mov     edx, r14d; unsigned int
0x180028687  mov     rcx, r15; void *
0x18002868a  call    ?IsDocFile@@YAJPEAXK@Z; IsDocFile(void *,ulong)
0x18002868f  test    eax, eax
0x180028691  mov     edx, 1
0x180028696  cmovz   ebx, edx
0x180028699  and     dword ptr [rdi+0B8h], 0FFFFFFFEh
0x1800286a0  or      [rdi+0B8h], ebx
0x1800286a6  mov     ebx, 1
0x1800286ab  mov     eax, [rdi+0B8h]
0x1800286b1  mov     r9, [rbp+2D0h+var_350]
0x1800286b5  mov     r11d, [r9]
0x1800286b8  test    r11d, r11d
0x1800286bb  jnz     loc_180028B76
0x1800286c1  mov     r14d, r13d
0x1800286c4  test    bl, al
0x1800286c6  jnz     loc_18002926B
0x1800286cc  mov     edx, [rdi+0A8h]
0x1800286d2  mov     rcx, [rdi+98h]
0x1800286d9  call    IsXmlProlog
0x1800286de  mov     r9, [rbp+2D0h+var_350]
0x1800286e2  test    al, al
0x1800286e4  jnz     loc_180029272
0x1800286ea  xor     r14d, r14d
0x1800286ed  mov     r13, [rbp+2D0h+var_348]
0x1800286f1  cmp     esi, 8000000Ah
0x1800286f7  jnz     loc_180028D32
0x1800286fd  mov     eax, [rdi+0ACh]
0x180028703  cmp     [rdi+0A8h], eax
0x180028709  jnb     loc_180028D3A
0x18002870f  mov     esi, 2
0x180028714  mov     ebx, 1
0x180028719  mov     r15d, [rsp+3D0h+var_364]
0x18002871e  mov     ecx, [rdi+0B8h]
0x180028724  test    cl, 2
0x180028727  jnz     loc_180028AFA
0x18002872d  mov     eax, [rdi+0ACh]
0x180028733  cmp     [r13+0], eax
0x180028737  jb      loc_180029369
0x18002873d  mov     rsi, [rdi+88h]
0x180028744  or      ecx, 2; this
0x180028747  cmp     [rdi+0C0h], r14
0x18002874e  mov     ebx, r14d
0x180028751  mov     [rdi+0B8h], ecx
0x180028757  setz    bl
0x18002875a  mov     [rbp+2D0h+psz], r14
0x18002875e  mov     [rbp+2D0h+var_33C], r14d
0x180028762  mov     [rsp+3D0h+var_35C], r14d
0x180028767  mov     [rbp+2D0h+var_340], r14d
0x18002876b  test    rsi, rsi
0x18002876e  jnz     loc_180028BD7
0x180028774  cmp     cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA, r14; CFeatureCache * g_pFeatureCache
0x18002877b  mov     r15d, 3
0x180028781  mov     rsi, [rdi+0E0h]
0x180028788  mov     [rsp+3D0h+var_368], r15d
0x18002878d  jz      short loc_1800287A7
0x18002878f  mov     edx, r15d; enum _tagINTERNETFEATURELIST
0x180028792  call    ?IsFeatureEnabled@CFeatureCache@@QEAA_NW4_tagINTERNETFEATURELIST@@@Z; CFeatureCache::IsFeatureEnabled(_tagINTERNETFEATURELIST)
0x180028797  test    al, al
0x180028799  jnz     short loc_1800287C0
0x18002879b  mov     eax, r14d
0x18002879e  mov     [rsp+3D0h+var_368], eax
0x1800287a2  jmp     loc_180028827
0x1800287a7  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING@FCK@@3VCFeatureControlKey@@A; this
0x1800287ae  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800287b3  test    eax, eax
0x1800287b5  js      loc_180028D63
0x1800287bb  cmp     eax, 1
0x1800287be  jz      short loc_18002879B
0x1800287c0  test    rsi, rsi
0x1800287c3  jz      loc_180029376
0x1800287c9  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x1800287ce  test    eax, eax
0x1800287d0  js      loc_180028D5E
0x1800287d6  mov     rcx, cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x1800287dd  lea     r9, [rsp+3D0h+var_368]
0x1800287e2  mov     [rsp+3D0h+var_388], r14
0x1800287e7  mov     r8d, 2100h
0x1800287ed  mov     [rsp+3D0h+var_390], r14
0x1800287f2  mov     rdx, rsi
0x1800287f5  mov     [rsp+3D0h+var_398], 1
0x1800287fd  mov     rax, [rcx]
0x180028800  mov     dword ptr [rsp+3D0h+var_3A0], r14d
0x180028805  mov     qword ptr [rsp+3D0h+cchCount2], r14
0x18002880a  mov     dword ptr [rsp+3D0h+lpString2], 4
0x180028812  mov     rax, [rax+68h]
0x180028816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002881b  test    eax, eax
0x18002881d  js      loc_180028D5E
0x180028823  mov     eax, [rsp+3D0h+var_368]
0x180028827  test    al, 0Fh
0x180028829  jnz     short loc_18002882E
0x18002882b  or      ebx, 2
0x18002882e  test    [rsp+3D0h+var_35C], 2000000h
0x180028836  jz      loc_180028BC6
0x18002883c  or      ebx, 10h
0x18002883f  mov     edx, [rdi+0B8h]
0x180028845  mov     ecx, ebx
0x180028847  mov     rax, [rdi+98h]
0x18002884e  or      ecx, 40h
0x180028851  test    dl, 10h
0x180028854  mov     [rsp+3D0h+var_360], r14d
0x180028859  mov     r14, [rdi+0C0h]
0x180028860  mov     r13, rax
0x180028863  cmovz   ecx, ebx
0x180028866  mov     r12d, ecx
0x180028869  bts     r12d, 7
0x18002886e  test    dl, 20h
0x180028871  cmovz   r12d, ecx
0x180028875  xor     ecx, ecx
0x180028877  mov     [rsp+3D0h+cchCount1], r12d
0x18002887c  test    r14, r14
0x18002887f  jz      loc_1800291DF
0x180028885  mov     rbx, [rdi+0C8h]
0x18002888c  test    rax, rax
0x18002888f  jz      loc_180028D94
0x180028895  mov     r12d, [rdi+0A8h]
0x18002889c  mov     esi, 80004005h
0x1800288a1  mov     [rbp+2D0h+ppURI], rcx
0x1800288a5  test    rbx, rbx
0x1800288a8  jnz     short loc_1800288AF
0x1800288aa  mov     r15d, esi
0x1800288ad  jmp     short loc_1800288C8
0x1800288af  lea     r9, [rbp+2D0h+ppURI]
0x1800288b3  mov     r8, rbx
0x1800288b6  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800288bb  xor     ecx, ecx
0x1800288bd  mov     r15d, eax
0x1800288c0  test    eax, eax
0x1800288c2  jns     loc_180028D29
0x1800288c8  xorps   xmm0, xmm0
0x1800288cb  mov     [rbp+2D0h+var_240], rcx
0x1800288d2  xor     eax, eax
0x1800288d4  mov     [rbp+2D0h+var_238], cl
0x1800288da  mov     [rbp+2D0h+var_1EC], eax
0x1800288e0  mov     r9d, r12d; int
0x1800288e3  lea     rax, [rsp+3D0h+var_360]
0x1800288e8  mov     [rbp+2D0h+var_220], ecx
0x1800288ee  mov     [rsp+3D0h+var_3A0], rax; unsigned int *
0x1800288f3  lea     rcx, [rbp+2D0h+MultiByteStr]; this
0x1800288f7  mov     eax, [rsp+3D0h+cchCount1]
0x1800288fb  mov     r8, r13; char *
0x1800288fe  mov     [rsp+3D0h+cchCount2], eax; unsigned int
0x180028902  mov     rdx, r14; unsigned __int16 *
0x180028905  mov     [rsp+3D0h+lpString2], rbx; unsigned __int16 *
0x18002890a  movups  xmmword ptr [rbp+2D0h+MultiByteStr], xmm0
0x18002890e  movups  [rbp+2D0h+var_250], xmm0
0x180028915  movups  [rbp+2D0h+var_21C], xmm0
0x18002891c  movups  [rbp+2D0h+var_20C], xmm0
0x180028923  movups  [rbp+2D0h+var_1FC], xmm0
0x18002892a  call    ?FindMimeFromData@CContentAnalyzer@@QEAAPEBGPEBGPEADHPEAGKPEAK@Z; CContentAnalyzer::FindMimeFromData(ushort const *,char *,int,ushort *,ulong,ulong *)
0x18002892f  xor     r13d, r13d
0x180028932  test    rax, rax
0x180028935  jz      short loc_180028951
0x180028937  mov     rcx, rax; unsigned __int16 *
0x18002893a  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x18002893f  mov     [rbp+2D0h+psz], rax
0x180028943  mov     esi, 8007000Eh
0x180028948  neg     rax
0x18002894b  sbb     edx, edx
0x18002894d  not     edx
0x18002894f  and     esi, edx
0x180028951  test    r15d, r15d
0x180028954  js      short loc_180028965
0x180028956  mov     rcx, rbx; pv
0x180028959  call    cs:__imp_CoTaskMemFree
0x180028960  nop     dword ptr [rax+rax+00h]
0x180028965  mov     r12d, [rsp+3D0h+cchCount1]
0x18002896a  mov     r15d, 3
0x180028970  test    esi, esi
0x180028972  jz      loc_180028C5C
0x180028978  cmp     cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA, r13; CFeatureCache * g_pFeatureCache
0x18002897f  mov     rbx, [rdi+0E0h]
0x180028986  mov     [rsp+3D0h+cchCount1], r15d
0x18002898b  jz      short loc_18002899E
0x18002898d  mov     edx, r15d; enum _tagINTERNETFEATURELIST
0x180028990  call    ?IsFeatureEnabled@CFeatureCache@@QEAA_NW4_tagINTERNETFEATURELIST@@@Z; CFeatureCache::IsFeatureEnabled(_tagINTERNETFEATURELIST)
0x180028995  test    al, al
0x180028997  jnz     short loc_1800289B7
0x180028999  mov     r15d, r13d
0x18002899c  jmp     short loc_180028A1B
0x18002899e  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING@FCK@@3VCFeatureControlKey@@A; this
0x1800289a5  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800289aa  test    eax, eax
0x1800289ac  js      loc_180028D7C
0x1800289b2  cmp     eax, 1
0x1800289b5  jz      short loc_180028999
0x1800289b7  test    rbx, rbx
0x1800289ba  jz      short loc_180028A1B
0x1800289bc  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x1800289c1  test    eax, eax
0x1800289c3  js      loc_180028D77
0x1800289c9  mov     rcx, cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x1800289d0  lea     r9, [rsp+3D0h+cchCount1]
0x1800289d5  mov     [rsp+3D0h+var_388], r13
0x1800289da  mov     r8d, 2100h
0x1800289e0  mov     [rsp+3D0h+var_390], r13
0x1800289e5  mov     rdx, rbx
0x1800289e8  mov     [rsp+3D0h+var_398], 1
0x1800289f0  mov     rax, [rcx]
0x1800289f3  mov     dword ptr [rsp+3D0h+var_3A0], r13d
0x1800289f8  mov     qword ptr [rsp+3D0h+cchCount2], r13
0x1800289fd  mov     dword ptr [rsp+3D0h+lpString2], 4
0x180028a05  mov     rax, [rax+68h]
0x180028a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a0e  test    eax, eax
0x180028a10  js      loc_180028D77
0x180028a16  mov     r15d, [rsp+3D0h+cchCount1]
0x180028a1b  test    r15b, 0Fh
0x180028a1f  mov     r12, [rbp+2D0h+psz]
0x180028a23  jz      short loc_180028A2E
0x180028a25  test    r12, r12
0x180028a28  jnz     loc_180028FA2
0x180028a2e  mov     rcx, rdi; this
0x180028a31  mov     r14d, r13d
0x180028a34  call    ?ShouldCheckCacheExtension@COInetProt@@QEAAHXZ; COInetProt::ShouldCheckCacheExtension(void)
0x180028a39  test    eax, eax
0x180028a3b  jz      short loc_180028A5B
0x180028a3d  mov     rax, [rdi+0D0h]
0x180028a44  mov     rdx, r12
0x180028a47  mov     r8d, [rsp+3D0h+var_360]; unsigned int
0x180028a4c  test    rax, rax
0x180028a4f  cmovnz  rdx, rax; unsigned __int16 *
0x180028a53  call    ?CheckCacheExtension@COInetProt@@QEAAHPEBGK@Z; COInetProt::CheckCacheExtension(ushort const *,ulong)
0x180028a58  mov     r14d, eax
0x180028a5b  lea     rbx, [rdi+128h]
0x180028a62  mov     [rbp+2D0h+psz], r13
0x180028a66  mov     rcx, rbx; lpCriticalSection
0x180028a69  call    cs:__imp_EnterCriticalSection
0x180028a70  nop     dword ptr [rax+rax+00h]
0x180028a75  mov     rcx, [rdi+78h]
0x180028a79  test    rcx, rcx
  ... truncated ...
```
