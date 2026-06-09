# CoInternetGetSecurityUrlEx

- ea: `0x18001cb00`
- end: `0x18001d53a`
- name: `CoInternetGetSecurityUrlEx`
- size: `2618`
- prototype: `HRESULT __stdcall(IUri *pUri, IUri **ppSecUri, PSUACTION psuAction, DWORD_PTR dwReserved)`
- caller_count: `5`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019b40`
- `0x18001b230`
- `0x18003d4f0`
- `0x18010ae70`
- `0x18010d4b8`

## callees

- `0x18001cb00`
- `0x18001d540`
- `0x18001db50`
- `0x18001db94`
- `0x180024ea0`
- `0x1800325fc`
- `0x1800498c0`
- `0x180064f50`
- `0x18006c5dc`
- `0x180077a40`
- `0x180088604`
- `0x1800ff8b4`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001d0df`
- `msvcrt!wcsrchr` at `0x18001d0df`
- `iertutil!CreateUri` at `0x18001ce60`
- `iertutil!CreateUri` at `0x18001ce60`
- `iertutil!GetIUriPriv` at `0x18001cb98`
- `iertutil!GetIUriPriv` at `0x18001cb98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cbe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cbe9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18001cc52`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18001cc52`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ccc0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001cfc4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ccc0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001cfc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cd3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d02f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cd3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d02f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cee6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cefc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d11a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d2d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d2f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d33d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cee6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cefc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d11a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d2d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d2f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d33d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18001d43c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18001d43c`

## pseudocode

