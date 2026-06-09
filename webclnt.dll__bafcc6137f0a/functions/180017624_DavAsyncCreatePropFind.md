# DavAsyncCreatePropFind

- ea: `0x180017624`
- end: `0x180018326`
- name: `DavAsyncCreatePropFind`
- size: `3330`
- prototype: `__int64 __fastcall(unsigned int *pvCallbackContext, int, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001507c`
- `0x1800196d0`

## callees

- `0x18000b4f0`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x18000b93c`
- `0x18000d9e4`
- `0x180014fa0`
- `0x18001507c`
- `0x180016d24`
- `0x180017624`
- `0x18001832c`
- `0x18001ad0c`
- `0x18001c0d0`
- `0x18001c4f0`
- `0x1800297e4`
- `0x180029bec`
- `0x18002bce0`
- `0x18002be24`
- `0x18002cf56`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!_wtoi` at `0x18001794d`
- `msvcrt!_wtoi` at `0x18001794d`
- `msvcrt!_wcsnicmp` at `0x180017901`
- `msvcrt!_wcsnicmp` at `0x180017901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001810b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001810b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018203`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017c05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017c05`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017b0e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017e1a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017b0e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017e1a`
- `KERNEL32!LocalFree` at `0x180018299`
- `KERNEL32!LocalFree` at `0x180018299`
- `KERNEL32!LocalAlloc` at `0x180017b6e`
- `KERNEL32!LocalAlloc` at `0x180017fea`
- `KERNEL32!LocalAlloc` at `0x180018033`
- `KERNEL32!LocalAlloc` at `0x180017b6e`
- `KERNEL32!LocalAlloc` at `0x180017fea`
- `KERNEL32!LocalAlloc` at `0x180018033`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800181f9`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800181f9`
- `WINHTTP!WinHttpSetOption` at `0x180017de4`
- `WINHTTP!WinHttpSetOption` at `0x1800181b2`
- `WINHTTP!WinHttpSetOption` at `0x180017de4`
- `WINHTTP!WinHttpSetOption` at `0x1800181b2`
- `WINHTTP!WinHttpQueryHeaders` at `0x180017794`
- `WINHTTP!WinHttpQueryHeaders` at `0x180017988`
- `WINHTTP!WinHttpQueryHeaders` at `0x180017794`
- `WINHTTP!WinHttpQueryHeaders` at `0x180017988`

## string_xrefs

- `0x180017965`: `Lock-Token`
- `0x180017d63`: `DavAsyncCreate`
- `0x1800180f1`: `DavAsyncCreate`

## pseudocode

