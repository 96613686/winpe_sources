# InternalInternetGetCookieEx2(ushort const *,ushort const *,ulong,INTERNET_COOKIE2 * *,ulong *)

- ea: `0x1800dd1a0`
- end: `0x1800ddccc`
- name: `?InternalInternetGetCookieEx2@@YAKPEBG0KPEAPEAUINTERNET_COOKIE2@@PEAK@Z`
- size: `2860`
- prototype: `unsigned int __usercall@<eax>(LPCWCH lpWideCharStr@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct INTERNET_COOKIE2 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800dd140`

## callees

- `0x18000660c`
- `0x180009cf0`
- `0x18000b8b4`
- `0x180017674`
- `0x18006dd10`
- `0x18006f5e0`
- `0x1800701d0`
- `0x1800967e8`
- `0x1800c2d90`
- `0x1800c7560`
- `0x1800c78bc`
- `0x1800dcfc0`
- `0x1800dd1a0`
- `0x1800ef8a4`
- `0x1800fa3ac`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x18015fea8`
- `0x18017ffe8`
- `0x1801804e4`
- `0x180191aac`
- `0x1801d5c08`
- `0x1801e1790`
- `0x1801e285c`
- `0x1801ec86c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ddc5f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ddc7e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ddc5f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ddc7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dda2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ddb4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dda2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ddb4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dd7c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dd7c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dd6ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dd6ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dd71f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dda56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dda6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dda8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddaa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddb74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddbf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddc30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddc45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dd71f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dda56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dda6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dda8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddaa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddb74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddbf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddc30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ddc45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800dd782`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800dd782`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dd696`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dd6f1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dd696`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dd6f1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800dd472`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800dd472`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800dd9b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800dd9b3`

## pseudocode

```c
__int64 __fastcall InternalInternetGetCookieEx2(
        LPCWCH lpWideCharStr,
        const unsigned __int16 *a2,
        int a3,
        struct INTERNET_COOKIE2 **a4,
        unsigned int *a5)
{
  unsigned int *v6; // rcx
  INTERNET_COOKIE2 *v7; // rsi
  DWORD v8; // r14d
  signed int AllCookies; // r15d
  int v12; // eax
  __int64 v13; // rcx
  bool v14; // zf
  CHAR *v15; // rdi
  __int64 v16; // rdx
  unsigned __int64 cchCount2; // rcx
  __int64 v18; // rdx
  const WCHAR *v19; // rax
  int v20; // r15d
  int v21; // r9d
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r10
  unsigned __int64 v24; // rdx
  LPCWCH i; // rax
  unsigned __int64 v26; // r8
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  const WCHAR *v30; // rax
  unsigned __int64 v31; // r8
  int v32; // r15d
  int v33; // r9d
  __int64 v34; // r8
  __int64 v35; // r10
  __int64 v36; // rcx
  LPCWCH v37; // rax
  __int64 v38; // r8
  __int64 v39; // rdx
  CHAR *v40; // rbx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  const char *v44; // rdi
  void *v45; // r13
  int LastError; // eax
  int v47; // eax
  const WCHAR *v48; // r15
  _BYTE *v49; // rbx
  unsigned int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rcx
  int v53; // edi
  bool v54; // sf
  DWORD ZoneFromUrl; // eax
  unsigned int CookieMainSwitch; // r13d
  int v57; // ebx
  int v58; // r8d
  struct CCookieLocation *v59; // r12
  const char *v60; // rax
  _BYTE *j; // rcx
  int v62; // r14d
  _BYTE *v63; // rax
  _BYTE *k; // rcx
  __int64 v65; // rdi
  unsigned int v66; // ecx
  __int64 v67; // rsi
  int v68; // eax
  unsigned int v69; // ebx
  unsigned int v70; // eax
  __int64 result; // rax
  struct CCookieHost *v72; // r14
  unsigned int v73; // r15d
  void **v74; // rbx
  void *v75; // r8
  void **v76; // rsi
  void **v77; // rdi
  void **v78; // rbx
  void *v79; // r8
  void **v80; // rbx
  void *v81; // r8
  __int64 v82; // rbx
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-79h]
  __int64 v84; // [rsp+40h] [rbp-71h] BYREF
  LPCCH lpMultiByteStr; // [rsp+48h] [rbp-69h] BYREF
  int v86; // [rsp+50h] [rbp-61h]
  DWORD dwCookieCount; // [rsp+54h] [rbp-5Dh] BYREF
  LPVOID v88; // [rsp+58h] [rbp-59h]
  LPVOID lpMem; // [rsp+60h] [rbp-51h]
  int v90; // [rsp+68h] [rbp-49h]
  LPCSTR v91; // [rsp+70h] [rbp-41h]
  int v92; // [rsp+78h] [rbp-39h]
  int v93; // [rsp+7Ch] [rbp-35h]
  int v94; // [rsp+80h] [rbp-31h]
  INTERNET_COOKIE2 *pCookies; // [rsp+88h] [rbp-29h] BYREF
  unsigned int *v96; // [rsp+90h] [rbp-21h]
  LPCWCH lpWideCharStra; // [rsp+98h] [rbp-19h]
  struct INTERNET_COOKIE2 **v98; // [rsp+A0h] [rbp-11h]
  unsigned int v99; // [rsp+A8h] [rbp-9h] BYREF
  struct CCookieHost *v100; // [rsp+B0h] [rbp-1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp+7h] BYREF

  lpWideCharStra = a2;
  v98 = a4;
  v6 = a5;
  v7 = 0;
  v96 = a5;
  v8 = 0;
  pCookies = 0;
  lpMem = 0;
  v88 = 0;
  v90 = 0;
  lpMultiByteStr = 0;
  v99 = 0;
  SystemTimeAsFileTime = 0;
  dwCookieCount = 0;
  v84 = 0;
  v100 = 0;
  if ( (xmmword_180266B60 & 0x40) != 0 )
  {
    WPP_SF_SSdqq((_DWORD)a5, 0, a3, (_DWORD)lpWideCharStr, (__int64)a2, a3, (__int64)a4, (__int64)a5);
    v6 = v96;
  }
  if ( !lpWideCharStr )
  {
    AllCookies = -2147024809;
    HIDWORD(v84) = 7266;
    goto LABEL_180;
  }
  if ( !a4 )
  {
    AllCookies = -2147024809;
    HIDWORD(v84) = 7267;
    goto LABEL_180;
  }
  if ( !v6 )
  {
    AllCookies = -2147024809;
    HIDWORD(v84) = 7268;
    goto LABEL_180;
  }
  if ( (a3 & 0xDFB9EFEF) != 0 )
  {
    AllCookies = -2147024809;
    HIDWORD(v84) = 7269;
    goto LABEL_180;
  }
  *a4 = 0;
  *v6 = 0;
  v12 = GlobalDataInitialize();
  AllCookies = v12;
  if ( v12 > 0 )
    AllCookies = (unsigned __int16)v12 | 0x80070000;
  if ( AllCookies < 0 )
  {
    HIDWORD(v84) = 7274;
    goto LABEL_180;
  }
  v13 = -1;
  do
    ++v13;
  while ( lpWideCharStr[v13] );
  if ( (a3 & 0x20000000) != 0 )
  {
    if ( v13 )
    {
      AllCookies = -2147024809;
      HIDWORD(v84) = 7282;
    }
    else if ( (a3 & 0xDFFFFFFF) != 0 )
    {
      AllCookies = -2147024809;
      HIDWORD(v84) = 7283;
    }
    else
    {
      AllCookies = CCookieJar::RetrieveAllCookies(a4, v96);
      if ( AllCookies >= 0 )
        AllCookies = 0;
      else
        HIDWORD(v84) = 7284;
    }
    goto LABEL_180;
  }
  v14 = *lpWideCharStr == 58;
  v15 = 0;
  v91 = 0;
  LODWORD(v16) = 0;
  if ( !v14 )
  {
    while ( (_DWORD)v13 && lpWideCharStr[(unsigned int)v16] )
    {
      v16 = (unsigned int)(v16 + 1);
      LODWORD(v13) = v13 - 1;
      if ( lpWideCharStr[v16] == 58 )
        goto LABEL_29;
    }
    goto LABEL_83;
  }
