# DavInternetSetOption

- ea: `0x180012468`
- end: `0x180012e24`
- name: `DavInternetSetOption`
- size: `2492`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d9e4`
- `0x180013c08`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x180020c1c`
- `0x180021008`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000bc5c`
- `0x180012468`
- `0x1800135b4`
- `0x180014ed0`
- `0x180014f50`
- `0x18002cf56`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001267c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001267c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001256d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012dda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001256d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012dda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012509`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012509`
- `KERNEL32!LocalFree` at `0x180012c10`
- `KERNEL32!LocalFree` at `0x180012c8a`
- `KERNEL32!LocalFree` at `0x180012c10`
- `KERNEL32!LocalFree` at `0x180012c8a`
- `KERNEL32!LocalAlloc` at `0x180012b67`
- `KERNEL32!LocalAlloc` at `0x180012b67`
- `WINHTTP!WinHttpSetCredentials` at `0x1800128c7`
- `WINHTTP!WinHttpSetCredentials` at `0x1800129a7`
- `WINHTTP!WinHttpSetCredentials` at `0x1800129f7`
- `WINHTTP!WinHttpSetCredentials` at `0x180012a42`
- `WINHTTP!WinHttpSetCredentials` at `0x180012c3a`
- `WINHTTP!WinHttpSetCredentials` at `0x180012cb0`
- `WINHTTP!WinHttpSetCredentials` at `0x180012d1f`
- `WINHTTP!WinHttpSetCredentials` at `0x1800128c7`
- `WINHTTP!WinHttpSetCredentials` at `0x1800129a7`
- `WINHTTP!WinHttpSetCredentials` at `0x1800129f7`
- `WINHTTP!WinHttpSetCredentials` at `0x180012a42`
- `WINHTTP!WinHttpSetCredentials` at `0x180012c3a`
- `WINHTTP!WinHttpSetCredentials` at `0x180012cb0`
- `WINHTTP!WinHttpSetCredentials` at `0x180012d1f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180012612`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180012612`
- `WINHTTP!WinHttpSetOption` at `0x18001259a`
- `WINHTTP!WinHttpSetOption` at `0x180012672`
- `WINHTTP!WinHttpSetOption` at `0x18001259a`
- `WINHTTP!WinHttpSetOption` at `0x180012672`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x1800126b4`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x1800126b4`
- `CRYPT32!CryptUnprotectMemory` at `0x180012bc0`
- `CRYPT32!CryptUnprotectMemory` at `0x180012bc0`

## pseudocode

