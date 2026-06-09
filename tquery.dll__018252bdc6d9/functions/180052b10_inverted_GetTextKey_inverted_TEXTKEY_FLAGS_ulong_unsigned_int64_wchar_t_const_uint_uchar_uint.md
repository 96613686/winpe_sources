# inverted::GetTextKey(inverted::TEXTKEY_FLAGS,ulong,unsigned __int64,wchar_t const *,uint,uchar *,uint *)

- ea: `0x180052b10`
- end: `0x180053abc`
- name: `?GetTextKey@inverted@@YAXW4TEXTKEY_FLAGS@1@K_KPEB_WIPEAEPEAI@Z`
- size: `4012`
- prototype: `void __high(enum inverted::TEXTKEY_FLAGS, unsigned int, unsigned __int64, const wchar_t *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `4`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800517e0`
- `0x180089e58`
- `0x1800ab000`
- `0x18017ae68`

## callees

- `0x180038f08`
- `0x180052b10`
- `0x180053ac4`
- `0x180054178`
- `0x18005492c`
- `0x180055618`
- `0x18008a284`
- `0x1800bd230`
- `0x1800bd388`
- `0x1800d99b4`
- `0x1800d9e90`
- `0x1801134cc`
- `0x180147154`
- `0x18015708c`
- `0x18015eee4`
- `0x180188d74`
- `0x180188d90`
- `0x180189260`
- `0x180189280`
- `0x18018940c`
- `0x180189474`
- `0x1801895b0`
- `0x180189cce`
- `0x18018a0e1`
- `0x18018a123`
- `0x18018e778`
- `0x18018e8cb`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180053046`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180053046`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800535d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800535d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053646`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005377b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005377b`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x180053473`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x1800536ec`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x180053473`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x1800536ec`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180052c15`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180053546`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18005357d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180052c15`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180053546`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18005357d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053165`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053769`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800539ca`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053165`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053769`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800539ca`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180053117`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180053117`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180052f76`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180052f76`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530e8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530e8`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180052b93`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180053098`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18005369e`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180052b93`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180053098`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18005369e`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x180052fab`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x180052fab`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180052f37`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180052f37`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18005361f`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18005361f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall inverted::GetTextKey(
        char a1,
        LCID a2,
        unsigned __int64 a3,
        const WCHAR *a4,
        unsigned int Size,
        WCHAR *a6,
        unsigned int *a7)
{
  unsigned __int64 v7; // r13
  __int64 result; // rax
  char v10; // r12
  char v11; // si
  char v12; // r14
  __int64 v13; // rcx
  unsigned int v14; // edi
  WCHAR *v15; // rbx
  int v16; // eax
  int v17; // esi
  DWORD v18; // esi
  __int64 v19; // rcx
  unsigned int *v20; // rax
  unsigned int *v21; // rsi
  DWORD v22; // eax
  unsigned __int64 v23; // rsi
  _WORD *v24; // rax
  WCHAR *v25; // rcx
  __int64 v26; // r9
  LPCWSTR v27; // rax
  WCHAR v28; // dx
  unsigned __int64 v29; // rsi
  int v30; // edx
  const WCHAR *v31; // r10
  int v32; // eax
  int v33; // ecx
  unsigned __int64 v34; // rcx
  LPCWSTR v35; // rdx
  WCHAR *v36; // r8
  __int64 v37; // r9
  __int64 v38; // r11
  WCHAR v39; // ax
  __int64 v40; // r11
  bool v41; // cf
  bool v42; // zf
  HRESULT Services; // esi
  __int64 v44; // r8
  int v45; // ecx
  int v46; // r14d
  bool v47; // zf
  PWSTR v48; // rax
  int v49; // esi
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rsi
  const WCHAR *v52; // r12
  LCID v53; // r14d
  const WCHAR *v54; // rsi
  const unsigned __int16 *v55; // r8
  unsigned int v56; // r13d
  const WCHAR *v57; // r13
  WCHAR *v58; // rdx
  int Error; // ecx
  unsigned int v60; // eax
  unsigned int v61; // r8d
  LPWSTR v62; // r9
  unsigned int v63; // ecx
  int v64; // r11d
  char v65; // r12
  char v66; // dl
  int v67; // edx
  unsigned int v68; // r10d
  unsigned int j; // ecx
  LPWSTR v70; // r11
  unsigned int v71; // r9d
  unsigned int v72; // edx
  unsigned int v73; // r13d
  char v74; // cl
  char v75; // r12
  int v76; // r10d
  signed int v77; // r12d
  void *v78; // rcx
  void *v79; // rdi
  __int64 v80; // rcx
  int v81; // r10d
  char v82; // cl
  __int64 v83; // rdx
  const char *v84; // r9
  unsigned int v85; // eax
  const char *v86; // r9
  unsigned int v87; // eax
  const char *v88; // r9
  unsigned int v89; // ecx
  const char *v90; // r9
  const WCHAR *v91; // r12
  unsigned int v92; // eax
  signed int LastError; // eax
  int v94; // edx
  int v95; // r9d
  __int64 v96; // rcx
  unsigned int v97; // r14d
  int v98; // esi
  char v99; // dl
  char v100; // al
  inverted::CLocaleNameCache *v101; // rax
  const WCHAR *LocaleName; // rax
  int SearchKey; // eax
  unsigned __int8 *v104; // r12
  unsigned int v105; // edi
  inverted::CLocaleNameCache *v106; // rax
  const WCHAR *v107; // rax
  int v108; // eax
  unsigned int v109; // eax
  WCHAR *v110; // rdx
  WCHAR *v111; // rax
  int v112; // ecx
  LPWSTR v113; // r13
  signed __int32 v114[8]; // [rsp+0h] [rbp-100h] BYREF
  LPWSTR lpDestStr; // [rsp+20h] [rbp-E0h]
  char v116; // [rsp+50h] [rbp-B0h]
  int v117; // [rsp+54h] [rbp-ACh]
  char v118; // [rsp+58h] [rbp-A8h]
  LPCWSTR pszText; // [rsp+60h] [rbp-A0h] BYREF
  int SearchKeyFlags; // [rsp+68h] [rbp-98h]
  int v121; // [rsp+6Ch] [rbp-94h]
  LCID Locale; // [rsp+70h] [rbp-90h]
  unsigned int v123; // [rsp+74h] [rbp-8Ch]
  LPCWSTR v124; // [rsp+78h] [rbp-88h]
  DWORD dwMapFlags; // [rsp+80h] [rbp-80h]
  LPCWSTR lpSrcStr; // [rsp+88h] [rbp-78h]
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v128; // [rsp+98h] [rbp-68h]
  unsigned __int64 v129; // [rsp+A0h] [rbp-60h]
  LPCWSTR v130; // [rsp+A8h] [rbp-58h]
  _MAPPING_ENUM_OPTIONS pOptions; // [rsp+B0h] [rbp-50h] BYREF
  _MAPPING_PROPERTY_BAG pbag; // [rsp+100h] [rbp+0h] BYREF
  int cchDest[2]; // [rsp+140h] [rbp+40h]
  LPWSTR v134; // [rsp+148h] [rbp+48h]
  _BYTE v135[576]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+2D8h]

  lpSrcStr = a4;
  v7 = a3;
  Locale = a2;
  result = (__int64)a7;
  v128 = a7;
  if ( !a3 )
  {
    *a7 = 0;
    return result;
  }
  v10 = a1 & 1;
  if ( (a1 & 2) != 0 )
  {
    v11 = 1;
    v12 = 0;
  }
  else
  {
    v11 = 0;
    v12 = 1;
  }
  v116 = v12;
  v118 = v11;
  if ( LCIDToLocaleName(a2, 0, 0, 0) <= 0 && a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  v14 = 0;
  v15 = 0;
  v130 = 0;
  if ( !v11 )
    goto LABEL_262;
  if ( Locale == 1042 )
  {
    v129 = (unsigned int)v7;
    v29 = (unsigned int)v7 + 1LL;
    if ( v29 >= (unsigned int)v7 )
    {
      pbag.Size = 0;
      if ( is_mul_ok(v29, 2u) )
      {
        v31 = (const WCHAR *)WINRT_IMPL_CoTaskMemAlloc(2 * v29);
        pszText = v31;
        v32 = 0;
        v33 = -2147024882;
        if ( !v31 )
          v32 = -2147024882;
        LODWORD(v124) = v32;
        if ( v32 < 0 )
        {
          pszText = v31;
          v42 = v32 == 0;
        }
        else
        {
          if ( (v31 || (unsigned int)v7 == -1) && v29 <= 0x7FFFFFFF )
          {
            if ( v129 >= 0x7FFFFFFF )
            {
              pszText = v31;
              if ( (unsigned int)v7 != -1 )
                *v31 = 0;
            }
            else
            {
              v34 = v129;
              v35 = lpSrcStr;
              if ( !lpSrcStr )
              {
                v35 = &psz;
                v34 = 0;
              }
              pszText = v31;
              if ( (unsigned int)v7 != -1 )
              {
                v36 = (WCHAR *)v31;
                v37 = 0;
                v38 = (unsigned int)v7 + 1LL;
                while ( v34 )
                {
                  v39 = *v35;
                  if ( !*v35 )
                  {
                    if ( !v29 )
                    {
LABEL_64:
                      *(v36 - 1) = 0;
                      goto LABEL_70;
                    }
                    break;
                  }
                  ++v35;
                  *v36++ = v39;
                  --v34;
                  ++v37;
                  if ( !--v29 )
                    goto LABEL_64;
                }
                *v36 = 0;
                v41 = v38 == v37;
                v40 = v38 - v37;
                if ( !v41 && v40 != 1 && (unsigned __int64)(2 * v40) > 2 )
                  memset_0((void *)&v31[v37 + 1], 0, 2 * v40 - 2);
              }
            }
          }
          else
          {
            *v31 = 0;
            pszText = v31;
          }
LABEL_70:
          *(_OWORD *)&pbag.Size = xmmword_1802DD280;
          Services = 0;
          if ( !byte_18036932C )
          {
            AcquireSRWLockExclusive(&s_srwElsServiceLock);
            if ( !byte_18036932C )
            {
              memset(&pOptions.pszCategory, 0, 56);
              *((_QWORD *)&pOptions + 9) = 0;
              pOptions.Size = 80;
              pOptions.pGuid = (GUID *)&pbag;
              Services = MappingGetServices(&pOptions, &g_scriptAutoDetection, &pdwServicesCount);
              if ( Services >= 0 )
              {
                if ( pdwServicesCount )
                  byte_18036932C = 1;
                else
                  Services = -2147467259;
              }
            }
            ReleaseSRWLockExclusive(&s_srwElsServiceLock);
          }
          if ( Services >= 0 )
          {
            memset(&pbag.prgResultRanges, 0, 56);
            pbag.Size = 64;
            v44 = -1;
            do
              ++v44;
            while ( pszText[v44] );
            Services = MappingRecognizeText(g_scriptAutoDetection, pszText, v44, 0, 0, &pbag);
            if ( Services >= 0 )
            {
              LOBYTE(v45) = 0;
              v123 = v45;
              LODWORD(v124) = 0;
              if ( !pbag.dwRangesCount )
                goto LABEL_83;
              v46 = 0;
              while ( 1 )
              {
                v47 = (_BYTE)v45 == 0;
                if ( (_BYTE)v45 )
                  break;
                v48 = StrStrIW(L"Hang", (PCWSTR)pbag.prgResultRanges[v46].pData);
                v45 = (unsigned __int8)v123;
                if ( v48 )
                  v45 = 1;
                v123 = v45;
                if ( ++v46 >= pbag.dwRangesCount )
                {
                  v47 = (_BYTE)v45 == 0;
                  break;
                }
              }
              v12 = v116;
              if ( v47 )
LABEL_83:
                Services = 1;
              MappingFreePropertyBag(&pbag);
            }
          }
          CoTaskMemFree_0((LPVOID)pszText);
          v42 = Services == 0;
        }
        if ( v42 )
        {
          pszText = 0;
          pv = 0;
          if ( (int)_AllocStringWorker<CTCoAllocPolicy>(
                      v33,
                      v30,
                      (_DWORD)lpSrcStr,
                      v129,
                      (_DWORD)lpDestStr,
                      (__int64)&pv) >= 0 )
          {
            v49 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                    (PMAPPING_SERVICE_INFO *)g_koreanDecomposition,
                    (LPCWSTR)pv,
                    (wchar_t **)&pszText);
            CoTaskMemFree_0(pv);
            if ( v49 >= 0 )
            {
              lpSrcStr = pszText;
              v15 = (WCHAR *)pszText;
              v130 = pszText;
              v7 = -1;
              do
                ++v7;
              while ( pszText[v7] );
            }
            v12 = v116;
          }
        }
      }
    }
  }
  if ( !v10 )
  {
LABEL_262:
    if ( !`IsIcuSortingDefaultEnabled'::`2'::checked )
    {
      memset(&pbag, 0, 32);
      LODWORD(pbag.Size) = 32;
      if ( GetNLSVersionEx(0x8001u, 0, (LPNLSVERSIONINFOEX)&pbag) )
      {
        if ( (HIDWORD(pbag.Size) & 0xFF000000) == 0x1000000 )
        {
          `IsIcuSortingDefaultEnabled'::`2'::usingICU = 1;
          _InterlockedOr(v114, 0);
        }
        `IsIcuSortingDefaultEnabled'::`2'::checked = 1;
      }
    }
    if ( `IsIcuSortingDefaultEnabled'::`2'::usingICU )
    {
      v18 = 134415363;
    }
    else
    {
      if ( v12 )
      {
        v16 = 1032;
        v17 = 134414337;
      }
      else
      {
        v16 = 1024;
        v17 = 134414339;
      }
      v18 = v16 | v17;
    }
    v19 = (unsigned int)LCMapStringW(Locale, v18, lpSrcStr, v7, a6, Size);
    v20 = v128;
    *v128 = v19;
    if ( (_DWORD)v19 )
    {
      v21 = v20;
    }
    else
    {
      if ( GetLastError() != 122 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x405,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
          v84);
      v85 = LCMapStringW(Locale, v18, lpSrcStr, v7, 0, 0);
      LODWORD(pszText) = v85;
      if ( !v85 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x40C,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
          v86);
      pbag.Size = (size_t)operator new[](v85);
      v87 = LCMapStringW(Locale, v18, lpSrcStr, v7, (LPWSTR)pbag.Size, (int)pszText);
      v89 = v87;
      if ( !v87 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x419,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
          v88);
      if ( Size < v87 )
        v89 = Size;
      v21 = v128;
      *v128 = v89;
      memcpy_0(a6, (const void *)pbag.Size, v89);
      operator delete((void *)pbag.Size);
      v19 = *v21;
    }
    if ( v12 && (_DWORD)v19 )
    {
      v83 = (unsigned int)(v19 - 1);
      if ( *((_BYTE *)a6 + v83) )
        LODWORD(v83) = v19;
      else
        *v21 = v83;
      for ( ; (_DWORD)v83; *v21 = v83 )
      {
        v83 = (unsigned int)(v83 - 1);
        if ( *((_BYTE *)a6 + v83) != 1 )
          break;
      }
    }
    if ( v118 )
    {
      if ( v10 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v19);
      v19 = *v21;
      while ( v14 < (unsigned int)v19 )
      {
        if ( *((_BYTE *)a6 + v14) == 1 )
        {
          *v21 = v14;
          goto LABEL_26;
        }
        ++v14;
      }
    }
    goto LABEL_26;
  }
  if ( dword_180369330 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_180369330);
    if ( dword_180369330 == -1 )
    {
      TPUtils::combinable<inverted::CLocaleNameCache>::combinable<inverted::CLocaleNameCache>();
      atexit(inverted::GetTextKey_::_19_::_dynamic_atexit_destructor_for__s_localeNameCache__);
      Init_thread_footer(&dword_180369330);
    }
  }
  if ( !`IsIcuSortingDefaultEnabled'::`2'::checked )
  {
    memset(&pbag, 0, 32);
    LODWORD(pbag.Size) = 32;
    if ( GetNLSVersionEx(0x8001u, 0, (LPNLSVERSIONINFOEX)&pbag) )
    {
      if ( (HIDWORD(pbag.Size) & 0xFF000000) == 0x1000000 )
      {
        `IsIcuSortingDefaultEnabled'::`2'::usingICU = 1;
        _InterlockedOr(v114, 0);
      }
      `IsIcuSortingDefaultEnabled'::`2'::checked = 1;
    }
  }
  v22 = 134415361;
  if ( `IsIcuSortingDefaultEnabled'::`2'::usingICU )
    v22 = 134415363;
  dwMapFlags = v22;
  v23 = v7 + 1;
  v24 = operator new[](saturated_mul(v7 + 1, 2u));
  pv = v24;
  if ( v7 == -1 )
  {
    v26 = 2147942487LL;
  }
  else if ( v7 > 0x7FFFFFFE || v23 > 0x7FFFFFFF )
  {
    v26 = 2147942487LL;
    *v24 = 0;
  }
  else
  {
    v25 = v24;
    v26 = 0;
    v27 = lpSrcStr;
    while ( v7 )
    {
      v28 = *v27;
      if ( !*v27 )
      {
        if ( !v23 )
        {
LABEL_44:
          --v25;
          v26 = 2147942522LL;
          break;
        }
        break;
      }
      ++v27;
      *v25++ = v28;
      --v7;
      if ( !--v23 )
        goto LABEL_44;
    }
    *v25 = 0;
  }
  if ( (int)v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
      (const char *)v26,
      (int)lpDestStr);
  CurrentThreadId = (unsigned int)Concurrency::details::platform::GetCurrentThreadId(retaddr);
  for ( i = *(_QWORD *)(qword_180369340 + 8 * (CurrentThreadId % qword_180369348)); i; i = *(_QWORD *)(i + 184) )
  {
    if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      goto LABEL_96;
  }
  i = TPUtils::combinable<inverted::CLocaleNameCache>::_AddLocalItem(
        qword_180369340,
        (unsigned int)CurrentThreadId,
        CurrentThreadId % qword_180369348);
LABEL_96:
  v52 = (const WCHAR *)(i + 8);
  v53 = Locale;
  if ( Locale != *(_DWORD *)(i + 4) )
  {
    if ( !LCIDToLocaleName(Locale, (LPWSTR)(i + 8), 85, 0x8000000u)
      && !LCIDToLocaleName(0, (LPWSTR)(i + 8), 85, 0x8000000u) )
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xD17,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\indexdefinition.h",
        v90);
    }
    *(_DWORD *)(i + 4) = v53;
  }
  v54 = (const WCHAR *)pv;
  v124 = (LPCWSTR)pv;
  pbag.Size = 0;
  pszText = 0;
  v56 = Size;
  if ( (!StrCmpIW(v52, L"ko") || !StrCmpIW(v52, L"ko-KR"))
    && !(unsigned int)CScriptAutoDetection::HasScript(&g_scriptAutoDetection, v54, v55) )
  {
    v117 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
             (PMAPPING_SERVICE_INFO *)g_koreanDecomposition,
             v54,
             (unsigned __int16 **)&pszText);
    if ( v117 < 0 )
    {
      v78 = (void *)pszText;
      v21 = v128;
      v77 = v117;
      goto LABEL_148;
    }
    pbag.Size = (size_t)pszText;
    v124 = pszText;
  }
  SearchKeyFlags = GetSearchKeyFlags(v52);
  *(_QWORD *)cchDest = 576;
  v134 = 0;
  v21 = v128;
  *v128 = 0;
  v57 = &psz;
  if ( IsValidLocaleName(v52) )
    v57 = v52;
  v58 = (WCHAR *)v135;
  if ( v134 )
    v58 = v134;
  if ( LCMapStringEx(v57, dwMapFlags, v124, -1, v58, cchDest[0], 0, 0, 0) )
  {
    v117 = 0;
    goto LABEL_110;
  }
  Error = ResultFromKnownLastError();
  v117 = Error;
  if ( Error != -2147024774 )
  {
LABEL_108:
    if ( Error >= 0 )
    {
      v60 = 0;
      v113 = v134;
LABEL_145:
      v77 = v117;
LABEL_146:
      *v21 = v60;
      goto LABEL_147;
    }
    v77 = v117;
    goto LABEL_213;
  }
  v91 = v124;
  v92 = LCMapStringEx(v57, dwMapFlags, v124, -1, 0, 0, 0, 0, 0);
  LODWORD(v124) = v92;
  if ( v92 )
  {
    if ( v92 < 0x240uLL )
    {
      v110 = v134;
      v112 = cchDest[0];
    }
    else
    {
      v110 = (WCHAR *)operator new[](v92, (const struct std::nothrow_t *)&std::nothrow);
      v129 = (unsigned __int64)v110;
      v134 = v110;
      if ( !v110 )
      {
        v77 = -2147024882;
        v113 = 0;
        goto LABEL_147;
      }
      v112 = (int)v124;
      *(_QWORD *)cchDest = (unsigned int)v124;
    }
    v111 = (WCHAR *)v135;
    if ( v110 )
      v111 = v110;
    if ( LCMapStringEx(v57, dwMapFlags, v91, -1, v111, v112, 0, 0, 0) )
    {
      v117 = 0;
LABEL_110:
      v61 = cchDest[0];
      v62 = (LPWSTR)v135;
      v113 = v134;
      v129 = (unsigned __int64)v134;
      if ( v134 )
        v62 = v134;
      v63 = 0;
      v64 = 0;
      v65 = SearchKeyFlags;
      while ( v63 < cchDest[0] )
      {
        v66 = *((_BYTE *)v62 + v63);
        if ( v66 == 1 )
        {
          v68 = v63 + 1;
          LODWORD(lpSrcStr) = v63 + 1;
          for ( j = v63 + 1; j < cchDest[0]; ++j )
          {
            if ( *((_BYTE *)v62 + j) == 1 )
            {
              v60 = v64 + 1;
              v123 = v64 + 1;
              if ( v64 != -1 && Size )
              {
                if ( v60 > Size )
                {
                  v60 = 0;
                  v77 = -2147024774;
                  goto LABEL_146;
                }
                LODWORD(v124) = j - 1;
                v70 = (LPWSTR)v135;
                if ( v134 )
                  v70 = v134;
                v121 = 0;
                v71 = 0;
                v72 = 0;
                LODWORD(pszText) = v68;
                v73 = v60;
                do
                {
                  if ( v68 >= v61 )
                    break;
                  if ( v72 >= v61 )
                    break;
                  v74 = *((_BYTE *)v70 + v72);
                  if ( v74 == 1 )
                    break;
                  if ( (unsigned __int8)(v74 + 87) <= 6u || (v65 & 2) != 0 && (unsigned __int8)(v74 + 64) <= 0x39u )
                  {
                    v75 = 0;
                    v76 = 3;
                  }
                  else
                  {
                    v75 = 1;
                    ++v121;
                    v76 = 2;
                  }
                  for ( ; v71 < v60; --v76 )
                  {
                    if ( v72 >= v61 )
                      break;
                    if ( !v76 )
                      break;
                    *((_BYTE *)a6 + v71++) = *((_BYTE *)v70 + v72++);
                  }
                  if ( (SearchKeyFlags & 4) != 0 )
                  {
                    v42 = v75 == 0;
                    v65 = SearchKeyFlags;
                    if ( !v42 )
                    {
                      if ( v71 >= v60 )
                        goto LABEL_143;
                      if ( (SearchKeyFlags & 1) == 0 )
                      {
                        v81 = (int)lpSrcStr;
                        v82 = *((_BYTE *)v70 + (unsigned int)lpSrcStr);
                        if ( v82 == 1 )
                        {
                          *((_BYTE *)a6 + v71) = 2;
                        }
                        else
                        {
                          *((_BYTE *)a6 + v71) = v82;
                          LODWORD(lpSrcStr) = v81 + 1;
                        }
                      }
                      ++v71;
                    }
                  }
                  else
                  {
                    v65 = SearchKeyFlags;
                  }
                  v68 = (unsigned int)lpSrcStr;
                }
                while ( v71 < v60 );
                if ( (v65 & 4) == 0 )
                  goto LABEL_144;
LABEL_143:
                if ( (v65 & 1) != 0 )
                {
                  v94 = v121;
                  v95 = v121 - (_DWORD)v124 + (_DWORD)pszText - 1;
                  LODWORD(v96) = 0;
                  if ( v60 )
                  {
                    v97 = (unsigned int)v124;
                    v98 = v117;
                    do
                    {
                      if ( v97 >= v61 || !v94 )
                        break;
                      v99 = *((_BYTE *)a6 + (unsigned int)v96);
                      if ( (unsigned __int8)(v99 + 87) <= 6u || (v65 & 2) != 0 && (unsigned __int8)(v99 + 64) <= 0x39u )
                      {
                        LODWORD(v96) = v96 + 3;
                        v94 = v121;
                      }
                      else
                      {
                        v96 = (unsigned int)(v96 + 2);
                        if ( (unsigned int)v96 < v73 )
                        {
                          if ( v95 )
                          {
                            --v95;
                            v100 = 2;
                          }
                          else
                          {
                            v100 = *((_BYTE *)v70 + v97--);
                          }
                          *((_BYTE *)a6 + v96) = v100;
                          LODWORD(v96) = v96 + 1;
                        }
                        v94 = --v121;
                      }
                    }
                    while ( (unsigned int)v96 < v73 );
                    v117 = v98;
                    v123 = v73;
                    v21 = v128;
                    v53 = Locale;
                  }
                }
LABEL_144:
                *((_BYTE *)a6 + v73 - 1) = 0;
                v60 = v123;
                v113 = (LPWSTR)v129;
              }
              goto LABEL_145;
            }
          }
          break;
        }
        if ( (unsigned __int8)(v66 + 87) <= 6u || (SearchKeyFlags & 2) != 0 && (unsigned __int8)(v66 + 64) <= 0x39u )
          v67 = 3;
        else
          v67 = 2;
        v63 += v67;
        if ( v67 + (unsigned int)((SearchKeyFlags & 4) != 0) > 3 )
          v64 += 3;
        else
          v64 += v67 + ((SearchKeyFlags & 4) != 0);
      }
      v60 = 0;
      goto LABEL_145;
    }
    Error = ResultFromKnownLastError();
    v117 = Error;
    goto LABEL_108;
  }
  LastError = GetLastError();
  v77 = LastError;
  if ( LastError > 0 )
    v77 = (unsigned __int16)LastError | 0x80070000;
  if ( v77 >= 0 )
    v77 = -2147467259;