LABEL_29:
  cchCount2 = (int)v16;
  switch ( (_DWORD)v16 )
  {
    case 4:
      v18 = 4;
      v19 = L"http";
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --v18;
      }
      while ( v18 );
      v20 = -2147024809;
      v21 = -2147024809;
      if ( v18 )
      {
        v21 = 0;
        v22 = cchCount2 - v18;
      }
      else
      {
        v22 = 0;
      }
      if ( !v18 )
        v22 = 0;
      v23 = cchCount2;
      if ( v21 >= 0 )
        v23 = v22;
      if ( cchCount2 > 0x7FFFFFFF )
        goto LABEL_48;
      v24 = cchCount2;
      for ( i = lpWideCharStr; v24; --v24 )
      {
        if ( !*i )
          break;
        ++i;
      }
      if ( v24 )
      {
        v20 = 0;
        v26 = cchCount2 - v24;
      }
      else
      {
        v26 = 0;
      }
      if ( !v24 )
LABEL_48:
        v26 = 0;
      if ( v20 >= 0 )
        cchCount2 = v26;
      if ( v23 == cchCount2 )
      {
        v27 = CompareStringW(0x7Fu, 1u, L"http", v23, lpWideCharStr, cchCount2);
        goto LABEL_53;
      }
      break;
    case 5:
      v29 = 5;
      v30 = L"https";
      v31 = cchCount2;
      do
      {
        if ( !*v30 )
          break;
        ++v30;
        --cchCount2;
      }
      while ( cchCount2 );
      v32 = -2147024809;
      v33 = -2147024809;
      if ( cchCount2 )
      {
        v33 = 0;
        v34 = v31 - cchCount2;
      }
      else
      {
        v34 = 0;
      }
      if ( !cchCount2 )
        v34 = 0;
      v35 = 5;
      if ( v33 >= 0 )
        v35 = v34;
      v36 = 5;
      v37 = lpWideCharStr;
      do
      {
        if ( !*v37 )
          break;
        ++v37;
        --v36;
      }
      while ( v36 );
      if ( v36 )
      {
        v32 = 0;
        v38 = 5 - v36;
      }
      else
      {
        v38 = 0;
      }
      if ( !v36 )
        v38 = 0;
      if ( v32 >= 0 )
        v29 = v38;
      if ( v35 == v29 )
      {
        v27 = CompareStringW(0x7Fu, 1u, L"https", v35, lpWideCharStr, v29);
LABEL_53:
        if ( v27 == 2 )
        {
          v28 = UrlWCharToChar(lpWideCharStr, -1, &lpMultiByteStr, &v99);
          goto LABEL_84;
        }
      }
      break;
    case 6:
      if ( !(unsigned int)CompareStringNW(L"cookie", lpWideCharStr, 6) )
      {
        v28 = CookieWCharToChar(lpWideCharStr, v39, &lpMultiByteStr, &v99);
        goto LABEL_84;
      }
      break;
    case 7:
      CompareStringNW(L"visited", lpWideCharStr, 7);
      break;
  }
