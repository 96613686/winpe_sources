# COInetProt::OnDataReceived(ulong *,ulong *,ulong *)

- ea: `0x180021604`
- end: `0x18002298b`
- name: `?OnDataReceived@COInetProt@@QEAAJPEAK00@Z`
- size: `4999`
- prototype: `__int64 __fastcall(COInetProt *__hidden this, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005a6f0`

## callees

- `0x180008300`
- `0x1800150e0`
- `0x18001c470`
- `0x18001e160`
- `0x18001e340`
- `0x18001f9a0`
- `0x1800214d0`
- `0x1800215c0`
- `0x180021604`
- `0x180029298`
- `0x18002d5dc`
- `0x180030880`
- `0x18003b010`
- `0x18003f2b0`
- `0x180044b84`
- `0x180045a68`
- `0x1800478b0`
- `0x180049d20`
- `0x1800556d8`
- `0x18005cc7c`
- `0x18006d948`
- `0x1800701c0`
- `0x18007075c`
- `0x180080ad8`
- `0x1800853dc`
- `0x18008df68`
- `0x18009c8ac`
- `0x1800a5aac`
- `0x1800a5b1c`
- `0x1800f32c8`
- `0x1800f56bc`
- `0x1800f5838`
- `0x18011ba26`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800223d9`
- `msvcrt!memcpy_s` at `0x1800223d9`
- `iertutil!CreateUri` at `0x18002205b`
- `iertutil!CreateUri` at `0x18002205b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021d27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002225b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021d27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002225b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021d13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021d13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022302`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180021f1f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180021f1f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180021f0a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180021f0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021b6a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021c03`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021b6a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021c03`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002170c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002170c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022938`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002235d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180022615`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002235d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180022615`
- `OLEAUT32!__imp_SysFreeString` at `0x180022538`
- `OLEAUT32!__imp_SysFreeString` at `0x180022538`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x180021e52`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x180021e52`

## pseudocode