```c
__int64 __fastcall DavAsyncCreatePropFind(unsigned int *pvCallbackContext, int a2, __int64 a3)
{
  unsigned int v4; // r14d
  unsigned int QueryParentDirectory; // edi
  void *v6; // rcx
  DWORD LastError; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r9
  void *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned int v17; // eax
  _QWORD *v18; // rdx
  __int64 v19; // rdi
  void *v20; // rcx
  SIZE_T v21; // r14
  HLOCAL v22; // rax
  _WORD *v23; // r9
  _WORD *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r8
  _WORD *v27; // rcx
  HANDLE FileW; // rax
  unsigned int v29; // eax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // eax
  void **v33; // rdi
  void *v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // ebx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  size_t v40; // rdi
  char *v41; // rax
  char *v42; // r14
  char *v43; // rax
  HINTERNET *v44; // rdi
  __int64 v45; // rcx
  DWORD v46; // eax
  void *v47; // rcx
  DWORD v48; // eax
  __int64 v49; // rdx
  unsigned int v50; // eax
  __int64 v51; // rdx
  int lpdwBufferLength; // [rsp+20h] [rbp-99h]
  int lpdwIndex; // [rsp+28h] [rbp-91h]
  int hTemplateFile; // [rsp+30h] [rbp-89h]
  int v56; // [rsp+70h] [rbp-49h] BYREF
  DWORD dwBufferLength[3]; // [rsp+74h] [rbp-45h] BYREF
  wchar_t Buffer[7]; // [rsp+80h] [rbp-39h] BYREF
  wchar_t String[25]; // [rsp+8Eh] [rbp-2Bh] BYREF

  pvCallbackContext[972] = 0;
  v4 = pvCallbackContext[136];
  v56 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_DDDDDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      pvCallbackContext[173],
      pvCallbackContext[176],
      pvCallbackContext[177],
      pvCallbackContext[178],
      pvCallbackContext[179],
      *((_QWORD *)pvCallbackContext + 79));
  pvCallbackContext[176] &= 0xFFFFE7FF;
  if ( v4 )
  {
    v10 = pvCallbackContext[1376];
    if ( (v10 & 1) != 0 )
    {
      if ( (v11 = pvCallbackContext[178], (v11 & 0xFFFFFFFA) == 0) && (_DWORD)v11 != 1
        || (pvCallbackContext[179] & 0x1000) != 0
        || (pvCallbackContext[173] & 0x50000006) != 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_dDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, a3, v11, pvCallbackContext[173], v10);
          v8 = WPP_GLOBAL_Control;
        }
        QueryParentDirectory = 5;
        goto LABEL_203;
      }
    }
    v12 = pvCallbackContext[179];
    if ( (v12 & 1) != 0 && !*((_BYTE *)pvCallbackContext + 5533) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          118,
          WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
          v12,
          pvCallbackContext[1376]);
        v8 = WPP_GLOBAL_Control;
      }
      QueryParentDirectory = -1073741565;
      goto LABEL_203;
    }
    if ( (v12 & 0x40) != 0 && *((_BYTE *)pvCallbackContext + 5533) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          119,
          WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
          v12,
          pvCallbackContext[1376]);
        v8 = WPP_GLOBAL_Control;
      }
      QueryParentDirectory = -1073741638;
      goto LABEL_203;
    }
  }
  else if ( (pvCallbackContext[179] & 1) == 0 )
  {
    pvCallbackContext[176] |= 0x20u;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
  if ( !*(_DWORD *)&DavSupportLockingOfFiles )
  {
    QueryParentDirectory = 0;
    if ( v4 )
      goto LABEL_59;
LABEL_137:
    *((_QWORD *)pvCallbackContext + 5) = 2;
    goto LABEL_138;
  }
  if ( !v4 )
    goto LABEL_137;
  QueryParentDirectory = 0;
  if ( *((_BYTE *)pvCallbackContext + 5533) || pvCallbackContext[177] > 1 || (pvCallbackContext[173] & 0x50000006) == 0 )
    goto LABEL_59;
  if ( !pvCallbackContext[155] )
  {
    v14 = DavLockTheFileOnTheServer((__int64)pvCallbackContext);
    QueryParentDirectory = v14;
    if ( v14 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_202;
      v15 = 124;
      goto LABEL_56;
    }
    goto LABEL_59;
  }
  *((_QWORD *)pvCallbackContext + 681) = 0;
  v6 = (void *)*((_QWORD *)pvCallbackContext + 74);
  dwBufferLength[0] = 64;
  if ( !WinHttpQueryHeaders(v6, 0xFFFFu, L"X-MSDAVEXTLockTimeout", Buffer, dwBufferLength, 0) )
  {
    LastError = GetLastError();
    QueryParentDirectory = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 121;
LABEL_20:
      WPP_SF_d(v8[2], v9, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, LastError);
LABEL_200:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_201;
    }
    goto LABEL_201;
  }
  if ( !_wcsnicmp(Buffer, L"Second-", 7u) )
  {
    pvCallbackContext[1361] = _wtoi(String);
    v13 = (void *)*((_QWORD *)pvCallbackContext + 74);
    dwBufferLength[0] = 520;
    if ( !WinHttpQueryHeaders(v13, 0xFFFFu, L"Lock-Token", pvCallbackContext + 974, dwBufferLength, 0) )
    {
      LastError = GetLastError();
      QueryParentDirectory = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 123;
        goto LABEL_20;
      }
LABEL_201:
      if ( !QueryParentDirectory )
        return QueryParentDirectory;
      goto LABEL_202;
    }
    pvCallbackContext[1362] = 1;
LABEL_59:
    v16 = pvCallbackContext[178];
    if ( (_DWORD)v16 )
    {
      v16 = (unsigned int)(v16 - 4);
      if ( (unsigned int)v16 < 2 )
        *((_QWORD *)pvCallbackContext + 5) = 3;
      else
        *((_QWORD *)pvCallbackContext + 5) = 1;
    }
    else
    {
      *((_QWORD *)pvCallbackContext + 5) = 0;
    }
    v17 = pvCallbackContext[178];
    if ( v17 != 5 )
    {
      if ( v17 == 2 )
      {
        QueryParentDirectory = 183;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return QueryParentDirectory;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_203;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
        goto LABEL_46;
      }
      if ( (pvCallbackContext[179] & 0x1000) != 0 )
      {
        v16 = (unsigned __int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            139,
            WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
            *((_QWORD *)pvCallbackContext + 71));
        pvCallbackContext[971] = 1;
      }
      if ( *((_BYTE *)pvCallbackContext + 5533) )
        goto LABEL_200;
      if ( (pvCallbackContext[1376] & 0x4000) == 0 && (pvCallbackContext[173] & 0xFFEEFE7F) == 0 )
      {
        pvCallbackContext[972] = 1;
        v18 = (_QWORD *)*((_QWORD *)pvCallbackContext + 76);
        if ( v18 )
          TfsReleaseEntry(v16, *v18);
        goto LABEL_200;
      }
      RevertToSelf();
      if ( pvCallbackContext[157] )
      {
        v19 = *((_QWORD *)pvCallbackContext + 76);
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            140,
            WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
            *((_QWORD *)pvCallbackContext + 73));
        TfsReferenceEntry(v20, *(_QWORD *)v19);
        v21 = (unsigned int)(2 * *(_DWORD *)(v19 + 16) + 2);
        v22 = LocalAlloc(0x40u, v21);
        *((_QWORD *)pvCallbackContext + 72) = v22;
        if ( !v22 )
        {
          v29 = GetLastError();
          QueryParentDirectory = v29;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_126;
          v31 = 142;
          goto LABEL_125;
        }
        v23 = *(_WORD **)(v19 + 8);
        v24 = pvCallbackContext + 578;
        v25 = 2147483646;
        v26 = 260;
        do
        {
          if ( !v25 )
            break;
          if ( !*v23 )
            break;
          *v24++ = *v23++;
          --v25;
          --v26;
        }
        while ( v26 );
        v27 = v24 - 1;
        if ( v26 )
          v27 = v24;
        *v27 = 0;
        StringCbCopyW(*((STRSAFE_LPWSTR *)pvCallbackContext + 72), v21, *(STRSAFE_LPCWSTR *)(v19 + 8));
        FileW = CreateFileW(*((LPCWSTR *)pvCallbackContext + 72), 0xC0000000, 3u, 0, 3u, 0x80u, 0);
        *((_QWORD *)pvCallbackContext + 67) = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          v29 = GetLastError();
          QueryParentDirectory = v29;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_126;
          v31 = 141;
LABEL_125:
          WPP_SF_d(v30[2], v31, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v29);
LABEL_126:
          v35 = UMReflectorImpersonate((__int64)pvCallbackContext, *((void **)pvCallbackContext + 9));
          v36 = v35;
          if ( !v35 )
            goto LABEL_200;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v35);
            v8 = WPP_GLOBAL_Control;
          }
          if ( !QueryParentDirectory )
            QueryParentDirectory = v36;
LABEL_202:
          if ( QueryParentDirectory == 2 )
            return QueryParentDirectory;
          goto LABEL_203;
        }
        v32 = DavAsyncCreateGet((__int64)pvCallbackContext);
LABEL_95:
        QueryParentDirectory = v32;
        goto LABEL_200;
      }
      v29 = UMReflectorImpersonate((__int64)pvCallbackContext, *((void **)pvCallbackContext + 9));
      QueryParentDirectory = v29;
      if ( v29 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_126;
        v31 = 143;
        goto LABEL_125;
      }
      pvCallbackContext[128] = 2;
      pvCallbackContext[14] = 1;
      if ( pvCallbackContext[154] )
      {
        pvCallbackContext[13] = 3;
        v32 = DavAsyncCreate(pvCallbackContext, 0);
        goto LABEL_95;
      }
      pvCallbackContext[13] = 1;
      if ( *((_QWORD *)pvCallbackContext + 690) > (__int64)*(unsigned int *)&DavFileSizeLimitInBytes )
      {
        QueryParentDirectory = 223;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return QueryParentDirectory;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_203;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, 223);
        goto LABEL_46;
      }
      v33 = (void **)(pvCallbackContext + 148);
      if ( !(unsigned int)DavHttpOpenRequestW(
                            *(_QWORD *)(*((_QWORD *)pvCallbackContext + 62) + 32LL),
                            *(_QWORD *)(*((_QWORD *)pvCallbackContext + 62) + 40LL),
                            (unsigned int)L"GET",
                            *((_QWORD *)pvCallbackContext + 71),
                            lpdwBufferLength,
                            lpdwIndex,
                            hTemplateFile,
                            256) )
      {
        v32 = GetLastError();
        goto LABEL_95;
      }
      v34 = *v33;
      if ( !*v33 )
      {
        LastError = GetLastError();
        QueryParentDirectory = LastError;
        if ( LastError == 997 )
          goto LABEL_200;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 145;
          goto LABEL_20;
        }
        goto LABEL_201;
      }
      v56 = 1;
      if ( g_DisableCookies && !WinHttpSetOption(v34, 0x3Fu, &v56, 4u) )
      {
        LastError = GetLastError();
        QueryParentDirectory = LastError;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 146;
          goto LABEL_20;
        }
        goto LABEL_201;
      }
      RevertToSelf();
      DavAddIfModifiedSinceHeader(pvCallbackContext);
      v29 = UMReflectorImpersonate((__int64)pvCallbackContext, *((void **)pvCallbackContext + 9));
      QueryParentDirectory = v29;
      if ( v29 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_126;
        v31 = 147;
        goto LABEL_125;
      }
      v14 = DavAsyncCommonStates(pvCallbackContext);
      QueryParentDirectory = v14;
      if ( !v14 )
        return QueryParentDirectory;
      if ( v14 == 997 )
      {
LABEL_57:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_202;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_202;
      v15 = 148;
LABEL_56:
      WPP_SF_d(v8[2], v15, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v14);
      goto LABEL_57;
    }
LABEL_138:
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
          v4,
          pvCallbackContext[178]);
        v37 = WPP_GLOBAL_Control;
      }
      if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 2) != 0 )
      {
        WPP_SF_d(v37[2], 126, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, pvCallbackContext[179]);
        v37 = WPP_GLOBAL_Control;
      }
    }
    if ( pvCallbackContext[178] == 1 )
    {
      QueryParentDirectory = 2;
      if ( v37 == &WPP_GLOBAL_Control || (*((_BYTE *)v37 + 28) & 2) == 0 )
        return QueryParentDirectory;
      v51 = 127;
    }
    else
    {
      if ( pvCallbackContext[178] != 4 )
      {
        if ( *((_BYTE *)pvCallbackContext + 734) || (pvCallbackContext[176] & 0x4000) != 0 )
        {
          v42 = 0;
          if ( *((_BYTE *)pvCallbackContext + 735) || (pvCallbackContext[176] & 0x4000) != 0 )
            pvCallbackContext[1376] |= 0x4000u;
          QueryParentDirectory = DavAsyncCreateQueryParentDirectory(pvCallbackContext);
          goto LABEL_197;
        }
        if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 2) != 0 )
          WPP_SF_S(v37[2], 129, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, *((_QWORD *)pvCallbackContext + 71));
        v38 = *((_QWORD *)pvCallbackContext + 71);
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)(v38 + 2 * v39) );
        if ( (_DWORD)v39 )
        {
          while ( 1 )
          {
            v40 = 2LL * (unsigned int)v39;
            if ( *(_WORD *)(v38 + v40) == 92 )
              break;
            LODWORD(v39) = v39 - 1;
            if ( !(_DWORD)v39 )
              goto LABEL_156;
          }
          v43 = (char *)LocalAlloc(0x40u, 2LL * (unsigned int)(v39 + 1));
          v42 = v43;
          if ( !v43 )
          {
            LastError = GetLastError();
            QueryParentDirectory = LastError;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v9 = 131;
              goto LABEL_20;
            }
            goto LABEL_201;
          }
          memcpy_0(v43, *((const void **)pvCallbackContext + 71), v40);
          *(_WORD *)&v42[v40] = 0;
        }
        else
        {
LABEL_156:
          v41 = (char *)LocalAlloc(0x40u, 2u);
          v42 = v41;
          if ( !v41 )
          {
            LastError = GetLastError();
            QueryParentDirectory = LastError;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v9 = 130;
              goto LABEL_20;
            }
            goto LABEL_201;
          }
          *(_WORD *)v41 = 0;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v42);
        v44 = (HINTERNET *)(pvCallbackContext + 150);
        v45 = *((_QWORD *)pvCallbackContext + 62);
        *(_QWORD *)(pvCallbackContext + 13) = 1;
        pvCallbackContext[128] = 1;
        if ( !(unsigned int)DavHttpOpenRequestW(
                              *(_QWORD *)(v45 + 32),
                              *(_QWORD *)(v45 + 40),
                              (unsigned int)L"PROPFIND",
                              (_DWORD)v42,
                              lpdwBufferLength,
                              lpdwIndex,
                              hTemplateFile,
                              0) )
        {
          v46 = GetLastError();
          QueryParentDirectory = v46;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_198;
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v46, v46);
LABEL_197:
          v8 = WPP_GLOBAL_Control;
LABEL_198:
          if ( !v42 )
            goto LABEL_201;
          LocalFree(v42);
          goto LABEL_200;
        }
        v47 = *v44;
        if ( *v44 )
        {
          v56 = 1;
          if ( !g_DisableCookies || WinHttpSetOption(v47, 0x3Fu, &v56, 4u) )
          {
            if ( WinHttpAddRequestHeaders(*v44, L"Content-Length: 0", 0xFFFFFFFF, 0xA0000000) )
            {
              v50 = DavAsyncCommonStates(pvCallbackContext);
              QueryParentDirectory = v50;
              if ( v50 && v50 != 997 )
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  goto LABEL_198;
                }
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v50);
              }
              goto LABEL_197;
            }
            v48 = GetLastError();
            QueryParentDirectory = v48;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_198;
            v49 = 136;
          }
          else
          {
            v48 = GetLastError();
            QueryParentDirectory = v48;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_198;
            v49 = 135;
          }
        }
        else
        {
          v48 = GetLastError();
          QueryParentDirectory = v48;
          if ( v48 == 997 )
            goto LABEL_197;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_198;
          v49 = 134;
        }
        WPP_SF_d(v8[2], v49, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v48);
        goto LABEL_197;
      }
      QueryParentDirectory = 2;
      if ( v37 == &WPP_GLOBAL_Control || (*((_BYTE *)v37 + 28) & 2) == 0 )
        return QueryParentDirectory;
      v51 = 128;
    }
    WPP_SF_(v37[2], v51, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
    return QueryParentDirectory;
  }
  QueryParentDirectory = 87;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return QueryParentDirectory;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_203;
  WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, Buffer);
LABEL_46:
  v8 = WPP_GLOBAL_Control;
LABEL_203:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_d(v8[2], 150, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, QueryParentDirectory);
  return QueryParentDirectory;
}

```