LABEL_83:
  v28 = WCharToCharHelper(lpWideCharStr, 0xFFFFFFFF, 0xFDE9u, 0, (char **)&lpMultiByteStr, &v99);
LABEL_84:
  AllCookies = v28;
  if ( v28 > 0 )
    AllCookies = (unsigned __int16)v28 | 0x80070000;
  v40 = (CHAR *)lpMultiByteStr;
  if ( AllCookies < 0 )
  {
    HIDWORD(v84) = 7288;
    goto LABEL_176;
  }
  v41 = PathAndRDomainFromURL((void *)lpMultiByteStr, 1);
  v44 = (const char *)lpMem;
  v45 = v88;
  if ( !v41 )
  {
    LastError = WxGetLastError(v43, v42);
    AllCookies = LastError;
    if ( LastError > 0 )
      AllCookies = (unsigned __int16)LastError | 0x80070000;
    HIDWORD(v84) = 7289;
    if ( AllCookies >= 0 )
      AllCookies = -2147418113;
    goto LABEL_171;
  }
  v94 = a3 & 0x400000;
  v47 = 3;
  if ( (a3 & 0x400000) == 0 )
    v47 = 1;
  v48 = lpWideCharStra;
  v93 = v47;
  if ( lpWideCharStra )
  {
    v49 = 0;
    v50 = WideCharToMultiByte(0, 0, lpWideCharStra, -1, 0, 0, 0, 0);
    v53 = v50;
    if ( !v50 )
      goto LABEL_101;
    v49 = HeapAlloc(g_hWxProcessHeap, 0, v50);
    if ( !v49 )
    {
      AllCookies = -2147024888;
      goto LABEL_110;
    }
    if ( WideCharToMultiByte(0, 0, v48, -1, v49, v53, 0, 0) )
    {
      AllCookies = 0;
      v49[v53 - 1] = 0;
    }
    else
    {
LABEL_101:
      AllCookies = WxGetLastError(v52, v51);
      if ( AllCookies )
      {
        if ( v49 )
          HeapFree(g_hWxProcessHeap, 0, v49);
        v54 = AllCookies < 0;
        if ( AllCookies <= 0 )
          goto LABEL_111;
        AllCookies = (unsigned __int16)AllCookies | 0x80070000;
LABEL_110:
        v54 = AllCookies < 0;
LABEL_111:
        if ( v54 )
        {
          HIDWORD(v84) = 7322;
          goto LABEL_171;
        }
        v44 = (const char *)lpMem;
        v40 = (CHAR *)lpMultiByteStr;
        goto LABEL_114;
      }
      if ( !v49 )
        goto LABEL_110;
    }
    v91 = v49;
    goto LABEL_110;
  }
LABEL_114:
  if ( (a3 & 0x20000) != 0 )
    ZoneFromUrl = 4;
  else
    ZoneFromUrl = GetZoneFromUrl(v40);
  CookieMainSwitch = GetCookieMainSwitch(ZoneFromUrl);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  AllCookies = CCookieJar::GetHost(v44, &v100);
  if ( AllCookies < 0 )
  {
    HIDWORD(v84) = 7339;
    goto LABEL_170;
  }
  v57 = a3 & 0x1000;
  v86 = v57;
  v92 = a3 & 0x10;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v100 + 56));
  CCookieHost::Sync(v100);
  v59 = (struct CCookieLocation *)*((_QWORD *)v100 + 5);
  if ( !v59 )
    goto LABEL_169;
  while ( 1 )
  {
    v60 = v44;
    for ( j = (_BYTE *)*((_QWORD *)v59 + 2); *v60; ++j )
    {
      if ( !*j )
        break;
      if ( *j != *v60 )
        break;
      ++v60;
    }
    if ( *j )
      goto LABEL_167;
    if ( !*v60 )
      break;
    v62 = 0;
    if ( *v60 == 46 )
      goto LABEL_129;
LABEL_167:
    v59 = (struct CCookieLocation *)*((_QWORD *)v59 + 1);
    if ( !v59 )
    {
      v7 = pCookies;
      v8 = dwCookieCount;
LABEL_169:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v100 + 56));
      *v98 = v7;
      *v96 = v8;
      goto LABEL_170;
    }
  }
  v62 = 1;