```c
__int64 __fastcall DavInternetSetOption(__int64 a1, int a2, void *a3, int a4, int a5)
{
  const WCHAR *v5; // rbx
  int v6; // r15d
  int v10; // edi
  __int64 v11; // rax
  unsigned int v12; // edi
  DWORD LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rbx
  DWORD v17; // eax
  _WORD *v18; // rax
  __int64 v19; // rdx
  bool v20; // zf
  _WORD *v21; // rdx
  __int64 v22; // r15
  DWORD v23; // ebx
  __int64 v24; // rdx
  BOOL v25; // ebx
  __int64 v26; // r9
  const WCHAR *v27; // r9
  BOOL v28; // ebx
  int v29; // edx
  __int64 v30; // rdx
  __int64 v31; // r13
  const WCHAR *v32; // r9
  SIZE_T v33; // r13
  SIZE_T v34; // r12
  _BYTE *v35; // rax
  _BYTE *pwszPassword; // r15
  DWORD v37; // eax
  _BYTE *v38; // rax
  BOOL v39; // ebx
  _BYTE *v40; // rax
  int v42; // [rsp+30h] [rbp-10h]
  DWORD dwSupportedSchemes; // [rsp+34h] [rbp-Ch] BYREF
  int Buffer; // [rsp+38h] [rbp-8h] BYREF
  DWORD dwFirstScheme; // [rsp+3Ch] [rbp-4h] BYREF
  DWORD pdwAuthTarget; // [rsp+80h] [rbp+40h] BYREF
  HINTERNET hRequest; // [rsp+90h] [rbp+50h]

  hRequest = a3;
  v5 = *(const WCHAR **)(a1 + 7104);
  v6 = a5;
  dwSupportedSchemes = 0;
  dwFirstScheme = 0;
  pdwAuthTarget = 0;
  v10 = 0;
  v42 = 0;
  if ( v5 )
    goto LABEL_20;
  v11 = *(_QWORD *)(a1 + 496);
  if ( !v11 )
  {
LABEL_10:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, 0);
    goto LABEL_13;
  }
  if ( *(_QWORD *)(v11 + 112) )
  {
    if ( a5 != 1 )
    {
LABEL_7:
      if ( *(_DWORD *)(v11 + 172) )
        goto LABEL_9;
    }
  }
  else if ( !a2 )
  {
    goto LABEL_7;
  }
  DavQueryWinInetCookies(a3, **(_QWORD **)(a1 + 504), *(void **)(a1 + 72));
  *(_DWORD *)(*(_QWORD *)(a1 + 496) + 172LL) = 1;
LABEL_9:
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 496) + 120LL));
  v10 = 1;
  v42 = 1;
  v5 = *(const WCHAR **)(*(_QWORD *)(a1 + 496) + 112LL);
  if ( !v5 )
    goto LABEL_10;
LABEL_20:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v5);
  if ( WinHttpAddRequestHeaders(a3, v5, 0xFFFFFFFF, 0xA0000000) )
  {
LABEL_13:
    if ( v10 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 496) + 120LL));
      v42 = 0;
    }
    v12 = 0;
    if ( a4 )
    {
      Buffer = 2;
      if ( WinHttpSetOption(a3, 0x4Du, &Buffer, 4u) )
      {
LABEL_28:
        v14 = WPP_GLOBAL_Control;
        goto LABEL_162;
      }
      LastError = GetLastError();
      v12 = LastError;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 186;
LABEL_27:
        WPP_SF_d(v14[2], v15, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
        goto LABEL_28;
      }
      goto LABEL_162;
    }
    Buffer = 0;
    if ( !WinHttpSetOption(a3, 0x4Du, &Buffer, 4u) )
    {
      LastError = GetLastError();
      v12 = LastError;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 187;
        goto LABEL_27;
      }
      goto LABEL_162;
    }
    if ( WinHttpQueryAuthSchemes(a3, &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget) )
    {
      v23 = 16;
      if ( (dwSupportedSchemes & 0x10) == 0 )
      {
        if ( (dwSupportedSchemes & 2) != 0 )
        {
          v23 = 2;
        }
        else if ( (dwSupportedSchemes & 4) != 0 )
        {
          v23 = 4;
        }
        else if ( (dwSupportedSchemes & 8) != 0 )
        {
          v23 = 8;
        }
        else
        {
          v23 = dwSupportedSchemes & 1;
        }
      }
      v22 = a1 + 504;
      *(_DWORD *)(*(_QWORD *)(a1 + 504) + 68LL) = v23;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 190;
        goto LABEL_64;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v17 = GetLastError();
        WPP_SF_d(v16, 188, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v17);
        v14 = WPP_GLOBAL_Control;
      }
      if ( !v6 && *(_DWORD *)(*(_QWORD *)(a1 + 504) + 68LL) == 2 )
      {
        if ( *(_DWORD *)(a1 + 48) == 4 )
        {
          v18 = (_WORD *)(a1 + 5536);
          if ( a1 == -5536 )
            goto LABEL_47;
          v19 = 513;
          do
          {
            if ( !*v18 )
              break;
            ++v18;
            --v19;
          }
          while ( v19 );
          if ( !v19 )
            goto LABEL_47;
          v20 = ((513 - v19) & -(__int64)(v19 != 0)) == 0;
        }
        else
        {
          v21 = *(_WORD **)(*(_QWORD *)(a1 + 496) + 72LL);
          if ( !v21 )
            goto LABEL_47;
          v20 = *v21 == 0;
        }
        if ( v20 )
        {
LABEL_47:
          v12 = 0;
          goto LABEL_162;
        }
      }
      v22 = a1 + 504;
      pdwAuthTarget = 0;
      v23 = *(_DWORD *)(*(_QWORD *)(a1 + 504) + 68LL);
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
      {
        v24 = 189;
LABEL_64:
        WPP_SF_d(v14[2], v24, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v23);
        v14 = WPP_GLOBAL_Control;
      }
    }
    if ( v23 == 1 )
    {
      if ( *(_DWORD *)&BasicAuthLevel )
      {
        if ( *(_DWORD *)&BasicAuthLevel == 1 && !*(_DWORD *)(*(_QWORD *)v22 + 32LL) )
        {
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
          {
            WPP_SF_(v14[2], 192, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
            v14 = WPP_GLOBAL_Control;
          }
          v23 = 0;
        }
      }
      else
      {
        v23 = 0;
        if ( v14 == &WPP_GLOBAL_Control )
          goto LABEL_79;
        if ( (*((_BYTE *)v14 + 28) & 2) != 0 )
        {
          WPP_SF_(v14[2], 191, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
          v14 = WPP_GLOBAL_Control;
        }
      }
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
    {
      WPP_SF_d(v14[2], 193, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, pdwAuthTarget);
      v14 = WPP_GLOBAL_Control;
    }
LABEL_79:
    if ( pdwAuthTarget == 1 )
    {
      v12 = 0;
      v25 = WinHttpSetCredentials(a3, 1u, v23, 0, 0, 0);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      if ( !v25 )
      {
        LastError = GetLastError();
        v12 = LastError;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 195;
          goto LABEL_27;
        }
      }
      goto LABEL_162;
    }
    if ( !v23 )
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
      {
        WPP_SF_(v14[2], 210, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      v12 = 50;
      goto LABEL_162;
    }
    v26 = *(unsigned int *)(a1 + 48);
    if ( (_DWORD)v26 == 4 )
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
      {
        WPP_SF_(v14[2], 196, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      if ( *(_WORD *)(a1 + 5536) )
      {
        v27 = (const WCHAR *)(a1 + 5536);
        if ( *(_WORD *)(a1 + 6562) )
        {
          v28 = WinHttpSetCredentials(a3, pdwAuthTarget, v23, v27, (LPCWSTR)(a1 + 6562), 0);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v29 = 197;
LABEL_97:
            WPP_SF_qS(v14[2], v29, (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, a1, a1 + 5536);
LABEL_106:
            v14 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          v28 = WinHttpSetCredentials(a3, pdwAuthTarget, v23, v27, &::pwszPassword, 0);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v29 = 198;
            goto LABEL_97;
          }
        }
LABEL_107:
        if ( !v28 )
        {
          LastError = GetLastError();
          v12 = LastError;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 201;
            goto LABEL_27;
          }
        }
        goto LABEL_162;
      }
      if ( v23 != 1 && v23 != 8 )
      {
        v28 = WinHttpSetCredentials(a3, pdwAuthTarget, v23, 0, 0, 0);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, a1);
          goto LABEL_106;
        }
        goto LABEL_107;
      }
      if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 1) == 0 )
      {
LABEL_115:
        v12 = 5;
        goto LABEL_162;
      }
      v30 = 199;
LABEL_114:
      WPP_SF_qd(v14[2], v30, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, a1, v23);
      v14 = WPP_GLOBAL_Control;
      goto LABEL_115;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
    {
      WPP_SF_d(v14[2], 202, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v26);
      v14 = WPP_GLOBAL_Control;
    }
    v31 = *(_QWORD *)(a1 + 496);
    v32 = *(const WCHAR **)(v31 + 72);
    if ( v32 && *v32 )
    {
      v33 = *(unsigned int *)(v31 + 108);
      if ( (_DWORD)v33 )
      {
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
          WPP_SF_d(v14[2], 203, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, (unsigned int)v33);
        v34 = v33;
        v35 = LocalAlloc(0x40u, v33);
        pwszPassword = v35;
        if ( !v35 )
        {
          LastError = GetLastError();
          v12 = LastError;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 204;
            goto LABEL_27;
          }
          goto LABEL_162;
        }
        memcpy_0(v35, *(const void **)(*(_QWORD *)(a1 + 496) + 80LL), v33);
        if ( !CryptUnprotectMemory(pwszPassword, v33, 0) )
        {
          v37 = GetLastError();
          v12 = v37;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v37);
          v38 = pwszPassword;
          do
          {
            *v38++ = 0;
            --v34;
          }
          while ( v34 );
          LocalFree(pwszPassword);
          goto LABEL_28;
        }
        v39 = WinHttpSetCredentials(
                hRequest,
                pdwAuthTarget,
                v23,
                *(LPCWSTR *)(*(_QWORD *)(a1 + 496) + 72LL),
                (LPCWSTR)pwszPassword,
                0);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            206,
            (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
            a1,
            a1 + 5536);
        v40 = pwszPassword;
        do
        {
          *v40++ = 0;
          --v34;
        }
        while ( v34 );
        LocalFree(pwszPassword);
        goto LABEL_150;
      }
      v39 = WinHttpSetCredentials(hRequest, pdwAuthTarget, v23, v32, &::pwszPassword, 0);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          207,
          (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
          a1,
          *(_QWORD *)(*(_QWORD *)(a1 + 496) + 72LL));
LABEL_150:
        v14 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      if ( v23 == 1 || v23 == 8 )
      {
        if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 1) == 0 )
          goto LABEL_115;
        v30 = 208;
        goto LABEL_114;
      }
      v39 = WinHttpSetCredentials(hRequest, pdwAuthTarget, v23, 0, 0, 0);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, a1);
        goto LABEL_150;
      }
    }
    if ( !v39 )
    {
      LastError = GetLastError();
      v12 = LastError;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 211;
        goto LABEL_27;
      }
    }
    goto LABEL_162;
  }
  LastError = GetLastError();
  v12 = LastError;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 183;
    goto LABEL_27;
  }
LABEL_162:
  if ( v42 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 496) + 120LL));
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
    WPP_SF_d(v14[2], 212, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180012468  mov     [rsp-38h+arg_8], rbx
0x18001246d  mov     [rsp-38h+hRequest], r8
0x180012472  push    rbp
0x180012473  push    rsi
0x180012474  push    rdi
0x180012475  push    r12
0x180012477  push    r13
0x180012479  push    r14
0x18001247b  push    r15
0x18001247d  mov     rbp, rsp
0x180012480  sub     rsp, 40h
0x180012484  mov     rbx, [rcx+1BC0h]
0x18001248b  xor     esi, esi
0x18001248d  mov     r15d, [rbp+arg_20]
0x180012491  mov     r12d, r9d
0x180012494  mov     [rbp+dwSupportedSchemes], esi
0x180012497  mov     r13, r8
0x18001249a  mov     [rbp+dwFirstScheme], esi
0x18001249d  mov     r14, rcx
0x1800124a0  mov     [rbp+pdwAuthTarget], esi
0x1800124a3  mov     edi, esi
0x1800124a5  mov     [rbp+var_10], esi
0x1800124a8  test    rbx, rbx
0x1800124ab  jnz     loc_1800125D1
0x1800124b1  mov     rax, [rcx+1F0h]
0x1800124b8  test    rax, rax
0x1800124bb  jz      short loc_18001252B
0x1800124bd  cmp     [rax+70h], rsi
0x1800124c1  jz      short loc_1800124CB
0x1800124c3  cmp     r15d, 1
0x1800124c7  jz      short loc_1800124D7
0x1800124c9  jmp     short loc_1800124CF
0x1800124cb  test    edx, edx
0x1800124cd  jnz     short loc_1800124D7
0x1800124cf  cmp     [rax+0ACh], esi
0x1800124d5  jnz     short loc_1800124FE
0x1800124d7  mov     rdx, [rcx+1F8h]
0x1800124de  mov     r8, [rcx+48h]
0x1800124e2  mov     rcx, r13; hInternet
0x1800124e5  mov     rdx, [rdx]
0x1800124e8  call    DavQueryWinInetCookies
0x1800124ed  mov     rax, [r14+1F0h]
0x1800124f4  mov     dword ptr [rax+0ACh], 1
0x1800124fe  mov     rcx, [r14+1F0h]
0x180012505  add     rcx, 78h ; 'x'; lpCriticalSection
0x180012509  call    cs:__imp_EnterCriticalSection
0x18001250f  mov     rax, [r14+1F0h]
0x180012516  mov     edi, 1
0x18001251b  mov     [rbp+var_10], edi
0x18001251e  mov     rbx, [rax+70h]
0x180012522  test    rbx, rbx
0x180012525  jnz     loc_1800125D1
0x18001252b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012532  lea     rsi, WPP_GLOBAL_Control
0x180012539  cmp     rcx, rsi
0x18001253c  jz      short loc_18001255C
0x18001253e  test    byte ptr [rcx+1Ch], 1
0x180012542  jz      short loc_18001255C
0x180012544  mov     rcx, [rcx+10h]
0x180012548  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001254f  mov     edx, 0B8h
0x180012554  xor     r9d, r9d
0x180012557  call    WPP_SF_d
0x18001255c  xor     eax, eax
0x18001255e  test    edi, edi
0x180012560  jz      short loc_180012578
0x180012562  mov     rcx, [r14+1F0h]
0x180012569  add     rcx, 78h ; 'x'; lpCriticalSection
0x18001256d  call    cs:__imp_LeaveCriticalSection
0x180012573  xor     eax, eax
0x180012575  mov     [rbp+var_10], eax
0x180012578  lea     r8, [rbp+Buffer]; lpBuffer
0x18001257c  mov     edi, eax
0x18001257e  mov     edx, 4Dh ; 'M'; dwOption
0x180012583  mov     rcx, r13; hInternet
0x180012586  test    r12d, r12d
0x180012589  jz      loc_180012666
0x18001258f  lea     r9d, [rdx-49h]; dwBufferLength
0x180012593  mov     [rbp+Buffer], 2
0x18001259a  call    cs:__imp_WinHttpSetOption
0x1800125a0  test    eax, eax
0x1800125a2  jnz     loc_18001265A
0x1800125a8  call    cs:__imp_GetLastError
0x1800125ae  mov     edi, eax
0x1800125b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125b7  cmp     rcx, rsi
0x1800125ba  jz      loc_180012DC9
0x1800125c0  test    byte ptr [rcx+1Ch], 1
0x1800125c4  jz      loc_180012DC9
0x1800125ca  mov     edx, 0BAh
0x1800125cf  jmp     short loc_180012647
0x1800125d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125d8  lea     rsi, WPP_GLOBAL_Control
0x1800125df  cmp     rcx, rsi
0x1800125e2  jz      short loc_180012602
0x1800125e4  test    byte ptr [rcx+1Ch], 2
0x1800125e8  jz      short loc_180012602
0x1800125ea  mov     rcx, [rcx+10h]
0x1800125ee  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800125f5  mov     edx, 0B6h
0x1800125fa  mov     r9, rbx
0x1800125fd  call    WPP_SF_S
0x180012602  mov     r9d, 0A0000000h; dwModifiers
0x180012608  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x18001260c  mov     rdx, rbx; lpszHeaders
0x18001260f  mov     rcx, r13; hRequest
0x180012612  call    cs:__imp_WinHttpAddRequestHeaders
0x180012618  test    eax, eax
0x18001261a  jnz     loc_18001255C
0x180012620  call    cs:__imp_GetLastError
0x180012626  mov     edi, eax
0x180012628  mov     rcx, cs:WPP_GLOBAL_Control
0x18001262f  cmp     rcx, rsi
0x180012632  jz      loc_180012DC9
0x180012638  test    byte ptr [rcx+1Ch], 1
0x18001263c  jz      loc_180012DC9
0x180012642  mov     edx, 0B7h
0x180012647  mov     rcx, [rcx+10h]
0x18001264b  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180012652  mov     r9d, eax
0x180012655  call    WPP_SF_d
0x18001265a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012661  jmp     loc_180012DC9
0x180012666  mov     r12d, 4
0x18001266c  mov     [rbp+Buffer], eax
0x18001266f  mov     r9d, r12d; dwBufferLength
0x180012672  call    cs:__imp_WinHttpSetOption
0x180012678  test    eax, eax
0x18001267a  jnz     short loc_1800126A5
0x18001267c  call    cs:__imp_GetLastError
0x180012682  mov     edi, eax
0x180012684  mov     rcx, cs:WPP_GLOBAL_Control
0x18001268b  cmp     rcx, rsi
0x18001268e  jz      loc_180012DC9
0x180012694  test    byte ptr [rcx+1Ch], 1
0x180012698  jz      loc_180012DC9
0x18001269e  mov     edx, 0BBh
0x1800126a3  jmp     short loc_180012647
0x1800126a5  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x1800126a9  mov     rcx, r13; hRequest
0x1800126ac  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x1800126b0  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x1800126b4  call    cs:__imp_WinHttpQueryAuthSchemes
0x1800126ba  test    eax, eax
0x1800126bc  jnz     loc_180012795
0x1800126c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126c9  cmp     rcx, rsi
0x1800126cc  jz      short loc_1800126FC
0x1800126ce  test    byte ptr [rcx+1Ch], 1
0x1800126d2  jz      short loc_1800126FC
0x1800126d4  mov     rbx, [rcx+10h]
0x1800126d8  call    cs:__imp_GetLastError
0x1800126de  mov     edx, 0BCh
0x1800126e3  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800126ea  mov     r9d, eax
0x1800126ed  mov     rcx, rbx
0x1800126f0  call    WPP_SF_d
0x1800126f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126fc  xor     r10d, r10d
0x1800126ff  test    r15d, r15d
0x180012702  jnz     short loc_180012772
0x180012704  mov     rax, [r14+1F8h]
0x18001270b  cmp     dword ptr [rax+44h], 2
0x18001270f  jnz     short loc_180012772
0x180012711  cmp     [r14+30h], r12d
0x180012715  jnz     short loc_18001275C
0x180012717  lea     rax, [r14+15A0h]
0x18001271e  test    rax, rax
0x180012721  jz      short loc_180012755
0x180012723  mov     r8d, 201h
0x180012729  mov     edx, r8d
0x18001272c  cmp     [rax], r10w
0x180012730  jz      short loc_18001273C
0x180012732  add     rax, 2
0x180012736  sub     rdx, 1
0x18001273a  jnz     short loc_18001272C
0x18001273c  sub     r8, rdx
0x18001273f  mov     rax, rdx
0x180012742  neg     rax
0x180012745  sbb     r9, r9
0x180012748  and     r9, r8
0x18001274b  test    rdx, rdx
0x18001274e  jz      short loc_180012755
0x180012750  test    r9, r9
0x180012753  jnz     short loc_180012772
0x180012755  xor     edi, edi
0x180012757  jmp     loc_180012DC9
0x18001275c  mov     rax, [r14+1F0h]
0x180012763  mov     rdx, [rax+48h]
0x180012767  test    rdx, rdx
0x18001276a  jz      short loc_180012755
0x18001276c  cmp     [rdx], r10w
0x180012770  jmp     short loc_180012753
0x180012772  lea     r15, [r14+1F8h]
0x180012779  mov     [rbp+pdwAuthTarget], r10d
0x18001277d  mov     rax, [r15]
0x180012780  mov     ebx, [rax+44h]
0x180012783  cmp     rcx, rsi
0x180012786  jz      short loc_180012805
0x180012788  test    byte ptr [rcx+1Ch], 1
0x18001278c  jz      short loc_180012805
0x18001278e  mov     edx, 0BDh
0x180012793  jmp     short loc_1800127EB
0x180012795  mov     eax, [rbp+dwSupportedSchemes]
0x180012798  mov     ebx, 10h
0x18001279d  test    bl, al
0x18001279f  jnz     short loc_1800127C7
0x1800127a1  test    al, 2
0x1800127a3  jz      short loc_1800127AC
0x1800127a5  mov     ebx, 2
0x1800127aa  jmp     short loc_1800127C7
0x1800127ac  test    r12b, al
0x1800127af  jz      short loc_1800127B6
0x1800127b1  mov     ebx, r12d
0x1800127b4  jmp     short loc_1800127C7
0x1800127b6  test    al, 8
0x1800127b8  jz      short loc_1800127C1
0x1800127ba  mov     ebx, 8
0x1800127bf  jmp     short loc_1800127C7
0x1800127c1  movzx   ebx, al
0x1800127c4  and     ebx, 1
0x1800127c7  lea     r15, [r14+1F8h]
0x1800127ce  mov     rax, [r15]
0x1800127d1  mov     [rax+44h], ebx
0x1800127d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127db  cmp     rcx, rsi
0x1800127de  jz      short loc_180012805
0x1800127e0  test    byte ptr [rcx+1Ch], 2
0x1800127e4  jz      short loc_180012805
0x1800127e6  mov     edx, 0BEh
0x1800127eb  mov     rcx, [rcx+10h]
0x1800127ef  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800127f6  mov     r9d, ebx
0x1800127f9  call    WPP_SF_d
0x1800127fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012805  cmp     ebx, 1
0x180012808  jnz     short loc_180012878
0x18001280a  mov     eax, cs:BasicAuthLevel
0x180012810  xor     edx, edx
0x180012812  test    eax, eax
0x180012814  jz      short loc_18001284F
0x180012816  cmp     eax, ebx
0x180012818  jnz     short loc_180012878
0x18001281a  mov     rax, [r15]
0x18001281d  cmp     [rax+20h], edx
0x180012820  jnz     short loc_180012878
0x180012822  cmp     rcx, rsi
0x180012825  jz      short loc_18001284B
0x180012827  test    byte ptr [rcx+1Ch], 2
0x18001282b  jz      short loc_18001284B
0x18001282d  mov     rcx, [rcx+10h]
0x180012831  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180012838  mov     edx, 0C0h
0x18001283d  call    WPP_SF_
0x180012842  mov     rcx, cs:WPP_GLOBAL_Control
0x180012849  xor     edx, edx
0x18001284b  mov     ebx, edx
0x18001284d  jmp     short loc_180012878
0x18001284f  mov     ebx, edx
0x180012851  cmp     rcx, rsi
0x180012854  jz      short loc_1800128A3
0x180012856  test    byte ptr [rcx+1Ch], 2
0x18001285a  jz      short loc_180012878
0x18001285c  mov     rcx, [rcx+10h]
0x180012860  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180012867  mov     edx, 0BFh
0x18001286c  call    WPP_SF_
0x180012871  mov     rcx, cs:WPP_GLOBAL_Control
0x180012878  cmp     rcx, rsi
0x18001287b  jz      short loc_1800128A3
0x18001287d  test    byte ptr [rcx+1Ch], 2
0x180012881  jz      short loc_1800128A3
0x180012883  mov     r9d, [rbp+pdwAuthTarget]
0x180012887  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001288e  mov     rcx, [rcx+10h]
0x180012892  mov     edx, 0C1h
0x180012897  call    WPP_SF_d
0x18001289c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128a3  cmp     [rbp+pdwAuthTarget], 1
0x1800128a7  jnz     loc_180012931
0x1800128ad  xor     eax, eax
0x1800128af  xor     r9d, r9d; pwszUserName
0x1800128b2  mov     [rsp+40h+pAuthParams], rax; pAuthParams
0x1800128b7  mov     r8d, ebx; AuthScheme
0x1800128ba  mov     rcx, r13; hRequest
0x1800128bd  mov     [rsp+40h+pwszPassword], rax; pwszPassword
0x1800128c2  mov     edi, eax
0x1800128c4  lea     edx, [rax+1]; AuthTargets
0x1800128c7  call    cs:__imp_WinHttpSetCredentials
0x1800128cd  mov     ebx, eax
0x1800128cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128d6  cmp     rcx, rsi
0x1800128d9  jz      short loc_1800128FD
0x1800128db  test    byte ptr [rcx+1Ch], 2
0x1800128df  jz      short loc_1800128FD
0x1800128e1  mov     rcx, [rcx+10h]
0x1800128e5  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800128ec  mov     edx, 0C2h
0x1800128f1  call    WPP_SF_
0x1800128f6  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
