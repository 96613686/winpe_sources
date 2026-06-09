# FindUrlComponents(int,ushort const *,int,ProxyResolveScheme,tagProxyResolveUrl * *)

- ea: `0x180040650`
- end: `0x180040ee4`
- name: `?FindUrlComponents@@YAJHPEBGHW4ProxyResolveScheme@@PEAPEAUtagProxyResolveUrl@@@Z`
- size: `2196`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f744`
- `0x18004738c`
- `0x180070048`

## callees

- `0x1800403d4`
- `0x180040470`
- `0x180040650`
- `0x180041eb0`
- `0x180041f20`
- `0x180043230`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800ab418`
- `0x1800ab48c`
- `0x1800d650c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b34`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x1800408e5`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180040c5e`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x1800408e5`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180040c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004071e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004071e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800407f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040ab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d4c`

## pseudocode

```c
__int64 __fastcall FindUrlComponents(
        int a1,
        WCHAR *a2,
        unsigned int a3,
        unsigned int a4,
        struct tagProxyResolveUrl **a5)
{
  WCHAR *v5; // rdi
  struct tagProxyResolveUrl *v6; // rbx
  __int64 v7; // r14
  WCHAR *v8; // r15
  bool v9; // zf
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  unsigned __int64 v12; // r8
  WCHAR *v13; // rax
  __int64 v14; // rdx
  WCHAR *v15; // rdx
  int v16; // edi
  _WORD *v17; // rax
  void *v18; // rdi
  _WORD *v19; // rax
  void *v20; // rsi
  CHAR *v21; // rax
  CHAR *v22; // r14
  __int64 v23; // r13
  LPSTR lpszHostName; // rax
  __int64 v25; // rcx
  unsigned int v26; // edx
  int v27; // eax
  int v28; // eax
  int v29; // r12d
  int v30; // eax
  WCHAR *v31; // rax
  __int64 v32; // rcx
  unsigned int v33; // edx
  unsigned int v34; // r12d
  size_t v35; // r9
  WCHAR *i; // rdx
  __int64 v37; // rcx
  _WORD *v38; // rcx
  signed int LastError; // eax
  LPSTR v41; // r11
  const wchar_t *lpszUrlPath; // r13
  size_t *v43; // r8
  HRESULT v44; // eax
  __int64 v45; // r8
  int v46; // ecx
  int v47; // r8d
  struct tagProxyResolveUrl *v48; // rbx
  int v49; // r8d
  const WCHAR *v50; // rdx
  int v51; // eax
  __int16 v52; // cx
  __int64 v53; // rdx
  __int16 v54; // cx
  LPSTR v55; // rdx
  WCHAR *v56; // rcx
  __int64 v57; // r8
  __int64 v58; // rax
  int cchASCIIChar[2]; // [rsp+28h] [rbp-E0h]
  int cchUnicodeChar; // [rsp+48h] [rbp-C0h] BYREF
  int v61; // [rsp+50h] [rbp-B8h] BYREF
  int v62; // [rsp+54h] [rbp-B4h]
  __int64 v63; // [rsp+58h] [rbp-B0h]
  LPCWSTR lpUnicodeCharStr; // [rsp+60h] [rbp-A8h] BYREF
  INTERNET_PORT nPort; // [rsp+68h] [rbp-A0h]
  int v66; // [rsp+6Ch] [rbp-9Ch]
  struct tagProxyResolveUrl *v67; // [rsp+70h] [rbp-98h] BYREF
  int v68; // [rsp+78h] [rbp-90h]
  unsigned __int64 v69; // [rsp+7Ch] [rbp-8Ch]
  struct tagProxyResolveUrl **v70; // [rsp+88h] [rbp-80h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+98h] [rbp-70h] BYREF
  _BYTE cchToCopy[32]; // [rsp+108h] [rbp+0h] BYREF
  WCHAR ASCIICharStr[256]; // [rsp+128h] [rbp+20h] BYREF

  v5 = a2;
  v68 = a1;
  v6 = 0;
  v67 = 0;
  v69 = __PAIR64__(a4, a3);
  v70 = a5;
  v62 = 0;
  memset(&UrlComponents, 0, sizeof(UrlComponents));
  if ( !a5 )
  {
    v62 = 199;
    v29 = -2147024809;
    goto LABEL_68;
  }
  *a5 = 0;
  if ( !a2 )
  {
    v62 = 202;
    v29 = -2147024809;
    goto LABEL_68;
  }
  v7 = -1;
  v8 = 0;
  v62 = 0;
  do
    v9 = a2[++v7] == 0;
  while ( !v9 );
  HIDWORD(lpUnicodeCharStr) = 0;
  v10 = (WCHAR *)CoTaskMemAlloc((unsigned int)(2 * v7 + 2));
  v11 = v10;
  if ( !v10 )
  {
    HIDWORD(lpUnicodeCharStr) = 76;
    v16 = -2147024882;
    v62 = 544;
    goto LABEL_17;
  }
  memset_0(v10, 0, (unsigned int)(2 * v7 + 2));
  v12 = (unsigned int)(v7 + 1);
  v13 = v11;
  if ( (_DWORD)v7 == -1 )
  {
    v16 = -2147024809;
    goto LABEL_15;
  }
  if ( v12 <= 0x7FFFFFFF )
  {
    v14 = 2147483646;
    do
    {
      if ( !v14 )
        break;
      if ( !*v5 )
        break;
      *v11++ = *v5++;
      --v14;
      --v12;
    }
    while ( v12 );
    v15 = v11 - 1;
    v16 = -2147024774;
    if ( v12 )
    {
      v15 = v11;
      v16 = 0;
    }
    *v15 = 0;
LABEL_15:
    if ( v16 >= 0 )
    {
      v8 = v13;
      goto LABEL_17;
    }
    goto LABEL_107;
  }
  *v11 = 0;
  v16 = -2147024809;
LABEL_107:
  v62 = 548;
  if ( v13 )
    CoTaskMemFree(v13);
LABEL_17:
  if ( v16 < 0 )
  {
    v62 = 204;
    v29 = v16;
  }
  else
  {
    HIDWORD(lpUnicodeCharStr) = 0;
    v17 = CoTaskMemAlloc(0x1048u);
    v18 = v17;
    if ( v17 )
    {
      *v17 = 0;
      HIDWORD(lpUnicodeCharStr) = 0;
      v19 = CoTaskMemAlloc(0x2090u);
      v20 = v19;
      if ( !v19 )
      {
        HIDWORD(lpUnicodeCharStr) = 52;
        v29 = -2147024882;
        v62 = 210;
LABEL_65:
        CoTaskMemFree(v18);
        goto LABEL_66;
      }
      *v19 = 0;
      HIDWORD(lpUnicodeCharStr) = 0;
      v21 = (CHAR *)CoTaskMemAlloc(0x1048u);
      v22 = v21;
      if ( !v21 )
      {
        HIDWORD(lpUnicodeCharStr) = 52;
        v29 = -2147024882;
        v62 = 213;
LABEL_63:
        CoTaskMemFree(v20);
LABEL_64:
        if ( !v18 )
          goto LABEL_66;
        goto LABEL_65;
      }
      *(_WORD *)v21 = 0;
      v23 = 2084;
      UrlComponents.dwStructSize = 104;
      UrlComponents.dwHostNameLength = 2084;
      UrlComponents.dwUrlPathLength = 2084;
      UrlComponents.dwExtraInfoLength = 2084;
      UrlComponents.lpszHostName = (LPSTR)v18;
      UrlComponents.lpszUrlPath = (LPSTR)v20;
      UrlComponents.lpszExtraInfo = v21;
      if ( !WinHttpCrackUrl(v8, 0, 0x10000000u, &UrlComponents) )
      {
        UrlComponents.dwHostNameLength = 2084;
        UrlComponents.dwUrlPathLength = 0;
        UrlComponents.dwExtraInfoLength = 0;
        UrlComponents.lpszHostName = (LPSTR)v18;
        UrlComponents.lpszUrlPath = 0;
        UrlComponents.lpszExtraInfo = 0;
        if ( !WinHttpCrackUrl(v8, 0, 0x10000000u, &UrlComponents) )
        {
          LastError = GetLastError();
          v29 = LastError;
          if ( LastError > 0 )
            v29 = (unsigned __int16)LastError | 0x80070000;
          v62 = 246;
          if ( v29 >= 0 )
            v29 = -2147418113;
          goto LABEL_61;
        }
      }
      switch ( UrlComponents.nScheme )
      {
        case INTERNET_SCHEME_GOPHER:
          LODWORD(v63) = 4;
          break;
        case INTERNET_SCHEME_FTP:
          LODWORD(v63) = 3;
          break;
        case INTERNET_SCHEME_PARTIAL:
        case INTERNET_SCHEME_UNKNOWN:
        case INTERNET_SCHEME_DEFAULT:
          LODWORD(v63) = UrlComponents.nScheme;
          break;
        case INTERNET_SCHEME_HTTP:
          LODWORD(v63) = 1;
          break;
        default:
          LODWORD(v63) = -1;
          if ( UrlComponents.nScheme == INTERNET_SCHEME_HTTPS )
            LODWORD(v63) = 8;
          break;
      }
      nPort = UrlComponents.nPort;
      lpszHostName = UrlComponents.lpszHostName;
      v62 = 0;
      lpUnicodeCharStr = (LPCWSTR)UrlComponents.lpszHostName;
      cchUnicodeChar = 0;
      if ( UrlComponents.lpszHostName )
      {
        v25 = 0x7FFFFFFF;
        do
        {
          if ( !*(_WORD *)lpszHostName )
            break;
          lpszHostName += 2;
          --v25;
        }
        while ( v25 );
        v26 = -2147024809;
        if ( v25 )
        {
          v26 = 0;
          v27 = 0x7FFFFFFF - v25;
          goto LABEL_30;
        }
        v62 = 81;
      }
      else
      {
        v26 = -2147024809;
        v62 = 77;
      }
      v27 = 0;
LABEL_30:
      cchUnicodeChar = v27;
      v28 = WX_WIN32_FROM_HR(v26);
      v29 = v28;
      if ( v28 )
      {
        if ( v28 <= 0 )
          goto LABEL_35;
      }
      else
      {
        v30 = IdnToAscii(0, lpUnicodeCharStr, cchUnicodeChar, ASCIICharStr, 255);
        v66 = v30;
        if ( v30 )
        {
          ASCIICharStr[v30] = 0;
          goto LABEL_35;
        }
        if ( GetLastError() == 122 )
        {
          v49 = cchUnicodeChar;
          v50 = lpUnicodeCharStr;
          ASCIICharStr[v66] = 0;
          v51 = IdnToAscii(0, v50, v49, 0, 0);
          v52 = 122;
          if ( !v51 )
            v52 = 12005;
          LOWORD(v29) = v52;
        }
        else
        {
          LOWORD(v29) = 12005;
        }
      }
      v29 = (unsigned __int16)v29 | 0x80070000;
LABEL_35:
      if ( v29 < 0 )
      {
        v62 = 257;
        goto LABEL_54;
      }
      v31 = ASCIICharStr;
      cchUnicodeChar = 0;
      memset(cchToCopy, 0, 28);
      v61 = 0;
      HIDWORD(lpUnicodeCharStr) = 0;
      v32 = 0x7FFFFFFF;
      v66 = 0;
      do
      {
        if ( !*v31 )
          break;
        ++v31;
        --v32;
      }
      while ( v32 );
      v33 = -2147024809;
      if ( v32 )
      {
        v33 = 0;
        v34 = 0x7FFFFFFF - v32;
      }
      else
      {
        HIDWORD(lpUnicodeCharStr) = 81;
        v34 = 0;
      }
      if ( (unsigned int)WX_WIN32_FROM_HR(v33)
        || IsHostLiteralOrLocalHostW(ASCIICharStr, v34, &cchUnicodeChar, &v61, (struct sockaddr_in6 *)cchToCopy) )
      {
LABEL_49:
        v29 = -2147012891;
        v62 = 261;
        goto LABEL_54;
      }
      if ( !cchUnicodeChar )
        goto LABEL_44;
      if ( *(_WORD *)cchToCopy != 2 )
      {
        if ( ASCIICharStr[0] != 91 )
          goto LABEL_44;
        v58 = -1;
        do
          v9 = ASCIICharStr[++v58] == 0;
        while ( !v9 );
        if ( *(_WORD *)&cchToCopy[2 * v58 + 30] != 93 )
        {
LABEL_44:
          for ( i = ASCIICharStr; ; ++i )
          {
            v37 = *i;
            if ( !(_WORD)v37 )
              break;
            if ( (unsigned __int16)(v37 - 33) > 0x5Du || (*((_BYTE *)&qword_1800E6EF0[-4] + v37 - 1) & 0x88) != 0 )
              goto LABEL_49;
          }
        }
      }
      v55 = UrlComponents.lpszHostName;
      v56 = ASCIICharStr;
      v57 = 2147483646;
      do
      {
        if ( !v57 )
          break;
        if ( !*v56 )
          break;
        *(_WORD *)v55 = *v56++;
        v55 += 2;
        --v57;
        --v23;
      }
      while ( v23 );
      v38 = v55 - 2;
      v29 = -2147024774;
      if ( v23 )
      {
        v38 = v55;
        v29 = 0;
      }
      *v38 = 0;
      if ( !v23 )
      {
        v62 = 266;
        goto LABEL_54;
      }
      v41 = UrlComponents.lpszHostName;
      if ( v68 )
      {
        v53 = 0;
        if ( *(_WORD *)UrlComponents.lpszHostName )
        {
          do
          {
            v54 = *(_WORD *)&v41[2 * v53];
            if ( (unsigned __int16)(v54 - 65) <= 0x19u )
              v54 += 32;
            *(_WORD *)&v41[2 * v53] = v54;
            v53 = (unsigned int)(v53 + 1);
            v41 = UrlComponents.lpszHostName;
          }
          while ( *(_WORD *)&UrlComponents.lpszHostName[2 * v53] );
        }
      }
      lpszUrlPath = (const wchar_t *)UrlComponents.lpszUrlPath;
      if ( UrlComponents.lpszUrlPath )
      {
        if ( !*(_WORD *)UrlComponents.lpszUrlPath )
        {
          *(_WORD *)UrlComponents.lpszUrlPath = 47;
          *((_WORD *)UrlComponents.lpszUrlPath + 1) = 0;
          lpszUrlPath = (const wchar_t *)UrlComponents.lpszUrlPath;
        }
        lpUnicodeCharStr = 0;
        v29 = StringValidateDestAndLengthW(lpszUrlPath, 0x1048u, (size_t *)&lpUnicodeCharStr, v35);
        if ( v29 >= 0 )
        {
          v44 = StringCopyWorkerW(
                  (STRSAFE_LPWSTR)&lpszUrlPath[(_QWORD)lpUnicodeCharStr],
                  4168LL - (_QWORD)lpUnicodeCharStr,
                  v43,
                  (STRSAFE_PCNZWCH)UrlComponents.lpszExtraInfo,
                  *(size_t *)cchASCIIChar);
          lpszUrlPath = (const wchar_t *)UrlComponents.lpszUrlPath;
          v29 = v44;
          v41 = UrlComponents.lpszHostName;
        }
        if ( v29 < 0 )
        {
          v62 = 290;
          goto LABEL_54;
        }
        v45 = (unsigned int)v63;
        if ( v69 != __PAIR64__(v63, 0) )
          goto LABEL_85;
      }
      else
      {
        v45 = (unsigned int)v63;
      }
      lpszUrlPath = L"/";
LABEL_85:
      v29 = CreateUrl(v41, lpszUrlPath, v45, nPort, &v67);
      if ( v29 < 0 )
      {
        v6 = v67;
        v62 = 307;
      }
      else
      {
        v48 = v67;
        if ( (xmmword_180107A60 & 0x20) != 0 )
          WPP_SF_SSSdd(
            v46,
            11,
            v47,
            *(_QWORD *)v67,
            *((_QWORD *)v67 + 1),
            *((_QWORD *)v67 + 2),
            *((_DWORD *)v67 + 6),
            *((_WORD *)v67 + 14));
        *v70 = v48;
        v6 = 0;
        v67 = 0;
      }
LABEL_54:
      if ( !v22 )
      {
LABEL_62:
        if ( !v20 )
          goto LABEL_64;
        goto LABEL_63;
      }
LABEL_61:
      CoTaskMemFree(v22);
      goto LABEL_62;
    }
    HIDWORD(lpUnicodeCharStr) = 52;
    v29 = -2147024882;
    v62 = 207;
  }
LABEL_66:
  if ( v8 )
    CoTaskMemFree(v8);
LABEL_68:
  if ( v6 )
    FreeProxyResolveUrl(&v67);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180040650  mov     r11, rsp
0x180040653  push    rbp
0x180040654  push    r12
0x180040656  lea     rbp, [r11-258h]
0x18004065d  sub     rsp, 348h
0x180040664  mov     rax, cs:__security_cookie
0x18004066b  xor     rax, rsp
0x18004066e  mov     [rbp+250h+var_30], rax
0x180040675  mov     rax, [rbp+250h+arg_20]
0x18004067c  xorps   xmm0, xmm0
0x18004067f  mov     [r11+8], rbx
0x180040683  mov     [r11+20h], rdi
0x180040687  mov     rdi, rdx
0x18004068a  mov     [r11-18h], r13
0x18004068e  xor     r13d, r13d
0x180040691  mov     [rsp+350h+var_2E0], ecx
0x180040695  mov     ebx, r13d
0x180040698  xor     ecx, ecx
0x18004069a  mov     [rsp+350h+var_2E8], rbx
0x18004069f  mov     [rsp+350h+var_2D8], r9d
0x1800406a4  mov     [rsp+350h+var_2DC], r8d
0x1800406a9  mov     [rbp+250h+var_2D0], rax
0x1800406ad  mov     [rsp+350h+var_304], r13d
0x1800406b2  mov     qword ptr [rbp+250h+UrlComponents.dwExtraInfoLength], rcx
0x1800406b6  movups  xmmword ptr [rbp+250h+UrlComponents.dwStructSize], xmm0
0x1800406ba  movups  xmmword ptr [rbp+250h+UrlComponents.dwSchemeLength], xmm0
0x1800406be  movups  xmmword ptr [rbp+250h+UrlComponents.dwHostNameLength], xmm0
0x1800406c2  movups  xmmword ptr [rbp+250h+UrlComponents.dwUserNameLength], xmm0
0x1800406c6  movups  xmmword ptr [rbp+250h+UrlComponents.dwPasswordLength], xmm0
0x1800406ca  movups  xmmword ptr [rbp+250h+UrlComponents.dwUrlPathLength], xmm0
0x1800406ce  test    rax, rax
0x1800406d1  jz      loc_180040D57
0x1800406d7  mov     [rax], r13
0x1800406da  test    rdx, rdx
0x1800406dd  jz      loc_180040D6A
0x1800406e3  mov     [r11+18h], rsi
0x1800406e7  mov     [r11-20h], r14
0x1800406eb  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800406f2  mov     [r11-28h], r15
0x1800406f6  mov     r15d, r13d
0x1800406f9  mov     [rsp+350h+var_304], r13d
0x1800406fe  xchg    ax, ax
0x180040700  cmp     [rdx+r14*2+2], cx
0x180040706  lea     r14, [r14+1]
0x18004070a  jnz     short loc_180040700
0x18004070c  lea     eax, ds:2[r14*2]
0x180040714  mov     dword ptr [rsp+350h+lpUnicodeCharStr+4], r13d
0x180040719  mov     ecx, eax; cb
0x18004071b  mov     r12d, eax
0x18004071e  call    cs:__imp_CoTaskMemAlloc
0x180040724  mov     rsi, rax
0x180040727  test    rax, rax
0x18004072a  jz      loc_180040B1A
0x180040730  mov     r8d, r12d; Size
0x180040733  xor     edx, edx; Val
0x180040735  mov     rcx, rax; void *
0x180040738  call    memset_0
0x18004073d  lea     eax, [r14+1]
0x180040741  mov     r8d, eax
0x180040744  test    eax, eax
0x180040746  mov     rax, rsi
0x180040749  jz      loc_180040D88
0x18004074f  cmp     r8, 7FFFFFFFh
0x180040756  ja      loc_180040D7D
0x18004075c  mov     edx, 7FFFFFFEh
0x180040761  test    rdx, rdx
0x180040764  jz      short loc_180040782
0x180040766  movzx   ecx, word ptr [rdi]
0x180040769  test    cx, cx
0x18004076c  jz      short loc_180040782
0x18004076e  mov     [rsi], cx
0x180040771  add     rdi, 2
0x180040775  add     rsi, 2
0x180040779  dec     rdx
0x18004077c  sub     r8, 1
0x180040780  jnz     short loc_180040761
0x180040782  test    r8, r8
0x180040785  lea     rdx, [rsi-2]
0x180040789  mov     edi, 8007007Ah
0x18004078e  cmovnz  rdx, rsi
0x180040792  cmovnz  edi, r13d
0x180040796  mov     [rdx], r13w
0x18004079a  test    edi, edi
0x18004079c  js      loc_180040D38
0x1800407a2  mov     r15, rax
0x1800407a5  test    edi, edi
0x1800407a7  js      loc_180040D92
0x1800407ad  mov     r14d, 1048h
0x1800407b3  mov     dword ptr [rsp+350h+lpUnicodeCharStr+4], r13d
0x1800407b8  mov     ecx, r14d; cb
0x1800407bb  call    cs:__imp_CoTaskMemAlloc
0x1800407c1  mov     rdi, rax
0x1800407c4  test    rax, rax
0x1800407c7  jz      loc_180040DA2
0x1800407cd  mov     [rax], r13w
0x1800407d1  mov     ecx, 2090h; cb
0x1800407d6  mov     dword ptr [rsp+350h+lpUnicodeCharStr+4], r13d
0x1800407db  call    cs:__imp_CoTaskMemAlloc
0x1800407e1  mov     rsi, rax
0x1800407e4  test    rax, rax
0x1800407e7  jz      loc_180040DBD
0x1800407ed  mov     [rax], r13w
0x1800407f1  mov     ecx, r14d; cb
0x1800407f4  mov     dword ptr [rsp+350h+lpUnicodeCharStr+4], r13d
0x1800407f9  call    cs:__imp_CoTaskMemAlloc
0x1800407ff  mov     r14, rax
0x180040802  test    rax, rax
0x180040805  jz      loc_180040DD8
0x18004080b  mov     [rax], r13w
0x18004080f  lea     r9, [rbp+250h+UrlComponents]; lpUrlComponents
0x180040813  mov     r13d, 824h
0x180040819  mov     [rbp+250h+UrlComponents.dwStructSize], 68h ; 'h'
0x180040820  xor     edx, edx; dwUrlLength
0x180040822  mov     [rbp+250h+UrlComponents.dwHostNameLength], r13d
0x180040826  mov     r8d, 10000000h; dwFlags
0x18004082c  mov     [rbp+250h+UrlComponents.dwUrlPathLength], r13d
0x180040830  mov     rcx, r15; pwszUrl
0x180040833  mov     [rbp+250h+UrlComponents.dwExtraInfoLength], r13d
0x180040837  mov     [rbp+250h+UrlComponents.lpszHostName], rdi
0x18004083b  mov     [rbp+250h+UrlComponents.lpszUrlPath], rsi
0x18004083f  mov     [rbp+250h+UrlComponents.lpszExtraInfo], rax
0x180040843  call    WinHttpCrackUrl
0x180040848  xor     r12d, r12d
0x18004084b  test    eax, eax
0x18004084d  jz      loc_180040A15
0x180040853  mov     eax, [rbp+250h+UrlComponents.nScheme]
0x180040856  cmp     eax, 2
0x180040859  jnz     loc_180040B04
0x18004085f  mov     dword ptr [rsp+350h+var_300], 4
0x180040867  movzx   eax, [rbp+250h+UrlComponents.nPort]
0x18004086b  mov     word ptr [rsp+350h+var_2F0], ax
0x180040870  mov     rax, [rbp+250h+UrlComponents.lpszHostName]
0x180040874  mov     [rsp+350h+var_304], r12d
0x180040879  mov     [rsp+350h+lpUnicodeCharStr], rax
0x18004087e  mov     [rsp+350h+cchUnicodeChar], r12d
0x180040883  test    rax, rax
0x180040886  jz      loc_180040E3A
0x18004088c  mov     r8d, 7FFFFFFFh
0x180040892  mov     ecx, r8d
0x180040895  cmp     [rax], bx
0x180040898  jz      short loc_1800408A4
0x18004089a  add     rax, 2
0x18004089e  sub     rcx, 1
0x1800408a2  jnz     short loc_180040895
0x1800408a4  test    rcx, rcx
0x1800408a7  mov     edx, 80070057h
0x1800408ac  cmovnz  edx, r12d
0x1800408b0  jz      loc_180040D18
0x1800408b6  mov     eax, r8d
0x1800408b9  sub     eax, ecx
0x1800408bb  mov     [rsp+350h+cchUnicodeChar], eax
0x1800408bf  mov     ecx, edx
0x1800408c1  call    WX_WIN32_FROM_HR
0x1800408c6  mov     r12d, eax
0x1800408c9  test    eax, eax
0x1800408cb  jnz     short loc_180040902
0x1800408cd  mov     r8d, [rsp+350h+cchUnicodeChar]; cchUnicodeChar
0x1800408d2  lea     r9, [rbp+250h+ASCIICharStr]; lpASCIICharStr
0x1800408d6  mov     rdx, [rsp+350h+lpUnicodeCharStr]; lpUnicodeCharStr
0x1800408db  xor     ecx, ecx; dwFlags
0x1800408dd  mov     [rsp+350h+cchASCIIChar], 0FFh; cchASCIIChar
0x1800408e5  call    cs:__imp_IdnToAscii
0x1800408eb  mov     dword ptr [rsp+350h+var_2F0+4], eax
0x1800408ef  test    eax, eax
0x1800408f1  jz      loc_180040B34
0x1800408f7  mov     ecx, eax
0x1800408f9  xor     eax, eax
0x1800408fb  mov     [rbp+rcx*2+250h+ASCIICharStr], ax
0x180040900  jmp     short loc_18004090F
0x180040902  jle     short loc_18004090F
0x180040904  movzx   r12d, r12w
0x180040908  or      r12d, 80070000h
0x18004090f  test    r12d, r12d
0x180040912  js      loc_180040E4C
0x180040918  xor     edx, edx
0x18004091a  lea     rax, [rbp+250h+ASCIICharStr]
0x18004091e  xorps   xmm0, xmm0
0x180040921  mov     [rsp+350h+cchUnicodeChar], edx
0x180040925  movups  xmmword ptr [rbp+250h+cchToCopy], xmm0
0x180040929  mov     r12d, 7FFFFFFFh
0x18004092f  mov     [rsp+350h+var_308], edx
0x180040933  movups  xmmword ptr [rbp+250h+cchToCopy+0Ch], xmm0
0x180040937  mov     dword ptr [rsp+350h+lpUnicodeCharStr+4], edx
0x18004093b  mov     ecx, r12d
0x18004093e  mov     dword ptr [rsp+350h+var_2F0+4], edx
0x180040942  cmp     [rax], dx
0x180040945  jz      short loc_180040951
0x180040947  add     rax, 2
0x18004094b  sub     rcx, 1
0x18004094f  jnz     short loc_180040942
0x180040951  mov     eax, edx
0x180040953  test    rcx, rcx
0x180040956  mov     edx, 80070057h
0x18004095b  cmovnz  edx, eax
0x18004095e  jz      loc_180040D28
0x180040964  sub     r12d, ecx
0x180040967  mov     ecx, edx
0x180040969  call    WX_WIN32_FROM_HR
0x18004096e  test    eax, eax
0x180040970  jnz     short loc_1800409D3
0x180040972  lea     rax, [rbp+250h+cchToCopy]
0x180040976  mov     edx, r12d; unsigned int
0x180040979  lea     r9, [rsp+350h+var_308]; int *
0x18004097e  mov     qword ptr [rsp+350h+cchASCIIChar], rax; struct sockaddr_in6 *
0x180040983  lea     r8, [rsp+350h+cchUnicodeChar]; int *
0x180040988  lea     rcx, [rbp+250h+ASCIICharStr]; AddressString
0x18004098c  call    ?IsHostLiteralOrLocalHostW@@YAKPEBGKPEAH1PEAUsockaddr_in6@@@Z; IsHostLiteralOrLocalHostW(ushort const *,ulong,int *,int *,sockaddr_in6 *)
0x180040991  test    eax, eax
0x180040993  jnz     short loc_1800409D3
0x180040995  cmp     [rsp+350h+cchUnicodeChar], ebx
0x180040999  jnz     loc_180040E59
0x18004099f  lea     rdx, [rbp+250h+ASCIICharStr]
0x1800409a3  lea     r8, qword_1800E6EF0
0x1800409aa  nop     word ptr [rax+rax+00h]
0x1800409b0  movzx   ecx, word ptr [rdx]
0x1800409b3  test    cx, cx
0x1800409b6  jz      loc_180040CCC
0x1800409bc  lea     eax, [rcx-21h]
0x1800409bf  cmp     ax, 5Dh ; ']'
0x1800409c3  ja      short loc_1800409D3
0x1800409c5  test    byte ptr [rcx+r8-21h], 88h
0x1800409cb  jnz     short loc_1800409D3
0x1800409cd  add     rdx, 2
0x1800409d1  jmp     short loc_1800409B0
0x1800409d3  mov     r12d, 80072EE5h
0x1800409d9  mov     [rsp+350h+var_304], 105h
0x1800409e1  jmp     short loc_180040A0E
0x1800409e3  test    r13, r13
0x1800409e6  lea     rcx, [rdx-2]
0x1800409ea  mov     r12d, 8007007Ah
0x1800409f0  cmovnz  rcx, rdx
0x1800409f4  xor     eax, eax
0x1800409f6  test    r13, r13
0x1800409f9  cmovnz  r12d, eax
0x1800409fd  mov     [rcx], ax
0x180040a00  jnz     loc_180040B4E
0x180040a06  mov     [rsp+350h+var_304], 10Ah
0x180040a0e  test    r14, r14
0x180040a11  jnz     short loc_180040A75
0x180040a13  jmp     short loc_180040A7E
0x180040a15  lea     r9, [rbp+250h+UrlComponents]; lpUrlComponents
0x180040a19  mov     [rbp+250h+UrlComponents.dwHostNameLength], r13d
0x180040a1d  xor     edx, edx; dwUrlLength
0x180040a1f  mov     [rbp+250h+UrlComponents.dwUrlPathLength], r12d
0x180040a23  mov     r8d, 10000000h; dwFlags
0x180040a29  mov     [rbp+250h+UrlComponents.dwExtraInfoLength], r12d
0x180040a2d  mov     rcx, r15; pwszUrl
0x180040a30  mov     [rbp+250h+UrlComponents.lpszHostName], rdi
0x180040a34  mov     [rbp+250h+UrlComponents.lpszUrlPath], r12
0x180040a38  mov     [rbp+250h+UrlComponents.lpszExtraInfo], r12
0x180040a3c  call    WinHttpCrackUrl
0x180040a41  test    eax, eax
0x180040a43  jnz     loc_180040853
0x180040a49  call    cs:__imp_GetLastError
0x180040a4f  mov     r12d, eax
0x180040a52  test    eax, eax
0x180040a54  jle     short loc_180040A61
0x180040a56  movzx   r12d, ax
0x180040a5a  or      r12d, 80070000h
0x180040a61  test    r12d, r12d
0x180040a64  mov     [rsp+350h+var_304], 0F6h
0x180040a6c  mov     eax, 8000FFFFh
0x180040a71  cmovns  r12d, eax
0x180040a75  mov     rcx, r14; pv
0x180040a78  call    cs:__imp_CoTaskMemFree
0x180040a7e  test    rsi, rsi
0x180040a81  jz      short loc_180040A8C
0x180040a83  mov     rcx, rsi; pv
0x180040a86  call    cs:__imp_CoTaskMemFree
0x180040a8c  test    rdi, rdi
0x180040a8f  jz      short loc_180040A9A
0x180040a91  mov     rcx, rdi; pv
0x180040a94  call    cs:__imp_CoTaskMemFree
0x180040a9a  mov     r14, [rsp+350h+var_18]
0x180040aa2  mov     rsi, [rsp+350h+arg_10]
0x180040aaa  test    r15, r15
0x180040aad  jz      short loc_180040AB8
0x180040aaf  mov     rcx, r15; pv
0x180040ab2  call    cs:__imp_CoTaskMemFree
0x180040ab8  mov     r15, [rsp+350h+var_20]
0x180040ac0  mov     r13, [rsp+340h]
0x180040ac8  test    rbx, rbx
0x180040acb  mov     rbx, [rsp+350h+arg_0]
0x180040ad3  mov     rdi, [rsp+350h+arg_18]
0x180040adb  jz      short loc_180040AE7
0x180040add  lea     rcx, [rsp+350h+var_2E8]; struct tagProxyResolveUrl **
0x180040ae2  call    ?FreeProxyResolveUrl@@YAXPEAPEAUtagProxyResolveUrl@@@Z; FreeProxyResolveUrl(tagProxyResolveUrl * *)
0x180040ae7  mov     eax, r12d
0x180040aea  mov     rcx, [rbp+250h+var_30]
0x180040af1  xor     rcx, rsp; StackCookie
0x180040af4  call    __security_check_cookie
0x180040af9  add     rsp, 348h
0x180040b00  pop     r12
0x180040b02  pop     rbp
0x180040b03  retn
0x180040b04  cmp     eax, 1
0x180040b07  jnz     loc_180040DF3
0x180040b0d  mov     dword ptr [rsp+350h+var_300], 3
0x180040b15  jmp     loc_180040867
0x180040b1a  mov     dword ptr [rsp+350h+lpUnicodeCharStr+4], 4Ch ; 'L'
  ... truncated ...
```