LABEL_129:
  v63 = v88;
  for ( k = (_BYTE *)*((_QWORD *)v59 + 4); *v63; ++k )
  {
    if ( !*k )
      break;
    if ( *k != *v63 )
      break;
    ++v63;
  }
  if ( *k )
    goto LABEL_167;
  v65 = *(_QWORD *)v59;
  if ( !*(_QWORD *)v59 )
  {
LABEL_166:
    v44 = (const char *)lpMem;
    goto LABEL_167;
  }
  while ( 1 )
  {
    if ( (*(_DWORD *)(v65 + 16) & 0x400) == 0 )
      ConvertLegacyCookie(v100, (struct CCookie *)v65, v59);
    if ( CookieMainSwitch && (CookieMainSwitch == 3 || (*(_DWORD *)(v65 + 16) & 0x200) != 0 && v92) )
      goto LABEL_165;
    v66 = *(_DWORD *)(v65 + 16);
    if ( (v66 & 0x2000) != 0 && !v57 )
      goto LABEL_165;
    if ( !v90 && (v66 & 1) != 0 || *(_QWORD *)v65 < *(__int64 *)&SystemTimeAsFileTime )
      goto LABEL_165;
    if ( (v66 & 0x4000) != 0 && !v62 )
    {
      if ( (xmmword_180266B60 & 2) != 0 )
        WPP_SF_s(1025, 35, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, *(_QWORD *)(v65 + 32));
      goto LABEL_165;
    }
    v67 = *((_QWORD *)v100 + 1);
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      LODWORD(lpUsedDefaultChar) = (v66 >> 21) & 1;
      WPP_SF_dlsll(
        (v66 >> 20) & 1,
        *(_QWORD *)v65,
        v58,
        v93,
        0,
        *(_QWORD *)(v65 + 32),
        (v66 & 0x100000) != 0,
        lpUsedDefaultChar,
        v84);
    }
    if ( !v94 )
      goto LABEL_157;
    v68 = *(_DWORD *)(v65 + 16);
    if ( (v68 & 0x100000) != 0 )
    {
      v69 = 0;
      TraceLoggingSameSiteBlockedCookie(v67, 0);
      goto LABEL_158;
    }
    if ( (v68 & 0x200000) != 0 )
    {
      v69 = 0;
      TraceLoggingSameSiteBlockedCookie(v67, 1);
    }
    else
    {
LABEL_157:
      v69 = 1;
    }
LABEL_158:
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_d(1025, 93, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, v69);
    if ( v69 && (!lpWideCharStra || !lstrcmpA(*(LPCSTR *)(v65 + 32), v91)) )
    {
      AllCookies = AddCookieToArray(v59, (struct CCookie *)v65, 1, 5u, &pCookies, (unsigned int *)&v84, &dwCookieCount);
      if ( AllCookies < 0 )
        break;
    }
    v57 = v86;
LABEL_165:
    v65 = *(_QWORD *)(v65 + 24);
    if ( !v65 )
      goto LABEL_166;
  }
  HIDWORD(v84) = 7401;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v100 + 56));
  if ( pCookies )
    InternetFreeCookies(pCookies, dwCookieCount);
LABEL_170:
  v45 = v88;
LABEL_171:
  if ( lpMem )
    HeapFree(g_hWxProcessHeap, 0, lpMem);
  if ( v45 )
    HeapFree(g_hWxProcessHeap, 0, v45);
  v15 = (CHAR *)v91;
  v40 = (CHAR *)lpMultiByteStr;
LABEL_176:
  if ( v40 )
    HeapFree(g_hWxProcessHeap, 0, v40);
  if ( v15 )
    HeapFree(g_hWxProcessHeap, 0, v15);
