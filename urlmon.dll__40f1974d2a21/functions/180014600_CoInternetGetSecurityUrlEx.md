# CoInternetGetSecurityUrlEx

- ea: `0x180014600`
- end: `0x1800150d8`
- name: `CoInternetGetSecurityUrlEx`
- size: `2776`
- prototype: `HRESULT __stdcall(IUri *pUri, IUri **ppSecUri, PSUACTION psuAction, DWORD_PTR dwReserved)`
- caller_count: `5`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011540`
- `0x180012e20`
- `0x18003a370`
- `0x1800ffddc`
- `0x180102308`

## callees

- `0x180014600`
- `0x1800150e0`
- `0x18001511c`
- `0x1800151d0`
- `0x180018e90`
- `0x18001e340`
- `0x18002c428`
- `0x180045a68`
- `0x1800478b0`
- `0x18004ca90`
- `0x180061440`
- `0x18006a260`
- `0x1800f52b8`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180014bb6`
- `msvcrt!wcsrchr` at `0x180014bb6`
- `msvcrt!wcschr` at `0x1800148ba`
- `msvcrt!wcschr` at `0x1800148ba`
- `iertutil!CreateUri` at `0x180014998`
- `iertutil!CreateUri` at `0x180014998`
- `iertutil!GetIUriPriv` at `0x180014698`
- `iertutil!GetIUriPriv` at `0x180014698`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014715`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014715`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800146e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800146e3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180014740`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180014740`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800147a0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180014aa2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800147a0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180014aa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001481b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001481b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014beb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014beb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014edd`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180014fd5`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180014fd5`

## pseudocode

```c
HRESULT __stdcall CoInternetGetSecurityUrlEx(IUri *pUri, IUri **ppSecUri, PSUACTION psuAction, DWORD_PTR dwReserved)
{
  volatile signed __int32 *v7; // r13
  struct IUriVtbl *lpVtbl; // rax
  HRESULT result; // eax
  WCHAR *v10; // r12
  COInetSession *v11; // rax
  int v12; // esi
  WCHAR *v13; // rdx
  unsigned __int16 *v14; // rbx
  unsigned int v15; // r9d
  int j; // ebx
  __int64 v17; // rdi
  WCHAR v18; // cx
  __int64 v19; // rdi
  unsigned __int64 v20; // rbx
  SIZE_T v21; // rsi
  WCHAR *v22; // rax
  WCHAR *v23; // r15
  wchar_t *v24; // r8
  __int64 v25; // rcx
  WCHAR *v26; // rdx
  __int64 v27; // r9
  wchar_t *v28; // rcx
  wchar_t *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  WCHAR *v32; // r8
  WCHAR *v33; // rcx
  HRESULT Uri; // eax
  COInetSession *v35; // rax
  int i; // ebx
  __int64 v37; // rdi
  WCHAR v38; // cx
  int v39; // eax
  __int64 v40; // rax
  unsigned __int64 v42; // r14
  SIZE_T v43; // rdi
  unsigned __int16 *v44; // rax
  int ProtocolInfo; // edi
  wchar_t *v46; // rax
  const unsigned __int16 *v47; // rdi
  __int64 v48; // rax
  unsigned int v49; // eax
  int FirstCF; // eax
  unsigned int v51; // edi
  unsigned int v52; // eax
  unsigned __int16 *v53; // r14
  unsigned int v54; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v55; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v56; // [rsp+60h] [rbp-A8h]
  LPWSTR pszPath; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v58[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v59; // [rsp+78h] [rbp-90h] BYREF
  __int64 v60; // [rsp+80h] [rbp-88h] BYREF
  int v61; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v62; // [rsp+8Ch] [rbp-7Ch] BYREF
  PCWSTR psz1; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v64; // [rsp+98h] [rbp-70h] BYREF
  IUri **ppURI; // [rsp+A0h] [rbp-68h]
  struct _GUID v66; // [rsp+A8h] [rbp-60h] BYREF
  WCHAR String1[8]; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t Str[32]; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t pszDest[272]; // [rsp+108h] [rbp+0h] BYREF

  ppURI = ppSecUri;
  if ( !pUri || !ppSecUri )
    return -2147024809;
  if ( (unsigned int)(psuAction - 1) > 1 )
    return -2147467263;
  v7 = 0;
  *ppSecUri = 0;
  lpVtbl = pUri->lpVtbl;
  LODWORD(v59) = 0;
  if ( !((unsigned int (__fastcall *)(IUri *, __int64 *, PSUACTION, DWORD_PTR))lpVtbl->GetScheme)(
          pUri,
          &v59,
          psuAction,
          dwReserved)
    && ((unsigned int)(v59 - 1) <= 1 || (_DWORD)v59 == 11) )
  {
    ((void (__fastcall *)(IUri *))pUri->lpVtbl->AddRef)(pUri);
    *ppSecUri = pUri;
    return 0;
  }
  psz1 = 0;
  v61 = 0;
  v60 = 0;
  result = GetIUriPriv(pUri, &v60);
  if ( result >= 0 )
  {
    (*(void (__fastcall **)(__int64, PCWSTR *, int *))(*(_QWORD *)v60 + 232LL))(v60, &psz1, &v61);
    v10 = (WCHAR *)psz1;
    if ( !psz1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      return -2147024809;
    }
    LODWORD(v56) = 0;
    EnterCriticalSection(&g_mxsOInet);
    v11 = g_pCOInetSession;
    if ( g_pCOInetSession )
    {
      v12 = 0;
    }
    else
    {
      v35 = (COInetSession *)operator new(0x180u);
      if ( v35 && (v11 = COInetSession::COInetSession(v35)) != 0 )
      {
        v12 = 0;
        g_pCOInetSession = v11;
      }
      else
      {
        v11 = g_pCOInetSession;
        v12 = -2147024882;
      }
      if ( !v11 )
      {
        LeaveCriticalSection(&g_mxsOInet);
        v12 = 0;
        v54 = 0;
        goto LABEL_17;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)v11 + 4);
    v7 = (volatile signed __int32 *)g_pCOInetSession;
    LeaveCriticalSection(&g_mxsOInet);
    if ( v12 )
    {
      v12 = 0;
      v54 = 0;
      goto LABEL_17;
    }
    while ( 1 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 12 )
          goto LABEL_85;
        v37 = 40LL * i;
        if ( !StrCmpNICW(
                v10,
                *(LPCWSTR *)((char *)&off_18011D010 + v37),
                *(_DWORD *)((char *)&off_18011D010 + v37 + 32)) )
        {
          v38 = v10[*(int *)((char *)&off_18011D010 + v37 + 32)];
          if ( v38 == 58 || !v38 )
            break;
        }
      }
      v39 = *(_DWORD *)((char *)&off_18011D010 + v37 + 16);
      if ( v39 && v39 != 7 )
        goto LABEL_16;
LABEL_85:
      v40 = -1;
      while ( v10[++v40] != 0 )
        ;
      LODWORD(v42) = v40 + 1;
      v55 = 0;
      v43 = saturated_mul((unsigned int)(v40 + 1), 2u);
      v44 = (unsigned __int16 *)CoTaskMemAlloc(v43);
      v14 = v44;
      if ( !v44 )
        goto LABEL_123;
      memset_0(v44, 0, v43);
      pszPath = 0;
      ProtocolInfo = COInetSession::CreateProtocolInfo(
                       (COInetSession *)v7,
                       v10,
                       (struct IInternetProtocolInfo **)&pszPath);
      if ( ProtocolInfo >= 0 )
        ProtocolInfo = (*(__int64 (__fastcall **)(LPWSTR, WCHAR *, __int64, _QWORD, unsigned __int16 *, _DWORD, unsigned int *, _DWORD))(*(_QWORD *)pszPath + 24LL))(
                         pszPath,
                         v10,
                         3,
                         0,
                         v14,
                         v42,
                         &v55,
                         0);
      if ( pszPath )
        (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)pszPath + 16LL))(pszPath);
      if ( ProtocolInfo >= 0
        || ProtocolInfo == -2146695931
        || ProtocolInfo == -2146697199
        || ProtocolInfo == -2146697202
        || ProtocolInfo == -2147024891 )
      {
        v12 = ProtocolInfo;
        if ( !ProtocolInfo )
          goto LABEL_117;
      }
      else
      {
        ProtocolInfo = -2146697199;
        v12 = -2146697199;
      }
      if ( GetUrlScheme(v10) == 28 )
      {
        v46 = wcsrchr(v10, 1u);
        if ( v46 )
        {
          v47 = v46 + 1;
          v48 = -1;
          do
            ++v48;
          while ( v47[v48] );
          v49 = v48 + 1;
          v55 = v49;
          if ( v49 > (unsigned int)v42 )
          {
            CoTaskMemFree(v14);
            v14 = (unsigned __int16 *)operator new(saturated_mul(v55, 2u));
            v49 = v55;
          }
          StringCchCopyW(v14, v49, v47);
          goto LABEL_119;
        }
      }