```c
__int64 __fastcall COInetProt::OnDataReceived(COInetProt *this, unsigned int *a2, unsigned int *a3, unsigned int *a4)
{
  int v4; // eax
  unsigned int *v5; // r12
  int v8; // ecx
  HRESULT Uri; // r13d
  __int64 v10; // rdx
  int v11; // esi
  HRESULT v12; // eax
  int v13; // edx
  int v14; // esi
  unsigned int v15; // esi
  int v16; // eax
  void *v17; // r14
  BOOL v18; // ebx
  unsigned int *v19; // r9
  unsigned int v20; // r11d
  unsigned int v21; // esi
  char v22; // al
  int v23; // ecx
  __int64 v24; // rsi
  CFeatureCache *v25; // rcx
  int v26; // ebx
  __int64 v27; // rsi
  char v28; // r14
  unsigned int v29; // eax
  int IsFeatureEnabledInternal; // eax
  bool v31; // zf
  __int64 v32; // rdx
  const unsigned __int16 *v33; // rsi
  int v34; // ecx
  char *v35; // rax
  char *v36; // r12
  int v37; // r15d
  __int64 v38; // rcx
  OLECHAR *v39; // rbx
  int v40; // r15d
  int v41; // r14d
  const unsigned __int16 *MimeFromData; // rax
  int v43; // r12d
  __int64 v44; // rbx
  int v45; // eax
  bool v46; // zf
  wchar_t *v47; // r15
  unsigned int v48; // ebx
  int v49; // eax
  int v50; // esi
  bool v51; // sf
  unsigned int cchCount2; // eax
  const wchar_t *v53; // rsi
  int v54; // eax
  int v55; // r14d
  __int64 v56; // rdx
  int v57; // eax
  int v58; // esi
  void (__fastcall ***v59)(_QWORD, GUID *, STRSAFE_PCNZWCH *); // rcx
  int v60; // eax
  __int64 v61; // rdx
  STRSAFE_PCNZWCH v62; // rcx
  unsigned int *v63; // rbx
  unsigned int v64; // eax
  size_t v66; // rsi
  const unsigned __int16 *v67; // rdx
  LPWSTR ExtensionW; // rax
  unsigned int v69; // ecx
  unsigned int v70; // edx
  _QWORD *ThreadLocalStoragePointer; // rax
  BOOL v72; // ebx
  int v73; // eax
  const unsigned __int16 *v74; // r14
  int v75; // eax
  wchar_t *v76; // r15
  unsigned __int16 *v77; // r12
  const unsigned __int16 *v78; // rcx
  const unsigned __int16 **v79; // rbx
  int v80; // eax
  int v81; // ecx
  int v82; // eax
  unsigned int v83; // ecx
  unsigned int v84; // edx
  unsigned int v85; // eax
  char v86; // si
  size_t v87; // rcx
  void *v88; // rcx
  void (__fastcall ***v89)(_QWORD, GUID *, size_t *); // rcx
  unsigned int v90; // ebx
  void *v91; // rax
  void *v92; // rsi
  HRESULT v93; // eax
  int v94; // ecx
  int v95; // edx
  unsigned int v96; // edx
  unsigned int v97; // eax
  char v98; // al
  rsize_t v99; // rdx
  void *v100; // rcx
  const unsigned __int16 **v101; // rbx
  void *v102; // rcx
  const unsigned __int16 *v103; // r8
  const unsigned __int16 *v104; // r8
  unsigned __int16 *v105; // rdx
  int v106; // r8d
  int v107; // r9d
  int v108; // eax
  __int64 v109; // r8
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // rax
  int v113; // eax
  unsigned __int64 v114; // rsi
  unsigned __int16 *v115; // rax
  unsigned __int16 *v116; // rbx
  const unsigned __int16 *v117; // r8
  unsigned int v118; // eax
  bool v119[4]; // [rsp+60h] [rbp-A0h] BYREF
  int cchCount1; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v121; // [rsp+68h] [rbp-98h] BYREF
  int v122; // [rsp+6Ch] [rbp-94h]
  unsigned int v123; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v124; // [rsp+74h] [rbp-8Ch] BYREF
  int v125; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v126; // [rsp+80h] [rbp-80h]
  unsigned int *v127; // [rsp+88h] [rbp-78h]
  int v128; // [rsp+90h] [rbp-70h] BYREF
  int v129; // [rsp+94h] [rbp-6Ch] BYREF
  void **v130; // [rsp+98h] [rbp-68h] BYREF
  __int64 v131; // [rsp+A0h] [rbp-60h]
  int v132; // [rsp+A8h] [rbp-58h]
  BSTR bstrString[2]; // [rsp+B0h] [rbp-50h]
  int v134; // [rsp+C0h] [rbp-40h]
  STRSAFE_PCNZWCH psz[2]; // [rsp+C8h] [rbp-38h] BYREF
  size_t pcchLength[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int Size; // [rsp+F0h] [rbp-10h] BYREF
  size_t Size_4; // [rsp+F4h] [rbp-Ch] BYREF
  void *v139; // [rsp+F8h] [rbp-8h]
  STGMEDIUM v140; // [rsp+100h] [rbp+0h] BYREF
  void *v141; // [rsp+120h] [rbp+20h]
  __int64 v142; // [rsp+160h] [rbp+60h]
  CHAR MultiByteStr[16]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v144; // [rsp+180h] [rbp+80h]
  __int64 v145; // [rsp+190h] [rbp+90h]
  char v146; // [rsp+198h] [rbp+98h]
  int v147; // [rsp+1B0h] [rbp+B0h]
  __int128 v148; // [rsp+1B4h] [rbp+B4h]
  __int128 v149; // [rsp+1C4h] [rbp+C4h]
  __int128 v150; // [rsp+1D4h] [rbp+D4h]
  int v151; // [rsp+1E4h] [rbp+E4h]

  v4 = *((_DWORD *)this + 46);
  v5 = a3;
  v126 = a4;
  v127 = a3;
  if ( (v4 & 0x100) != 0 )
  {
    Uri = 2;
    goto LABEL_100;
  }
  v8 = *((_DWORD *)this + 37);
  Uri = 0;
  if ( (v8 & 0x230) != 0 && ((v4 & 2) == 0 || (v4 & 0x40) != 0) || (v8 & 0x200) != 0 && (v4 & 0x200) == 0 )
  {
    v10 = *((unsigned int *)this + 42);
    v11 = 0;
    v122 = 0;
    v125 = 0;
    if ( (unsigned int)v10 >= *((_DWORD *)this + 43) )
      goto LABEL_95;
    do
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 14) + 72LL))(
              *((_QWORD *)this + 14),
              *((_QWORD *)this + 19) + v10,
              (unsigned int)(*((_DWORD *)this + 40) - v10),
              &v125);
      v13 = v125;
      Uri = v12;
      v14 = *((_DWORD *)this + 42);
      *((_DWORD *)this + 41) += v125;
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
      v17 = (void *)*((_QWORD *)this + 19);
      v18 = 0;
      InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
      if ( !byte_18015DE34 && v15 )
        v18 = IsDocFile(v17, v15) == 0;
      *((_DWORD *)this + 46) &= ~1u;
      *((_DWORD *)this + 46) |= v18;
      v16 = *((_DWORD *)this + 46);
    }
    v19 = v126;
    v20 = *v126;
    if ( *v126 )
    {
      if ( v20 <= *((_DWORD *)this + 40) )
        goto LABEL_15;
      v21 = *v126;
    }
    else
    {
      v21 = 0;
    }
    if ( (v16 & 1) != 0 )
    {
      v90 = 4096;
    }
    else
    {
      v22 = IsXmlProlog(*((_QWORD *)this + 19), *((unsigned int *)this + 42));
      v19 = v126;
      if ( !v22 )
        goto LABEL_15;
      v90 = 512;
      v20 = v21;
    }
    if ( *((_DWORD *)this + 40) < v90 )
    {
      v91 = operator new(v90);
      v92 = v91;
      if ( v91 )
      {
        memcpy_s(v91, v90, *((const void *const *)this + 19), *((unsigned int *)this + 42));
        operator delete(*((void **)this + 19));
        *((_QWORD *)this + 19) = v92;
        *((_DWORD *)this + 40) = v90;
        if ( !Uri )
        {
          do
          {
            v93 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 14) + 72LL))(
                    *((_QWORD *)this + 14),
                    *((_QWORD *)this + 19) + *((unsigned int *)this + 42),
                    v90 - *((_DWORD *)this + 42),
                    &v125);
            v94 = v125;
            Uri = v93;
            v95 = *((_DWORD *)this + 42);
            *((_DWORD *)this + 41) += v125;
            v96 = v94 + v95;
            *((_DWORD *)this + 45) += v94;
            *((_DWORD *)this + 42) = v96;
            if ( v93 )
              break;
            v90 = *((_DWORD *)this + 40);
          }
          while ( v96 < v90 );
        }
      }
      v19 = v126;
      v97 = *v126;
      if ( !*v126 || v97 >= *((_DWORD *)this + 40) )
        v97 = *((_DWORD *)this + 40);
      *((_DWORD *)this + 43) = v97;
      v20 = *v19;
    }
LABEL_15:
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
        v85 = *((_DWORD *)this + 41);
        *v19 = v85;
        *v5 = v85;
        v122 = 1;
        goto LABEL_19;
      }
LABEL_18:
      v11 = v122;
LABEL_19:
      v23 = *((_DWORD *)this + 46);
      if ( (v23 & 2) != 0 || *v5 < *((_DWORD *)this + 43) && Uri != 1 )
        goto LABEL_95;
      v24 = *((_QWORD *)this + 17);
      v25 = (CFeatureCache *)(v23 | 2u);
      v31 = *((_QWORD *)this + 24) == 0;
      *((_DWORD *)this + 46) = (_DWORD)v25;
      v26 = v31;
      psz[0] = 0;
      v129 = 0;
      v124 = 0;
      v128 = 0;
      if ( v24 )
      {
        memset_0(&Size_4, 0, 0x7Cu);
        Size = 128;
        if ( (*(int (__fastcall **)(__int64, int *, unsigned int *, unsigned int *, int *))(*(_QWORD *)(v24 + 16) + 40LL))(
               v24 + 16,
               &v129,
               &Size,
               &v124,
               &v128) >= 0 )
        {
          v66 = Size;
          if ( Size )
          {
            if ( Size >= 0x78 && v142 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v142 + 16LL))(v142);
            if ( v139 )
              operator delete(v139);
            if ( v141 )
              operator delete(v141);
            ReleaseStgMedium(&v140);
            memset_0(&Size, 0, v66);
            Size = v66;
          }
          if ( *((_QWORD *)this + 26) && (v124 & 0x80000000) == 0 )
            v26 |= 8u;
        }
      }
      v27 = *((_QWORD *)this + 28);
      v28 = 3;
      v121 = 3;
      if ( g_pFeatureCache )
      {
        if ( !CFeatureCache::IsFeatureEnabled(v25, FEATURE_MIME_SNIFFING) )
        {
LABEL_24:
          v29 = 0;
LABEL_25:
          v121 = v29;
LABEL_32:
          v31 = (v29 & 0xF) == 0;
          goto LABEL_33;
        }
      }
      else
      {
        IsFeatureEnabledInternal = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING);
        if ( IsFeatureEnabledInternal < 0 )
          goto LABEL_145;
        if ( IsFeatureEnabledInternal == 1 )
          goto LABEL_24;
      }
      if ( !v27 )
      {
        v29 = 3;
        goto LABEL_25;
      }
      if ( (int)EnsureSecurityManager() >= 0
        && ((int (__fastcall *)(struct IInternetSecurityManagerEx2 *, __int64, __int64, unsigned int *, int, _QWORD, _DWORD, int, _QWORD, _QWORD))g_pInternetSecurityManagerEx2->lpVtbl->ProcessUrlActionEx2)(
             g_pInternetSecurityManagerEx2,
             v27,
             8448,
             &v121,
             4,
             0,
             0,
             1,
             0,
             0) >= 0 )
      {
        LOBYTE(v29) = v121;
        goto LABEL_32;
      }
      v121 = 3;
LABEL_145:
      v31 = (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING) == 1;
LABEL_33:
      if ( v31 )
        v26 |= 2u;
      if ( (v124 & 0x2000000) != 0 )
      {
        v26 |= 0x10u;
      }
      else if ( (v26 & 2) == 0 )
      {
        v26 |= 4u;
      }
      v32 = *((unsigned int *)this + 46);
      v33 = (const unsigned __int16 *)*((_QWORD *)this + 24);
      v34 = v26 | 0x40;
      v35 = (char *)*((_QWORD *)this + 19);
      v123 = 0;
      v36 = v35;
      if ( (v32 & 0x10) == 0 )
        v34 = v26;
      v37 = v34 | 0x80;
      if ( (v32 & 0x20) == 0 )
        v37 = v34;
      v38 = 2147500037LL;
      cchCount1 = v37;
      if ( v33 || (v33 = (const unsigned __int16 *)*((_QWORD *)this + 33)) != 0 || v35 )
      {
        v39 = (OLECHAR *)*((_QWORD *)this + 25);
        if ( v35 || v39 )
        {
          v40 = *((_DWORD *)this + 42);
          pcchLength[0] = 0;
          Uri = -2147467259;
          if ( v39 )
          {
            v41 = _AllocString<CTCoAllocPolicy>(2147500037LL, v32, v39, pcchLength);
            if ( v41 >= 0 )
              v39 = (OLECHAR *)pcchLength[0];
          }
          else
          {
            v41 = -2147467259;
          }
          v145 = 0;
          v146 = 0;
          v147 = 0;
          v151 = 0;
          *(_OWORD *)MultiByteStr = 0;
          v144 = 0;
          v148 = 0;
          v149 = 0;
          v150 = 0;
          MimeFromData = CContentAnalyzer::FindMimeFromData(
                           (CContentAnalyzer *)MultiByteStr,
                           v33,
                           v36,
                           v40,
                           v39,
                           cchCount1,
                           &v123);
          if ( MimeFromData )
          {
            psz[0] = OLESTRDuplicate(MimeFromData);
            Uri = psz[0] == 0 ? 0x8007000E : 0;
          }
          if ( v41 >= 0 )
            CoTaskMemFree(v39);
          LOBYTE(v37) = cchCount1;
          v43 = -2147467259;
          v28 = 3;
        }
        else
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          cchCount1 = 260;
          if ( dword_1801656B0 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
          {
            Init_thread_header(&dword_1801656B0);
            if ( dword_1801656B0 == -1 )
            {
              dwFlags = HelperAddUriDefaultFlags(0x3002B80u, 5u);
              Init_thread_footer(&dword_1801656B0);
            }
          }
          v130 = &CUString::`vftable';
          pcchLength[0] = 0;
          v131 = 0;
          v132 = 11;
          *(_OWORD *)bstrString = 0;
          v134 = 0;
          Uri = CreateUri(v33, dwFlags, 0, (IUri **)pcchLength);
          if ( Uri < 0 )
          {
            v43 = -2147467259;
          }
          else
          {
            if ( !(unsigned int)CUString::Set((CUString *)&v130, (struct IUri *)pcchLength[0], Uri_PROPERTY_EXTENSION)
              && bstrString[1] )
            {
              Uri = GetMimeFromExt(bstrString[1], (unsigned __int16 *)MultiByteStr, (unsigned int *)&cchCount1);
              v43 = -2147467259;
            }
            else
            {
              v43 = -2147467259;
              Uri = -2147467259;
            }
            (*(void (__fastcall **)(size_t))(*(_QWORD *)pcchLength[0] + 16LL))(pcchLength[0]);
            if ( Uri >= 0 )
            {
              psz[0] = OLESTRDuplicate((const unsigned __int16 *)MultiByteStr);
              if ( psz[0] )
              {
                v123 = 2;
                Uri = 0;
              }
              else
              {
                Uri = -2147024882;
              }
            }
          }
          v38 = v131;
          v130 = &CUString::`vftable';
          v72 = v131 != 0;
          if ( v131 || v132 != 11 )
          {
            if ( bstrString[0] )
            {
              SysFreeString(bstrString[0]);
              v38 = v131;
              bstrString[0] = 0;
            }
            bstrString[1] = 0;
            v134 = 0;
            if ( v72 && v38 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              v131 = 0;
            }
          }
          v132 = 11;
        }
        if ( !Uri && v123 == 4 )
        {
          if ( *((_QWORD *)this + 17) )
          {
            if ( *((_QWORD *)this + 24) )
            {
              if ( (v37 & 0x10) != 0 )
              {
                v38 = *((_QWORD *)this + 25);
                if ( v38 )
                {
                  if ( !StrCmpICW((LPCWSTR)v38, L"text/plain") )
                  {
                    ExtensionW = PathFindExtensionW(*((LPCWSTR *)this + 24));
                    if ( ExtensionW )
                    {
                      if ( *ExtensionW == 46 && !(unsigned int)StrCmpNIIW(ExtensionW, L".txt", 4u) )
                      {
                        v119[0] = 0;
                        COInetProt::SafeReportProgressToProtocolSink(this, 0x3Eu, 0, v119);
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
        v43 = -2147467259;
      }
      v44 = *((_QWORD *)this + 28);
      cchCount1 = 3;
      if ( g_pFeatureCache )
      {
        if ( !CFeatureCache::IsFeatureEnabled((CFeatureCache *)v38, FEATURE_MIME_SNIFFING) )
        {
LABEL_55:
          v28 = 0;
LABEL_62:
          v46 = (v28 & 0xF) == 0;
LABEL_63:
          v47 = (wchar_t *)psz[0];
          if ( !v46 && psz[0] )
          {
            v48 = 10;
            psz[0] = 0;
            pcchLength[0] = 0;
            cchCount1 = 0;
            v121 = 0;
            if ( StringLengthWorkerW(v47, 0xAu, (size_t *)psz) < 0
              || (v49 = LongLongToULong((__int64)psz[0], (unsigned int *)&cchCount1), v50 = cchCount1, v49 < 0) )
            {
              v50 = 10;
            }
            if ( StringLengthWorkerW(L"text/plain", 0xAu, pcchLength) < 0
              || (v51 = (int)LongLongToULong(pcchLength[0], &v121) < 0, cchCount2 = v121, v51) )
            {
              cchCount2 = 10;
            }
            if ( CompareStringW(0x7Fu, 0x1001u, v47, v50, L"text/plain", cchCount2) != 2 )
            {
              v53 = (const wchar_t *)*((_QWORD *)this + 25);
              if ( v53 )
              {
                psz[0] = 0;
                pcchLength[0] = 0;
                cchCount1 = 0;
                v121 = 0;
                if ( StringLengthWorkerW(v53, 0xAu, (size_t *)psz) < 0
                  || (v54 = LongLongToULong((__int64)psz[0], (unsigned int *)&cchCount1), v55 = cchCount1, v54 < 0) )
                {
                  v55 = 10;
                }
                if ( StringLengthWorkerW(L"text/plain", 0xAu, pcchLength) >= 0
                  && (int)LongLongToULong(pcchLength[0], &v121) >= 0 )
                {
                  v48 = v121;
                }
                if ( CompareStringW(0x7Fu, 0x1001u, v53, v55, L"text/plain", v48) == 2 )
                {
                  v56 = *((_QWORD *)this + 17);
                  if ( v56 )
                  {
                    v98 = *(_BYTE *)(v56 + 440);
                    if ( (v98 & 1) != 0 )
                    {
                      *(_BYTE *)(v56 + 440) = v98 & 0xFE;
                    }
                    else
                    {
                      operator delete(v47);
                      v47 = OLESTRDuplicate(*((const unsigned __int16 **)this + 25));
                      v119[0] = 0;
                      *(_BYTE *)(*((_QWORD *)this + 17) + 440LL) |= 2u;
                      COInetProt::SafeReportProgressToProtocolSink(this, 0x32u, v47, v119);
                    }
                  }
                  else
                  {
                    operator delete(v47);
                    v47 = OLESTRDuplicate(*((const unsigned __int16 **)this + 25));
                  }
                }
              }
            }
          }
          v57 = *((_DWORD *)this + 46);
          v58 = 0;
          if ( (v57 & 0x800) != 0
            && (v57 & 0x1000) == 0
            && (v57 & 0x2000) == 0
            && (v57 & 0x4000) == 0
            && (v57 & 0x10000) != 0 )
          {
            v67 = v47;
            if ( *((_QWORD *)this + 26) )
              v67 = (const unsigned __int16 *)*((_QWORD *)this + 26);
            v58 = COInetProt::CheckCacheExtension(this, v67, v123);
          }
          psz[0] = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
          v59 = (void (__fastcall ***)(_QWORD, GUID *, STRSAFE_PCNZWCH *))*((_QWORD *)this + 15);
          if ( v59 )
            (**v59)(v59, &GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b, psz);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
          v60 = *((_DWORD *)this + 46);
          v61 = 0x8000;
          if ( v58 || (v60 & 0x8000) == 0 )
          {
            v62 = psz[0];
            if ( !psz[0] )
            {
LABEL_92:
              if ( v47 )
              {
                pcchLength[0] = 0;
                v86 = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(pcchLength);
                pcchLength[0] = 0;
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
                v89 = (void (__fastcall ***)(_QWORD, GUID *, size_t *))*((_QWORD *)this + 15);
                if ( v89 )
                {
                  (**v89)(v89, &GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b, pcchLength);
                  v43 = 0;
                }
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
                if ( !v43 )
                {
                  v86 = 1;
                  (*(void (__fastcall **)(size_t, __int64, wchar_t *))(*(_QWORD *)pcchLength[0] + 32LL))(
                    pcchLength[0],
                    13,
                    v47);
                }
                v87 = pcchLength[0];
                if ( pcchLength[0] )
                {
                  pcchLength[0] = 0;
                  (*(void (__fastcall **)(size_t))(*(_QWORD *)v87 + 16LL))(v87);
                }
                if ( v86 )
                  *((_DWORD *)this + 46) |= 4u;
                v88 = (void *)*((_QWORD *)this + 25);
                if ( v88 )
                  CoTaskMemFree(v88);
                *((_QWORD *)this + 25) = v47;
              }
              if ( (*((_BYTE *)this + 184) & 1) == 0 )
                goto LABEL_94;
              if ( (*((_BYTE *)this + 148) & 0x20) == 0 )
                goto LABEL_94;
              v99 = *((unsigned int *)this + 42);
              v100 = (void *)*((_QWORD *)this + 19);
              *(_OWORD *)psz = 0;
              if ( (unsigned int)GetClassDocFileBuffer(v100, v99, (struct _GUID *)psz) )
                goto LABEL_94;
              v101 = (const unsigned __int16 **)((char *)this + 216);
              v102 = (void *)*((_QWORD *)this + 27);
              if ( v102 )
              {
                operator delete(v102);
                *v101 = 0;
              }
              StringFromCLSID((const IID *const)psz, (LPOLESTR *)this + 27);
              v103 = *v101;
              if ( *v101 )
              {
                v119[0] = 0;
                COInetProt::SafeReportProgressToProtocolSink(this, 0xCu, v103, v119);
                v5 = v127;
                v11 = v122;
                if ( v119[0] )
                  *((_DWORD *)this + 46) |= 0x400u;
              }
              else
              {
LABEL_94:
                v11 = v122;
                v5 = v127;
              }
LABEL_95:
              if ( (*((_DWORD *)this + 37) & 0x200) == 0 || (v73 = *((_DWORD *)this + 46), (v73 & 0x80u) != 0) )
              {
                v63 = v126;
LABEL_97:
                v64 = *v63;
                if ( *v63 && v64 < *v5 )
                  *v5 = v64;
                if ( Uri == 1 )
                  Uri = 0;
                goto LABEL_100;
              }
              v74 = (const unsigned __int16 *)*((_QWORD *)this + 26);
              if ( !v74 )
                v74 = (const unsigned __int16 *)*((_QWORD *)this + 25);
              v75 = v73 | 0x200;
              v123 = 0;
              *((_DWORD *)this + 46) = v75;
              v124 = 0;
              v76 = 0;
              psz[0] = 0;
              v77 = 0;
              *(_OWORD *)pcchLength = 0;
              if ( (v75 & 0x400) == 0 )
              {
                v104 = (const unsigned __int16 *)*((_QWORD *)this + 27);
                if ( v104 )
                {
                  v119[0] = 0;
                  COInetProt::SafeReportProgressToProtocolSink(this, 0xCu, v104, v119);
                  if ( v119[0] )
                    *((_DWORD *)this + 46) |= 0x400u;
                }
              }
              v78 = (const unsigned __int16 *)*((_QWORD *)this + 24);
              v79 = (const unsigned __int16 **)((char *)this + 264);
              if ( !v78 )
                v78 = *v79;
              v80 = IsHandlerAvailable(
                      v78,
                      v74,
                      (struct _GUID *)pcchLength,
                      *((unsigned __int8 **)this + 19),
                      *((_DWORD *)this + 42));
              v81 = *((_DWORD *)this + 46);
              if ( !v80 )
              {
                v81 |= 0x80u;
                *((_DWORD *)this + 46) = v81;
                goto LABEL_170;
              }
              if ( (v81 & 1) == 0 )
              {
LABEL_170:
                if ( (v81 & 0x40) != 0 || (v81 & 0x80u) != 0 || (v81 & 1) == 0 )
                {
LABEL_171:
                  if ( v76 )
                    CoTaskMemFree(v76);
                  goto LABEL_173;
                }
                if ( !v76 )
                {
LABEL_173:
                  if ( v77 )
                    operator delete(v77);
                  v82 = *((_DWORD *)this + 46);
                  v63 = v126;
                  if ( (v82 & 1) != 0 && (v82 & 0x80u) != 0 )
                  {
                    v118 = 2048;
                    if ( *v126 - 1 <= 0x7FE )
                      v118 = *v126;
                    *((_DWORD *)this + 43) = v118;
                    if ( *((_DWORD *)this + 42) >= v118 )
                      COInetProt::ReportCacheFileName(this, 0);
                  }
                  v83 = *((_DWORD *)this + 41);
                  v5 = v127;
                  v84 = *v127;
                  if ( *v127 <= v83 )
                    v84 = v83 + 1;
                  *v127 = v84;
                  goto LABEL_97;
                }
                psz[0] = 0;
                if ( !memcmp_0(pcchLength, &GUID_NULL, 0x10u) )
                {
                  if ( v74 && !(unsigned int)StrCmpNIIW(v74, L"application/octet-stream", 0x18u) )
                    *((_DWORD *)this + 46) |= 0x80u;
                }
                else
                {
                  StringFromCLSID((const IID *const)pcchLength, (LPOLESTR *)psz);
                }
                if ( *((char *)this + 184) < 0 || !psz[0] && !v74 )
                  goto LABEL_293;
                if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_RESTRICT_CDL) != 1 )
                {
                  if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
                    IECompatLogCDLRestrictions(0, 0, 1);
                  goto LABEL_293;
                }
                v109 = -1;
                do
                  ++v109;
                while ( v76[v109] );
                if ( psz[0] )
                {
                  v110 = -1;
                  do
                    ++v110;
                  while ( psz[0][v110] );
                }
                else
                {
                  LODWORD(v110) = 0;
                }
                if ( v74 )
                {
                  v111 = -1;
                  do
                    ++v111;
                  while ( v74[v111] );
                }
                else
                {
                  LODWORD(v111) = 0;
                }
                if ( v77 )
                {
                  v112 = -1;
                  do
                    ++v112;
                  while ( v77[v112] );
                  v113 = v112 + 1;
                }
                else
                {
                  v113 = 0;
                }
                v114 = (int)v110 + (int)v111 + (int)v109 + v113 + 3LL;
                v115 = (unsigned __int16 *)operator new(saturated_mul(v114, 2u));
                v116 = v115;
                if ( !v115 )
                {
LABEL_293:
                  operator delete((void *)psz[0]);
                  goto LABEL_171;
                }
                *v115 = 0;
                if ( *v76 )
                  StringCchCopyW(v115, v114, v76);
                StringCchCatW(v116, v114, L"?");
                v117 = psz[0];
                if ( !psz[0] )
                {
                  if ( !v74 )
                  {
LABEL_290:
                    if ( v77 )
                    {
                      StringCchCatW(v116, v114, L"?");
                      StringCchCatW(v116, v114, v77);
                    }
                    (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)this + 17) + 32LL))(
                      *((_QWORD *)this + 17),
                      23,
                      v116);
                    operator delete(v116);
                    *((_DWORD *)this + 46) |= 0x1C0u;
                    Uri = 2;
                    goto LABEL_293;
                  }
                  v117 = v74;
                }
                StringCchCatW(v116, v114, v117);
                goto LABEL_290;
              }
              if ( GetCodeBaseFromDocFile(
                     *((unsigned __int8 **)this + 19),
                     *((_DWORD *)this + 42),
                     (unsigned __int16 **)psz,
                     *v79,
                     &v123,
                     &v124) < 0 )
              {
                if ( *((_DWORD *)this + 42) < *((_DWORD *)this + 43) )
                {
                  v108 = 64;
                  if ( !v11 )
                    goto LABEL_251;
                }
              }
              else if ( v123 || v124 )
              {
                StringCchPrintfA(MultiByteStr, 0x104u, "%ld,%ld", v123, v124);
                v77 = WzA2WDynamic(MultiByteStr, v105, v106, v107);
              }
              v108 = 0;
LABEL_251:
              *((_DWORD *)this + 46) &= ~0x40u;
              *((_DWORD *)this + 46) |= v108;
              v81 = *((_DWORD *)this + 46);
              v76 = (wchar_t *)psz[0];
              goto LABEL_170;
            }
            if ( !*((_QWORD *)this + 24) )
            {
LABEL_90:
              if ( v62 )
              {
                psz[0] = 0;
                (*(void (__fastcall **)(STRSAFE_PCNZWCH, __int64))(*(_QWORD *)v62 + 16LL))(v62, v61);
              }
              goto LABEL_92;
            }
            *((_DWORD *)this + 46) = v60 | 0x8000;
            (*(void (__fastcall **)(STRSAFE_PCNZWCH, __int64))(*(_QWORD *)v62 + 32LL))(v62, 14);
          }
          v62 = psz[0];
          goto LABEL_90;
        }
      }
      else
      {
        v45 = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING);
        if ( v45 < 0 )
          goto LABEL_147;
        if ( v45 == 1 )
          goto LABEL_55;
      }
      if ( !v44 )
        goto LABEL_62;
      if ( (int)EnsureSecurityManager() >= 0
        && ((int (__fastcall *)(struct IInternetSecurityManagerEx2 *, __int64, __int64, int *, int, _QWORD, _DWORD, int, _QWORD, _QWORD))g_pInternetSecurityManagerEx2->lpVtbl->ProcessUrlActionEx2)(
             g_pInternetSecurityManagerEx2,
             v44,
             8448,
             &cchCount1,
             4,
             0,
             0,
             1,
             0,
             0) >= 0 )
      {
        v28 = cchCount1;
        goto LABEL_62;
      }
      cchCount1 = 3;
LABEL_147:
      v46 = (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING) == 1;
      goto LABEL_63;
    }
    v69 = *((_DWORD *)this + 41);
    v70 = *v5;
    if ( *v5 <= v69 )
      v70 = v69 + 1;
    if ( v20 && v70 > v20 )
      v70 = v20;
    *v5 = v70;
    goto LABEL_18;
  }
LABEL_100:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *((_DWORD *)this + 44) = *v5;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x180021604  push    rbp
0x180021606  push    rbx
0x180021607  push    rsi
0x180021608  push    rdi
0x180021609  push    r12
0x18002160b  push    r13
0x18002160d  push    r14
0x18002160f  push    r15
0x180021611  lea     rbp, [rsp-298h]
0x180021619  sub     rsp, 398h
0x180021620  mov     rax, cs:__security_cookie
0x180021627  xor     rax, rsp
0x18002162a  mov     [rbp+2D0h+var_50], rax
0x180021631  mov     eax, [rcx+0B8h]
0x180021637  mov     r12, r8
0x18002163a  mov     [rbp+2D0h+var_350], r9
0x18002163e  mov     r15, rdx
0x180021641  mov     [rbp+2D0h+var_348], r8
0x180021645  mov     rdi, rcx
0x180021648  bt      eax, 8
0x18002164c  jb      loc_180022368
0x180021652  mov     ecx, [rcx+94h]
0x180021658  xor     r14d, r14d
0x18002165b  mov     r13d, r14d
0x18002165e  test    ecx, 230h
0x180021664  jz      loc_18002237B
0x18002166a  test    al, 2
0x18002166c  jnz     loc_180022373
0x180021672  mov     edx, [rdi+0A8h]
0x180021678  mov     esi, r14d
0x18002167b  mov     ebx, 1
0x180021680  mov     [rsp+3D0h+var_364], r14d
0x180021685  mov     [rsp+3D0h+var_358], r14d
0x18002168a  cmp     edx, [rdi+0ACh]
0x180021690  jnb     loc_180021CE4
0x180021696  mov     rcx, [rdi+70h]
0x18002169a  lea     r9, [rsp+3D0h+var_358]
0x18002169f  mov     r8d, [rdi+0A0h]
0x1800216a6  sub     r8d, edx
0x1800216a9  add     rdx, [rdi+98h]
0x1800216b0  mov     rax, [rcx]
0x1800216b3  mov     rax, [rax+48h]
0x1800216b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216bc  mov     edx, [rsp+3D0h+var_358]
0x1800216c0  mov     r13d, eax
0x1800216c3  mov     esi, [rdi+0A8h]
0x1800216c9  add     [rdi+0A4h], edx
0x1800216cf  add     esi, edx
0x1800216d1  add     [rdi+0B4h], edx
0x1800216d7  mov     [rdi+0A8h], esi
0x1800216dd  test    eax, eax
0x1800216df  jz      loc_180021EB1
0x1800216e5  mov     eax, [rdi+0B8h]
0x1800216eb  test    bl, al
0x1800216ed  jnz     short loc_180021755
0x1800216ef  mov     r14, [rdi+98h]
0x1800216f6  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800216fd  xor     r9d, r9d; Context
0x180021700  lea     rcx, stru_18015EA38; InitOnce
0x180021707  xor     r8d, r8d; Parameter
0x18002170a  xor     ebx, ebx
0x18002170c  call    cs:__imp_InitOnceExecuteOnce
0x180021712  xor     eax, eax
0x180021714  cmp     cs:byte_18015DE34, al
0x18002171a  jnz     loc_180021D83
0x180021720  test    esi, esi
0x180021722  jz      loc_180021D83
0x180021728  mov     edx, esi; unsigned int
0x18002172a  mov     rcx, r14; void *
0x18002172d  call    ?IsDocFile@@YAJPEAXK@Z; IsDocFile(void *,ulong)
0x180021732  xor     r14d, r14d
0x180021735  test    eax, eax
0x180021737  lea     eax, [rbx+1]
0x18002173a  cmovz   ebx, eax
0x18002173d  and     dword ptr [rdi+0B8h], 0FFFFFFFEh
0x180021744  or      [rdi+0B8h], ebx
0x18002174a  mov     ebx, 1
0x18002174f  mov     eax, [rdi+0B8h]
0x180021755  mov     r9, [rbp+2D0h+var_350]
0x180021759  mov     r11d, [r9]
0x18002175c  test    r11d, r11d
0x18002175f  jnz     loc_180021D6E
0x180021765  mov     esi, r14d
0x180021768  test    bl, al
0x18002176a  jnz     loc_180022394
0x180021770  mov     edx, [rdi+0A8h]
0x180021776  mov     rcx, [rdi+98h]
0x18002177d  call    IsXmlProlog
0x180021782  mov     r9, [rbp+2D0h+var_350]
0x180021786  test    al, al
0x180021788  jnz     loc_18002239B
0x18002178e  cmp     r13d, 8000000Ah
0x180021795  jnz     loc_180021F8E
0x18002179b  mov     eax, [rdi+0ACh]
0x1800217a1  cmp     [rdi+0A8h], eax
0x1800217a7  jnb     loc_180021F97
0x1800217ad  mov     r13d, 2
0x1800217b3  mov     ebx, 1
0x1800217b8  mov     esi, [rsp+3D0h+var_364]
0x1800217bc  mov     ecx, [rdi+0B8h]
0x1800217c2  test    cl, 2
0x1800217c5  jnz     loc_180021CE4
0x1800217cb  mov     eax, [rdi+0ACh]
0x1800217d1  cmp     [r12], eax
0x1800217d5  jb      loc_18002248E
0x1800217db  mov     rsi, [rdi+88h]
0x1800217e2  or      ecx, 2; this
0x1800217e5  cmp     [rdi+0C0h], r14
0x1800217ec  mov     ebx, r14d
0x1800217ef  mov     [rdi+0B8h], ecx
0x1800217f5  setz    bl
0x1800217f8  mov     [rbp+2D0h+psz], r14
0x1800217fc  mov     [rbp+2D0h+var_33C], r14d
0x180021800  mov     [rsp+3D0h+var_35C], r14d
0x180021805  mov     [rbp+2D0h+var_340], r14d
0x180021809  test    rsi, rsi
0x18002180c  jnz     loc_180021DD7
0x180021812  mov     rsi, [rdi+0E0h]
0x180021819  xor     r13d, r13d
0x18002181c  cmp     cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA, r13; CFeatureCache * g_pFeatureCache
0x180021823  mov     r14d, 3
0x180021829  mov     [rsp+3D0h+var_368], r14d
0x18002182e  jz      short loc_180021848
0x180021830  mov     edx, r14d; enum _tagINTERNETFEATURELIST
0x180021833  call    ?IsFeatureEnabled@CFeatureCache@@QEAA_NW4_tagINTERNETFEATURELIST@@@Z; CFeatureCache::IsFeatureEnabled(_tagINTERNETFEATURELIST)
0x180021838  test    al, al
0x18002183a  jnz     short loc_180021861
0x18002183c  mov     eax, r13d
0x18002183f  mov     [rsp+3D0h+var_368], eax
0x180021843  jmp     loc_1800218C8
0x180021848  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING@FCK@@3VCFeatureControlKey@@A; this
0x18002184f  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180021854  test    eax, eax
0x180021856  js      loc_180021FC0
0x18002185c  cmp     eax, 1
0x18002185f  jz      short loc_18002183C
0x180021861  test    rsi, rsi
0x180021864  jz      loc_1800224C1
0x18002186a  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x18002186f  test    eax, eax
0x180021871  js      loc_180021FBB
0x180021877  mov     rcx, cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x18002187e  lea     r9, [rsp+3D0h+var_368]
0x180021883  mov     [rsp+3D0h+var_388], r13
0x180021888  mov     r8d, 2100h
0x18002188e  mov     [rsp+3D0h+var_390], r13
0x180021893  mov     rdx, rsi
0x180021896  mov     [rsp+3D0h+var_398], 1
0x18002189e  mov     rax, [rcx]
0x1800218a1  mov     dword ptr [rsp+3D0h+var_3A0], r13d
0x1800218a6  mov     qword ptr [rsp+3D0h+cchCount2], r13
0x1800218ab  mov     dword ptr [rsp+3D0h+lpString2], 4
0x1800218b3  mov     rax, [rax+68h]
0x1800218b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218bc  test    eax, eax
0x1800218be  js      loc_180021FBB
0x1800218c4  mov     eax, [rsp+3D0h+var_368]
0x1800218c8  test    al, 0Fh
0x1800218ca  jnz     short loc_1800218CF
0x1800218cc  or      ebx, 2
0x1800218cf  test    [rsp+3D0h+var_35C], 2000000h
0x1800218d7  jz      loc_180021DC6
0x1800218dd  or      ebx, 10h
0x1800218e0  mov     edx, [rdi+0B8h]
0x1800218e6  mov     ecx, ebx
0x1800218e8  mov     rsi, [rdi+0C0h]
0x1800218ef  or      ecx, 40h
0x1800218f2  mov     rax, [rdi+98h]
0x1800218f9  test    dl, 10h
0x1800218fc  mov     [rsp+3D0h+var_360], r13d
0x180021901  mov     r12, rax
0x180021904  cmovz   ecx, ebx
0x180021907  mov     r15d, ecx
0x18002190a  bts     r15d, 7
0x18002190f  test    dl, 20h
0x180021912  cmovz   r15d, ecx
0x180021916  mov     ecx, 80004005h
0x18002191b  mov     [rsp+3D0h+cchCount1], r15d
0x180021920  test    rsi, rsi
0x180021923  jz      loc_1800222C4
0x180021929  mov     rbx, [rdi+0C8h]
0x180021930  test    rax, rax
0x180021933  jz      loc_180021FED
0x180021939  mov     r15d, [rdi+0A8h]
0x180021940  xor     eax, eax
0x180021942  mov     [rbp+2D0h+pcchLength], rax
0x180021946  mov     r13d, ecx
0x180021949  test    rbx, rbx
0x18002194c  jnz     short loc_180021953
0x18002194e  mov     r14d, ecx
0x180021951  jmp     short loc_18002196D
0x180021953  lea     r9, [rbp+2D0h+pcchLength]
0x180021957  mov     r8, rbx
0x18002195a  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18002195f  mov     r14d, eax
0x180021962  xor     eax, eax
0x180021964  test    r14d, r14d
0x180021967  jns     loc_180021F85
0x18002196d  xorps   xmm0, xmm0
0x180021970  mov     [rbp+2D0h+var_240], rax
0x180021977  mov     [rbp+2D0h+var_238], al
0x18002197d  lea     rcx, [rbp+2D0h+MultiByteStr]; this
0x180021981  mov     [rbp+2D0h+var_220], eax
0x180021987  mov     r9d, r15d; int
0x18002198a  xor     eax, eax
0x18002198c  mov     r8, r12; char *
0x18002198f  mov     [rbp+2D0h+var_1EC], eax
0x180021995  mov     rdx, rsi; unsigned __int16 *
0x180021998  lea     rax, [rsp+3D0h+var_360]
0x18002199d  mov     [rsp+3D0h+var_3A0], rax; unsigned int *
0x1800219a2  mov     eax, [rsp+3D0h+cchCount1]
0x1800219a6  mov     [rsp+3D0h+cchCount2], eax; unsigned int
0x1800219aa  mov     [rsp+3D0h+lpString2], rbx; unsigned __int16 *
0x1800219af  movups  xmmword ptr [rbp+2D0h+MultiByteStr], xmm0
0x1800219b3  movups  [rbp+2D0h+var_250], xmm0
0x1800219ba  movups  [rbp+2D0h+var_21C], xmm0
0x1800219c1  movups  [rbp+2D0h+var_20C], xmm0
0x1800219c8  movups  [rbp+2D0h+var_1FC], xmm0
0x1800219cf  call    ?FindMimeFromData@CContentAnalyzer@@QEAAPEBGPEBGPEADHPEAGKPEAK@Z; CContentAnalyzer::FindMimeFromData(ushort const *,char *,int,ushort *,ulong,ulong *)
0x1800219d4  xor     esi, esi
0x1800219d6  test    rax, rax
0x1800219d9  jz      short loc_1800219F7
0x1800219db  mov     rcx, rax; unsigned __int16 *
0x1800219de  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x1800219e3  mov     [rbp+2D0h+psz], rax
0x1800219e7  mov     r13d, 8007000Eh
0x1800219ed  neg     rax
0x1800219f0  sbb     edx, edx
0x1800219f2  not     edx
0x1800219f4  and     r13d, edx
0x1800219f7  test    r14d, r14d
0x1800219fa  js      short loc_180021A05
0x1800219fc  mov     rcx, rbx; pv
0x1800219ff  call    cs:__imp_CoTaskMemFree
0x180021a05  mov     r15d, [rsp+3D0h+cchCount1]
0x180021a0a  mov     r12d, 80004005h
0x180021a10  mov     r14d, 3
0x180021a16  test    r13d, r13d
0x180021a19  jz      loc_180021EC4
0x180021a1f  cmp     cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA, rsi; CFeatureCache * g_pFeatureCache
0x180021a26  mov     rbx, [rdi+0E0h]
0x180021a2d  mov     [rsp+3D0h+cchCount1], r14d
0x180021a32  jz      short loc_180021A45
0x180021a34  mov     edx, r14d; enum _tagINTERNETFEATURELIST
0x180021a37  call    ?IsFeatureEnabled@CFeatureCache@@QEAA_NW4_tagINTERNETFEATURELIST@@@Z; CFeatureCache::IsFeatureEnabled(_tagINTERNETFEATURELIST)
0x180021a3c  test    al, al
0x180021a3e  jnz     short loc_180021A5E
0x180021a40  mov     r14d, esi
0x180021a43  jmp     short loc_180021AC1
0x180021a45  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING@FCK@@3VCFeatureControlKey@@A; this
0x180021a4c  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180021a51  test    eax, eax
0x180021a53  js      loc_180021FD9
0x180021a59  cmp     eax, 1
0x180021a5c  jz      short loc_180021A40
0x180021a5e  test    rbx, rbx
0x180021a61  jz      short loc_180021AC1
0x180021a63  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x180021a68  test    eax, eax
0x180021a6a  js      loc_180021FD4
0x180021a70  mov     rcx, cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x180021a77  lea     r9, [rsp+3D0h+cchCount1]
0x180021a7c  mov     [rsp+3D0h+var_388], rsi
0x180021a81  mov     r8d, 2100h
0x180021a87  mov     [rsp+3D0h+var_390], rsi
0x180021a8c  mov     rdx, rbx
0x180021a8f  mov     [rsp+3D0h+var_398], 1
0x180021a97  mov     rax, [rcx]
0x180021a9a  mov     dword ptr [rsp+3D0h+var_3A0], esi
0x180021a9e  mov     qword ptr [rsp+3D0h+cchCount2], rsi
0x180021aa3  mov     dword ptr [rsp+3D0h+lpString2], 4
0x180021aab  mov     rax, [rax+68h]
0x180021aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ab4  test    eax, eax
0x180021ab6  js      loc_180021FD4
0x180021abc  mov     r14d, [rsp+3D0h+cchCount1]
0x180021ac1  test    r14b, 0Fh
0x180021ac5  mov     r15, [rbp+2D0h+psz]
0x180021ac9  jz      loc_180021C3A
0x180021acf  xor     r14d, r14d
0x180021ad2  test    r15, r15
0x180021ad5  jz      loc_180021C3D
0x180021adb  lea     ebx, [r14+0Ah]
0x180021adf  mov     [rbp+2D0h+psz], r14
0x180021ae3  mov     edx, ebx; cchMax
0x180021ae5  mov     [rbp+2D0h+pcchLength], r14
0x180021ae9  lea     r8, [rbp+2D0h+psz]; pcchLength
0x180021aed  mov     [rsp+3D0h+cchCount1], r14d
0x180021af2  mov     rcx, r15; psz
0x180021af5  mov     [rsp+3D0h+var_368], r14d
0x180021afa  call    StringLengthWorkerW
0x180021aff  test    eax, eax
0x180021b01  js      short loc_180021B19
0x180021b03  mov     rcx, [rbp+2D0h+psz]; __int64
0x180021b07  lea     rdx, [rsp+3D0h+cchCount1]; unsigned int *
0x180021b0c  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180021b11  mov     esi, [rsp+3D0h+cchCount1]
0x180021b15  test    eax, eax
0x180021b17  jns     short loc_180021B1B
0x180021b19  mov     esi, ebx
  ... truncated ...
```