LABEL_180:
  if ( (xmmword_180266B60 & 0x40) != 0 )
  {
    v70 = WX_WIN32_FROM_HR((unsigned int)AllCookies);
    WPP_SF_d(1030, 100, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, v70);
  }
  result = WX_WIN32_FROM_HR((unsigned int)AllCookies);
  v72 = v100;
  v73 = result;
  if ( v100 && _InterlockedExchangeAdd((volatile signed __int32 *)v100, 0xFFFFFFFF) == 1 && v72 )
  {
    v74 = (void **)((char *)v72 + 8);
    if ( v72 != (struct CCookieHost *)-8LL )
    {
      v75 = *v74;
      if ( *v74 )
      {
        v14 = g_fWxHeapExtensionInitialized == 0;
        *v74 = 0;
        if ( v14 )
          HeapFree(g_hWxProcessHeap, 0, v75);
        else
          g_WxHeapExtensionInterfaces(v75);
        *v74 = 0;
      }
    }
    v76 = (void **)*((_QWORD *)v72 + 5);
    *((_DWORD *)v72 + 4) = 0;
    *((_QWORD *)v72 + 3) = 0;
    *((_QWORD *)v72 + 5) = 0;
    while ( v76 )
    {
      v77 = v76;
      v76 = (void **)v76[1];
      CCookieLocation::Purge(v77, CCookie::PurgeAll, 0);
      v78 = v77 + 6;
      if ( v77 != (void **)-48LL )
      {
        v79 = *v78;
        if ( *v78 )
        {
          v14 = g_fWxHeapExtensionInitialized == 0;
          *v78 = 0;
          if ( v14 )
            HeapFree(g_hWxProcessHeap, 0, v79);
          else
            g_WxHeapExtensionInterfaces(v79);
          *v78 = 0;
        }
      }
      v80 = v77 + 7;
      if ( v77 != (void **)-56LL )
      {
        v81 = *v80;
        if ( *v80 )
        {
          v14 = g_fWxHeapExtensionInitialized == 0;
          *v80 = 0;
          if ( v14 )
            HeapFree(g_hWxProcessHeap, 0, v81);
          else
            g_WxHeapExtensionInterfaces(v81);
          *v80 = 0;
        }
      }
      HeapFree(g_hWxProcessHeap, 0, v77);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v72 + 56));
    v82 = *((_QWORD *)v72 + 6);
    if ( v82 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v82, 0xFFFFFFFF) == 1 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(v82 + 9224));
        operator delete((void *)v82, 0x2430u);
      }
      *((_QWORD *)v72 + 6) = 0;
    }
    operator delete(v72, 0x60u);
    return v73;
  }
  return result;
}

