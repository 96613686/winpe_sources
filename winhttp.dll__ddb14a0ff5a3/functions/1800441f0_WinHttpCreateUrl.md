# WinHttpCreateUrl

- ea: `0x1800441f0`
- end: `0x180045260`
- name: `WinHttpCreateUrl`
- size: `4208`
- prototype: `BOOL __stdcall(LPURL_COMPONENTS lpUrlComponents, DWORD dwFlags, LPWSTR pwszUrl, LPDWORD pdwUrlLength)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180043230`
- `0x180043840`

## callees

- `0x18002acec`
- `0x180033404`
- `0x180041eb0`
- `0x1800441f0`
- `0x180045268`
- `0x180085b54`
- `0x18009df9c`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800a671c`
- `0x1800cdd7c`
- `0x1800cfe48`
- `0x1800db6b0`
- `0x1800dbccc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004442d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044467`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004471c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044a32`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044ecb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044efa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004442d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044467`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004471c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044a32`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044ecb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180044efa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044dc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044f4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045000`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044dc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044f4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045000`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800451b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800451d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800451f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800451b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800451d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800451f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044323`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044962`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044962`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004431b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004431b`
- `ntdll!EtwEventActivityIdControl` at `0x1800442e4`
- `ntdll!EtwEventActivityIdControl` at `0x18004435a`
- `ntdll!EtwEventActivityIdControl` at `0x180044946`
- `ntdll!EtwEventActivityIdControl` at `0x1800442e4`
- `ntdll!EtwEventActivityIdControl` at `0x18004435a`
- `ntdll!EtwEventActivityIdControl` at `0x180044946`

## pseudocode