```c
HRESULT __stdcall CoInternetGetSecurityUrlEx(IUri *pUri, IUri **ppSecUri, PSUACTION psuAction, DWORD_PTR dwReserved)
{
  volatile signed __int32 *v7; // r12
  struct IUriVtbl *lpVtbl; // rax
  HRESULT result; // eax
  WCHAR *v10; // r14
  COInetSession *v11; // rax
  int ProtocolInfo; // esi
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
  WCHAR *v23; // r13
  __int64 v24; // rcx
  WCHAR *v25; // r8
  WCHAR *v26; // rcx
  HRESULT Uri; // eax
  COInetSession *v28; // rax
  int i; // ebx
  __int64 v30; // rdi
  WCHAR v31; // cx
  int v32; // eax
  __int64 v33; // rax
  unsigned __int64 v35; // r15
  SIZE_T v36; // rdi
  unsigned __int16 *v37; // rax
  int v38; // edi
  wchar_t *v39; // rax
  const unsigned __int16 *v40; // rdi
  __int64 v41; // rax
  unsigned int v42; // eax
  unsigned int v43; // edi
  unsigned int v44; // eax
  unsigned __int16 *v45; // r15
  unsigned int v46; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v47; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v48; // [rsp+60h] [rbp-A8h]
  struct IInternetProtocolInfo *v49; // [rsp+68h] [rbp-A0h] BYREF
  LPWSTR pszPath; // [rsp+70h] [rbp-98h] BYREF
  __int64 v51; // [rsp+78h] [rbp-90h] BYREF
  __int64 v52; // [rsp+80h] [rbp-88h] BYREF
  int v53; // [rsp+88h] [rbp-80h] BYREF
  PCWSTR psz1; // [rsp+90h] [rbp-78h] BYREF
  IUri **ppURI; // [rsp+98h] [rbp-70h]
  unsigned __int64 v56; // [rsp+A0h] [rbp-68h] BYREF
  WCHAR String1[8]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 v58[8]; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t pszDest[272]; // [rsp+C8h] [rbp-40h] BYREF

  ppURI = ppSecUri;
  if ( !pUri || !ppSecUri )
    return -2147024809;
  if ( (unsigned int)(psuAction - 1) > 1 )
    return -2147467263;
  v7 = 0;
  *ppSecUri = 0;
  lpVtbl = pUri->lpVtbl;
  LODWORD(v51) = 0;
  if ( !((unsigned int (__fastcall *)(IUri *, __int64 *, PSUACTION, DWORD_PTR))lpVtbl->GetScheme)(
          pUri,
          &v51,
          psuAction,
          dwReserved)
    && ((unsigned int)(v51 - 1) <= 1 || (_DWORD)v51 == 11) )
  {
    ((void (__fastcall *)(IUri *))pUri->lpVtbl->AddRef)(pUri);
    *ppSecUri = pUri;
    return 0;
  }
  psz1 = 0;
  v53 = 0;
  v52 = 0;
  result = GetIUriPriv(pUri, &v52);
  if ( result >= 0 )
  {
    (*(void (__fastcall **)(__int64, PCWSTR *, int *))(*(_QWORD *)v52 + 232LL))(v52, &psz1, &v53);
    v10 = (WCHAR *)psz1;
    if ( !psz1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      return -2147024809;
    }
    LODWORD(v48) = 0;
    EnterCriticalSection(&g_mxsOInet);
    v11 = g_pCOInetSession;
    if ( g_pCOInetSession )
    {
      ProtocolInfo = 0;
    }
    else
    {
      v28 = (COInetSession *)operator new(0x180u);
      if ( v28 && (v11 = COInetSession::COInetSession(v28)) != 0 )
      {
        ProtocolInfo = 0;
        g_pCOInetSession = v11;
      }
      else
      {
        v11 = g_pCOInetSession;
        ProtocolInfo = -2147024882;
      }
      if ( !v11 )
      {
        LeaveCriticalSection(&g_mxsOInet);
        ProtocolInfo = 0;
        v46 = 0;
        goto LABEL_17;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)v11 + 4);
    v7 = (volatile signed __int32 *)g_pCOInetSession;
    LeaveCriticalSection(&g_mxsOInet);
    if ( ProtocolInfo )
    {
      ProtocolInfo = 0;
      v46 = 0;
      goto LABEL_17;
    }
    while ( 1 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 12 )
          goto LABEL_79;
        v30 = 40LL * i;
        if ( !StrCmpNICW(
                v10,
                *(LPCWSTR *)((char *)&off_18012A010 + v30),
                *(_DWORD *)((char *)&off_18012A010 + v30 + 32)) )
        {
          v31 = v10[*(int *)((char *)&off_18012A010 + v30 + 32)];
          if ( v31 == 58 || !v31 )
            break;
        }
      }
      v32 = *(_DWORD *)((char *)&off_18012A010 + v30 + 16);
      if ( v32 && v32 != 7 )
        goto LABEL_16;
LABEL_79:
      v33 = -1;
      while ( v10[++v33] != 0 )
        ;
      LODWORD(v35) = v33 + 1;
      v47 = 0;
      v36 = saturated_mul((unsigned int)(v33 + 1), 2u);
      v37 = (unsigned __int16 *)CoTaskMemAlloc(v36);
      v14 = v37;
      if ( !v37 )
        goto LABEL_117;
      memset_0(v37, 0, v36);
      v49 = 0;
      v38 = COInetSession::CreateProtocolInfo((COInetSession *)v7, v10, &v49);
      if ( v38 >= 0 )
        v38 = ((__int64 (__fastcall *)(struct IInternetProtocolInfo *, WCHAR *, __int64, _QWORD, unsigned __int16 *, _DWORD, unsigned int *, _DWORD))v49->lpVtbl->ParseUrl)(
                v49,
                v10,
                3,
                0,
                v14,
                v35,
                &v47,
                0);
      if ( v49 )
        ((void (__fastcall *)(struct IInternetProtocolInfo *))v49->lpVtbl->Release)(v49);
      if ( v38 >= 0 || v38 == -2146695931 || v38 == -2146697199 || v38 == -2146697202 || v38 == -2147024891 )
      {
        ProtocolInfo = v38;
        if ( !v38 )
          goto LABEL_111;
      }
      else
      {
        v38 = -2146697199;
        ProtocolInfo = -2146697199;
      }
      if ( (unsigned int)GetUrlScheme(v10) == 28 )
      {
        v39 = wcsrchr(v10, 1u);
        if ( v39 )
        {
          v40 = v39 + 1;
          v41 = -1;
          do
            ++v41;
          while ( v40[v41] );
          v42 = v41 + 1;
          v47 = v42;
          if ( v42 > (unsigned int)v35 )
          {
            CoTaskMemFree(v14);
            v14 = (unsigned __int16 *)operator new(saturated_mul(v47, 2u));
            v42 = v47;
          }
          StringCchCopyW(v14, v42, v40);
          goto LABEL_113;
        }
      }
LABEL_111:
      if ( v38 == 1 )
      {
        v44 = v47;
        if ( (unsigned int)v35 >= v47 )
          v44 = 2085;
        v35 = v44;
        CoTaskMemFree(v14);
        v14 = (unsigned __int16 *)operator new(saturated_mul(v35, 2u));
        if ( !v14 )
        {
LABEL_117:
          ProtocolInfo = -2147024882;
LABEL_16:
          v15 = 0;
          v46 = 0;
          if ( ProtocolInfo < 0 )
          {
LABEL_151:
            v23 = v10;
            goto LABEL_52;
          }
LABEL_17:
          for ( j = 0; ; ++j )
          {
            if ( j >= 12 )
              goto LABEL_23;
            v17 = 40LL * j;
            if ( !StrCmpNICW(
                    v10,
                    *(LPCWSTR *)((char *)&off_18012A010 + v17),
                    *(_DWORD *)((char *)&off_18012A010 + v17 + 32)) )
            {
              v18 = v10[*(int *)((char *)&off_18012A010 + v17 + 32)];
              if ( v18 == 58 || !v18 )
                break;
            }
          }
          if ( !*(_DWORD *)((char *)&off_18012A010 + v17 + 16) )
          {
LABEL_23:
            if ( psuAction == PSU_DEFAULT )
            {
              if ( !v10 )
              {
                v10 = (WCHAR *)psz1;
                LODWORD(v48) = 0;
              }
              v19 = -1;
              do
                ++v19;
              while ( v10[v19] );
              LODWORD(v49) = 0;
              v20 = (unsigned int)(v19 + 1);
              v21 = saturated_mul(v20, 2u);
              v22 = (WCHAR *)CoTaskMemAlloc(v21);
              v23 = v22;
              if ( !v22 )
              {
                v15 = v46;
                ProtocolInfo = -2147024882;
                goto LABEL_52;
              }
              memset_0(v22, 0, v21);
              v15 = 1;
              v46 = 1;
              if ( !v7 )
                goto LABEL_42;
              pszPath = 0;
              ProtocolInfo = COInetSession::CreateProtocolInfo(
                               (COInetSession *)v7,
                               v10,
                               (struct IInternetProtocolInfo **)&pszPath);
              if ( ProtocolInfo >= 0 )
                ProtocolInfo = (*(__int64 (__fastcall **)(LPWSTR, WCHAR *, __int64, _QWORD, WCHAR *, int, struct IInternetProtocolInfo **, _DWORD))(*(_QWORD *)pszPath + 24LL))(
                                 pszPath,
                                 v10,
                                 17,
                                 0,
                                 v23,
                                 (int)v19 + 1,
                                 &v49,
                                 0);
              if ( pszPath )
                (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)pszPath + 16LL))(pszPath);
              if ( ProtocolInfo >= 0 || ProtocolInfo == -2146695931 )
              {
LABEL_40:
                if ( ProtocolInfo == -2146697199 )
                  goto LABEL_41;
                v15 = v46;
                if ( ProtocolInfo == 1 )
                  ProtocolInfo = -2147418113;
              }
              else
              {
                if ( ProtocolInfo != -2146697199 )
                {
                  if ( ProtocolInfo != -2147024891 && ProtocolInfo != -2146697202 )
                    ProtocolInfo = -2146697199;
                  goto LABEL_40;
                }
LABEL_41:
                v15 = v46;
LABEL_42:
                if ( (_DWORD)v19 == -1 )
                {
                  ProtocolInfo = -2147024809;
                }
                else if ( v20 > 0x7FFFFFFF )
                {
                  ProtocolInfo = -2147024809;
                  *v23 = 0;
                }
                else if ( (unsigned int)v19 > 0x7FFFFFFE )
                {
                  ProtocolInfo = -2147024809;
                  *v23 = 0;
                }
                else
                {
                  v24 = (unsigned int)v19;
                  v13 = v10;
                  v25 = v23;
                  do
                  {
                    if ( !v24 )
                      break;
                    if ( !*v13 )
                      break;
                    *v25++ = *v13++;
                    --v24;
                    --v20;
                  }
                  while ( v20 );
                  v26 = v25 - 1;
                  ProtocolInfo = -2147024774;
                  if ( v20 )
                  {
                    v26 = v25;
                    ProtocolInfo = 0;
                  }
                  *v26 = 0;
                }
              }
LABEL_52:
              if ( !ProtocolInfo )
              {
                Uri = CreateUri(v23, 0x3002B86u, 0, ppURI);
                v15 = v46;
                ProtocolInfo = Uri;
              }
              if ( v15 && v23 )
                CoTaskMemFree(v23);
              if ( (_DWORD)v48 && v10 )
                CoTaskMemFree(v10);
              if ( v52 )
                (*(void (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v52 + 16LL))(v52, v13);
              if ( v7 )
                _InterlockedDecrement(v7 + 4);
              return ProtocolInfo;
            }
          }
          v15 = v46;
          goto LABEL_151;
        }
        ProtocolInfo = COInetSession::ParseUrl((COInetSession *)(v7 + 2), v10, PARSE_SECURITY_URL, 0, v14, v35, &v47, 0);
        if ( ProtocolInfo == 1 )
        {
          ProtocolInfo = -2147418113;
LABEL_15:
          CoTaskMemFree(v14);
          goto LABEL_16;
        }
      }
      if ( ProtocolInfo )
      {
LABEL_119:
        if ( ProtocolInfo == -2146697199 || ProtocolInfo == -2147467263 )
          ProtocolInfo = 0;
LABEL_14:
        if ( !v14 )
          goto LABEL_16;
        goto LABEL_15;
      }
LABEL_113:
      wcscpy(String1, L"file:");
      *(_OWORD *)v58 = *(_OWORD *)L"file://";
      if ( v47 != 5 || (unsigned int)StrCmpNIIW(String1, v14, 5u) )
      {
        ProtocolInfo = 0;
      }
      else
      {
        v49 = (struct IInternetProtocolInfo *)268;
        pszPath = pszDest;
        v46 = 0;
        ProtocolInfo = StringCchCopyNExW(pszDest, 0x10Cu, v58, 7u, &pszPath, &v56, 0);
        if ( ProtocolInfo >= 0 )
        {
          ProtocolInfo = SHGetFolderPathW(0, 36, 0, 0x4000u, pszPath);
          if ( !ProtocolInfo )
          {
            ProtocolInfo = StringCchLengthW(pszDest, 0x10Cu, (unsigned __int64 *)&v49);
            if ( !ProtocolInfo )
            {
              v43 = (unsigned int)v49;
              if ( (struct IInternetProtocolInfo *)((char *)&v49->lpVtbl + 1) < v49 )
              {
                ProtocolInfo = -2147024362;
                goto LABEL_14;
              }
              ProtocolInfo = LongLongToULong((__int64)&v49->lpVtbl + 1, &v46);
              if ( ProtocolInfo >= 0 )
              {
                if ( v46 <= (unsigned int)v35 )
                {
                  ProtocolInfo = StringCchCopyW(v14, (unsigned int)v35, pszDest);
                }
                else
                {
                  v45 = OLESTRDuplicate(pszDest, v43);
                  if ( !v45 )
                  {
                    ProtocolInfo = -2147024882;
                    goto LABEL_14;
                  }
                  if ( v14 )
                    CoTaskMemFree(v14);
                  v14 = v45;
                  v47 = v43;
                }
              }
            }
          }
        }
        if ( ProtocolInfo )
          goto LABEL_119;
      }
      if ( !StrCmpW(v10, v14) )
        goto LABEL_14;
      if ( (_DWORD)v48 && v10 )
        CoTaskMemFree(v10);
      v10 = v14;
      LODWORD(v48) = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001cb00  mov     r11, rsp
0x18001cb03  push    rbp
0x18001cb04  push    rbx
0x18001cb05  push    rsi
0x18001cb06  push    rdi
0x18001cb07  push    r13
0x18001cb09  lea     rbp, [r11-228h]
0x18001cb10  sub     rsp, 300h
0x18001cb17  mov     rax, cs:__security_cookie
0x18001cb1e  xor     rax, rsp
0x18001cb21  mov     [rbp+220h+var_40], rax
0x18001cb28  mov     [rbp+220h+ppURI], rdx
0x18001cb2c  mov     r13d, r8d
0x18001cb2f  mov     rdi, rdx
0x18001cb32  mov     rbx, rcx
0x18001cb35  test    rcx, rcx
0x18001cb38  jz      loc_18001D290
0x18001cb3e  test    rdx, rdx
0x18001cb41  jz      loc_18001D290
0x18001cb47  lea     eax, [r8-1]
0x18001cb4b  cmp     eax, 1
0x18001cb4e  ja      loc_18001D303
0x18001cb54  mov     [r11+18h], r12
0x18001cb58  xor     r12d, r12d
0x18001cb5b  mov     [rdx], r12
0x18001cb5e  lea     rdx, [rsp+320h+var_2B0]
0x18001cb63  mov     rax, [rcx]
0x18001cb66  mov     [r11-30h], r14
0x18001cb6a  mov     dword ptr [rsp+320h+var_2B0], r12d
0x18001cb6f  mov     rax, [rax+0C0h]
0x18001cb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb7b  test    eax, eax
0x18001cb7d  jz      loc_18001D176
0x18001cb83  lea     rdx, [rsp+320h+var_2A8]
0x18001cb88  mov     [rbp+220h+psz1], r12
0x18001cb8c  mov     rcx, rbx
0x18001cb8f  mov     [rbp+220h+var_2A0], r12d
0x18001cb93  mov     [rsp+320h+var_2A8], r12
0x18001cb98  call    cs:__imp_GetIUriPriv
0x18001cb9f  nop     dword ptr [rax+rax+00h]
0x18001cba4  test    eax, eax
0x18001cba6  js      loc_18001CEA2
0x18001cbac  mov     rcx, [rsp+320h+var_2A8]
0x18001cbb1  lea     r8, [rbp+220h+var_2A0]
0x18001cbb5  lea     rdx, [rbp+220h+psz1]
0x18001cbb9  mov     rax, [rcx]
0x18001cbbc  mov     rax, [rax+0E8h]
0x18001cbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc8  mov     r14, [rbp+220h+psz1]
0x18001cbcc  test    r14, r14
0x18001cbcf  jz      loc_18001D30D
0x18001cbd5  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001cbdc  mov     [rsp+320h+var_30], r15
0x18001cbe4  mov     dword ptr [rsp+320h+var_2C8], r12d
0x18001cbe9  call    cs:__imp_EnterCriticalSection
0x18001cbf0  nop     dword ptr [rax+rax+00h]
0x18001cbf5  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001cbfc  lea     r15, off_18012A010; "h\x00t\x00t\x00p"
0x18001cc03  test    rax, rax
0x18001cc06  jz      loc_18001CF0D
0x18001cc0c  mov     esi, r12d
0x18001cc0f  lock inc dword ptr [rax+10h]
0x18001cc13  mov     r12, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001cc1a  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001cc21  call    cs:__imp_LeaveCriticalSection
0x18001cc28  nop     dword ptr [rax+rax+00h]
0x18001cc2d  test    esi, esi
0x18001cc2f  jz      loc_18001CFA2
0x18001cc35  xor     esi, esi
0x18001cc37  mov     [rsp+320h+var_2D0], esi
0x18001cc3b  jmp     short loc_18001CC99
0x18001cc3d  mov     rbx, r15
0x18001cc40  mov     [rsp+320h+var_2CC], edi
0x18001cc44  test    esi, esi
0x18001cc46  jnz     loc_18001D29A
0x18001cc4c  mov     rdx, rbx; psz2
0x18001cc4f  mov     rcx, r14; psz1
0x18001cc52  call    cs:__imp_StrCmpW
0x18001cc59  nop     dword ptr [rax+rax+00h]
0x18001cc5e  test    eax, eax
0x18001cc60  jnz     loc_18001D1B5
0x18001cc66  test    rbx, rbx
0x18001cc69  jz      short loc_18001CC7A
0x18001cc6b  mov     rcx, rbx; pv
0x18001cc6e  call    cs:__imp_CoTaskMemFree
0x18001cc75  nop     dword ptr [rax+rax+00h]
0x18001cc7a  lea     r15, off_18012A010; "h\x00t\x00t\x00p"
0x18001cc81  mov     edi, dword ptr [rsp+320h+var_2C8]
0x18001cc85  xor     r9d, r9d
0x18001cc88  mov     [rsp+320h+var_2D0], r9d
0x18001cc8d  mov     dword ptr [rsp+320h+var_2C8], edi
0x18001cc91  test    esi, esi
0x18001cc93  js      loc_18001D532
0x18001cc99  xor     ebx, ebx
0x18001cc9b  nop     dword ptr [rax+rax+00h]
0x18001cca0  cmp     ebx, 0Ch
0x18001cca3  jge     short loc_18001CCF4
0x18001cca5  movsxd  rax, ebx
0x18001cca8  lea     rcx, [rax+rax*4]
0x18001ccac  lea     rdi, ds:0[rcx*8]
0x18001ccb4  mov     rcx, r14; pszStr1
0x18001ccb7  mov     r8d, [rdi+r15+20h]; nChar
0x18001ccbc  mov     rdx, [rdi+r15]; pszStr2
0x18001ccc0  call    cs:__imp_StrCmpNICW
0x18001ccc7  nop     dword ptr [rax+rax+00h]
0x18001cccc  test    eax, eax
0x18001ccce  jz      short loc_18001CCD4
0x18001ccd0  inc     ebx
0x18001ccd2  jmp     short loc_18001CCA0
0x18001ccd4  movsxd  rax, dword ptr [rdi+r15+20h]
0x18001ccd9  movzx   ecx, word ptr [r14+rax*2]
0x18001ccde  cmp     cx, 3Ah ; ':'
0x18001cce2  jnz     loc_18001CED0
0x18001cce8  cmp     dword ptr [rdi+r15+10h], 0
0x18001ccee  jnz     loc_18001D52D
0x18001ccf4  cmp     r13d, 1
0x18001ccf8  jnz     loc_18001D52D
0x18001ccfe  test    r14, r14
0x18001cd01  jz      loc_18001D4D7
0x18001cd07  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001cd0e  mov     rdi, rcx
0x18001cd11  inc     rdi
0x18001cd14  cmp     word ptr [r14+rdi*2], 0
0x18001cd1a  jnz     short loc_18001CD11
0x18001cd1c  lea     r15d, [rdi+1]
0x18001cd20  mov     dword ptr [rsp+320h+var_2C0], 0
0x18001cd28  mov     ebx, r15d
0x18001cd2b  mov     eax, 2
0x18001cd30  mul     rbx
0x18001cd33  mov     rsi, rax
0x18001cd36  cmovb   rsi, rcx
0x18001cd3a  mov     rcx, rsi; cb
0x18001cd3d  call    cs:__imp_CoTaskMemAlloc
0x18001cd44  nop     dword ptr [rax+rax+00h]
0x18001cd49  mov     r13, rax
0x18001cd4c  test    rax, rax
0x18001cd4f  jz      loc_18001D261
0x18001cd55  mov     r8, rsi; Size
0x18001cd58  xor     edx, edx; Val
0x18001cd5a  mov     rcx, rax; void *
0x18001cd5d  call    memset_0
0x18001cd62  mov     r9d, 1
0x18001cd68  mov     [rsp+320h+var_2D0], r9d
0x18001cd6d  test    r12, r12
0x18001cd70  jz      short loc_18001CDDE
0x18001cd72  lea     r8, [rsp+320h+var_2B8]; struct IInternetProtocolInfo **
0x18001cd77  mov     [rsp+320h+var_2B8], 0
0x18001cd80  mov     rdx, r14; unsigned __int16 *
0x18001cd83  mov     rcx, r12; this
0x18001cd86  call    ?CreateProtocolInfo@COInetSession@@AEAAJPEBGPEAPEAUIInternetProtocolInfo@@@Z; COInetSession::CreateProtocolInfo(ushort const *,IInternetProtocolInfo * *)
0x18001cd8b  mov     esi, eax
0x18001cd8d  test    eax, eax
0x18001cd8f  jns     loc_18001CF62
0x18001cd95  mov     rcx, [rsp+320h+var_2B8]
0x18001cd9a  test    rcx, rcx
0x18001cd9d  jz      short loc_18001CDAB
0x18001cd9f  mov     rax, [rcx]
0x18001cda2  mov     rax, [rax+10h]
0x18001cda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdab  mov     eax, 800C0011h
0x18001cdb0  test    esi, esi
0x18001cdb2  jns     short loc_18001CDD1
0x18001cdb4  cmp     esi, 800C0505h
0x18001cdba  jz      short loc_18001CDD1
0x18001cdbc  cmp     esi, eax
0x18001cdbe  jz      short loc_18001CDD9
0x18001cdc0  cmp     esi, 80070005h
0x18001cdc6  jz      short loc_18001CDD1
0x18001cdc8  cmp     esi, 800C000Eh
0x18001cdce  cmovnz  esi, eax
0x18001cdd1  cmp     esi, eax
0x18001cdd3  jnz     loc_18001D4E8
0x18001cdd9  mov     r9d, [rsp+320h+var_2D0]
0x18001cdde  test    r15d, r15d
0x18001cde1  jz      loc_18001D513
0x18001cde7  cmp     rbx, 7FFFFFFFh
0x18001cdee  ja      loc_18001D50C
0x18001cdf4  cmp     edi, 7FFFFFFEh
0x18001cdfa  ja      loc_18001D275
0x18001ce00  mov     ecx, edi
0x18001ce02  mov     rdx, r14
0x18001ce05  mov     r8, r13
0x18001ce08  test    rcx, rcx
0x18001ce0b  jz      short loc_18001CE2A
0x18001ce0d  movzx   eax, word ptr [rdx]
0x18001ce10  test    ax, ax
0x18001ce13  jz      short loc_18001CE2A
0x18001ce15  mov     [r8], ax
0x18001ce19  add     rdx, 2
0x18001ce1d  add     r8, 2
0x18001ce21  dec     rcx
0x18001ce24  sub     rbx, 1
0x18001ce28  jnz     short loc_18001CE08
0x18001ce2a  test    rbx, rbx
0x18001ce2d  lea     rcx, [r8-2]
0x18001ce31  mov     esi, 8007007Ah
0x18001ce36  cmovnz  rcx, r8
0x18001ce3a  xor     eax, eax
0x18001ce3c  test    rbx, rbx
0x18001ce3f  cmovnz  esi, eax
0x18001ce42  mov     [rcx], ax
0x18001ce45  mov     r15, [rsp+320h+var_30]
0x18001ce4d  test    esi, esi
0x18001ce4f  jnz     short loc_18001CE73
0x18001ce51  mov     r9, [rbp+220h+ppURI]; ppURI
0x18001ce55  xor     r8d, r8d; dwReserved
0x18001ce58  mov     edx, 3002B86h; dwFlags
0x18001ce5d  mov     rcx, r13; pwzURI
0x18001ce60  call    cs:__imp_CreateUri
0x18001ce67  nop     dword ptr [rax+rax+00h]
0x18001ce6c  mov     r9d, [rsp+320h+var_2D0]
0x18001ce71  mov     esi, eax
0x18001ce73  test    r9d, r9d
0x18001ce76  jnz     short loc_18001CEDE
0x18001ce78  cmp     dword ptr [rsp+320h+var_2C8], 0
0x18001ce7d  jnz     short loc_18001CEF4
0x18001ce7f  mov     rcx, [rsp+320h+var_2A8]
0x18001ce84  test    rcx, rcx
0x18001ce87  jz      short loc_18001CE95
0x18001ce89  mov     rax, [rcx]
0x18001ce8c  mov     rax, [rax+10h]
0x18001ce90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce95  test    r12, r12
0x18001ce98  jz      short loc_18001CEA0
0x18001ce9a  lock dec dword ptr [r12+10h]
0x18001cea0  mov     eax, esi
0x18001cea2  mov     r12, [rsp+320h+arg_10]
0x18001ceaa  mov     r14, [rsp+2F8h]
0x18001ceb2  mov     rcx, [rbp+220h+var_40]
0x18001ceb9  xor     rcx, rsp; StackCookie
0x18001cebc  call    __security_check_cookie
0x18001cec1  add     rsp, 300h
0x18001cec8  pop     r13
0x18001ceca  pop     rdi
0x18001cecb  pop     rsi
0x18001cecc  pop     rbx
0x18001cecd  pop     rbp
0x18001cece  retn
0x18001ced0  test    cx, cx
0x18001ced3  jnz     loc_18001CCD0
0x18001ced9  jmp     loc_18001CCE8
0x18001cede  test    r13, r13
0x18001cee1  jz      short loc_18001CE78
0x18001cee3  mov     rcx, r13; pv
0x18001cee6  call    cs:__imp_CoTaskMemFree
0x18001ceed  nop     dword ptr [rax+rax+00h]
0x18001cef2  jmp     short loc_18001CE78
0x18001cef4  test    r14, r14
0x18001cef7  jz      short loc_18001CE7F
0x18001cef9  mov     rcx, r14; pv
0x18001cefc  call    cs:__imp_CoTaskMemFree
0x18001cf03  nop     dword ptr [rax+rax+00h]
0x18001cf08  jmp     loc_18001CE7F
0x18001cf0d  mov     ecx, 180h; Size
0x18001cf12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cf17  test    rax, rax
0x18001cf1a  jz      loc_18001D165
0x18001cf20  mov     rcx, rax; this
0x18001cf23  call    ??0COInetSession@@QEAA@XZ; COInetSession::COInetSession(void)
0x18001cf28  test    rax, rax
0x18001cf2b  jz      loc_18001D165
0x18001cf31  mov     esi, r12d
0x18001cf34  mov     cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA, rax; COInetSession * g_pCOInetSession
0x18001cf3b  test    rax, rax
0x18001cf3e  jnz     loc_18001CC0F
0x18001cf44  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001cf4b  call    cs:__imp_LeaveCriticalSection
0x18001cf52  nop     dword ptr [rax+rax+00h]
0x18001cf57  xor     esi, esi
0x18001cf59  mov     [rsp+320h+var_2D0], esi
0x18001cf5d  jmp     loc_18001CC99
0x18001cf62  mov     rcx, [rsp+320h+var_2B8]
0x18001cf67  lea     rdx, [rsp+320h+var_2C0]
0x18001cf6c  mov     dword ptr [rsp+38h], 0
0x18001cf74  xor     r9d, r9d
0x18001cf77  mov     [rsp+320h+var_2F0], rdx
0x18001cf7c  mov     r8d, 11h
0x18001cf82  mov     dword ptr [rsp+320h+var_2F8], r15d
0x18001cf87  mov     rdx, r14
0x18001cf8a  mov     rax, [rcx]
0x18001cf8d  mov     [rsp+320h+pszPath], r13
0x18001cf92  mov     rax, [rax+18h]
0x18001cf96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf9b  mov     esi, eax
0x18001cf9d  jmp     loc_18001CD95
0x18001cfa2  xor     ebx, ebx
0x18001cfa4  cmp     ebx, 0Ch
0x18001cfa7  jge     short loc_18001CFF9
0x18001cfa9  movsxd  rax, ebx
0x18001cfac  lea     rcx, [rax+rax*4]
0x18001cfb0  lea     rdi, ds:0[rcx*8]
0x18001cfb8  mov     rcx, r14; pszStr1
0x18001cfbb  mov     r8d, [rdi+r15+20h]; nChar
0x18001cfc0  mov     rdx, [rdi+r15]; pszStr2
0x18001cfc4  call    cs:__imp_StrCmpNICW
0x18001cfcb  nop     dword ptr [rax+rax+00h]
0x18001cfd0  test    eax, eax
0x18001cfd2  jz      short loc_18001CFD8
0x18001cfd4  inc     ebx
0x18001cfd6  jmp     short loc_18001CFA4
  ... truncated ...
```