```

## disassembly

```asm
0x1800dd1a0  mov     [rsp-8+arg_10], rbx
0x1800dd1a5  push    rbp
0x1800dd1a6  push    rsi
0x1800dd1a7  push    rdi
0x1800dd1a8  push    r12
0x1800dd1aa  push    r13
0x1800dd1ac  push    r14
0x1800dd1ae  push    r15
0x1800dd1b0  lea     rbp, [rsp-1Fh]
0x1800dd1b5  sub     rsp, 0D0h
0x1800dd1bc  mov     rax, cs:__security_cookie
0x1800dd1c3  xor     rax, rsp
0x1800dd1c6  mov     [rbp+4Fh+var_40], rax
0x1800dd1ca  mov     rax, rdx
0x1800dd1cd  mov     [rbp+4Fh+lpWideCharStr], rdx
0x1800dd1d1  xor     edx, edx
0x1800dd1d3  mov     [rbp+4Fh+var_60], r9
0x1800dd1d7  mov     rbx, rcx
0x1800dd1da  mov     [rbp+4Fh+var_BC], edx
0x1800dd1dd  mov     rcx, [rbp+4Fh+arg_20]
0x1800dd1e1  mov     esi, edx
0x1800dd1e3  mov     [rbp+4Fh+var_70], rcx
0x1800dd1e7  mov     r14d, edx
0x1800dd1ea  mov     [rbp+4Fh+pCookies], rdx
0x1800dd1ee  mov     r13, r9
0x1800dd1f1  mov     [rbp+4Fh+lpMem], rdx
0x1800dd1f5  mov     r12d, r8d
0x1800dd1f8  mov     [rbp+4Fh+var_A8], rdx
0x1800dd1fc  mov     [rbp+4Fh+var_98], edx
0x1800dd1ff  mov     [rbp+4Fh+lpMultiByteStr], rdx
0x1800dd203  mov     [rbp+4Fh+var_58], edx
0x1800dd206  mov     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], rdx
0x1800dd20a  mov     [rbp+4Fh+dwCookieCount], edx
0x1800dd20d  mov     [rbp+4Fh+var_C0], edx
0x1800dd210  mov     [rbp+4Fh+var_50], rdx
0x1800dd214  test    byte ptr cs:xmmword_180266B60, 40h
0x1800dd21b  jz      short loc_1800DD23F
0x1800dd21d  mov     [rsp+100h+lpUsedDefaultChar], rcx
0x1800dd222  mov     [rsp+100h+lpDefaultChar], r9
0x1800dd227  mov     r9, rbx
0x1800dd22a  mov     [rsp+100h+cchCount2], r8d
0x1800dd22f  mov     [rsp+100h+lpString2], rax
0x1800dd234  call    WPP_SF_SSdqq
0x1800dd239  mov     rcx, [rbp+4Fh+var_70]
0x1800dd23d  xor     edx, edx
0x1800dd23f  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800dd246  test    rbx, rbx
0x1800dd249  jnz     short loc_1800DD260
0x1800dd24b  mov     r15d, 80070057h
0x1800dd251  mov     [rbp+4Fh+var_BC], 1C62h
0x1800dd258  xor     r13d, r13d
0x1800dd25b  jmp     loc_1800DDAB3
0x1800dd260  test    r13, r13
0x1800dd263  jnz     short loc_1800DD277
0x1800dd265  mov     r15d, 80070057h
0x1800dd26b  mov     [rbp+4Fh+var_BC], 1C63h
0x1800dd272  jmp     loc_1800DDAB3
0x1800dd277  test    rcx, rcx
0x1800dd27a  jnz     short loc_1800DD291
0x1800dd27c  mov     r15d, 80070057h
0x1800dd282  mov     [rbp+4Fh+var_BC], 1C64h
0x1800dd289  xor     r13d, r13d
0x1800dd28c  jmp     loc_1800DDAB3
0x1800dd291  test    r12d, 0DFB9EFEFh
0x1800dd298  jz      short loc_1800DD2AF
0x1800dd29a  mov     r15d, 80070057h
0x1800dd2a0  mov     [rbp+4Fh+var_BC], 1C65h
0x1800dd2a7  xor     r13d, r13d
0x1800dd2aa  jmp     loc_1800DDAB3
0x1800dd2af  mov     [r13+0], rdx
0x1800dd2b3  mov     [rcx], edx
0x1800dd2b5  call    GlobalDataInitialize
0x1800dd2ba  mov     r15d, eax
0x1800dd2bd  test    eax, eax
0x1800dd2bf  jle     short loc_1800DD2CC
0x1800dd2c1  movzx   r15d, ax
0x1800dd2c5  or      r15d, 80070000h
0x1800dd2cc  test    r15d, r15d
0x1800dd2cf  jns     short loc_1800DD2E0
0x1800dd2d1  mov     [rbp+4Fh+var_BC], 1C6Ah
0x1800dd2d8  xor     r13d, r13d
0x1800dd2db  jmp     loc_1800DDAB3
0x1800dd2e0  mov     eax, r12d
0x1800dd2e3  mov     rcx, rdi
0x1800dd2e6  and     eax, 20000000h
0x1800dd2eb  nop     dword ptr [rax+rax+00h]
0x1800dd2f0  inc     rcx
0x1800dd2f3  cmp     [rbx+rcx*2], si
0x1800dd2f7  jnz     short loc_1800DD2F0
0x1800dd2f9  test    eax, eax
0x1800dd2fb  jz      short loc_1800DD35F
0x1800dd2fd  test    rcx, rcx
0x1800dd300  jz      short loc_1800DD317
0x1800dd302  mov     r15d, 80070057h
0x1800dd308  mov     [rbp+4Fh+var_BC], 1C72h
0x1800dd30f  xor     r13d, r13d
0x1800dd312  jmp     loc_1800DDAB3
0x1800dd317  test    r12d, 0DFFFFFFFh
0x1800dd31e  jz      short loc_1800DD335
0x1800dd320  mov     r15d, 80070057h
0x1800dd326  mov     [rbp+4Fh+var_BC], 1C73h
0x1800dd32d  xor     r13d, r13d
0x1800dd330  jmp     loc_1800DDAB3
0x1800dd335  mov     rdx, [rbp+4Fh+var_70]; unsigned int *
0x1800dd339  mov     rcx, r13; struct INTERNET_COOKIE2 **
0x1800dd33c  call    ?RetrieveAllCookies@CCookieJar@@SAJPEAPEAUINTERNET_COOKIE2@@PEAK@Z; CCookieJar::RetrieveAllCookies(INTERNET_COOKIE2 * *,ulong *)
0x1800dd341  xor     r13d, r13d
0x1800dd344  mov     r15d, eax
0x1800dd347  test    eax, eax
0x1800dd349  jns     short loc_1800DD357
0x1800dd34b  mov     [rbp+4Fh+var_BC], 1C74h
0x1800dd352  jmp     loc_1800DDAB3
0x1800dd357  mov     r15d, r13d
0x1800dd35a  jmp     loc_1800DDAB3
0x1800dd35f  xor     r13d, r13d
0x1800dd362  mov     r11d, 1
0x1800dd368  cmp     word ptr [rbx], 3Ah ; ':'
0x1800dd36c  mov     edi, r13d
0x1800dd36f  mov     [rbp+4Fh+var_90], r13
0x1800dd373  mov     edx, r13d
0x1800dd376  jz      short loc_1800DD397
0x1800dd378  test    ecx, ecx
0x1800dd37a  jz      loc_1800DD5A7
0x1800dd380  mov     eax, edx
0x1800dd382  cmp     [rbx+rax*2], si
0x1800dd386  jz      loc_1800DD5A7
0x1800dd38c  inc     edx
0x1800dd38e  dec     ecx
0x1800dd390  cmp     word ptr [rbx+rdx*2], 3Ah ; ':'
0x1800dd395  jnz     short loc_1800DD378
0x1800dd397  movsxd  rcx, edx
0x1800dd39a  cmp     edx, 4
0x1800dd39d  jnz     loc_1800DD49B
0x1800dd3a3  cmp     rcx, 7FFFFFFFh
0x1800dd3aa  ja      short loc_1800DD3EF
0x1800dd3ac  mov     rdx, rcx
0x1800dd3af  lea     rax, aHttp_4; "http"
0x1800dd3b6  mov     r8, rcx
0x1800dd3b9  nop     dword ptr [rax+00000000h]
0x1800dd3c0  cmp     [rax], si
0x1800dd3c3  jz      short loc_1800DD3CE
0x1800dd3c5  add     rax, 2
0x1800dd3c9  sub     rdx, r11
0x1800dd3cc  jnz     short loc_1800DD3C0
0x1800dd3ce  mov     r15d, 80070057h
0x1800dd3d4  test    rdx, rdx
0x1800dd3d7  mov     r9d, r15d
0x1800dd3da  cmovnz  r9d, r13d
0x1800dd3de  jz      short loc_1800DD3E5
0x1800dd3e0  sub     r8, rdx
0x1800dd3e3  jmp     short loc_1800DD3E8
0x1800dd3e5  mov     r8, r13
0x1800dd3e8  test    rdx, rdx
0x1800dd3eb  jnz     short loc_1800DD3FB
0x1800dd3ed  jmp     short loc_1800DD3F8
0x1800dd3ef  mov     r15d, 80070057h
0x1800dd3f5  mov     r9d, r15d
0x1800dd3f8  mov     r8, r13
0x1800dd3fb  test    r9d, r9d
0x1800dd3fe  mov     r10, rcx
0x1800dd401  cmovns  r10, r8
0x1800dd405  cmp     rcx, 7FFFFFFFh
0x1800dd40c  ja      short loc_1800DD444
0x1800dd40e  mov     rdx, rcx
0x1800dd411  mov     rax, rbx
0x1800dd414  mov     r8, rcx
0x1800dd417  test    rcx, rcx
0x1800dd41a  jz      short loc_1800DD42E
0x1800dd41c  nop     dword ptr [rax+00h]
0x1800dd420  cmp     [rax], si
0x1800dd423  jz      short loc_1800DD42E
0x1800dd425  add     rax, 2
0x1800dd429  sub     rdx, r11
0x1800dd42c  jnz     short loc_1800DD420
0x1800dd42e  test    rdx, rdx
0x1800dd431  cmovnz  r15d, r13d
0x1800dd435  jz      short loc_1800DD43C
0x1800dd437  sub     r8, rdx
0x1800dd43a  jmp     short loc_1800DD43F
0x1800dd43c  mov     r8, r13
0x1800dd43f  test    rdx, rdx
0x1800dd442  jnz     short loc_1800DD447
0x1800dd444  mov     r8, r13
0x1800dd447  test    r15d, r15d
0x1800dd44a  cmovns  rcx, r8
0x1800dd44e  cmp     r10, rcx
0x1800dd451  jnz     loc_1800DD5A7
0x1800dd457  mov     [rsp+100h+cchCount2], ecx; cchCount2
0x1800dd45b  lea     r8, aHttp_4; "http"
0x1800dd462  mov     r9d, r10d; cchCount1
0x1800dd465  mov     [rsp+100h+lpString2], rbx; lpString2
0x1800dd46a  mov     edx, r11d; dwCmpFlags
0x1800dd46d  mov     ecx, 7Fh; Locale
0x1800dd472  call    cs:__imp_CompareStringW
0x1800dd478  cmp     eax, 2
0x1800dd47b  jnz     loc_1800DD5A7
0x1800dd481  lea     r9, [rbp+4Fh+var_58]
0x1800dd485  mov     edx, 0FFFFFFFFh; cchWideChar
0x1800dd48a  lea     r8, [rbp+4Fh+lpMultiByteStr]
0x1800dd48e  mov     rcx, rbx; lpWideCharStr
0x1800dd491  call    UrlWCharToChar
0x1800dd496  jmp     loc_1800DD5CF
0x1800dd49b  cmp     edx, 5
0x1800dd49e  jnz     loc_1800DD563
0x1800dd4a4  mov     rdx, rcx
0x1800dd4a7  cmp     rcx, 7FFFFFFFh
0x1800dd4ae  ja      short loc_1800DD4EF
0x1800dd4b0  lea     rax, aHttps_3; "https"
0x1800dd4b7  mov     r8, rcx
0x1800dd4ba  nop     word ptr [rax+rax+00h]
0x1800dd4c0  cmp     [rax], si
0x1800dd4c3  jz      short loc_1800DD4CE
0x1800dd4c5  add     rax, 2
0x1800dd4c9  sub     rcx, r11
0x1800dd4cc  jnz     short loc_1800DD4C0
0x1800dd4ce  mov     r15d, 80070057h
0x1800dd4d4  test    rcx, rcx
0x1800dd4d7  mov     r9d, r15d
0x1800dd4da  cmovnz  r9d, r13d
0x1800dd4de  jz      short loc_1800DD4E5
0x1800dd4e0  sub     r8, rcx
0x1800dd4e3  jmp     short loc_1800DD4E8
0x1800dd4e5  mov     r8, r13
0x1800dd4e8  test    rcx, rcx
0x1800dd4eb  jnz     short loc_1800DD4FB
0x1800dd4ed  jmp     short loc_1800DD4F8
0x1800dd4ef  mov     r15d, 80070057h
0x1800dd4f5  mov     r9d, r15d
0x1800dd4f8  mov     r8, r13
0x1800dd4fb  test    r9d, r9d
0x1800dd4fe  mov     r10, rdx
0x1800dd501  cmovns  r10, r8
0x1800dd505  cmp     rdx, 7FFFFFFFh
0x1800dd50c  ja      short loc_1800DD544
0x1800dd50e  mov     rcx, rdx
0x1800dd511  mov     rax, rbx
0x1800dd514  mov     r8, rdx
0x1800dd517  test    rdx, rdx
0x1800dd51a  jz      short loc_1800DD52E
0x1800dd51c  nop     dword ptr [rax+00h]
0x1800dd520  cmp     [rax], si
0x1800dd523  jz      short loc_1800DD52E
0x1800dd525  add     rax, 2
0x1800dd529  sub     rcx, r11
0x1800dd52c  jnz     short loc_1800DD520
0x1800dd52e  test    rcx, rcx
0x1800dd531  cmovnz  r15d, r13d
0x1800dd535  jz      short loc_1800DD53C
0x1800dd537  sub     r8, rcx
0x1800dd53a  jmp     short loc_1800DD53F
0x1800dd53c  mov     r8, r13
0x1800dd53f  test    rcx, rcx
0x1800dd542  jnz     short loc_1800DD547
0x1800dd544  mov     r8, r13
0x1800dd547  test    r15d, r15d
0x1800dd54a  cmovns  rdx, r8
0x1800dd54e  cmp     r10, rdx
0x1800dd551  jnz     short loc_1800DD5A7
0x1800dd553  mov     [rsp+100h+cchCount2], edx
0x1800dd557  lea     r8, aHttps_3; "https"
0x1800dd55e  jmp     loc_1800DD462
0x1800dd563  cmp     edx, 6
0x1800dd566  jnz     short loc_1800DD590
0x1800dd568  mov     r8d, edx; int
0x1800dd56b  lea     rcx, aCookie_2; "cookie"
0x1800dd572  mov     rdx, rbx; lpString2
0x1800dd575  call    ?CompareStringNW@@YAHPEBG0H@Z; CompareStringNW(ushort const *,ushort const *,int)
0x1800dd57a  test    eax, eax
0x1800dd57c  jnz     short loc_1800DD5A7
0x1800dd57e  lea     r9, [rbp+4Fh+var_58]
0x1800dd582  mov     rcx, rbx
0x1800dd585  lea     r8, [rbp+4Fh+lpMultiByteStr]
0x1800dd589  call    CookieWCharToChar
0x1800dd58e  jmp     short loc_1800DD5CF
0x1800dd590  cmp     edx, 7
0x1800dd593  jnz     short loc_1800DD5A7
0x1800dd595  mov     r8d, edx; int
0x1800dd598  lea     rcx, aVisited; "visited"
0x1800dd59f  mov     rdx, rbx; lpString2
0x1800dd5a2  call    ?CompareStringNW@@YAHPEBG0H@Z; CompareStringNW(ushort const *,ushort const *,int)
0x1800dd5a7  lea     rax, [rbp+4Fh+var_58]
0x1800dd5ab  xor     r9d, r9d; int
0x1800dd5ae  mov     qword ptr [rsp+100h+cchCount2], rax; unsigned int *
0x1800dd5b3  mov     r8d, 0FDE9h; CodePage
0x1800dd5b9  lea     rax, [rbp+4Fh+lpMultiByteStr]
0x1800dd5bd  mov     edx, 0FFFFFFFFh; cchWideChar
0x1800dd5c2  mov     rcx, rbx; lpWideCharStr
0x1800dd5c5  mov     [rsp+100h+lpString2], rax; char **
0x1800dd5ca  call    ?WCharToCharHelper@@YAKPEBGKKHPEAPEADPEAK@Z; WCharToCharHelper(ushort const *,ulong,ulong,int,char * *,ulong *)
0x1800dd5cf  mov     r15d, eax
0x1800dd5d2  test    eax, eax
0x1800dd5d4  jle     short loc_1800DD5E1
0x1800dd5d6  movzx   r15d, r15w
0x1800dd5da  or      r15d, 80070000h
0x1800dd5e1  mov     rbx, [rbp+4Fh+lpMultiByteStr]
0x1800dd5e5  test    r15d, r15d
0x1800dd5e8  jns     short loc_1800DD5F6
0x1800dd5ea  mov     [rbp+4Fh+var_BC], 1C78h
0x1800dd5f1  jmp     loc_1800DDA7E
0x1800dd5f6  mov     r15d, 1
  ... truncated ...
```