```c
BOOL __stdcall WinHttpCreateUrl(LPURL_COMPONENTS lpUrlComponents, DWORD dwFlags, LPWSTR pwszUrl, LPDWORD pdwUrlLength)
{
  LPDWORD v4; // rbx
  DWORD v5; // eax
  void *v7; // r15
  void *v8; // r13
  __int64 v9; // rcx
  __int128 *v10; // rax
  __int128 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int128 *v14; // rax
  int v15; // eax
  bool v16; // sf
  signed __int32 v17; // esi
  DWORD TickCount; // ebx
  unsigned __int64 v19; // rcx
  const struct _GUID *v20; // r9
  LPSTR lpszScheme; // r13
  DWORD dwSchemeLength; // r15d
  __int64 i; // rbx
  __int64 v24; // rdi
  __int64 nScheme; // rsi
  const unsigned __int16 *lpszHostName; // rbx
  DWORD dwHostNameLength; // r13d
  __int64 v28; // rcx
  const unsigned __int16 *v29; // rax
  DWORD v30; // ebx
  __int16 v31; // r9
  DWORD v32; // edi
  unsigned __int16 *v33; // r11
  BOOL v34; // r15d
  unsigned int v35; // r8d
  __int64 j; // rdx
  unsigned int v37; // ecx
  signed __int64 v38; // rdx
  LPURL_COMPONENTS v39; // r8
  STRSAFE_LPWSTR v40; // r12
  LPSTR lpszUserName; // r10
  DWORD dwUserNameLength; // esi
  unsigned __int16 *v43; // r15
  void *lpszPassword; // rbx
  _WORD *lpszUrlPath; // r9
  DWORD dwUrlPathLength; // r15d
  __int64 v47; // rcx
  _WORD *v48; // rax
  int v49; // eax
  DWORD v50; // r10d
  int v51; // edi
  unsigned int v52; // esi
  LPSTR lpszExtraInfo; // rdx
  DWORD dwExtraInfoLength; // r13d
  unsigned int v55; // ebx
  __int64 v56; // r12
  __int64 v57; // rdi
  int v58; // ecx
  const wchar_t *v59; // r14
  __int64 v60; // rsi
  unsigned int v61; // r8d
  unsigned int v62; // edx
  int v63; // eax
  DWORD v64; // eax
  __int64 v65; // rbx
  WCHAR *v66; // rdi
  WCHAR *v67; // rdi
  size_t v68; // rbx
  int v69; // r14d
  LPDWORD v70; // rsi
  unsigned __int16 *v71; // r15
  int v72; // eax
  bool v73; // sf
  int v75; // esi
  __int16 v76; // ax
  __int64 v77; // rcx
  _WORD *v78; // rax
  unsigned int v79; // edx
  __int64 v80; // rcx
  _WORD *v81; // rax
  unsigned int v82; // edx
  __int64 v83; // rcx
  _WORD *v84; // rax
  unsigned int v85; // edx
  unsigned int v86; // r8d
  unsigned __int16 *v87; // rax
  unsigned __int16 *v88; // rax
  unsigned int v89; // eax
  unsigned __int16 *v90; // rax
  char *v91; // rdi
  void *v92; // rdx
  char *v93; // rdi
  DWORD v94; // r8d
  DWORD dwFlagsa[2]; // [rsp+28h] [rbp-E0h]
  __int64 v96; // [rsp+38h] [rbp-D0h]
  DWORD v98; // [rsp+48h] [rbp-C0h]
  WCHAR *v100; // [rsp+58h] [rbp-B0h]
  unsigned int v101; // [rsp+60h] [rbp-A8h]
  int v102; // [rsp+64h] [rbp-A4h]
  unsigned int v103; // [rsp+68h] [rbp-A0h]
  unsigned int v104; // [rsp+6Ch] [rbp-9Ch]
  int v105; // [rsp+70h] [rbp-98h]
  unsigned __int16 *v106; // [rsp+78h] [rbp-90h]
  const void *v107; // [rsp+80h] [rbp-88h]
  unsigned int v108; // [rsp+88h] [rbp-80h]
  unsigned __int16 *lpMem; // [rsp+90h] [rbp-78h]
  CHAR *v111; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v112; // [rsp+A0h] [rbp-68h]
  unsigned int dwPasswordLength; // [rsp+A8h] [rbp-60h]
  const unsigned __int16 *v114; // [rsp+B0h] [rbp-58h]
  unsigned int v115; // [rsp+B8h] [rbp-50h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+C0h] [rbp-48h] BYREF
  void *Src; // [rsp+C8h] [rbp-40h]
  void *v118; // [rsp+D0h] [rbp-38h]
  void *v119; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v120; // [rsp+E0h] [rbp-28h]
  void *v121; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v122; // [rsp+F0h] [rbp-18h]
  void *v123; // [rsp+F8h] [rbp-10h]
  int v124; // [rsp+104h] [rbp-4h]
  unsigned int v125; // [rsp+108h] [rbp+0h] BYREF
  __int128 v126; // [rsp+110h] [rbp+8h] BYREF
  int v127; // [rsp+120h] [rbp+18h]
  __int128 v128; // [rsp+128h] [rbp+20h] BYREF
  struct _GUID v129; // [rsp+138h] [rbp+30h] BYREF
  __int128 v130; // [rsp+148h] [rbp+40h] BYREF
  wchar_t pszDest[12]; // [rsp+158h] [rbp+50h] BYREF
  _UNKNOWN *retaddr; // [rsp+1B0h] [rbp+A8h]

  v4 = pdwUrlLength;
  v5 = dwFlags;
  v7 = 0;
  v8 = 0;
  v100 = pwszUrl;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v126 = 0;
  v127 = 0;
  if ( WinHttpEtwInitialized )
  {
    v9 = 16;
    v10 = &v126;
    do
    {
      *(_BYTE *)v10 = 0;
      v10 = (__int128 *)((char *)v10 + 1);
      --v9;
    }
    while ( v9 );
    v127 = 0;
    v11 = &v126;
    v129 = 0;
    v12 = 16;
    v130 = 0;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (__int128 *)((char *)v11 + 1);
      --v12;
    }
    while ( v12 );
    v128 = 0;
    v13 = 16;
    v14 = &v130;
    do
    {
      *(_BYTE *)v14 = 0;
      v14 = (__int128 *)((char *)v14 + 1);
      --v13;
    }
    while ( v13 );
    v15 = EtwEventActivityIdControl(1, &v128);
    v16 = v15 < 0;
    if ( v15 > 0 )
      v16 = 1;
    if ( !v16 )
      v130 = v128;
    v17 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    TickCount = GetTickCount();
    *(_DWORD *)&v129.Data4[4] = GetCurrentProcessId();
    v129.Data1 = (unsigned int)retaddr;
    *(_DWORD *)&v129.Data2 = v17;
    *(_DWORD *)v129.Data4 = TickCount;
    if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfo(v19, &ActivityStart, &v129, v20, dwFlagsa[0]);
    EtwEventActivityIdControl(2, &v129);
    v5 = dwFlags;
    v4 = pdwUrlLength;
    pwszUrl = v100;
    v126 = v130;
    v127 = 1;
  }
  if ( (xmmword_180107A60 & 4) != 0 )
  {
    WPP_SF_qDqq(
      1026,
      15,
      (unsigned int)WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids,
      (_DWORD)lpUrlComponents,
      v5,
      (__int64)pwszUrl,
      (__int64)v4);
    v5 = dwFlags;
  }
  if ( !v4 || !lpUrlComponents || lpUrlComponents->dwStructSize != 104 || (v5 & 0x7FFF1FFF) != 0 )
    goto LABEL_170;
  lpszScheme = lpUrlComponents->lpszScheme;
  Src = lpszScheme;
  v101 = 4;
  if ( lpszScheme )
  {
    dwSchemeLength = lpUrlComponents->dwSchemeLength;
    v103 = dwSchemeLength;
    if ( !dwSchemeLength )
    {
      v77 = 0x7FFFFFFF;
      v125 = 0;
      v78 = lpszScheme;
      do
      {
        if ( !*v78 )
          break;
        ++v78;
        --v77;
      }
      while ( v77 );
      v79 = -2147024809;
      if ( v77 )
      {
        v79 = 0;
        dwSchemeLength = 0x7FFFFFFF - v77;
      }
      else
      {
        dwSchemeLength = 0;
      }
      v103 = dwSchemeLength;
      v30 = WX_WIN32_FROM_HR(v79);
      if ( v30 )
      {
        v70 = pdwUrlLength;
        v69 = (int)v100;
        goto LABEL_115;
      }
    }
    for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
    {
      v24 = 5 * i;
      if ( LODWORD(qword_1800DF730[5 * i + 2]) == dwSchemeLength
        && !(unsigned int)_o__wcsnicmp(qword_1800DF730[v24 + 1], lpszScheme, dwSchemeLength) )
      {
        LODWORD(nScheme) = HIDWORD(qword_1800DF730[v24 + 2]);
        goto LABEL_30;
      }
    }
    LODWORD(nScheme) = -1;
  }
  else
  {
    nScheme = lpUrlComponents->nScheme;
    if ( (_DWORD)nScheme )
    {
      if ( (unsigned int)(nScheme - 1) > 3 )
      {
        lpszScheme = 0;
        Src = 0;
        dwSchemeLength = 0;
        v103 = 0;
      }
      else
      {
        lpszScheme = (LPSTR)qword_1800DF730[5 * nScheme + 1];
        dwSchemeLength = qword_1800DF730[5 * nScheme + 2];
        Src = lpszScheme;
        v103 = dwSchemeLength;
      }
    }
    else
    {
      lpszScheme = (LPSTR)L"http";
      v103 = 4;
      Src = L"http";
      LODWORD(nScheme) = 1;
      dwSchemeLength = 4;
    }
  }
LABEL_30:
  if ( !dwSchemeLength )
  {
    v7 = v119;
    v8 = v121;
LABEL_170:
    v30 = 87;
    goto LABEL_150;
  }
  *(_QWORD *)&v128 = dwSchemeLength;
  v106 = 0;
  if ( (unsigned int)_o__wcsnicmp(lpszScheme, L"http", dwSchemeLength) )
  {
    if ( (unsigned int)_o__wcsnicmp(lpszScheme, L"https", dwSchemeLength) )
    {
      if ( (unsigned int)_o__wcsnicmp(lpszScheme, L"ftp", dwSchemeLength) )
      {
        if ( (unsigned int)_o__wcsnicmp(lpszScheme, L"gopher", dwSchemeLength) )
        {
          v102 = 0;
          v101 = 0;
        }
        else
        {
          v102 = 1;
          v101 = 2;
        }
      }
      else
      {
        v102 = 1;
        v101 = 1;
      }
    }
    else
    {
      v102 = 1;
      v101 = 4;
    }
  }
  else
  {
    v102 = 1;
  }
  lpszHostName = (const unsigned __int16 *)lpUrlComponents->lpszHostName;
  v114 = lpszHostName;
  if ( !lpszHostName )
  {
    LODWORD(v38) = 0;
    v32 = dwFlags & 0x2000;
    v115 = 0;
    v105 = 0;
    dwHostNameLength = 0;
    v104 = 0;
    v123 = 0;
    goto LABEL_54;
  }
  dwHostNameLength = lpUrlComponents->dwHostNameLength;
  v104 = dwHostNameLength;
  if ( !dwHostNameLength )
  {
    v28 = 0x7FFFFFFF;
    v125 = 0;
    v29 = lpszHostName;
    do
    {
      if ( !*v29 )
        break;
      ++v29;
      --v28;
    }
    while ( v28 );
    v30 = -2147024809;
    if ( v28 )
    {
      v30 = 0;
      dwHostNameLength = 0x7FFFFFFF - v28;
    }
    else
    {
      dwHostNameLength = 0;
    }
    v104 = dwHostNameLength;
    if ( v28 )
      goto LABEL_41;
    if ( (v30 & 0x1FFF0000) == 0x70000 )
    {
      v30 = (unsigned __int16)v30;
      if ( !(_WORD)v30 )
        v30 = 317;
    }
    else if ( !v30 )
    {
LABEL_41:
      lpszHostName = v114;
      goto LABEL_42;
    }
    v7 = v119;
    v8 = v121;
LABEL_150:
    v69 = (int)v100;
    v70 = pdwUrlLength;
    goto LABEL_116;
  }
LABEL_42:
  v31 = dwFlags;
  v32 = dwFlags & 0x2000;
  if ( (dwFlags & 0x2000) == 0 )
  {
    v33 = 0;
LABEL_44:
    v34 = 0;
    v106 = v33;
    v35 = 0;
    v105 = 0;
    for ( j = 0; (unsigned int)j < dwHostNameLength; j = (unsigned int)(j + 1) )
    {
      v37 = v35 + 1;
      if ( lpszHostName[j] != 58 )
        v37 = v35;
      v35 = v37;
      if ( v37 > 1 )
      {
        v34 = 1;
        v105 = 1;
        if ( *lpszHostName == 91 )
        {
          v34 = lpszHostName[dwHostNameLength - 1] != 93;
          v105 = v34;
        }
        break;
      }
    }
    LODWORD(v38) = 0;
    v123 = 0;
    v115 = 0;
    if ( lpszHostName )
    {
      v75 = nScheme - 1;
      if ( v75 )
      {
        if ( v75 == 1 )
          v76 = 443;
        else
          v76 = 0;
      }
      else
      {
        v76 = 80;
      }
      if ( lpUrlComponents->nPort != v76 || v31 < 0 )
      {
        LODWORD(v96) = lpUrlComponents->nPort;
        ppszDestEnd = 0;
        if ( StringCchPrintfExW(pszDest, 0xAu, &ppszDestEnd, 0, 0, L":%lu", v96) < 0 )
        {
          v30 = 87;
          goto LABEL_203;
        }
        v123 = pszDest;
        v38 = ppszDestEnd - pszDest;
        v115 = v38;
        v114 = lpszHostName;
        v104 = dwHostNameLength;
        v105 = v34;
      }
      else
      {
        v114 = lpszHostName;
      }
    }
    else
    {
      v106 = v33;
      v114 = 0;
      v104 = dwHostNameLength;
      v105 = v34;
    }
LABEL_54:
    v39 = lpUrlComponents;
    v40 = 0;
    lpMem = 0;
    ppszDestEnd = 0;
    lpszUserName = lpUrlComponents->lpszUserName;
    dwUserNameLength = lpUrlComponents->dwUserNameLength;
    v112 = (unsigned __int16 *)lpszUserName;
    v108 = dwUserNameLength;
    v125 = dwUserNameLength;
    if ( !lpszUserName )
    {
      dwUserNameLength = 0;
      v108 = 0;
      v43 = 0;
      goto LABEL_56;
    }
    if ( dwUserNameLength )
    {
LABEL_227:
      if ( v32 )
      {
        v125 = 129;
        v90 = (unsigned __int16 *)HeapAlloc(g_hWxProcessHeap, 0, 0x102u);
        lpMem = v90;
        v43 = v90;
        if ( !v90 )
        {
          v30 = 8;
          goto LABEL_203;
        }
        v30 = EncodeAuthorityComponentW(v112, dwUserNameLength, v90, &v125);
        if ( v30 )
        {
          v70 = pdwUrlLength;
          v69 = (int)v100;
LABEL_249:
          HeapFree(g_hWxProcessHeap, 0, v43);
LABEL_112:
          if ( v40 )
            HeapFree(g_hWxProcessHeap, 0, v40);
LABEL_114:
          v71 = v106;
          if ( !v106 )
          {
LABEL_115:
            v7 = v119;
            v8 = v121;
            goto LABEL_116;
          }
          goto LABEL_251;
        }
        dwUserNameLength = v125;
        lpszUserName = (LPSTR)v43;
        LODWORD(v38) = v115;
        v39 = lpUrlComponents;
        v108 = v125;
        v112 = v43;
      }
      else
      {
        v43 = 0;
      }
LABEL_56:
      lpszPassword = v39->lpszPassword;
      v118 = lpszPassword;
      if ( lpszPassword )
      {
        dwPasswordLength = v39->dwPasswordLength;
        if ( !dwPasswordLength )
        {
          v83 = 0x7FFFFFFF;
          v125 = 0;
          v84 = lpszPassword;
          do
          {
            if ( !*v84 )
              break;
            ++v84;
            --v83;
          }
          while ( v83 );
          v85 = -2147024809;
          if ( v83 )
            v85 = 0;
          v86 = 0x7FFFFFFF - v83;
          if ( !v83 )
            v86 = 0;
          dwPasswordLength = v86;
          if ( !v83 )
            dwPasswordLength = 0;
          v30 = WX_WIN32_FROM_HR(v85);
          if ( v30 )
            goto LABEL_109;
          lpszPassword = v118;
          lpszUserName = (LPSTR)v112;
          v39 = lpUrlComponents;
        }
        if ( v32 )
        {
          v125 = 129;
          v87 = (unsigned __int16 *)HeapAlloc(g_hWxProcessHeap, 0, 0x102u);
          v40 = v87;
          if ( !v87 )
          {
            v30 = 8;
            goto LABEL_109;
          }
          v30 = EncodeAuthorityComponentW((const unsigned __int16 *)lpszPassword, dwPasswordLength, v87, &v125);
          if ( v30 )
            goto LABEL_109;
          lpszUserName = (LPSTR)v112;
          v39 = lpUrlComponents;
          dwPasswordLength = v125;
          v118 = v40;
        }
        if ( !lpszUserName )
        {
          v30 = 87;
          goto LABEL_109;
        }
        LODWORD(v38) = v115;
        ppszDestEnd = v40;
      }
      else
      {
        dwPasswordLength = 0;
      }
      v125 = 0;
      if ( (v101 & 4) != 0 && (dwFlags & 0x4000) != 0 )
      {
        v112 = 0;
        v118 = 0;
      }
      lpszUrlPath = v39->lpszUrlPath;
      v107 = lpszUrlPath;
      if ( lpszUrlPath )
      {
        dwUrlPathLength = v39->dwUrlPathLength;
        if ( !dwUrlPathLength )
        {
          v124 = 0;
          v47 = 0x7FFFFFFF;
          v48 = lpszUrlPath;
          do
          {
            if ( !*v48 )
              break;
            ++v48;
            --v47;
          }
          while ( v47 );
          v30 = -2147024809;
          if ( v47 )
          {
            v30 = 0;
            dwUrlPathLength = 0x7FFFFFFF - v47;
          }
          else
          {
            v124 = 81;
            dwUrlPathLength = 0;
          }
          if ( !v47 )
          {
            if ( (v30 & 0x1FFF0000) == 0x70000 )
            {
              v49 = (unsigned __int16)v30;
              if ( !(_WORD)v30 )
                v49 = 317;
              v30 = v49;
              goto LABEL_108;
            }
            if ( v30 )
            {
LABEL_108:
              v43 = lpMem;
LABEL_109:
              v70 = pdwUrlLength;
              goto LABEL_110;
            }
          }
        }
        if ( *lpszUrlPath != 47 && *lpszUrlPath != 92 && (dwUserNameLength || dwHostNameLength || (_DWORD)v38) )
          v125 = 1;
        v50 = dwFlags & 0x80000000;
        v98 = v50;
        if ( v50 )
        {
          v51 = v102;
          if ( v102 )
          {
            v30 = CStringTemplate<unsigned short>::SetString(&v119, lpszUrlPath, dwUrlPathLength);
            if ( v30 )
              goto LABEL_108;
            v52 = v101;
            v30 = EncodeUrlPathAsAnsi(1u, v101, (struct CUnicodeString *)&v119);
            if ( v30 )
              goto LABEL_108;
            v107 = v119;
            dwUrlPathLength = v120 - 1;
            if ( !(_DWORD)v120 )
              dwUrlPathLength = 0;
            v39 = lpUrlComponents;
LABEL_78:
            lpszExtraInfo = v39->lpszExtraInfo;
            v111 = lpszExtraInfo;
            if ( !lpszExtraInfo )
            {
LABEL_79:
              dwExtraInfoLength = 0;
              goto LABEL_80;
            }
            dwExtraInfoLength = v39->dwExtraInfoLength;
            if ( !dwExtraInfoLength )
            {
              v124 = 0;
              v80 = 0x7FFFFFFF;
              v81 = lpszExtraInfo;
              do
              {
                if ( !*v81 )
                  break;
                ++v81;
                --v80;
              }
              while ( v80 );
              v82 = -2147024809;
              if ( v80 )
              {
                v82 = 0;
                dwExtraInfoLength = 0x7FFFFFFF - v80;
              }
              else
              {
                v124 = 81;
                dwExtraInfoLength = 0;
              }
              v30 = WX_WIN32_FROM_HR(v82);
              if ( v30 )
                goto LABEL_108;
              lpszExtraInfo = v111;
            }
            if ( v98 && v51 )
            {
              v30 = CStringTemplate<unsigned short>::SetString(&v121, lpszExtraInfo, dwExtraInfoLength);
              if ( v30 )
                goto LABEL_108;
              v30 = EncodeUrlPathAsAnsi(0, v52, (struct CUnicodeString *)&v121);
              if ( v30 )
                goto LABEL_108;
              v111 = (CHAR *)v121;
              if ( !(_DWORD)v122 )
                goto LABEL_79;
              dwExtraInfoLength = v122 - 1;
            }
LABEL_80:
            v55 = 0;
            v56 = v114 != 0;
            while ( v55 < 5 )
            {
              v57 = 5LL * v55;
              if ( LODWORD(qword_1800DF730[v57 + 2]) == v103
                && !(unsigned int)_o__wcsnicmp(qword_1800DF730[v57 + 1], Src, v103) )
              {
                LODWORD(v56) = HIDWORD(qword_1800DF730[v57 + 3]);
                break;
              }
              ++v55;
            }
            v58 = 3;
            v59 = L"://";
            v60 = 3;
            if ( !(_DWORD)v56 )
            {
              v60 = 1;
              v59 = L":";
            }
            if ( v112 )
              v61 = v108 + 1;
            else
              v61 = 0;
            if ( v118 )
              v62 = dwPasswordLength + 1;
            else
              v62 = 0;
            v63 = 0;
            if ( !v105 )
              v58 = 1;
            LOBYTE(v63) = v125 != 0;
            v64 = v104 + v60 + v61 + v62 + v103 + v115 + dwUrlPathLength + v58 + dwExtraInfoLength + v63;
            if ( *pdwUrlLength >= v64 )
            {
              if ( v100 )
              {
                v65 = v128;
                memcpy_0(v100, Src, 2 * v128);
                memcpy_0(&v100[v65], v59, 2 * v60);
                v66 = &v100[v65 + v60];
                if ( v112 )
                {
                  memcpy_0(v66, v112, 2LL * v108);
                  v91 = (char *)&v66[v108];
                  if ( v118 )
                  {
                    v92 = v118;
                    *(_WORD *)v91 = 58;
                    v93 = v91 + 2;
                    memcpy_0(v93, v92, 2LL * dwPasswordLength);
                    v91 = &v93[2 * dwPasswordLength];
                  }
                  *(_WORD *)v91 = 64;
                  v66 = (WCHAR *)(v91 + 2);
                }
                if ( v114 )
                {
                  if ( v105 )
                    *v66++ = 91;
                  memcpy_0(v66, v114, 2LL * v104);
                  v66 += v104;
                  if ( v105 )
                    *v66++ = 93;
                  if ( v115 )
                  {
                    memcpy_0(v66, v123, 2LL * v115);
                    v66 += v115;
                  }
                }
                if ( v125 )
                  *v66++ = 47;
                memcpy_0(v66, v107, 2LL * dwUrlPathLength);
                v67 = &v66[dwUrlPathLength];
                v68 = dwExtraInfoLength;
                memcpy_0(v67, v111, v68 * 2);
                v69 = (int)v100;
                v70 = pdwUrlLength;
                v43 = lpMem;
                v40 = ppszDestEnd;
                v67[v68] = 0;
                *pdwUrlLength = &v67[v68] - v100;
                v30 = 0;
              }
              else
              {
                v43 = lpMem;
                v30 = 87;
                v40 = ppszDestEnd;
                v70 = pdwUrlLength;
                v69 = 0;
              }
LABEL_111:
              if ( !v43 )
                goto LABEL_112;
              goto LABEL_249;
            }
            v43 = lpMem;
            v30 = 122;
            v40 = ppszDestEnd;
            v70 = pdwUrlLength;
            *pdwUrlLength = v64;
LABEL_110:
            v69 = (int)v100;
            goto LABEL_111;
          }
          v98 = v50;
LABEL_77:
          v52 = v101;
          goto LABEL_78;
        }
        v98 = 0;
      }
      else
      {
        dwUrlPathLength = 0;
        v98 = dwFlags & 0x80000000;
      }
      v51 = v102;
      goto LABEL_77;
    }
    v89 = WxStringCchLengthDWordW(lpszUserName, 0x7FFFFFFF, &v125);
    v30 = WX_WIN32_FROM_HR(v89);
    if ( !v30 )
    {
      dwUserNameLength = v125;
      lpszUserName = (LPSTR)v112;
      LODWORD(v38) = v115;
      v39 = lpUrlComponents;
      v108 = v125;
      goto LABEL_227;
    }
LABEL_203:
    v70 = pdwUrlLength;
    v69 = (int)v100;
    goto LABEL_114;
  }
  v125 = 257;
  v88 = (unsigned __int16 *)HeapAlloc(g_hWxProcessHeap, 0, 0x202u);
  v71 = v88;
  if ( !v88 )
  {
    v7 = v119;
    v30 = 8;
    v8 = v121;
    goto LABEL_150;
  }
  v30 = EncodeAuthorityComponentW(lpszHostName, dwHostNameLength, v88, &v125);
  if ( !v30 )
  {
    dwHostNameLength = v125;
    v33 = v71;
    v31 = dwFlags;
    lpszHostName = v71;
    v104 = v125;
    goto LABEL_44;
  }
  v70 = pdwUrlLength;
  v69 = (int)v100;
LABEL_251:
  HeapFree(g_hWxProcessHeap, 0, v71);
  v7 = v119;
  v8 = v121;
LABEL_116:
  if ( (xmmword_180107A60 & 2) != 0 )
  {
    if ( v30 )
      LOBYTE(v94) = 0;
    else
      v94 = *v70;
    if ( v30 )
      v69 = 0;
    WPP_SF_Sd(1025, 16, (unsigned int)WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids, v69, v94);
  }
  if ( v30 && (xmmword_180107A50 & 4) != 0 )
    WPP_SF_d(514, 17, WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids, v30, *(_QWORD *)dwFlagsa);
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 18, WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids, v30 == 0, *(_QWORD *)dwFlagsa);
  if ( v127 )
  {
    DWORD1(v128) = 0;
    v72 = EtwEventActivityIdControl(2, &v126);
    v73 = v72 < 0;
    if ( v72 > 0 )
      v73 = 1;
    if ( v73 )
      DWORD1(v128) = 144;
  }
  SetLastError(v30);
  if ( v8 )
    operator delete(v8);
  if ( v7 )
    operator delete(v7);
  return v30 == 0;
}

```