LABEL_117:
      if ( ProtocolInfo == 1 )
      {
        v52 = v55;
        if ( (unsigned int)v42 >= v55 )
          v52 = 2085;
        v42 = v52;
        CoTaskMemFree(v14);
        v14 = (unsigned __int16 *)operator new(saturated_mul(v42, 2u));
        if ( !v14 )
        {
LABEL_123:
          v12 = -2147024882;
LABEL_16:
          v15 = 0;
          v54 = 0;
          if ( v12 < 0 )
          {
LABEL_167:
            v23 = v10;
            goto LABEL_58;
          }
LABEL_17:
          for ( j = 0; ; ++j )
          {
            if ( j >= 12 )
              goto LABEL_23;
            v17 = 40LL * j;
            if ( !StrCmpNICW(
                    v10,
                    *(LPCWSTR *)((char *)&off_18011D010 + v17),
                    *(_DWORD *)((char *)&off_18011D010 + v17 + 32)) )
            {
              v18 = v10[*(int *)((char *)&off_18011D010 + v17 + 32)];
              if ( v18 == 58 || !v18 )
                break;
            }
          }
          if ( !*(_DWORD *)((char *)&off_18011D010 + v17 + 16) )
          {
LABEL_23:
            if ( psuAction == PSU_DEFAULT )
            {
              if ( !v10 )
              {
                v10 = (WCHAR *)psz1;
                LODWORD(v56) = 0;
              }
              v19 = -1;
              do
                ++v19;
              while ( v10[v19] );
              LODWORD(v64) = 0;
              v20 = (unsigned int)(v19 + 1);
              v21 = saturated_mul(v20, 2u);
              v22 = (WCHAR *)CoTaskMemAlloc(v21);
              v23 = v22;
              if ( !v22 )
              {
                v15 = v54;
                v12 = -2147024882;
                goto LABEL_58;
              }
              memset_0(v22, 0, v21);
              v15 = 1;
              v54 = 1;
              if ( !v7 )
                goto LABEL_48;
              v24 = Str;
              *(_QWORD *)v58 = 0;
              pszPath = 0;
              v12 = -2146697203;
              v66 = 0;
              v62 = 0;
              v25 = 31;
              v26 = v10;
              v27 = 32;
              do
              {
                if ( !v25 )
                  break;
                if ( !*v26 )
                  break;
                *v24++ = *v26++;
                --v25;
                --v27;
              }
              while ( v27 );
              v28 = v24 - 1;
              if ( v27 )
                v28 = v24;
              *v28 = 0;
              v29 = wcschr(Str, 0x3Au);
              if ( !v29 )
              {
LABEL_37:
                v30 = *(_QWORD *)v58;
                goto LABEL_38;
              }
              *v29 = 0;
              FirstCF = COInetSession::FindFirstCF(
                          (COInetSession *)v7,
                          Str,
                          (struct IClassFactory **)&pszPath,
                          &v66,
                          &v62,
                          0);
              v12 = FirstCF;
              if ( FirstCF )
              {
                if ( FirstCF != -2146695931 )
                  v12 = -2147221020;
LABEL_129:
                v13 = 0;
                v30 = 0;
                *(_QWORD *)v58 = 0;
              }
              else
              {
                v12 = (**(__int64 (__fastcall ***)(LPWSTR, GUID *, unsigned int *))pszPath)(
                        pszPath,
                        &IID_IInternetProtocolInfo,
                        v58);
                if ( v12 )
                  v12 = (*(__int64 (__fastcall **)(LPWSTR, _QWORD, GUID *, unsigned int *))(*(_QWORD *)pszPath + 24LL))(
                          pszPath,
                          0,
                          &IID_IInternetProtocolInfo,
                          v58);
                (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)pszPath + 16LL))(pszPath);
                if ( v12 )
                  goto LABEL_129;
                v30 = *(_QWORD *)v58;
                v13 = 0;
              }
              if ( v12 >= 0 )
              {
                v12 = (*(__int64 (__fastcall **)(__int64, WCHAR *, __int64, _QWORD, WCHAR *, int, unsigned __int64 *, _DWORD))(*(_QWORD *)v30 + 24LL))(
                        v30,
                        v10,
                        17,
                        0,
                        v23,
                        (int)v19 + 1,
                        &v64,
                        0);
                goto LABEL_37;
              }
LABEL_38:
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              if ( v12 >= 0 || v12 == -2146695931 )
              {
LABEL_46:
                if ( v12 == -2146697199 )
                  goto LABEL_47;
                v15 = v54;
                if ( v12 == 1 )
                  v12 = -2147418113;
              }
              else
              {
                if ( v12 != -2146697199 )
                {
                  if ( v12 != -2147024891 && v12 != -2146697202 )
                    v12 = -2146697199;
                  goto LABEL_46;
                }
LABEL_47:
                v15 = v54;
LABEL_48:
                if ( (_DWORD)v19 == -1 )
                {
                  v12 = -2147024809;
                }
                else if ( v20 > 0x7FFFFFFF )
                {
                  v12 = -2147024809;
                  *v23 = 0;
                }
                else
                {
                  v31 = (unsigned int)v19;
                  if ( (unsigned int)v19 > 0x7FFFFFFEuLL )
                  {
                    v12 = -2147024809;
                    *v23 = 0;
                  }
                  else
                  {
                    v13 = v10;
                    v32 = v23;
                    do
                    {
                      if ( !v31 )
                        break;
                      if ( !*v13 )
                        break;
                      *v32++ = *v13++;
                      --v31;
                      --v20;
                    }
                    while ( v20 );
                    v33 = v32 - 1;
                    v12 = -2147024774;
                    if ( v20 )
                    {
                      v33 = v32;
                      v12 = 0;
                    }
                    *v33 = 0;
                  }
                }
              }
LABEL_58:
              if ( !v12 )
              {
                Uri = CreateUri(v23, 0x3002B86u, 0, ppURI);
                v15 = v54;
                v12 = Uri;
              }
              if ( v15 && v23 )
                CoTaskMemFree(v23);
              if ( (_DWORD)v56 && v10 )
                CoTaskMemFree(v10);
              if ( v60 )
                (*(void (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v60 + 16LL))(v60, v13);
              if ( v7 )
                _InterlockedDecrement(v7 + 4);
              return v12;
            }
          }
          v15 = v54;
          goto LABEL_167;
        }
        v12 = COInetSession::ParseUrl((COInetSession *)(v7 + 2), v10, PARSE_SECURITY_URL, 0, v14, v42, &v55, 0);
        if ( v12 == 1 )
        {
          v12 = -2147418113;
LABEL_15:
          CoTaskMemFree(v14);
          goto LABEL_16;
        }
      }
      if ( v12 )
      {
LABEL_134:
        if ( v12 == -2146697199 || v12 == -2147467263 )
          v12 = 0;
LABEL_14:
        if ( !v14 )
          goto LABEL_16;
        goto LABEL_15;
      }