## disassembly

```asm
0x180017624  push    rbp
0x180017626  push    rbx
0x180017627  push    rsi
0x180017628  push    rdi
0x180017629  push    r12
0x18001762b  push    r13
0x18001762d  push    r14
0x18001762f  push    r15
0x180017631  lea     rbp, [rsp-1Fh]
0x180017636  sub     rsp, 0D8h
0x18001763d  mov     rax, cs:__security_cookie
0x180017644  xor     rax, rsp
0x180017647  mov     [rbp+57h+var_50], rax
0x18001764b  xor     r15d, r15d
0x18001764e  mov     rbx, rcx
0x180017651  mov     [rcx+0F30h], r15d
0x180017658  mov     r14d, [rcx+220h]
0x18001765f  mov     [rbp+57h+var_A0], r15d
0x180017663  mov     rcx, cs:WPP_GLOBAL_Control
0x18001766a  lea     r12, WPP_GLOBAL_Control
0x180017671  cmp     rcx, r12
0x180017674  jz      short loc_1800176C0
0x180017676  test    byte ptr [rcx+1Ch], 2
0x18001767a  jz      short loc_1800176C0
0x18001767c  mov     rax, [rbx+278h]
0x180017683  mov     r9d, [rbx+2B4h]
0x18001768a  mov     rcx, [rcx+10h]
0x18001768e  mov     [rsp+110h+var_D0], rax
0x180017693  mov     eax, [rbx+2CCh]
0x180017699  mov     [rsp+110h+var_D8], eax
0x18001769d  mov     eax, [rbx+2C8h]
0x1800176a3  mov     dword ptr [rsp+110h+hTemplateFile], eax
0x1800176a7  mov     eax, [rbx+2C4h]
0x1800176ad  mov     dword ptr [rsp+110h+lpdwIndex], eax
0x1800176b1  mov     eax, [rbx+2C0h]
0x1800176b7  mov     dword ptr [rsp+110h+lpdwBufferLength], eax
0x1800176bb  call    WPP_SF_DDDDDS
0x1800176c0  and     dword ptr [rbx+2C0h], 0FFFFE7FFh
0x1800176ca  lea     r13, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800176d1  mov     esi, 1
0x1800176d6  test    r14d, r14d
0x1800176d9  jnz     loc_1800177DD
0x1800176df  test    [rbx+2CCh], sil
0x1800176e6  jnz     short loc_1800176EF
0x1800176e8  or      dword ptr [rbx+2C0h], 20h
0x1800176ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176f6  cmp     rcx, r12
0x1800176f9  jz      short loc_180017712
0x1800176fb  test    byte ptr [rcx+1Ch], 2
0x1800176ff  jz      short loc_180017712
0x180017701  mov     rcx, [rcx+10h]
0x180017705  mov     edx, 78h ; 'x'
0x18001770a  mov     r8, r13
0x18001770d  call    WPP_SF_
0x180017712  cmp     cs:DavSupportLockingOfFiles, r15d
0x180017719  jz      loc_180017A0E
0x18001771f  test    r14d, r14d
0x180017722  jz      loc_180017EF5
0x180017728  mov     edi, r15d
0x18001772b  cmp     [rbx+159Dh], r15b
0x180017732  jnz     loc_180017A1A
0x180017738  cmp     [rbx+2C4h], esi
0x18001773e  ja      loc_180017A1A
0x180017744  test    dword ptr [rbx+2B4h], 50000006h
0x18001774e  jz      loc_180017A1A
0x180017754  cmp     [rbx+26Ch], r15d
0x18001775b  jz      loc_1800179C6
0x180017761  mov     [rbx+1548h], r15
0x180017768  lea     rax, [rbp+57h+dwBufferLength]
0x18001776c  mov     rcx, [rbx+250h]; hRequest
0x180017773  lea     r9, [rbp+57h+Buffer]; lpBuffer
0x180017777  mov     [rsp+110h+lpdwIndex], r15; lpdwIndex
0x18001777c  lea     r8, aXMsdavextlockt; "X-MSDAVEXTLockTimeout"
0x180017783  mov     edx, 0FFFFh; dwInfoLevel
0x180017788  mov     [rsp+110h+lpdwBufferLength], rax; lpdwBufferLength
0x18001778d  mov     [rbp+57h+dwBufferLength], 40h ; '@'
0x180017794  call    cs:__imp_WinHttpQueryHeaders
0x18001779a  test    eax, eax
0x18001779c  jnz     loc_1800178F0
0x1800177a2  call    cs:__imp_GetLastError
0x1800177a8  mov     edi, eax
0x1800177aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177b1  cmp     rcx, r12
0x1800177b4  jz      loc_1800182A6
0x1800177ba  test    [rcx+1Ch], sil
0x1800177be  jz      loc_1800182A6
0x1800177c4  mov     edx, 79h ; 'y'
0x1800177c9  mov     rcx, [rcx+10h]
0x1800177cd  mov     r9d, eax
0x1800177d0  mov     r8, r13
0x1800177d3  call    WPP_SF_d
0x1800177d8  jmp     loc_18001829F
0x1800177dd  mov     eax, [rbx+1580h]
0x1800177e3  test    sil, al
0x1800177e6  jz      short loc_180017854
0x1800177e8  mov     r9d, [rbx+2C8h]
0x1800177ef  test    r9d, 0FFFFFFFAh
0x1800177f6  jnz     short loc_1800177FD
0x1800177f8  cmp     r9d, esi
0x1800177fb  jnz     short loc_180017815
0x1800177fd  test    dword ptr [rbx+2CCh], 1000h
0x180017807  jnz     short loc_180017815
0x180017809  test    dword ptr [rbx+2B4h], 50000006h
0x180017813  jz      short loc_180017854
0x180017815  mov     rcx, cs:WPP_GLOBAL_Control
0x18001781c  cmp     rcx, r12
0x18001781f  jz      short loc_18001784A
0x180017821  test    byte ptr [rcx+1Ch], 2
0x180017825  jz      short loc_18001784A
0x180017827  mov     rcx, [rcx+10h]
0x18001782b  mov     edx, 75h ; 'u'
0x180017830  mov     dword ptr [rsp+110h+lpdwIndex], eax
0x180017834  mov     eax, [rbx+2B4h]
0x18001783a  mov     dword ptr [rsp+110h+lpdwBufferLength], eax
0x18001783e  call    WPP_SF_dDD
0x180017843  mov     rcx, cs:WPP_GLOBAL_Control
0x18001784a  mov     edi, 5
0x18001784f  jmp     loc_1800182AF
0x180017854  mov     r9d, [rbx+2CCh]
0x18001785b  test    sil, r9b
0x18001785e  jz      short loc_1800178A1
0x180017860  cmp     [rbx+159Dh], r15b
0x180017867  jnz     short loc_1800178A1
0x180017869  mov     rcx, cs:WPP_GLOBAL_Control
0x180017870  cmp     rcx, r12
0x180017873  jz      short loc_180017897
0x180017875  test    byte ptr [rcx+1Ch], 2
0x180017879  jz      short loc_180017897
0x18001787b  mov     rcx, [rcx+10h]
0x18001787f  mov     edx, 76h ; 'v'
0x180017884  mov     r8, r13
0x180017887  mov     dword ptr [rsp+110h+lpdwBufferLength], eax
0x18001788b  call    WPP_SF_Dd
0x180017890  mov     rcx, cs:WPP_GLOBAL_Control
0x180017897  mov     edi, 0C0000103h
0x18001789c  jmp     loc_1800182AF
0x1800178a1  test    r9b, 40h
0x1800178a5  jz      loc_1800176EF
0x1800178ab  cmp     [rbx+159Dh], r15b
0x1800178b2  jz      loc_1800176EF
0x1800178b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178bf  cmp     rcx, r12
0x1800178c2  jz      short loc_1800178E6
0x1800178c4  test    byte ptr [rcx+1Ch], 2
0x1800178c8  jz      short loc_1800178E6
0x1800178ca  mov     rcx, [rcx+10h]
0x1800178ce  mov     edx, 77h ; 'w'
0x1800178d3  mov     r8, r13
0x1800178d6  mov     dword ptr [rsp+110h+lpdwBufferLength], eax
0x1800178da  call    WPP_SF_Dd
0x1800178df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178e6  mov     edi, 0C00000BAh
0x1800178eb  jmp     loc_1800182AF
0x1800178f0  mov     r8d, 7; MaxCount
0x1800178f6  lea     rdx, aSecond; "Second-"
0x1800178fd  lea     rcx, [rbp+57h+Buffer]; String1
0x180017901  call    cs:__imp__wcsnicmp
0x180017907  test    eax, eax
0x180017909  jz      short loc_180017949
0x18001790b  mov     edi, 57h ; 'W'
0x180017910  mov     rcx, cs:WPP_GLOBAL_Control
0x180017917  cmp     rcx, r12
0x18001791a  jz      loc_180018304
0x180017920  test    [rcx+1Ch], sil
0x180017924  jz      loc_1800182AF
0x18001792a  mov     rcx, [rcx+10h]
0x18001792e  lea     edx, [rdi+23h]
0x180017931  lea     r9, [rbp+57h+Buffer]
0x180017935  mov     r8, r13
0x180017938  call    WPP_SF_S
0x18001793d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017944  jmp     loc_1800182AF
0x180017949  lea     rcx, [rbp+57h+String]; String
0x18001794d  call    cs:__imp__wtoi
0x180017953  lea     r9, [rbx+0F38h]; lpBuffer
0x18001795a  mov     [rsp+110h+lpdwIndex], r15; lpdwIndex
0x18001795f  mov     [rbx+1544h], eax
0x180017965  lea     r8, aLockToken_0; "Lock-Token"
0x18001796c  mov     rcx, [rbx+250h]; hRequest
0x180017973  lea     rax, [rbp+57h+dwBufferLength]
0x180017977  mov     edx, 0FFFFh; dwInfoLevel
0x18001797c  mov     [rsp+110h+lpdwBufferLength], rax; lpdwBufferLength
0x180017981  mov     [rbp+57h+dwBufferLength], 208h
0x180017988  call    cs:__imp_WinHttpQueryHeaders
0x18001798e  test    eax, eax
0x180017990  jnz     short loc_1800179BE
0x180017992  call    cs:__imp_GetLastError
0x180017998  mov     edi, eax
0x18001799a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179a1  cmp     rcx, r12
0x1800179a4  jz      loc_1800182A6
0x1800179aa  test    [rcx+1Ch], sil
0x1800179ae  jz      loc_1800182A6
0x1800179b4  mov     edx, 7Bh ; '{'
0x1800179b9  jmp     loc_1800177C9
0x1800179be  mov     [rbx+1548h], esi
0x1800179c4  jmp     short loc_180017A1A
0x1800179c6  mov     rcx, rbx; __int64
0x1800179c9  call    DavLockTheFileOnTheServer
0x1800179ce  mov     edi, eax
0x1800179d0  test    eax, eax
0x1800179d2  jz      short loc_180017A1A
0x1800179d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179db  cmp     rcx, r12
0x1800179de  jz      loc_1800182AA
0x1800179e4  test    [rcx+1Ch], sil
0x1800179e8  jz      loc_1800182AA
0x1800179ee  mov     edx, 7Ch ; '|'
0x1800179f3  mov     rcx, [rcx+10h]
0x1800179f7  mov     r9d, eax
0x1800179fa  mov     r8, r13
0x1800179fd  call    WPP_SF_d
0x180017a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a09  jmp     loc_1800182AA
0x180017a0e  mov     edi, r15d
0x180017a11  test    r14d, r14d
0x180017a14  jz      loc_180017EF5
0x180017a1a  mov     ecx, [rbx+2C8h]
0x180017a20  test    ecx, ecx
0x180017a22  jz      short loc_180017A3E
0x180017a24  sub     ecx, 4
0x180017a27  jz      short loc_180017A34
0x180017a29  cmp     ecx, 1
0x180017a2c  jz      short loc_180017A34
0x180017a2e  mov     [rbx+28h], rsi
0x180017a32  jmp     short loc_180017A42
0x180017a34  mov     qword ptr [rbx+28h], 3
0x180017a3c  jmp     short loc_180017A42
0x180017a3e  mov     [rbx+28h], r15
0x180017a42  mov     eax, [rbx+2C8h]
0x180017a48  cmp     eax, 5
0x180017a4b  jz      loc_180017EFD
0x180017a51  cmp     eax, 2
0x180017a54  jnz     short loc_180017A89
0x180017a56  mov     edi, 0B7h
0x180017a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a62  cmp     rcx, r12
0x180017a65  jz      loc_180018304
0x180017a6b  test    [rcx+1Ch], sil
0x180017a6f  jz      loc_1800182AF
0x180017a75  mov     rcx, [rcx+10h]
0x180017a79  lea     edx, [rdi-2Dh]
0x180017a7c  mov     r8, r13
0x180017a7f  call    WPP_SF_
0x180017a84  jmp     loc_18001793D
0x180017a89  test    dword ptr [rbx+2CCh], 1000h
0x180017a93  jz      short loc_180017AC5
0x180017a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a9c  cmp     rcx, r12
0x180017a9f  jz      short loc_180017ABF
0x180017aa1  test    byte ptr [rcx+1Ch], 2
0x180017aa5  jz      short loc_180017ABF
0x180017aa7  mov     r9, [rbx+238h]
0x180017aae  mov     edx, 8Bh
0x180017ab3  mov     rcx, [rcx+10h]
0x180017ab7  mov     r8, r13
0x180017aba  call    WPP_SF_S
0x180017abf  mov     [rbx+0F2Ch], esi
0x180017ac5  cmp     [rbx+159Dh], r15b
0x180017acc  jnz     loc_18001829F
0x180017ad2  mov     eax, 4000h
0x180017ad7  test    [rbx+1580h], eax
0x180017add  jnz     short loc_180017B0E
0x180017adf  test    dword ptr [rbx+2B4h], 0FFEEFE7Fh
0x180017ae9  jnz     short loc_180017B0E
0x180017aeb  mov     [rbx+0F30h], esi
0x180017af1  mov     rdx, [rbx+260h]
0x180017af8  test    rdx, rdx
0x180017afb  jz      loc_18001829F
0x180017b01  mov     rdx, [rdx]
0x180017b04  call    TfsReleaseEntry
0x180017b09  jmp     loc_18001829F
0x180017b0e  call    cs:__imp_RevertToSelf
0x180017b14  cmp     [rbx+274h], r15d
0x180017b1b  jz      loc_180017C82
0x180017b21  mov     rdi, [rbx+260h]
0x180017b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b2f  cmp     rcx, r12
0x180017b32  jz      short loc_180017B52
0x180017b34  test    byte ptr [rcx+1Ch], 2
0x180017b38  jz      short loc_180017B52
0x180017b3a  mov     r9, [rbx+248h]
0x180017b41  mov     edx, 8Ch
0x180017b46  mov     rcx, [rcx+10h]
0x180017b4a  mov     r8, r13
0x180017b4d  call    WPP_SF_S
0x180017b52  mov     rdx, [rdi]
0x180017b55  call    TfsReferenceEntry
0x180017b5a  mov     eax, [rdi+10h]
0x180017b5d  mov     ecx, 40h ; '@'; uFlags
0x180017b62  lea     eax, ds:2[rax*2]
0x180017b69  mov     edx, eax; uBytes
0x180017b6b  mov     r14d, eax
0x180017b6e  call    cs:__imp_LocalAlloc
0x180017b74  mov     [rbx+240h], rax
0x180017b7b  test    rax, rax
0x180017b7e  jz      loc_180017C56
0x180017b84  mov     r9, [rdi+8]
0x180017b88  lea     rax, [rbx+908h]
0x180017b8f  mov     ecx, 7FFFFFFEh
  ... truncated ...
```