## disassembly

```asm
0x1800441f0  mov     r11, rsp
0x1800441f3  push    rbp
0x1800441f4  push    rdi
0x1800441f5  push    r15
0x1800441f7  lea     rbp, [r11-0A8h]
0x1800441fe  sub     rsp, 190h
0x180044205  mov     rax, cs:__security_cookie
0x18004420c  xor     rax, rsp
0x18004420f  mov     [rbp+0A0h+var_38], rax
0x180044213  mov     [r11+10h], rbx
0x180044217  xorps   xmm0, xmm0
0x18004421a  mov     [r11-20h], rsi
0x18004421e  mov     rbx, r9
0x180044221  mov     [r11-28h], r12
0x180044225  mov     eax, edx
0x180044227  mov     [r11-30h], r13
0x18004422b  mov     r12, rcx
0x18004422e  mov     [r11-38h], r14
0x180044232  xor     r11d, r11d
0x180044235  mov     [rbp+0A0h+var_110], rcx
0x180044239  mov     r15d, r11d
0x18004423c  xor     ecx, ecx
0x18004423e  mov     [rsp+1A0h+var_158], rbx
0x180044243  cmp     cs:?WinHttpEtwInitialized@@3EA, cl; uchar WinHttpEtwInitialized
0x180044249  mov     r13d, r11d
0x18004424c  mov     [rsp+1A0h+var_150], r8
0x180044251  mov     r14d, 1
0x180044257  mov     dword ptr [rsp+1A0h+var_160], edx
0x18004425b  mov     [rbp+0A0h+var_D0], r11
0x18004425f  mov     [rbp+0A0h+var_C8], r11
0x180044263  mov     [rbp+0A0h+var_C0], r11
0x180044267  mov     [rbp+0A0h+var_B8], r11
0x18004426b  movups  [rbp+0A0h+var_98], xmm0
0x18004426f  mov     [rbp+0A0h+var_88], ecx
0x180044272  jz      loc_180044391
0x180044278  mov     ecx, 10h
0x18004427d  lea     rax, [rbp+0A0h+var_98]
0x180044281  mov     [rax], r11b
0x180044284  lea     rax, [rax+1]
0x180044288  sub     rcx, r14
0x18004428b  jnz     short loc_180044281
0x18004428d  xorps   xmm0, xmm0
0x180044290  mov     [rbp+0A0h+var_88], r11d
0x180044294  xorps   xmm1, xmm1
0x180044297  lea     rax, [rbp+0A0h+var_98]
0x18004429b  movups  xmmword ptr [rbp+0A0h+var_70.Data1], xmm0
0x18004429f  mov     ecx, 10h
0x1800442a4  movups  [rbp+0A0h+var_60], xmm1
0x1800442a8  nop     dword ptr [rax+rax+00000000h]
0x1800442b0  mov     [rax], r11b
0x1800442b3  lea     rax, [rax+1]
0x1800442b7  sub     rcx, r14
0x1800442ba  jnz     short loc_1800442B0
0x1800442bc  xorps   xmm0, xmm0
0x1800442bf  mov     dword ptr [rsp+1A0h+var_128+4], r11d
0x1800442c4  movups  [rbp+0A0h+var_80], xmm0
0x1800442c8  mov     ecx, 10h
0x1800442cd  lea     rax, [rbp+0A0h+var_60]
0x1800442d1  mov     [rax], r11b
0x1800442d4  lea     rax, [rax+1]
0x1800442d8  sub     rcx, r14
0x1800442db  jnz     short loc_1800442D1
0x1800442dd  lea     rdx, [rbp+0A0h+var_80]
0x1800442e1  mov     ecx, r14d
0x1800442e4  call    cs:__imp_EtwEventActivityIdControl
0x1800442ea  test    eax, eax
0x1800442ec  jle     short loc_1800442F8
0x1800442ee  movzx   eax, ax
0x1800442f1  or      eax, 80070000h
0x1800442f6  test    eax, eax
0x1800442f8  js      loc_180044DF2
0x1800442fe  movaps  xmm0, [rbp+0A0h+var_80]
0x180044302  movdqa  [rbp+0A0h+var_60], xmm0
0x180044307  mov     rdi, [rbp+0A8h]
0x18004430e  mov     esi, r14d
0x180044311  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180044319  inc     esi
0x18004431b  call    cs:__imp_GetTickCount
0x180044321  mov     ebx, eax
0x180044323  call    cs:__imp_GetCurrentProcessId
0x180044329  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, r13d; int g_fEtwCorrelationProviderInitialized
0x180044330  mov     dword ptr [rbp+0A0h+var_70.Data4+4], eax
0x180044333  mov     [rbp+0A0h+var_70.Data1], edi
0x180044336  mov     dword ptr [rbp+0A0h+var_70.Data2], esi
0x180044339  mov     dword ptr [rbp+0A0h+var_70.Data4], ebx
0x18004433c  jz      short loc_18004434C
0x18004433e  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180044344  test    eax, eax
0x180044346  jnz     loc_180044C0C
0x18004434c  lea     rdx, [rbp+0A0h+var_70]
0x180044350  mov     dword ptr [rsp+1A0h+var_128+4], r13d
0x180044355  mov     ecx, 2
0x18004435a  call    cs:__imp_EtwEventActivityIdControl
0x180044360  test    eax, eax
0x180044362  jle     short loc_18004436E
0x180044364  movzx   eax, ax
0x180044367  or      eax, 80070000h
0x18004436c  test    eax, eax
0x18004436e  js      loc_180044E4E
0x180044374  movaps  xmm0, [rbp+0A0h+var_60]
0x180044378  xor     r11d, r11d
0x18004437b  mov     eax, dword ptr [rsp+1A0h+var_160]
0x18004437f  mov     rbx, [rsp+1A0h+var_158]
0x180044384  mov     r8, [rsp+1A0h+var_150]
0x180044389  movups  [rbp+0A0h+var_98], xmm0
0x18004438d  mov     [rbp+0A0h+var_88], r14d
0x180044391  test    byte ptr cs:xmmword_180107A60, 4
0x180044398  jnz     loc_180044E5B
0x18004439e  test    rbx, rbx
0x1800443a1  jz      loc_180044C61
0x1800443a7  test    r12, r12
0x1800443aa  jz      loc_180044C61
0x1800443b0  cmp     dword ptr [r12], 68h ; 'h'
0x1800443b5  jnz     loc_180044C61
0x1800443bb  test    eax, 7FFF1FFFh
0x1800443c0  jnz     loc_180044C61
0x1800443c6  mov     r13, [r12+8]
0x1800443cb  mov     eax, 4
0x1800443d0  mov     [rbp+0A0h+Src], r13
0x1800443d4  mov     edi, 80070057h
0x1800443d9  mov     [rsp+1A0h+var_148], eax
0x1800443dd  test    r13, r13
0x1800443e0  jz      loc_1800449E9
0x1800443e6  mov     r15d, [r12+10h]
0x1800443eb  mov     [rsp+1A0h+var_140], r15d
0x1800443f0  test    r15d, r15d
0x1800443f3  jz      loc_180044BA8
0x1800443f9  xor     ebx, ebx
0x1800443fb  lea     r14, qword_1800DF730
0x180044402  cmp     ebx, 5
0x180044405  jnb     loc_180044AAB
0x18004440b  lea     rcx, [rbx+rbx*4]
0x18004440f  lea     rdi, ds:0[rcx*8]
0x180044417  cmp     [rdi+r14+10h], r15d
0x18004441c  jz      short loc_180044422
0x18004441e  inc     ebx
0x180044420  jmp     short loc_180044402
0x180044422  mov     rcx, [rdi+r14+8]
0x180044427  mov     rdx, r13
0x18004442a  mov     r8d, r15d
0x18004442d  call    cs:__imp__o__wcsnicmp
0x180044433  test    eax, eax
0x180044435  jnz     short loc_18004441E
0x180044437  mov     esi, [rdi+r14+14h]
0x18004443c  mov     edi, 80070057h
0x180044441  test    r15d, r15d
0x180044444  jz      loc_180044C56
0x18004444a  mov     ebx, r15d
0x18004444d  lea     rdx, aHttp_4; "http"
0x180044454  mov     r8d, r15d
0x180044457  mov     rcx, r13
0x18004445a  mov     qword ptr [rbp+0A0h+var_80], rbx
0x18004445e  mov     qword ptr [rsp+70h], 0
0x180044467  call    cs:__imp__o__wcsnicmp
0x18004446d  test    eax, eax
0x18004446f  jnz     loc_180044A25
0x180044475  mov     [rsp+1A0h+var_144], 1
0x18004447d  xor     r11d, r11d
0x180044480  mov     rbx, [r12+18h]
0x180044485  mov     [rbp+0A0h+var_F8], rbx
0x180044489  test    rbx, rbx
0x18004448c  jz      loc_180044677
0x180044492  mov     r13d, [r12+20h]
0x180044497  mov     [rsp+64h], r13d
0x18004449c  test    r13d, r13d
0x18004449f  jnz     short loc_1800444EC
0x1800444a1  mov     dword ptr [rsp+1A0h+var_128+4], r11d
0x1800444a6  mov     ecx, 7FFFFFFFh
0x1800444ab  mov     [rbp+0A0h+var_A0], r11d
0x1800444af  mov     rax, rbx
0x1800444b2  cmp     word ptr [rax], 0
0x1800444b6  jz      short loc_1800444C2
0x1800444b8  add     rax, 2
0x1800444bc  sub     rcx, 1
0x1800444c0  jnz     short loc_1800444B2
0x1800444c2  test    rcx, rcx
0x1800444c5  mov     ebx, edi
0x1800444c7  cmovnz  ebx, r11d
0x1800444cb  jz      loc_180044C6B
0x1800444d1  mov     r13d, 7FFFFFFFh
0x1800444d7  sub     r13d, ecx
0x1800444da  mov     [rsp+64h], r13d
0x1800444df  test    rcx, rcx
0x1800444e2  jz      loc_180044AB5
0x1800444e8  mov     rbx, [rbp+0A0h+var_F8]
0x1800444ec  mov     r9d, dword ptr [rsp+1A0h+var_160]
0x1800444f1  mov     edi, r9d
0x1800444f4  and     edi, 2000h
0x1800444fa  jnz     loc_180044F35
0x180044500  mov     r11, [rsp+70h]
0x180044505  xor     r15d, r15d
0x180044508  mov     [rsp+70h], r11
0x18004450d  xor     r8d, r8d
0x180044510  mov     dword ptr [rsp+1A0h+var_138], r15d
0x180044515  xor     edx, edx
0x180044517  cmp     edx, r13d
0x18004451a  jnb     short loc_18004455A
0x18004451c  cmp     word ptr [rbx+rdx*2], 3Ah ; ':'
0x180044521  lea     ecx, [r8+1]
0x180044525  cmovnz  ecx, r8d
0x180044529  mov     r8d, ecx
0x18004452c  cmp     ecx, 1
0x18004452f  ja      short loc_180044535
0x180044531  inc     edx
0x180044533  jmp     short loc_180044517
0x180044535  cmp     word ptr [rbx], 5Bh ; '['
0x180044539  mov     r15d, 1
0x18004453f  mov     dword ptr [rsp+1A0h+var_138], r15d
0x180044544  jnz     short loc_18004455A
0x180044546  xor     eax, eax
0x180044548  lea     ecx, [r13-1]
0x18004454c  cmp     word ptr [rbx+rcx*2], 5Dh ; ']'
0x180044551  cmovz   r15d, eax
0x180044555  mov     dword ptr [rsp+1A0h+var_138], r15d
0x18004455a  xor     edx, edx
0x18004455c  mov     [rbp+0A0h+var_B0], 0
0x180044564  mov     [rbp+0A0h+var_F0], rdx
0x180044568  test    rbx, rbx
0x18004456b  jnz     loc_1800449AC
0x180044571  mov     [rsp+70h], r11
0x180044576  xor     r11d, r11d
0x180044579  mov     [rbp+0A0h+var_F8], rbx
0x18004457d  mov     [rsp+64h], r13d
0x180044582  mov     dword ptr [rsp+1A0h+var_138], r15d
0x180044587  mov     r8, [rbp+0A0h+var_110]
0x18004458b  mov     r12, r11
0x18004458e  mov     [rbp+0A0h+lpMem], r11
0x180044592  mov     [rbp+0A0h+ppszDestEnd], r11
0x180044596  mov     r10, [r8+28h]
0x18004459a  mov     esi, [r8+30h]
0x18004459e  mov     [rbp+0A0h+var_108], r10
0x1800445a2  mov     [rbp+0A0h+var_120], esi
0x1800445a5  mov     [rbp+0A0h+var_A0], esi
0x1800445a8  test    r10, r10
0x1800445ab  jnz     loc_180044FAB
0x1800445b1  mov     esi, r11d
0x1800445b4  mov     [rbp+0A0h+var_120], r11d
0x1800445b8  mov     r15, r11
0x1800445bb  mov     rbx, [r8+38h]
0x1800445bf  mov     [rbp+0A0h+var_D8], rbx
0x1800445c3  test    rbx, rbx
0x1800445c6  jnz     loc_180044D34
0x1800445cc  mov     [rbp+0A0h+var_100], r11d
0x1800445d0  test    byte ptr [rsp+1A0h+var_148], 4
0x1800445d5  mov     r10d, dword ptr [rsp+1A0h+var_160]
0x1800445da  setnz   cl
0x1800445dd  mov     [rbp+0A0h+var_A0], r11d
0x1800445e1  bt      r10d, 0Eh
0x1800445e6  setb    al
0x1800445e9  test    al, cl
0x1800445eb  jnz     loc_180044C49
0x1800445f1  mov     r9, [r8+48h]
0x1800445f5  mov     [rsp+1A0h+var_128], r9
0x1800445fa  test    r9, r9
0x1800445fd  jz      loc_180044B59
0x180044603  mov     r15d, [r8+50h]
0x180044607  test    r15d, r15d
0x18004460a  jnz     loc_18004469E
0x180044610  mov     [rbp+0A0h+var_A4], r11d
0x180044614  mov     ecx, 7FFFFFFFh
0x180044619  mov     dword ptr [rsp+1A0h+var_160], r11d
0x18004461e  mov     rax, r9
0x180044621  cmp     word ptr [rax], 0
0x180044625  jz      short loc_180044631
0x180044627  add     rax, 2
0x18004462b  sub     rcx, 1
0x18004462f  jnz     short loc_180044621
0x180044631  test    rcx, rcx
0x180044634  mov     ebx, 80070057h
0x180044639  cmovnz  ebx, r11d
0x18004463d  jz      loc_180044C21
0x180044643  mov     r15d, 7FFFFFFFh
0x180044649  sub     r15d, ecx
0x18004464c  test    rcx, rcx
0x18004464f  jnz     short loc_18004469E
0x180044651  mov     eax, ebx
0x180044653  and     eax, 1FFF0000h
0x180044658  cmp     eax, 70000h
0x18004465d  jnz     loc_1800448AF
0x180044663  movzx   eax, bx
0x180044666  mov     ebx, 13Dh
0x18004466b  test    eax, eax
0x18004466d  cmovz   eax, ebx
0x180044670  mov     ebx, eax
0x180044672  jmp     loc_1800448B7
0x180044677  mov     edi, dword ptr [rsp+1A0h+var_160]
0x18004467b  mov     edx, r11d
0x18004467e  and     edi, 2000h
0x180044684  mov     [rbp+0A0h+var_F0], rdx
0x180044688  mov     dword ptr [rsp+1A0h+var_138], r11d
0x18004468d  mov     r13d, r11d
0x180044690  mov     [rsp+64h], r11d
0x180044695  mov     [rbp+0A0h+var_B0], r11
0x180044699  jmp     loc_180044587
0x18004469e  movzx   eax, word ptr [r9]
0x1800446a2  cmp     ax, 2Fh ; '/'
0x1800446a6  jnz     loc_180044B6D
0x1800446ac  and     r10d, 80000000h
0x1800446b3  mov     dword ptr [rsp+1A0h+var_160], r10d
0x1800446b8  jnz     loc_1800450CF
  ... truncated ...
```