LABEL_119:
      wcscpy(String1, L"file:");
      v66 = *(struct _GUID *)L"file://";
      if ( v55 != 5 || (unsigned int)StrCmpNIIW(String1, v14, 5u) )
      {
        v12 = 0;
      }
      else
      {
        *(_QWORD *)v58 = 268;
        pszPath = pszDest;
        v54 = 0;
        v12 = StringCchCopyNExW(pszDest, 0x10Cu, (const unsigned __int16 *)&v66, 7u, &pszPath, &v64, 0);
        if ( v12 >= 0 )
        {
          v12 = SHGetFolderPathW(0, 36, 0, 0x4000u, pszPath);
          if ( !v12 )
          {
            v12 = StringCchLengthW(pszDest, 0x10Cu, (unsigned __int64 *)v58);
            if ( !v12 )
            {
              v51 = v58[0];
              if ( (unsigned __int64)(*(_QWORD *)v58 + 1LL) < *(_QWORD *)v58 )
              {
                v12 = -2147024362;
                goto LABEL_14;
              }
              v12 = LongLongToULong(*(_QWORD *)v58 + 1LL, &v54);
              if ( v12 >= 0 )
              {
                if ( v54 <= (unsigned int)v42 )
                {
                  v12 = StringCchCopyW(v14, (unsigned int)v42, pszDest);
                }
                else
                {
                  v53 = OLESTRDuplicate(pszDest, v51);
                  if ( !v53 )
                  {
                    v12 = -2147024882;
                    goto LABEL_14;
                  }
                  if ( v14 )
                    CoTaskMemFree(v14);
                  v14 = v53;
                  v55 = v51;
                }
              }
            }
          }
        }
        if ( v12 )
          goto LABEL_134;
      }
      if ( !StrCmpW(v10, v14) )
        goto LABEL_14;
      if ( (_DWORD)v56 && v10 )
        CoTaskMemFree(v10);
      v10 = v14;
      LODWORD(v56) = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014600  mov     r11, rsp
