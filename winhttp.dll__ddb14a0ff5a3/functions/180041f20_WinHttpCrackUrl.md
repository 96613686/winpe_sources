# WinHttpCrackUrl

- ea: `0x180041f20`
- end: `0x1800427e6`
- name: `WinHttpCrackUrl`
- size: `2246`
- prototype: `BOOL __stdcall(LPCWSTR pwszUrl, DWORD dwUrlLength, DWORD dwFlags, LPURL_COMPONENTS lpUrlComponents)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180040650`

## callees

- `0x180033404`
- `0x180041eb0`
- `0x180041f20`
- `0x1800427ec`
- `0x180042b20`
- `0x180042b90`
- `0x1800a1d10`
- `0x1800cfab8`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042022`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042022`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004228d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004228d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004201a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004201a`
- `ntdll!EtwEventActivityIdControl` at `0x180041fe3`
- `ntdll!EtwEventActivityIdControl` at `0x18004205c`
- `ntdll!EtwEventActivityIdControl` at `0x180042271`
- `ntdll!EtwEventActivityIdControl` at `0x180041fe3`
- `ntdll!EtwEventActivityIdControl` at `0x18004205c`
- `ntdll!EtwEventActivityIdControl` at `0x180042271`

## pseudocode

```c
BOOL __stdcall WinHttpCrackUrl(LPCWSTR pwszUrl, DWORD dwUrlLength, DWORD dwFlags, LPURL_COMPONENTS lpUrlComponents)
{
  __int64 v4; // rdi
  __int64 v8; // rcx
  __int128 *v9; // rax
  __int64 v10; // rdx
  __int128 *v11; // rax
  __int64 v12; // rdx
  __int128 *v13; // rax
  int v14; // eax
  bool v15; // sf
  signed __int32 v16; // esi
  DWORD TickCount; // ebx
  unsigned __int64 v18; // rcx
  const struct _GUID *v19; // r9
  int v20; // eax
  bool v21; // sf
  DWORD dwSchemeLength; // eax
  DWORD dwHostNameLength; // eax
  DWORD dwUserNameLength; // eax
  DWORD dwPasswordLength; // eax
  DWORD dwUrlPathLength; // eax
  DWORD dwExtraInfoLength; // ecx
  unsigned int *v28; // rdx
  char *v29; // r15
  unsigned __int64 v30; // rsi
  LPCWSTR v31; // rbx
  int i; // ecx
  wchar_t v33; // ax
  __int64 v34; // rdi
  unsigned __int64 v35; // rcx
  DWORD UrlAddressW; // ebx
  unsigned int v37; // edi
  int v38; // eax
  bool v39; // sf
  __int64 v41; // rcx
  LPCWSTR v42; // rax
  unsigned int v43; // edx
  const unsigned __int16 *v44; // r14
  unsigned __int16 *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rdx
  unsigned int v48; // r15d
  BOOL v49; // esi
  DWORD v50; // edi
  BOOL v51; // esi
  DWORD v52; // r12d
  int v53; // ecx
  int v54; // ecx
  __int64 v55; // rcx
  unsigned __int16 **v56; // [rsp+20h] [rbp-E0h]
  unsigned int v57[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v58; // [rsp+68h] [rbp-98h] BYREF
  int v59; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v60[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *Src[2]; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v62[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v63[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v64[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v65[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v66; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v67[4]; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v68; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v69; // [rsp+100h] [rbp+0h] BYREF
  int v70; // [rsp+110h] [rbp+10h]
  __int128 v71; // [rsp+120h] [rbp+20h] BYREF
  __int128 v72; // [rsp+130h] [rbp+30h] BYREF
  _UNKNOWN *retaddr; // [rsp+198h] [rbp+98h]

  LODWORD(v4) = dwUrlLength;
  *(_QWORD *)v57 = dwUrlLength;
  v69 = 0;
  v70 = 0;
  if ( WinHttpEtwInitialized )
  {
    v8 = 16;
    v9 = &v69;
    v10 = 16;
    do
    {
      *(_BYTE *)v9 = 0;
      v9 = (__int128 *)((char *)v9 + 1);
      --v10;
    }
    while ( v10 );
    v70 = 0;
    v11 = &v69;
    v68 = 0;
    v12 = 16;
    v71 = 0;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (__int128 *)((char *)v11 + 1);
      --v12;
    }
    while ( v12 );
    v59 = 0;
    v72 = 0;
    v13 = &v71;
    do
    {
      *(_BYTE *)v13 = 0;
      v13 = (__int128 *)((char *)v13 + 1);
      --v8;
    }
    while ( v8 );
    v14 = EtwEventActivityIdControl(1, &v72);
    v15 = v14 < 0;
    if ( v14 > 0 )
      v15 = 1;
    if ( v15 )
      v59 = 128;
    else
      v71 = v72;
    v16 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    TickCount = GetTickCount();
    *(_DWORD *)&v68.Data4[4] = GetCurrentProcessId();
    v68.Data1 = (unsigned int)retaddr;
    *(_DWORD *)&v68.Data2 = v16;
    *(_DWORD *)v68.Data4 = TickCount;
    if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfo(v18, &ActivityStart, &v68, v19, (unsigned int)v56);
    v59 = 0;
    v20 = EtwEventActivityIdControl(2, &v68);
    v21 = v20 < 0;
    if ( v20 > 0 )
      v21 = 1;
    if ( v21 )
      v59 = 144;
    LODWORD(v4) = v57[0];
    v69 = v71;
    v70 = 1;
  }
  if ( (xmmword_180107A60 & 4) != 0 )
  {
    LODWORD(v55) = v4;
    if ( !(_DWORD)v4 )
      LODWORD(v55) = -1;
    *(_QWORD *)v68.Data4 = 0;
    *(_QWORD *)&v68.Data1 = pwszUrl;
    if ( !pwszUrl )
      goto LABEL_137;
    if ( (_DWORD)v55 == -1 )
    {
      v55 = -1;
      do
        ++v55;
      while ( pwszUrl[v55] );
    }
    if ( (_DWORD)v55 )
    {
      dwUrlLength = 65534;
      if ( 2 * (unsigned __int64)(unsigned int)v55 <= 0xFFFE )
      {
        LOWORD(v55) = 2 * v55;
        *(_WORD *)v68.Data4 = v55;
      }
      else
      {
        *(_WORD *)v68.Data4 = -2;
      }
    }
    else
    {
LABEL_137:
      *(_WORD *)v68.Data4 = 1;
      *(_QWORD *)&v68.Data1 = &qword_1800E7F50;
    }
    WPP_SF__COUNTEDSTRINGW_DDq(v55, dwUrlLength, dwFlags, (unsigned int)&v68, v4, dwFlags, (__int64)lpUrlComponents);
  }
  if ( !pwszUrl || !lpUrlComponents || lpUrlComponents->dwStructSize != 104 || (dwFlags & 0x6FFFBFFF) != 0 )
    goto LABEL_103;
  dwSchemeLength = lpUrlComponents->dwSchemeLength;
  if ( lpUrlComponents->lpszScheme )
  {
    if ( !dwSchemeLength )
      goto LABEL_103;
  }
  else if ( dwSchemeLength && (dwFlags & 0x90000000) != 0 )
  {
    goto LABEL_103;
  }
  dwHostNameLength = lpUrlComponents->dwHostNameLength;
  if ( lpUrlComponents->lpszHostName )
  {
    if ( !dwHostNameLength )
      goto LABEL_103;
  }
  else if ( dwHostNameLength && (dwFlags & 0x90000000) != 0 )
  {
    goto LABEL_103;
  }
  dwUserNameLength = lpUrlComponents->dwUserNameLength;
  if ( lpUrlComponents->lpszUserName )
  {
    if ( !dwUserNameLength )
      goto LABEL_103;
  }
  else if ( dwUserNameLength && (dwFlags & 0x90000000) != 0 )
  {
    goto LABEL_103;
  }
  dwPasswordLength = lpUrlComponents->dwPasswordLength;
  if ( lpUrlComponents->lpszPassword )
  {
    if ( !dwPasswordLength )
      goto LABEL_103;
  }
  else if ( dwPasswordLength && (dwFlags & 0x90000000) != 0 )
  {
    goto LABEL_103;
  }
  dwUrlPathLength = lpUrlComponents->dwUrlPathLength;
  if ( lpUrlComponents->lpszUrlPath )
  {
    if ( !dwUrlPathLength )
      goto LABEL_103;
  }
  else if ( dwUrlPathLength && (dwFlags & 0x90000000) != 0 )
  {
    goto LABEL_103;
  }
  dwExtraInfoLength = lpUrlComponents->dwExtraInfoLength;
  if ( !lpUrlComponents->lpszExtraInfo )
  {
    if ( dwExtraInfoLength && (dwFlags & 0x90000000) != 0 )
      goto LABEL_103;
    goto LABEL_37;
  }
  if ( !dwExtraInfoLength )
  {
LABEL_103:
    UrlAddressW = 87;
    goto LABEL_95;
  }
LABEL_37:
  v28 = v67;
  v58 = 0;
  LODWORD(v60[0]) = 0;
  *(_QWORD *)v67 = 0;
  v29 = (char *)&v66 + 8;
  if ( !dwExtraInfoLength )
  {
    v28 = 0;
    v29 = 0;
  }
  *(_QWORD *)&v68.Data1 = v28;
  *(_QWORD *)&v71 = v29;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v62 = 0;
  *(_OWORD *)v63 = 0;
  *(_OWORD *)v64 = 0;
  *(_OWORD *)v65 = 0;
  v66 = 0;
  if ( (_DWORD)v4 )
    goto LABEL_148;
  DWORD1(v72) = 0;
  v41 = 0x7FFFFFFF;
  v57[0] = 0;
  v42 = pwszUrl;
  do
  {
    if ( !*v42 )
      break;
    ++v42;
    --v41;
  }
  while ( v41 );
  v43 = -2147024809;
  if ( v41 )
  {
    v43 = 0;
    v4 = (unsigned int)(0x7FFFFFFF - v41);
  }
  else
  {
    v4 = v57[0];
    DWORD1(v72) = 81;
  }
  *(_QWORD *)v57 = v4;
  UrlAddressW = WX_WIN32_FROM_HR(v43);
  if ( !UrlAddressW )
  {
LABEL_148:
    v30 = (unsigned int)v4;
    v31 = pwszUrl;
LABEL_41:
    if ( v31 >= &pwszUrl[(unsigned int)v4] || !*v31 )
      goto LABEL_53;
    for ( i = 0; ; ++i )
    {
      v33 = asc_1800E6F78[i];
      if ( !v33 )
      {
        ++v31;
        goto LABEL_41;
      }
      if ( *v31 == v33 )
        break;
    }
    v34 = v31 - pwszUrl;
    if ( !(unsigned int)ScanSchemes(pwszUrl, v34, (unsigned int *)v60) )
    {
LABEL_53:
      UrlAddressW = 12006;
      goto LABEL_54;
    }
    v35 = (unsigned int)v34 + 3LL;
    if ( v35 > v30 || *v31 != 58 || v31[1] != 47 || v31[2] != 47 )
    {
      UrlAddressW = 12005;
      goto LABEL_54;
    }
    Src[1] = (unsigned __int16 *)pwszUrl;
    LODWORD(v62[0]) = v31 - pwszUrl;
    HIDWORD(v62[0]) = dword_1800DF744[10 * LODWORD(v60[0])];
    v60[0] = (unsigned __int16 *)&pwszUrl[v35];
    v57[0] += -3 - v34;
    UrlAddressW = GetUrlAddressW(
                    v60,
                    v57,
                    &v63[1],
                    (unsigned int *)v64,
                    &v64[1],
                    v65,
                    &v62[1],
                    (unsigned int *)v63,
                    (unsigned __int16 *)v63 + 2,
                    &v58,
                    dwFlags & 0x4000);
    if ( !UrlAddressW )
    {
      v44 = v60[0];
      if ( v29 )
      {
        v45 = v60[0];
        v46 = v57[0];
        if ( v60[0] < &v60[0][v46] )
        {
          do
          {
            if ( *v45 == 35 )
              break;
            if ( *v45 == 63 )
              break;
            ++v45;
          }
          while ( v45 < &v60[0][v46] );
        }
        v47 = ((__int64)v60[0] + v46 * 2 - (__int64)v45) >> 1;
        v48 = v57[0] - v47;
        *(_QWORD *)v71 = v45;
        **(_DWORD **)&v68.Data1 = v47;
      }
      else
      {
        v48 = v57[0];
      }
      v49 = 0;
      v57[0] = 0;
      UrlAddressW = winHttpCrackUrlCopyResultToBuffer(
                      Src[1],
                      (unsigned int)v62[0],
                      (unsigned __int16 **)&lpUrlComponents->lpszScheme,
                      &lpUrlComponents->dwSchemeLength,
                      0,
                      0,
                      (int *)v57);
      if ( UrlAddressW )
        goto LABEL_95;
      v50 = dwFlags & 0x10000000;
      UrlAddressW = winHttpCrackUrlCopyResultToBuffer(
                      v62[1],
                      (unsigned int)v63[0],
                      (unsigned __int16 **)&lpUrlComponents->lpszHostName,
                      &lpUrlComponents->dwHostNameLength,
                      dwFlags & 0x10000000,
                      0,
                      (int *)v57);
      if ( UrlAddressW )
        goto LABEL_95;
      if ( lpUrlComponents->dwUserNameLength )
        v49 = lpUrlComponents->lpszUserName == 0;
      UrlAddressW = winHttpCrackUrlCopyResultToBuffer(
                      v63[1],
                      (unsigned int)v64[0],
                      (unsigned __int16 **)&lpUrlComponents->lpszUserName,
                      &lpUrlComponents->dwUserNameLength,
                      dwFlags & 0x10000000,
                      0,
                      (int *)v57);
      if ( UrlAddressW )
        goto LABEL_95;
      if ( v49 && !lpUrlComponents->dwUserNameLength )
        lpUrlComponents->lpszUserName = 0;
      v51 = lpUrlComponents->dwPasswordLength && !lpUrlComponents->lpszPassword;
      UrlAddressW = winHttpCrackUrlCopyResultToBuffer(
                      v64[1],
                      v65[0],
                      (unsigned __int16 **)&lpUrlComponents->lpszPassword,
                      &lpUrlComponents->dwPasswordLength,
                      dwFlags & 0x10000000,
                      0,
                      (int *)v57);
      if ( UrlAddressW )
        goto LABEL_95;
      if ( v51 && !lpUrlComponents->dwPasswordLength )
        lpUrlComponents->lpszPassword = 0;
      v52 = dwFlags & 0x80000000;
      UrlAddressW = winHttpCrackUrlCopyResultToBuffer(
                      v44,
                      v48,
                      (unsigned __int16 **)&lpUrlComponents->lpszUrlPath,
                      &lpUrlComponents->dwUrlPathLength,
                      v50,
                      v52,
                      (int *)v57);
      if ( UrlAddressW )
        goto LABEL_95;
      UrlAddressW = winHttpCrackUrlCopyResultToBuffer(
                      *((const unsigned __int16 **)&v66 + 1),
                      v67[0],
                      (unsigned __int16 **)&lpUrlComponents->lpszExtraInfo,
                      &lpUrlComponents->dwExtraInfoLength,
                      v50,
                      v52,
                      (int *)v57);
      if ( UrlAddressW )
        goto LABEL_95;
      v53 = HIDWORD(v62[0]);
      if ( v57[0] )
        UrlAddressW = 122;
      lpUrlComponents->nScheme = HIDWORD(v62[0]);
      if ( v58 )
        goto LABEL_94;
      v54 = v53 - 1;
      if ( v54 )
      {
        if ( v54 != 1 )
        {
LABEL_94:
          lpUrlComponents->nPort = WORD2(v63[0]);
          goto LABEL_54;
        }
        lpUrlComponents->nPort = 443;
      }
      else
      {
        lpUrlComponents->nPort = 80;
      }
    }
  }
LABEL_54:
  if ( !UrlAddressW )
  {
    v37 = 1;
    goto LABEL_56;
  }
LABEL_95:
  v37 = 0;
  if ( (xmmword_180107A50 & 4) != 0 )
    WPP_SF_d(514, 13, WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids, UrlAddressW, v56);
LABEL_56:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 14, WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids, v37, v56);
  if ( v70 )
  {
    *(_DWORD *)&v68.Data2 = 0;
    v38 = EtwEventActivityIdControl(2, &v69);
    v39 = v38 < 0;
    if ( v38 > 0 )
      v39 = 1;
    if ( v39 )
      *(_DWORD *)&v68.Data2 = 144;
  }
  SetLastError(UrlAddressW);
  return v37;
}

```

## disassembly

```asm
0x180041f20  mov     r11, rsp
0x180041f23  push    rbp
0x180041f24  push    rbx
0x180041f25  push    rdi
0x180041f26  lea     rbp, [rsp-80h]
0x180041f2b  sub     rsp, 180h
0x180041f32  mov     rax, cs:__security_cookie
0x180041f39  xor     rax, rsp
0x180041f3c  mov     [rbp+90h+var_50], rax
0x180041f40  mov     [r11-20h], rsi
0x180041f44  xor     eax, eax
0x180041f46  cmp     cs:?WinHttpEtwInitialized@@3EA, al; uchar WinHttpEtwInitialized
0x180041f4c  mov     edi, edx
0x180041f4e  mov     [r11-28h], r12
0x180041f52  xorps   xmm0, xmm0
0x180041f55  mov     [r11-30h], r13
0x180041f59  mov     r12d, r8d
0x180041f5c  mov     [r11-38h], r14
0x180041f60  mov     r13, r9
0x180041f63  mov     [r11-40h], r15
0x180041f67  mov     r14, rcx
0x180041f6a  mov     r15d, 1
0x180041f70  mov     qword ptr [rsp+190h+var_130], rdi
0x180041f75  movups  [rbp+90h+var_90], xmm0
0x180041f79  mov     [rbp+90h+var_80], eax
0x180041f7c  jz      loc_180042087
0x180041f82  mov     ecx, 10h
0x180041f87  lea     rax, [rbp+90h+var_90]
0x180041f8b  mov     edx, ecx
0x180041f8d  nop     dword ptr [rax]
0x180041f90  mov     byte ptr [rax], 0
0x180041f93  lea     rax, [rax+1]
0x180041f97  sub     rdx, r15
0x180041f9a  jnz     short loc_180041F90
0x180041f9c  xorps   xmm0, xmm0
0x180041f9f  mov     [rbp+90h+var_80], edx
0x180041fa2  xorps   xmm1, xmm1
0x180041fa5  lea     rax, [rbp+90h+var_90]
0x180041fa9  movups  xmmword ptr [rbp+90h+var_A0.Data1], xmm0
0x180041fad  mov     rdx, rcx
0x180041fb0  movups  [rbp+90h+var_70], xmm1
0x180041fb4  mov     byte ptr [rax], 0
0x180041fb7  lea     rax, [rax+1]
0x180041fbb  sub     rdx, r15
0x180041fbe  jnz     short loc_180041FB4
0x180041fc0  xorps   xmm0, xmm0
0x180041fc3  mov     [rsp+190h+var_124], edx
0x180041fc7  movups  [rbp+90h+var_60], xmm0
0x180041fcb  lea     rax, [rbp+90h+var_70]
0x180041fcf  nop
0x180041fd0  mov     byte ptr [rax], 0
0x180041fd3  lea     rax, [rax+1]
0x180041fd7  sub     rcx, r15
0x180041fda  jnz     short loc_180041FD0
0x180041fdc  lea     rdx, [rbp+90h+var_60]
0x180041fe0  mov     ecx, r15d
0x180041fe3  call    cs:__imp_EtwEventActivityIdControl
0x180041fe9  test    eax, eax
0x180041feb  jle     short loc_180041FF7
0x180041fed  movzx   eax, ax
0x180041ff0  or      eax, 80070000h
0x180041ff5  test    eax, eax
0x180041ff7  js      loc_1800426B7
0x180041ffd  movaps  xmm0, [rbp+90h+var_60]
0x180042001  movdqa  [rbp+90h+var_70], xmm0
0x180042006  mov     rdi, [rbp+98h]
0x18004200d  mov     esi, r15d
0x180042010  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180042018  inc     esi
0x18004201a  call    cs:__imp_GetTickCount
0x180042020  mov     ebx, eax
0x180042022  call    cs:__imp_GetCurrentProcessId
0x180042028  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, 0; int g_fEtwCorrelationProviderInitialized
0x18004202f  mov     dword ptr [rbp+90h+var_A0.Data4+4], eax
0x180042032  mov     [rbp+90h+var_A0.Data1], edi
0x180042035  mov     dword ptr [rbp+90h+var_A0.Data2], esi
0x180042038  mov     dword ptr [rbp+90h+var_A0.Data4], ebx
0x18004203b  jz      short loc_18004204B
0x18004203d  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180042043  test    eax, eax
0x180042045  jnz     loc_180042686
0x18004204b  lea     rdx, [rbp+90h+var_A0]
0x18004204f  mov     [rsp+190h+var_124], 0
0x180042057  mov     ecx, 2
0x18004205c  call    cs:__imp_EtwEventActivityIdControl
0x180042062  test    eax, eax
0x180042064  jle     short loc_180042070
0x180042066  movzx   eax, ax
0x180042069  or      eax, 80070000h
0x18004206e  test    eax, eax
0x180042070  js      loc_180042781
0x180042076  movaps  xmm0, [rbp+90h+var_70]
0x18004207a  mov     rdi, qword ptr [rsp+190h+var_130]
0x18004207f  movups  [rbp+90h+var_90], xmm0
0x180042083  mov     [rbp+90h+var_80], r15d
0x180042087  test    byte ptr cs:xmmword_180107A60, 4
0x18004208e  jnz     loc_180042730
0x180042094  test    r14, r14
0x180042097  jz      loc_1800425F6
0x18004209d  test    r13, r13
0x1800420a0  jz      loc_1800425F6
0x1800420a6  cmp     dword ptr [r13+0], 68h ; 'h'
0x1800420ab  jnz     loc_1800425F6
0x1800420b1  test    r12d, 6FFFBFFFh
0x1800420b8  jnz     loc_1800425F6
0x1800420be  cmp     qword ptr [r13+8], 0
0x1800420c3  mov     eax, [r13+10h]
0x1800420c7  jnz     loc_1800425EE
0x1800420cd  test    eax, eax
0x1800420cf  jnz     loc_1800426C4
0x1800420d5  cmp     qword ptr [r13+18h], 0
0x1800420da  mov     eax, [r13+20h]
0x1800420de  jnz     loc_1800425FD
0x1800420e4  test    eax, eax
0x1800420e6  jnz     loc_18004271E
0x1800420ec  cmp     qword ptr [r13+28h], 0
0x1800420f1  mov     eax, [r13+30h]
0x1800420f5  jnz     loc_180042607
0x1800420fb  test    eax, eax
0x1800420fd  jnz     loc_1800426D6
0x180042103  cmp     qword ptr [r13+38h], 0
0x180042108  mov     eax, [r13+40h]
0x18004210c  jnz     loc_180042611
0x180042112  test    eax, eax
0x180042114  jnz     loc_1800426E8
0x18004211a  cmp     qword ptr [r13+48h], 0
0x18004211f  mov     eax, [r13+50h]
0x180042123  jnz     loc_18004261B
0x180042129  test    eax, eax
0x18004212b  jnz     loc_1800426FA
0x180042131  cmp     qword ptr [r13+58h], 0
0x180042136  mov     ecx, [r13+60h]
0x18004213a  jnz     loc_180042625
0x180042140  test    ecx, ecx
0x180042142  jnz     loc_18004270C
0x180042148  xor     r10d, r10d
0x18004214b  lea     rdx, [rbp+90h+var_B0]
0x18004214f  xorps   xmm0, xmm0
0x180042152  mov     [rsp+190h+var_128], r10d
0x180042157  xor     eax, eax
0x180042159  mov     dword ptr [rsp+190h+var_120], r10d
0x18004215e  test    ecx, ecx
0x180042160  mov     qword ptr [rbp+90h+var_B0], rax
0x180042164  lea     r15, [rbp+90h+var_B8]
0x180042168  cmovz   rdx, r10
0x18004216c  cmovz   r15, r10
0x180042170  mov     qword ptr [rbp+90h+var_A0.Data1], rdx
0x180042174  mov     qword ptr [rbp+90h+var_70], r15
0x180042178  movups  xmmword ptr [rbp+90h+Src], xmm0
0x18004217c  movups  xmmword ptr [rbp+90h+var_100], xmm0
0x180042180  movups  xmmword ptr [rbp+90h+var_F0], xmm0
0x180042184  movups  xmmword ptr [rbp+90h+var_E0], xmm0
0x180042188  movups  xmmword ptr [rbp+90h+var_D0], xmm0
0x18004218c  movups  xmmword ptr [rbp-30h], xmm0
0x180042190  test    edi, edi
0x180042192  jz      loc_1800422AC
0x180042198  mov     esi, edi
0x18004219a  lea     r9, __ImageBase
0x1800421a1  mov     rbx, r14
0x1800421a4  lea     r8, [r14+rsi*2]
0x1800421a8  cmp     rbx, r8
0x1800421ab  jnb     short loc_180042216
0x1800421ad  movzx   edx, word ptr [rbx]
0x1800421b0  test    dx, dx
0x1800421b3  jz      short loc_180042216
0x1800421b5  mov     ecx, r10d
0x1800421b8  mov     eax, ecx
0x1800421ba  movzx   eax, word ptr ds:rva asc_1800E6F78[r9+rax*2]; ":" ...
0x1800421c3  test    ax, ax
0x1800421c6  jz      short loc_1800421D1
0x1800421c8  cmp     dx, ax
0x1800421cb  jz      short loc_1800421D7
0x1800421cd  inc     ecx
0x1800421cf  jmp     short loc_1800421B8
0x1800421d1  add     rbx, 2
0x1800421d5  jmp     short loc_1800421A8
0x1800421d7  mov     rdi, rbx
0x1800421da  lea     r8, [rsp+190h+var_120]; unsigned int *
0x1800421df  sub     rdi, r14
0x1800421e2  mov     rcx, r14; unsigned __int16 *
0x1800421e5  sar     rdi, 1
0x1800421e8  mov     edx, edi; unsigned int
0x1800421ea  call    ?ScanSchemes@@YAHPEBGKPEAK@Z; ScanSchemes(ushort const *,ulong,ulong *)
0x1800421ef  test    eax, eax
0x1800421f1  jz      short loc_180042216
0x1800421f3  mov     ecx, edi
0x1800421f5  add     rcx, 3
0x1800421f9  cmp     rcx, rsi
0x1800421fc  ja      short loc_18004220F
0x1800421fe  cmp     word ptr [rbx], 3Ah ; ':'
0x180042202  jnz     short loc_18004220F
0x180042204  cmp     word ptr [rbx+2], 2Fh ; '/'
0x180042209  jz      loc_180042302
0x18004220f  mov     ebx, 2EE5h
0x180042214  jmp     short loc_18004221B
0x180042216  mov     ebx, 2EE6h
0x18004221b  test    ebx, ebx
0x18004221d  jnz     loc_18004258D
0x180042223  mov     edi, 1
0x180042228  xor     eax, eax
0x18004222a  test    byte ptr cs:xmmword_180107A60, 4
0x180042231  mov     r15, [rsp+190h+var_38]
0x180042239  mov     r14, [rsp+190h+var_30]
0x180042241  mov     r13, [rsp+190h+var_28]
0x180042249  mov     r12, [rsp+190h+var_20]
0x180042251  mov     rsi, [rsp+190h+var_18]
0x180042259  jnz     loc_1800427C6
0x18004225f  cmp     [rbp+90h+var_80], 0
0x180042263  jz      short loc_18004228B
0x180042265  lea     rdx, [rbp+90h+var_90]
0x180042269  mov     dword ptr [rbp+90h+var_A0.Data2], eax
0x18004226c  mov     ecx, 2
0x180042271  call    cs:__imp_EtwEventActivityIdControl
0x180042277  test    eax, eax
0x180042279  jle     short loc_180042285
0x18004227b  movzx   eax, ax
0x18004227e  or      eax, 80070000h
0x180042283  test    eax, eax
0x180042285  js      loc_18004269B
0x18004228b  mov     ecx, ebx; dwErrCode
0x18004228d  call    cs:__imp_SetLastError
0x180042293  mov     eax, edi
0x180042295  mov     rcx, [rbp+90h+var_50]
0x180042299  xor     rcx, rsp; StackCookie
0x18004229c  call    __security_check_cookie
0x1800422a1  add     rsp, 180h
0x1800422a8  pop     rdi
0x1800422a9  pop     rbx
0x1800422aa  pop     rbp
0x1800422ab  retn
0x1800422ac  mov     edi, 7FFFFFFFh
0x1800422b1  mov     dword ptr [rbp+90h+var_60+4], r10d
0x1800422b5  mov     ecx, edi
0x1800422b7  mov     [rsp+190h+var_130], r10d
0x1800422bc  mov     rax, r14
0x1800422bf  nop
0x1800422c0  cmp     [rax], r10w
0x1800422c4  jz      short loc_1800422D0
0x1800422c6  add     rax, 2
0x1800422ca  sub     rcx, 1
0x1800422ce  jnz     short loc_1800422C0
0x1800422d0  test    rcx, rcx
0x1800422d3  mov     edx, 80070057h
0x1800422d8  cmovnz  edx, r10d
0x1800422dc  jz      loc_1800426A7
0x1800422e2  sub     edi, ecx
0x1800422e4  mov     qword ptr [rsp+190h+var_130], rdi
0x1800422e9  mov     ecx, edx
0x1800422eb  call    WX_WIN32_FROM_HR
0x1800422f0  mov     ebx, eax
0x1800422f2  test    eax, eax
0x1800422f4  jnz     loc_18004221B
0x1800422fa  xor     r10d, r10d
0x1800422fd  jmp     loc_180042198
0x180042302  cmp     word ptr [rbx+4], 2Fh ; '/'
0x180042307  jnz     loc_18004220F
0x18004230d  mov     eax, dword ptr [rsp+190h+var_120]
0x180042311  lea     rdx, __ImageBase
0x180042318  lea     r9, [rbp+90h+var_E0]; unsigned int *
0x18004231c  mov     [rbp+90h+Src+8], r14
0x180042320  lea     r8, [rbp+90h+var_F0+8]; unsigned __int16 **
0x180042324  mov     dword ptr [rbp+90h+var_100], edi
0x180042327  lea     rax, [rax+rax*4]
0x18004232b  mov     eax, ds:rva dword_1800DF744[rdx+rax*8]
0x180042332  lea     rdx, [rsp+190h+var_130]; unsigned int *
0x180042337  mov     dword ptr [rbp+90h+var_100+4], eax
0x18004233a  lea     rax, [r14+rcx*2]
0x18004233e  mov     rcx, qword ptr [rsp+190h+var_130]
0x180042343  mov     [rsp+190h+var_120], rax
0x180042348  mov     eax, 0FFFFFFFDh
0x18004234d  sub     eax, edi
0x18004234f  add     ecx, eax
0x180042351  mov     eax, r12d
0x180042354  and     eax, 4000h
0x180042359  mov     [rsp+190h+var_130], ecx
0x18004235d  mov     [rsp+190h+var_140], eax; int
0x180042361  lea     rcx, [rsp+190h+var_120]; unsigned __int16 **
0x180042366  lea     rax, [rsp+190h+var_128]
0x18004236b  mov     [rsp+190h+var_148], rax; int *
0x180042370  lea     rax, [rbp+90h+var_F0+4]
0x180042374  mov     [rsp+190h+var_150], rax; unsigned __int16 *
0x180042379  lea     rax, [rbp+90h+var_F0]
0x18004237d  mov     [rsp+190h+var_158], rax; unsigned int *
0x180042382  lea     rax, [rbp+90h+var_100+8]
0x180042386  mov     [rsp+190h+var_160], rax; unsigned __int16 **
0x18004238b  lea     rax, [rbp+90h+var_D0]
0x18004238f  mov     [rsp+190h+var_168], rax; unsigned int *
0x180042394  lea     rax, [rbp+90h+var_E0+8]
0x180042398  mov     [rsp+190h+var_170], rax; unsigned __int16 **
0x18004239d  call    ?GetUrlAddressW@@YAKPEAPEAGPEAK010101PEAGPEAHH@Z; GetUrlAddressW(ushort * *,ulong *,ushort * *,ulong *,ushort * *,ulong *,ushort * *,ulong *,ushort *,int *,int)
0x1800423a2  mov     ebx, eax
0x1800423a4  test    eax, eax
0x1800423a6  jnz     loc_18004221B
0x1800423ac  mov     r14, [rsp+190h+var_120]
0x1800423b1  test    r15, r15
0x1800423b4  jz      loc_1800425D5
0x1800423ba  mov     r15d, [rsp+190h+var_130]
0x1800423bf  mov     rcx, r14
0x1800423c2  lea     rdx, [r15+r15]
0x1800423c6  lea     r8, [rdx+r14]
  ... truncated ...
```