LABEL_213:
  v113 = v134;
LABEL_147:
  operator delete(v113);
  v78 = (void *)pbag.Size;
  v56 = Size;
LABEL_148:
  CoTaskMemFree_0(v78);
  if ( v77 < 0 )
  {
    if ( v77 != -2147024774 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3CB,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
        (const char *)(unsigned int)v77,
        (int)lpDestStr);
    v101 = (inverted::CLocaleNameCache *)TPUtils::combinable<inverted::CLocaleNameCache>::local();
    LocaleName = inverted::CLocaleNameCache::GetLocaleName(v101, v53);
    SearchKey = CreateSearchKey(LocaleName, dwMapFlags, (const unsigned __int16 *)pv, 0, 0, v21);
    if ( SearchKey < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
        (const char *)(unsigned int)SearchKey,
        (int)lpDestStr);
    v104 = (unsigned __int8 *)operator new[](*v21);
    pbag.Size = (size_t)v104;
    v105 = *v21;
    v106 = (inverted::CLocaleNameCache *)TPUtils::combinable<inverted::CLocaleNameCache>::local();
    v107 = inverted::CLocaleNameCache::GetLocaleName(v106, v53);
    LODWORD(lpDestStr) = v105;
    v79 = pv;
    v108 = CreateSearchKey(v107, dwMapFlags, (const unsigned __int16 *)pv, v104, (unsigned int)lpDestStr, v21);
    if ( v108 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3DB,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
        (const char *)(unsigned int)v108,
        (int)lpDestStr);
    v109 = *v21;
    if ( v56 < *v21 )
      v109 = v56;
    *v21 = v109;
    memcpy_0(a6, v104, v109);
    operator delete(v104);
  }
  else
  {
    v79 = pv;
  }
  if ( *v21 )
  {
    v80 = *v21 - 1;
    if ( !*((_BYTE *)a6 + v80) )
      *v21 = v80;
  }
  operator delete(v79);