0x180014603  push    rbp
0x180014604  push    rbx
0x180014605  push    rsi
0x180014606  push    rdi
0x180014607  push    r15
0x180014609  lea     rbp, [r11-268h]
0x180014610  sub     rsp, 340h
0x180014617  mov     rax, cs:__security_cookie
0x18001461e  xor     rax, rsp
0x180014621  mov     [rbp+260h+var_40], rax
0x180014628  mov     [rbp+260h+ppURI], rdx
0x18001462c  mov     r15d, r8d
0x18001462f  mov     rdi, rdx
0x180014632  mov     rbx, rcx
0x180014635  test    rcx, rcx
0x180014638  jz      loc_180014D5A
0x18001463e  test    rdx, rdx
0x180014641  jz      loc_180014D5A
0x180014647  lea     eax, [r8-1]
0x18001464b  cmp     eax, 1
0x18001464e  ja      loc_180014EA3
0x180014654  mov     [r11+18h], r12
0x180014658  mov     [r11-30h], r13
0x18001465c  xor     r13d, r13d
0x18001465f  mov     [rdx], r13
0x180014662  lea     rdx, [rsp+360h+var_2F0]
0x180014667  mov     rax, [rcx]
0x18001466a  mov     dword ptr [rsp+360h+var_2F0], r13d
0x18001466f  mov     rax, [rax+0C0h]
0x180014676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001467b  test    eax, eax
0x18001467d  jz      loc_180014C41
0x180014683  lea     rdx, [rsp+360h+var_2E8]
0x180014688  mov     [rbp+260h+psz1], r13
0x18001468c  mov     rcx, rbx
0x18001468f  mov     [rbp+260h+var_2E0], r13d
0x180014693  mov     [rsp+360h+var_2E8], r13
0x180014698  call    cs:__imp_GetIUriPriv
0x18001469e  test    eax, eax
0x1800146a0  js      loc_1800149D3
0x1800146a6  mov     rcx, [rsp+360h+var_2E8]
0x1800146ab  lea     r8, [rbp+260h+var_2E0]
0x1800146af  lea     rdx, [rbp+260h+psz1]
0x1800146b3  mov     rax, [rcx]
0x1800146b6  mov     rax, [rax+0E8h]
0x1800146bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c2  mov     r12, [rbp+260h+psz1]
0x1800146c6  test    r12, r12
0x1800146c9  jz      loc_180014EAD
0x1800146cf  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x1800146d6  mov     [rsp+360h+var_30], r14
0x1800146de  mov     dword ptr [rsp+360h+var_308], r13d
0x1800146e3  call    cs:__imp_EnterCriticalSection
0x1800146e9  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x1800146f0  lea     r14, off_18011D010; "h\x00t\x00t\x00p"
0x1800146f7  test    rax, rax
0x1800146fa  jz      loc_180014A2E
0x180014700  mov     esi, r13d
0x180014703  lock inc dword ptr [rax+10h]
0x180014707  mov     r13, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001470e  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180014715  call    cs:__imp_LeaveCriticalSection
0x18001471b  test    esi, esi
0x18001471d  jz      loc_180014A80
0x180014723  xor     esi, esi
0x180014725  mov     [rsp+360h+var_310], esi
0x180014729  jmp     short loc_18001477B
0x18001472b  mov     rbx, r14
0x18001472e  mov     [rsp+360h+var_30C], edi
0x180014732  test    esi, esi
0x180014734  jnz     loc_180014E46
0x18001473a  mov     rdx, rbx; psz2
0x18001473d  mov     rcx, r12; psz1
0x180014740  call    cs:__imp_StrCmpW
0x180014746  test    eax, eax
0x180014748  jnz     loc_180014C80
0x18001474e  test    rbx, rbx
0x180014751  jz      short loc_18001475C
0x180014753  mov     rcx, rbx; pv
0x180014756  call    cs:__imp_CoTaskMemFree
0x18001475c  lea     r14, off_18011D010; "h\x00t\x00t\x00p"
0x180014763  mov     edi, dword ptr [rsp+360h+var_308]
0x180014767  xor     r9d, r9d
0x18001476a  mov     [rsp+360h+var_310], r9d
0x18001476f  mov     dword ptr [rsp+360h+var_308], edi
0x180014773  test    esi, esi
0x180014775  js      loc_1800150D0
0x18001477b  xor     ebx, ebx
0x18001477d  nop     dword ptr [rax]
0x180014780  cmp     ebx, 0Ch
0x180014783  jge     short loc_1800147CE
0x180014785  movsxd  rax, ebx
0x180014788  lea     rcx, [rax+rax*4]
0x18001478c  lea     rdi, ds:0[rcx*8]
0x180014794  mov     rcx, r12; pszStr1
0x180014797  mov     r8d, [rdi+r14+20h]; nChar
0x18001479c  mov     rdx, [rdi+r14]; pszStr2
0x1800147a0  call    cs:__imp_StrCmpNICW
0x1800147a6  test    eax, eax
0x1800147a8  jz      short loc_1800147AE
0x1800147aa  inc     ebx
0x1800147ac  jmp     short loc_180014780
0x1800147ae  movsxd  rax, dword ptr [rdi+r14+20h]
0x1800147b3  movzx   ecx, word ptr [r12+rax*2]
0x1800147b8  cmp     cx, 3Ah ; ':'
0x1800147bc  jnz     loc_180014A00
0x1800147c2  cmp     dword ptr [rdi+r14+10h], 0
0x1800147c8  jnz     loc_1800150CB
0x1800147ce  cmp     r15d, 1
0x1800147d2  jnz     loc_1800150CB
0x1800147d8  test    r12, r12
0x1800147db  jz      loc_18001506A
0x1800147e1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800147e8  mov     rdi, rcx
0x1800147eb  nop     dword ptr [rax+rax+00h]
0x1800147f0  inc     rdi
0x1800147f3  cmp     word ptr [r12+rdi*2], 0
0x1800147f9  jnz     short loc_1800147F0
0x1800147fb  lea     r14d, [rdi+1]
0x1800147ff  mov     dword ptr [rbp+260h+var_2D0], 0
0x180014806  mov     ebx, r14d
0x180014809  mov     eax, 2
0x18001480e  mul     rbx
0x180014811  mov     rsi, rax
0x180014814  cmovb   rsi, rcx
0x180014818  mov     rcx, rsi; cb
0x18001481b  call    cs:__imp_CoTaskMemAlloc
0x180014821  mov     r15, rax
0x180014824  test    rax, rax
0x180014827  jz      loc_180014D2C
0x18001482d  mov     r8, rsi; Size
0x180014830  xor     edx, edx; Val
0x180014832  mov     rcx, rax; void *
0x180014835  call    memset_0
0x18001483a  mov     r9d, 1
0x180014840  mov     [rsp+360h+var_310], r9d
0x180014845  test    r13, r13
0x180014848  jz      loc_180014912
0x18001484e  xor     r10d, r10d
0x180014851  lea     r8, [rbp+260h+Str]
0x180014855  xorps   xmm0, xmm0
0x180014858  mov     qword ptr [rsp+360h+var_2F8], r10
0x18001485d  mov     [rsp+360h+var_300], r10
0x180014862  mov     esi, 800C000Dh
0x180014867  movups  xmmword ptr [rbp+260h+var_2C0.Data1], xmm0
0x18001486b  mov     [rbp+260h+var_2DC], r10d
0x18001486f  mov     ecx, 1Fh
0x180014874  mov     rdx, r12
0x180014877  mov     r9d, 20h ; ' '
0x18001487d  nop     dword ptr [rax]
0x180014880  test    rcx, rcx
0x180014883  jz      short loc_1800148A2
0x180014885  movzx   eax, word ptr [rdx]
0x180014888  test    ax, ax
0x18001488b  jz      short loc_1800148A2
0x18001488d  mov     [r8], ax
0x180014891  add     rdx, 2
0x180014895  add     r8, 2
0x180014899  dec     rcx
0x18001489c  sub     r9, 1
0x1800148a0  jnz     short loc_180014880
0x1800148a2  test    r9, r9
0x1800148a5  lea     rcx, [r8-2]
0x1800148a9  mov     edx, 3Ah ; ':'; Ch
0x1800148ae  cmovnz  rcx, r8
0x1800148b2  mov     [rcx], r10w
0x1800148b6  lea     rcx, [rbp+260h+Str]; Str
0x1800148ba  call    cs:__imp_wcschr
0x1800148c0  test    rax, rax
0x1800148c3  jnz     loc_180014D64
0x1800148c9  mov     rcx, qword ptr [rsp+360h+var_2F8]
0x1800148ce  test    rcx, rcx
0x1800148d1  jz      short loc_1800148DF
0x1800148d3  mov     rax, [rcx]
0x1800148d6  mov     rax, [rax+10h]
0x1800148da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148df  mov     eax, 800C0011h
0x1800148e4  test    esi, esi
0x1800148e6  jns     short loc_180014905
0x1800148e8  cmp     esi, 800C0505h
0x1800148ee  jz      short loc_180014905
0x1800148f0  cmp     esi, eax
0x1800148f2  jz      short loc_18001490D
0x1800148f4  cmp     esi, 80070005h
0x1800148fa  jz      short loc_180014905
0x1800148fc  cmp     esi, 800C000Eh
0x180014902  cmovnz  esi, eax
0x180014905  cmp     esi, eax
0x180014907  jnz     loc_180015087
0x18001490d  mov     r9d, [rsp+360h+var_310]
0x180014912  test    r14d, r14d
0x180014915  jz      loc_1800150B2
0x18001491b  cmp     rbx, 7FFFFFFFh
0x180014922  ja      loc_1800150AB
0x180014928  mov     eax, edi
0x18001492a  cmp     rax, 7FFFFFFEh
0x180014930  ja      loc_180014D40
0x180014936  mov     rdx, r12
0x180014939  mov     r8, r15
0x18001493c  nop     dword ptr [rax+00h]
0x180014940  test    rax, rax
0x180014943  jz      short loc_180014962
0x180014945  movzx   ecx, word ptr [rdx]
0x180014948  test    cx, cx
0x18001494b  jz      short loc_180014962
0x18001494d  mov     [r8], cx
0x180014951  add     rdx, 2
0x180014955  add     r8, 2
0x180014959  dec     rax
0x18001495c  sub     rbx, 1
0x180014960  jnz     short loc_180014940
0x180014962  test    rbx, rbx
0x180014965  lea     rcx, [r8-2]
0x180014969  mov     esi, 8007007Ah
0x18001496e  cmovnz  rcx, r8
0x180014972  xor     eax, eax
0x180014974  test    rbx, rbx
0x180014977  cmovnz  esi, eax
0x18001497a  mov     [rcx], ax
0x18001497d  mov     r14, [rsp+360h+var_30]
0x180014985  test    esi, esi
0x180014987  jnz     short loc_1800149A5
0x180014989  mov     r9, [rbp+260h+ppURI]; ppURI
0x18001498d  xor     r8d, r8d; dwReserved
0x180014990  mov     edx, 3002B86h; dwFlags
0x180014995  mov     rcx, r15; pwzURI
0x180014998  call    cs:__imp_CreateUri
0x18001499e  mov     r9d, [rsp+360h+var_310]
0x1800149a3  mov     esi, eax
0x1800149a5  test    r9d, r9d
0x1800149a8  jnz     short loc_180014A0E
0x1800149aa  cmp     dword ptr [rsp+360h+var_308], 0
0x1800149af  jnz     short loc_180014A1E
0x1800149b1  mov     rcx, [rsp+360h+var_2E8]
0x1800149b6  test    rcx, rcx
0x1800149b9  jz      short loc_1800149C7
0x1800149bb  mov     rax, [rcx]
0x1800149be  mov     rax, [rax+10h]
0x1800149c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149c7  test    r13, r13
0x1800149ca  jz      short loc_1800149D1
0x1800149cc  lock dec dword ptr [r13+10h]
0x1800149d1  mov     eax, esi
0x1800149d3  mov     r12, [rsp+360h+arg_10]
0x1800149db  mov     r13, [rsp+338h]
0x1800149e3  mov     rcx, [rbp+260h+var_40]
0x1800149ea  xor     rcx, rsp; StackCookie
0x1800149ed  call    __security_check_cookie
0x1800149f2  add     rsp, 340h
0x1800149f9  pop     r15
0x1800149fb  pop     rdi
0x1800149fc  pop     rsi
0x1800149fd  pop     rbx
0x1800149fe  pop     rbp
0x1800149ff  retn
0x180014a00  test    cx, cx
0x180014a03  jnz     loc_1800147AA
0x180014a09  jmp     loc_1800147C2
0x180014a0e  test    r15, r15
0x180014a11  jz      short loc_1800149AA
0x180014a13  mov     rcx, r15; pv
0x180014a16  call    cs:__imp_CoTaskMemFree
0x180014a1c  jmp     short loc_1800149AA
0x180014a1e  test    r12, r12
0x180014a21  jz      short loc_1800149B1
0x180014a23  mov     rcx, r12; pv
0x180014a26  call    cs:__imp_CoTaskMemFree
0x180014a2c  jmp     short loc_1800149B1
0x180014a2e  mov     ecx, 180h; Size
0x180014a33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014a38  test    rax, rax
0x180014a3b  jz      loc_180014C30
0x180014a41  mov     rcx, rax; this
0x180014a44  call    ??0COInetSession@@QEAA@XZ; COInetSession::COInetSession(void)
0x180014a49  test    rax, rax
0x180014a4c  jz      loc_180014C30
0x180014a52  mov     esi, r13d
0x180014a55  mov     cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA, rax; COInetSession * g_pCOInetSession
0x180014a5c  test    rax, rax
0x180014a5f  jnz     loc_180014703
0x180014a65  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180014a6c  call    cs:__imp_LeaveCriticalSection
0x180014a72  xor     esi, esi
0x180014a74  mov     [rsp+360h+var_310], esi
0x180014a78  jmp     loc_18001477B
0x180014a80  xor     ebx, ebx
0x180014a82  cmp     ebx, 0Ch
0x180014a85  jge     short loc_180014AD1
0x180014a87  movsxd  rax, ebx
0x180014a8a  lea     rcx, [rax+rax*4]
0x180014a8e  lea     rdi, ds:0[rcx*8]
0x180014a96  mov     rcx, r12; pszStr1
0x180014a99  mov     r8d, [rdi+r14+20h]; nChar
0x180014a9e  mov     rdx, [rdi+r14]; pszStr2
0x180014aa2  call    cs:__imp_StrCmpNICW
0x180014aa8  test    eax, eax
0x180014aaa  jz      short loc_180014AB0
0x180014aac  inc     ebx
0x180014aae  jmp     short loc_180014A82
  ... truncated ...
```