LABEL_26:
  if ( v15 )
    CoTaskMemFree_0(v15);
  result = *v21;
  if ( (_DWORD)result )
  {
    result = (unsigned int)(result - 1);
    if ( *((_BYTE *)a6 + result) == 1 )
      return MicrosoftTelemetryAssertTriggeredNoArgs(v19);
  }
  return result;
}

```

## disassembly

```asm
0x180052b10  mov     [rsp-8+arg_0], rbx
0x180052b15  push    rbp
0x180052b16  push    rsi
0x180052b17  push    rdi
0x180052b18  push    r12
0x180052b1a  push    r13
0x180052b1c  push    r14
0x180052b1e  push    r15
0x180052b20  lea     rbp, [rsp-2A0h]
0x180052b28  sub     rsp, 3A0h
0x180052b2f  mov     rax, cs:__security_cookie
0x180052b36  xor     rax, rsp
0x180052b39  mov     [rbp+2D0h+var_40], rax
0x180052b40  mov     [rbp+2D0h+lpSrcStr], r9
0x180052b44  mov     r13, r8
0x180052b47  mov     ebx, edx
0x180052b49  mov     [rsp+3D0h+Locale], edx
0x180052b4d  mov     r15, [rbp+2D0h+arg_28]
0x180052b54  mov     rax, [rbp+2D0h+arg_30]
0x180052b5b  mov     [rbp+2D0h+var_338], rax
0x180052b5f  test    r8, r8
0x180052b62  jz      loc_1800535C1
0x180052b68  movzx   r12d, cl
0x180052b6c  and     r12b, 1
0x180052b70  test    cl, 2
0x180052b73  jz      loc_18005303B
0x180052b79  mov     sil, 1
0x180052b7c  xor     r14b, r14b
0x180052b7f  mov     [rsp+3D0h+var_380], r14b
0x180052b84  mov     byte ptr [rsp+3D0h+var_37C+4], sil
0x180052b89  xor     r9d, r9d; dwFlags
0x180052b8c  xor     r8d, r8d; cchName
0x180052b8f  xor     edx, edx; lpName
0x180052b91  mov     ecx, ebx; Locale
0x180052b93  call    cs:__imp_LCIDToLocaleName
0x180052b99  test    eax, eax
0x180052b9b  jg      short loc_180052BA6
0x180052b9d  test    ebx, ebx
0x180052b9f  jz      short loc_180052BA6
0x180052ba1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180052ba6  xor     edi, edi
0x180052ba8  mov     ebx, edi
0x180052baa  mov     [rbp+2D0h+var_328], rbx
0x180052bae  test    sil, sil
0x180052bb1  jz      short loc_180052BCA
0x180052bb3  cmp     [rsp+3D0h+Locale], 412h
0x180052bbb  jz      loc_180052DB8
0x180052bc1  test    r12b, r12b
0x180052bc4  jnz     loc_180052CC6
0x180052bca  cmp     cs:?checked@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::checked
0x180052bd1  jz      loc_180053456
0x180052bd7  cmp     cs:?usingICU@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::usingICU
0x180052bde  jnz     loc_180052CBC
0x180052be4  test    r14b, r14b
0x180052be7  jz      loc_180052CAD
0x180052bed  mov     eax, 408h
0x180052bf2  mov     esi, 8030001h
0x180052bf7  or      esi, eax
0x180052bf9  mov     eax, dword ptr [rbp+2D0h+Size]
0x180052bff  mov     [rsp+3D0h+cchDest], eax; cchDest
0x180052c03  mov     [rsp+3D0h+lpDestStr], r15; lpDestStr
0x180052c08  mov     r9d, r13d; cchSrc
0x180052c0b  mov     r8, [rbp+2D0h+lpSrcStr]; lpSrcStr
0x180052c0f  mov     edx, esi; dwMapFlags
0x180052c11  mov     ecx, [rsp+3D0h+Locale]; Locale
0x180052c15  call    cs:__imp_LCMapStringW
0x180052c1b  mov     ecx, eax
0x180052c1d  mov     rax, [rbp+2D0h+var_338]
0x180052c21  mov     [rax], ecx
0x180052c23  test    ecx, ecx
0x180052c25  jz      loc_180053521
0x180052c2b  mov     rsi, rax
0x180052c2e  test    r14b, r14b
0x180052c31  jnz     loc_1800534B5
0x180052c37  cmp     byte ptr [rsp+3D0h+var_37C+4], 0
0x180052c3c  jz      short loc_180052C63
0x180052c3e  test    r12b, r12b
0x180052c41  jnz     loc_180053950
0x180052c47  mov     ecx, [rsi]
0x180052c49  nop     dword ptr [rax+00000000h]
0x180052c50  cmp     edi, ecx
0x180052c52  jnb     short loc_180052C63
0x180052c54  mov     eax, edi
0x180052c56  cmp     byte ptr [rax+r15], 1
0x180052c5b  jz      short loc_180052C61
0x180052c5d  inc     edi
0x180052c5f  jmp     short loc_180052C50
0x180052c61  mov     [rsi], edi
0x180052c63  test    rbx, rbx
0x180052c66  jz      short loc_180052C70
0x180052c68  mov     rcx, rbx; pv
0x180052c6b  call    CoTaskMemFree_0
0x180052c70  mov     eax, [rsi]
0x180052c72  test    eax, eax
0x180052c74  jz      short loc_180052C83
0x180052c76  dec     eax
0x180052c78  cmp     byte ptr [rax+r15], 1
0x180052c7d  jz      loc_180053AB2
0x180052c83  mov     rcx, [rbp+2D0h+var_40]
0x180052c8a  xor     rcx, rsp; StackCookie
0x180052c8d  call    __security_check_cookie
0x180052c92  mov     rbx, [rsp+3D0h+arg_0]
0x180052c9a  add     rsp, 3A0h
0x180052ca1  pop     r15
0x180052ca3  pop     r14
0x180052ca5  pop     r13
0x180052ca7  pop     r12
0x180052ca9  pop     rdi
0x180052caa  pop     rsi
0x180052cab  pop     rbp
0x180052cac  retn
0x180052cad  mov     eax, 400h
0x180052cb2  mov     esi, 8030003h
0x180052cb7  jmp     loc_180052BF7
0x180052cbc  mov     esi, 8030403h
0x180052cc1  jmp     loc_180052BF9
0x180052cc6  mov     ecx, cs:_tls_index
0x180052ccc  mov     rax, gs:58h
0x180052cd5  mov     edx, 10h
0x180052cda  mov     rax, [rax+rcx*8]
0x180052cde  mov     ecx, [rdx+rax]
0x180052ce1  cmp     cs:dword_180369330, ecx
0x180052ce7  jg      loc_180053651
0x180052ced  cmp     cs:?checked@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::checked
0x180052cf4  jz      loc_1800536CF
0x180052cfa  mov     eax, 8030401h
0x180052cff  mov     esi, 8030403h
0x180052d04  cmp     cs:?usingICU@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::usingICU
0x180052d0b  cmovnz  eax, esi
0x180052d0e  mov     [rbp+2D0h+dwMapFlags], eax
0x180052d11  lea     rsi, [r13+1]
0x180052d15  mov     eax, 2
0x180052d1a  mul     rsi
0x180052d1d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180052d24  cmovb   rax, rcx
0x180052d28  mov     rcx, rax; unsigned __int64
0x180052d2b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180052d30  mov     [rbp+2D0h+pv], rax
0x180052d34  test    rsi, rsi
0x180052d37  jz      loc_1800539E4
0x180052d3d  cmp     r13, 7FFFFFFEh
0x180052d44  ja      loc_1800537A8
0x180052d4a  cmp     rsi, 7FFFFFFFh
0x180052d51  ja      loc_1800537A8
0x180052d57  mov     rcx, rax
0x180052d5a  mov     r9d, edi; char *
0x180052d5d  mov     rax, [rbp+2D0h+lpSrcStr]
0x180052d61  test    r13, r13
0x180052d64  jz      short loc_180052D93
0x180052d66  movzx   edx, word ptr [rax]
0x180052d69  test    dx, dx
0x180052d6c  jz      short loc_180052D8E
0x180052d6e  add     rax, 2
0x180052d72  mov     [rcx], dx
0x180052d75  add     rcx, 2
0x180052d79  dec     r13
0x180052d7c  sub     rsi, 1
0x180052d80  jnz     short loc_180052D61
0x180052d82  sub     rcx, 2
0x180052d86  mov     r9d, 8007007Ah
0x180052d8c  jmp     short loc_180052D93
0x180052d8e  test    rsi, rsi
0x180052d91  jz      short loc_180052D82
0x180052d93  mov     [rcx], di
0x180052d96  mov     rcx, [rbp+2D8h]; this
0x180052d9d  test    r9d, r9d
0x180052da0  jns     loc_180053046
0x180052da6  lea     r8, aOnecoreuapBase_301; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180052dad  mov     edx, 3BDh; void *
0x180052db2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052db8  mov     eax, r13d
0x180052dbb  mov     [rbp+2D0h+var_330], rax
0x180052dbf  lea     rsi, [rax+1]
0x180052dc3  cmp     rsi, rax
0x180052dc6  jb      loc_180052BC1
0x180052dcc  mov     [rbp+2D0h+pbag.Size], rdi
0x180052dd0  mov     eax, 2
0x180052dd5  mul     rsi
0x180052dd8  test    rdx, rdx
0x180052ddb  jnz     loc_180052BC1
0x180052de1  mov     rcx, rax; cb
0x180052de4  call    WINRT_IMPL_CoTaskMemAlloc
0x180052de9  mov     r10, rax
0x180052dec  mov     [rsp+3D0h+pszText], rax
0x180052df1  mov     eax, edi
0x180052df3  test    r10, r10
0x180052df6  mov     ecx, 8007000Eh
0x180052dfb  cmovz   eax, ecx
0x180052dfe  mov     dword ptr [rsp+3D0h+var_358], eax
0x180052e02  test    eax, eax
0x180052e04  js      loc_180052EB3
0x180052e0a  test    r10, r10
0x180052e0d  jz      loc_180053A0F
0x180052e13  cmp     rsi, 7FFFFFFFh
0x180052e1a  ja      loc_180053A18
0x180052e20  mov     rax, [rbp+2D0h+var_330]
0x180052e24  cmp     rax, 7FFFFFFFh
0x180052e2a  jnb     loc_1800539F8
0x180052e30  mov     rcx, rax
0x180052e33  mov     rax, [rbp+2D0h+lpSrcStr]
0x180052e37  mov     rdx, rax
0x180052e3a  test    rax, rax
0x180052e3d  jz      loc_180053A26
0x180052e43  mov     [rsp+3D0h+pszText], r10
0x180052e48  test    rsi, rsi
0x180052e4b  jz      short loc_180052EC2
0x180052e4d  mov     r8, r10
0x180052e50  mov     r9, rdi
0x180052e53  mov     r11, rsi
0x180052e56  test    rcx, rcx
0x180052e59  jz      short loc_180052E87
0x180052e5b  movzx   eax, word ptr [rdx]
0x180052e5e  test    ax, ax
0x180052e61  jz      short loc_180052E82
0x180052e63  add     rdx, 2
0x180052e67  mov     [r8], ax
0x180052e6b  add     r8, 2
0x180052e6f  dec     rcx
0x180052e72  inc     r9
0x180052e75  sub     rsi, 1
0x180052e79  jnz     short loc_180052E56
0x180052e7b  mov     [r8-2], di
0x180052e80  jmp     short loc_180052EC2
0x180052e82  test    rsi, rsi
0x180052e85  jz      short loc_180052E7B
0x180052e87  mov     [r8], di
0x180052e8b  sub     r11, r9
0x180052e8e  cmp     r11, 1
0x180052e92  jbe     short loc_180052EC2
0x180052e94  lea     r8, [r11+r11]
0x180052e98  cmp     r8, 2
0x180052e9c  jbe     short loc_180052EC2
0x180052e9e  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180052ea2  add     r10, 2
0x180052ea6  lea     rcx, [r10+r9*2]; void *
0x180052eaa  xor     edx, edx; Val
0x180052eac  call    memset_0
0x180052eb1  jmp     short loc_180052EC2
0x180052eb3  mov     [rsp+3D0h+pszText], r10
0x180052eb8  mov     esi, eax
0x180052eba  test    eax, eax
0x180052ebc  js      loc_180052FBD
0x180052ec2  movups  xmm0, cs:xmmword_1802DD280
0x180052ec9  movaps  xmmword ptr [rbp+2D0h+pbag.Size], xmm0
0x180052ecd  mov     esi, edi
0x180052ecf  cmp     cs:byte_18036932C, sil
0x180052ed6  jz      loc_1800535CA
0x180052edc  test    esi, esi
0x180052ede  js      loc_180052FB1
0x180052ee4  mov     [rbp+2D0h+pbag.prgResultRanges], rdi
0x180052ee8  xorps   xmm0, xmm0
0x180052eeb  movdqa  xmmword ptr [rbp+2D0h+pbag.dwRangesCount], xmm0
0x180052ef0  xorps   xmm1, xmm1
0x180052ef3  movdqa  xmmword ptr [rbp+2D0h+pbag.dwServiceDataSize], xmm1
0x180052ef8  movdqa  xmmword ptr [rbp+2D0h+pbag.dwCallerDataSize], xmm0
0x180052efd  mov     [rbp+2D0h+pbag.Size], 40h ; '@'
0x180052f05  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180052f0c  mov     rax, [rsp+3D0h+pszText]
0x180052f11  inc     r8; dwLength
0x180052f14  cmp     word ptr [rax+r8*2], 0
0x180052f1a  jnz     short loc_180052F11
0x180052f1c  lea     rcx, [rbp+2D0h+pbag]
0x180052f20  mov     qword ptr [rsp+3D0h+cchDest], rcx; pbag
0x180052f25  mov     [rsp+3D0h+lpDestStr], rdi; pOptions
0x180052f2a  xor     r9d, r9d; dwIndex
0x180052f2d  mov     rdx, rax; pszText
0x180052f30  mov     rcx, cs:?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; pServiceInfo
0x180052f37  call    cs:__imp_MappingRecognizeText
0x180052f3d  mov     esi, eax
0x180052f3f  test    eax, eax
0x180052f41  js      short loc_180052FB1
0x180052f43  xor     cl, cl
0x180052f45  mov     [rsp+3D0h+var_35C], ecx
0x180052f49  mov     dword ptr [rsp+3D0h+var_358], edi
0x180052f4d  mov     eax, 1
0x180052f52  cmp     [rbp+2D0h+pbag.dwRangesCount], 0
0x180052f56  jbe     short loc_180052FA5
0x180052f58  mov     r14d, edi
0x180052f5b  test    cl, cl
0x180052f5d  jnz     short loc_180052F9D
0x180052f5f  mov     eax, r14d
0x180052f62  lea     rcx, [rax+rax*8]
0x180052f66  mov     rdx, [rbp+2D0h+pbag.prgResultRanges]
0x180052f6a  mov     rdx, [rdx+rcx*8+18h]; pszSrch
0x180052f6f  lea     rcx, pszFirst; "Hang"
0x180052f76  call    cs:__imp_StrStrIW
0x180052f7c  mov     ecx, [rsp+3D0h+var_35C]
0x180052f80  movzx   ecx, cl
0x180052f83  test    rax, rax
0x180052f86  mov     eax, 1
0x180052f8b  cmovnz  ecx, eax
0x180052f8e  mov     [rsp+3D0h+var_35C], ecx
0x180052f92  inc     r14d
0x180052f95  cmp     r14d, [rbp+2D0h+pbag.dwRangesCount]
0x180052f99  jb      short loc_180052F5B
0x180052f9b  test    cl, cl
0x180052f9d  movzx   r14d, [rsp+3D0h+var_380]
0x180052fa3  jnz     short loc_180052FA7
0x180052fa5  mov     esi, eax
0x180052fa7  lea     rcx, [rbp+2D0h+pbag]; pBag
  ... truncated ...
```
