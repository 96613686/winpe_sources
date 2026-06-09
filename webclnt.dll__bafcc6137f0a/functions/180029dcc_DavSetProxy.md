# DavSetProxy

- ea: `0x180029dcc`
- end: `0x18002a311`
- name: `DavSetProxy`
- size: `1349`
- prototype: `unsigned int __fastcall(HINTERNET hInternet, HINTERNET, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002986c`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000ba14`
- `0x180029c44`
- `0x180029c84`
- `0x180029dcc`
- `0x18002a5e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a279`
- `KERNEL32!LocalFree` at `0x18002a2f7`
- `KERNEL32!LocalFree` at `0x18002a2f7`
- `KERNEL32!GlobalFree` at `0x180029f8a`
- `KERNEL32!GlobalFree` at `0x180029fa4`
- `KERNEL32!GlobalFree` at `0x18002a2b2`
- `KERNEL32!GlobalFree` at `0x18002a2c1`
- `KERNEL32!GlobalFree` at `0x18002a2da`
- `KERNEL32!GlobalFree` at `0x18002a2e9`
- `KERNEL32!GlobalFree` at `0x180029f8a`
- `KERNEL32!GlobalFree` at `0x180029fa4`
- `KERNEL32!GlobalFree` at `0x18002a2b2`
- `KERNEL32!GlobalFree` at `0x18002a2c1`
- `KERNEL32!GlobalFree` at `0x18002a2da`
- `KERNEL32!GlobalFree` at `0x18002a2e9`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180029f32`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180029f32`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180029e63`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180029e63`
- `WINHTTP!WinHttpSetOption` at `0x18002a218`
- `WINHTTP!WinHttpSetOption` at `0x18002a26f`
- `WINHTTP!WinHttpSetOption` at `0x18002a218`
- `WINHTTP!WinHttpSetOption` at `0x18002a26f`

## pseudocode

```c
unsigned int __fastcall DavSetProxy(HINTERNET hInternet, HINTERNET a2, __int64 a3)
{
  BOOL ProxyForUrl; // r14d
  int v5; // r15d
  WCHAR *PathFromRequest; // rdi
  __int64 v9; // rbx
  DWORD LastError; // eax
  const WCHAR *lpszAutoConfigUrl; // rax
  _QWORD *v12; // r10
  DWORD v13; // eax
  WCHAR *v14; // rbx
  int v15; // edx
  int v16; // ecx
  WCHAR v17; // ax
  __int64 v18; // r10
  LPWSTR lpszProxyBypass; // rax
  DWORD v20; // eax
  unsigned int result; // eax
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+30h] [rbp-49h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+48h] [rbp-31h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+68h] [rbp-11h] BYREF

  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  ProxyForUrl = 0;
  v5 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  PathFromRequest = (WCHAR *)DavQueryPathFromRequest(a2);
  if ( !PathFromRequest
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_d(v9, 16, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, LastError);
  }
  if ( !WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    goto LABEL_32;
  lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
  if ( !pProxyConfig.fAutoDetect && !pProxyConfig.lpszAutoConfigUrl )
    goto LABEL_26;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
    lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    v12 = WPP_GLOBAL_Control;
  }
  pAutoProxyOptions.fAutoLogonIfChallenged = 1;
  if ( lpszAutoConfigUrl )
  {
    *(_QWORD *)&pAutoProxyOptions.dwFlags = 65538;
    pAutoProxyOptions.lpszAutoConfigUrl = lpszAutoConfigUrl;
  }
  else
  {
    pAutoProxyOptions.dwFlags = 65537;
    pAutoProxyOptions.lpszAutoConfigUrl = 0;
    pAutoProxyOptions.dwAutoDetectFlags = 3;
  }
  pAutoProxyOptions.lpvReserved = 0;
  pAutoProxyOptions.dwReserved = 0;
  if ( !PathFromRequest )
    goto LABEL_27;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    WPP_SF_S(v12[2], 18, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, PathFromRequest);
  ProxyForUrl = WinHttpGetProxyForUrl(hInternet, PathFromRequest, &pAutoProxyOptions, &pProxyInfo);
  if ( ProxyForUrl )
  {
LABEL_32:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  v13 = GetLastError();
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)(ProxyForUrl + 19),
      WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
      v13);
    v12 = WPP_GLOBAL_Control;
  }
  if ( pProxyInfo.lpszProxy )
  {
    GlobalFree(pProxyInfo.lpszProxy);
    v12 = WPP_GLOBAL_Control;
    pProxyInfo.lpszProxy = 0;
  }
  if ( !pProxyInfo.lpszProxyBypass )
    goto LABEL_27;
  GlobalFree(pProxyInfo.lpszProxyBypass);
  pProxyInfo.lpszProxyBypass = 0;
LABEL_26:
  v12 = WPP_GLOBAL_Control;
LABEL_27:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
  {
    WPP_SF_(v12[2], 20, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( pProxyConfig.lpszProxy )
  {
    pProxyInfo.lpszProxy = pProxyConfig.lpszProxy;
    pProxyInfo.lpszProxyBypass = pProxyConfig.lpszProxyBypass;
    pProxyInfo.dwAccessType = 3;
  }
LABEL_33:
  if ( pProxyInfo.lpszProxy )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    {
      lpszProxyBypass = L"NULL";
      if ( pProxyInfo.lpszProxyBypass )
        lpszProxyBypass = pProxyInfo.lpszProxyBypass;
      WPP_SF_SS(
        v12[2],
        25,
        (unsigned int)WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
        pProxyInfo.lpszProxy,
        (__int64)lpszProxyBypass);
    }
  }
  else
  {
    v14 = PathFromRequest;
    v15 = 0;
    if ( PathFromRequest )
    {
      while ( PathFromRequest[v15] )
      {
        if ( PathFromRequest[v15] == 47 && PathFromRequest[v15 + 1] == 47 )
        {
          v14 = &PathFromRequest[v15 + 2];
          break;
        }
        ++v15;
      }
    }
    v16 = 0;
    if ( v14 )
    {
      while ( 1 )
      {
        v17 = v14[v16];
        if ( !v17 )
          break;
        if ( v17 == 58 || v17 == 47 )
        {
          v14[v16] = 0;
          v12 = WPP_GLOBAL_Control;
          break;
        }
        ++v16;
      }
    }
    if ( ProxyForUrl )
    {
      pProxyInfo.dwAccessType = 3;
      pProxyInfo.lpszProxy = L"none";
      if ( PathFromRequest && v14 )
      {
        pProxyInfo.lpszProxyBypass = v14;
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_S(v12[2], 22, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v14);
      }
      else
      {
        pProxyInfo.lpszProxyBypass = L"<local>";
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_(v12[2], 21, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
      }
      v5 = 1;
    }
    else
    {
      pProxyInfo.dwAccessType = 1;
      if ( (unsigned int)DavIsUrlPathLocal(PathFromRequest) )
      {
        if ( (_UNKNOWN **)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 2) != 0 )
          WPP_SF_(*(_QWORD *)(v18 + 16), 23, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids);
        pProxyInfo.dwAccessType = 3;
        pProxyInfo.lpszProxy = L"none";
        pProxyInfo.lpszProxyBypass = L"<local>";
      }
      else if ( (unsigned int)DavIsHostInAdminBypassList(a3, PathFromRequest) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v14);
        pProxyInfo.dwAccessType = 3;
        pProxyInfo.lpszProxy = L"none";
        pProxyInfo.lpszProxyBypass = v14;
      }
    }
  }
  if ( !WinHttpSetOption(hInternet, 0x26u, &pProxyInfo, 0x18u) )
  {
    v20 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v20);
  }
  result = WinHttpSetOption(a2, 0x26u, &pProxyInfo, 0x18u);
  if ( !result )
  {
    result = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      result = WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 27,
                 WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
                 result);
  }
  if ( pProxyConfig.lpszProxy )
    result = (unsigned int)GlobalFree(pProxyConfig.lpszProxy);
  if ( pProxyConfig.lpszProxyBypass )
    result = (unsigned int)GlobalFree(pProxyConfig.lpszProxyBypass);
  if ( ProxyForUrl && !v5 )
  {
    if ( pProxyInfo.lpszProxy )
      result = (unsigned int)GlobalFree(pProxyInfo.lpszProxy);
    if ( pProxyInfo.lpszProxyBypass )
      result = (unsigned int)GlobalFree(pProxyInfo.lpszProxyBypass);
  }
  if ( PathFromRequest )
    return (unsigned int)LocalFree(PathFromRequest);
  return result;
}

```

## disassembly

```asm
0x180029dcc  push    rbp
0x180029dce  push    rbx
0x180029dcf  push    rsi
0x180029dd0  push    rdi
0x180029dd1  push    r12
0x180029dd3  push    r13
0x180029dd5  push    r14
0x180029dd7  push    r15
0x180029dd9  lea     rbp, [rsp-1Fh]
0x180029dde  sub     rsp, 98h
0x180029de5  xorps   xmm0, xmm0
0x180029de8  xor     ebx, ebx
0x180029dea  xorps   xmm1, xmm1
0x180029ded  mov     qword ptr [rbp+57h+pProxyInfo.dwAccessType], rbx
0x180029df1  mov     r12, rcx
0x180029df4  mov     r14d, ebx
0x180029df7  mov     rcx, rdx; hInternet
0x180029dfa  mov     r15d, ebx
0x180029dfd  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.dwFlags], xmm0
0x180029e01  mov     rsi, r8
0x180029e04  mov     r13, rdx
0x180029e07  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.lpvReserved], xmm0
0x180029e0b  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm1
0x180029e0f  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm1
0x180029e13  movdqu  xmmword ptr [rbp+57h+pProxyInfo.lpszProxy], xmm0
0x180029e18  call    DavQueryPathFromRequest
0x180029e1d  mov     rdi, rax
0x180029e20  lea     rax, WPP_GLOBAL_Control
0x180029e27  test    rdi, rdi
0x180029e2a  jnz     short loc_180029E5F
0x180029e2c  mov     rbx, cs:WPP_GLOBAL_Control
0x180029e33  cmp     rbx, rax
0x180029e36  jz      short loc_180029E5D
0x180029e38  test    byte ptr [rbx+1Ch], 1
0x180029e3c  jz      short loc_180029E5D
0x180029e3e  mov     rbx, [rbx+10h]
0x180029e42  call    cs:__imp_GetLastError
0x180029e48  lea     edx, [rdi+10h]
0x180029e4b  mov     rcx, rbx
0x180029e4e  mov     r9d, eax
0x180029e51  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029e58  call    WPP_SF_d
0x180029e5d  xor     ebx, ebx
0x180029e5f  lea     rcx, [rbp+57h+pProxyConfig]; pProxyConfig
0x180029e63  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180029e69  test    eax, eax
0x180029e6b  jz      loc_18002A002
0x180029e71  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x180029e75  cmp     [rbp+57h+pProxyConfig.fAutoDetect], ebx
0x180029e78  jnz     short loc_180029E83
0x180029e7a  test    rax, rax
0x180029e7d  jz      loc_180029FAE
0x180029e83  mov     r10, cs:WPP_GLOBAL_Control
0x180029e8a  lea     rcx, WPP_GLOBAL_Control
0x180029e91  cmp     r10, rcx
0x180029e94  jz      short loc_180029EC4
0x180029e96  test    byte ptr [r10+1Ch], 2
0x180029e9b  jz      short loc_180029EC4
0x180029e9d  mov     rcx, [r10+10h]
0x180029ea1  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029ea8  mov     edx, 11h
0x180029ead  call    WPP_SF_
0x180029eb2  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x180029eb6  lea     rcx, WPP_GLOBAL_Control
0x180029ebd  mov     r10, cs:WPP_GLOBAL_Control
0x180029ec4  mov     [rbp+57h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x180029ecb  test    rax, rax
0x180029ece  jz      short loc_180029EDE
0x180029ed0  mov     qword ptr [rbp+57h+pAutoProxyOptions.dwFlags], 10002h
0x180029ed8  mov     [rbp+57h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x180029edc  jmp     short loc_180029EF0
0x180029ede  mov     [rbp+57h+pAutoProxyOptions.dwFlags], 10001h
0x180029ee5  mov     [rbp+57h+pAutoProxyOptions.lpszAutoConfigUrl], rbx
0x180029ee9  mov     [rbp+57h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180029ef0  mov     [rbp+57h+pAutoProxyOptions.lpvReserved], rbx
0x180029ef4  mov     [rbp+57h+pAutoProxyOptions.dwReserved], ebx
0x180029ef7  test    rdi, rdi
0x180029efa  jz      loc_180029FB5
0x180029f00  cmp     r10, rcx
0x180029f03  jz      short loc_180029F24
0x180029f05  test    byte ptr [r10+1Ch], 2
0x180029f0a  jz      short loc_180029F24
0x180029f0c  mov     rcx, [r10+10h]
0x180029f10  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029f17  mov     edx, 12h
0x180029f1c  mov     r9, rdi
0x180029f1f  call    WPP_SF_S
0x180029f24  lea     r9, [rbp+57h+pProxyInfo]; pProxyInfo
0x180029f28  mov     rdx, rdi; lpcwszUrl
0x180029f2b  lea     r8, [rbp+57h+pAutoProxyOptions]; pAutoProxyOptions
0x180029f2f  mov     rcx, r12; hSession
0x180029f32  call    cs:__imp_WinHttpGetProxyForUrl
0x180029f38  mov     r14d, eax
0x180029f3b  test    eax, eax
0x180029f3d  jnz     loc_18002A002
0x180029f43  call    cs:__imp_GetLastError
0x180029f49  mov     r10, cs:WPP_GLOBAL_Control
0x180029f50  lea     rcx, WPP_GLOBAL_Control
0x180029f57  cmp     r10, rcx
0x180029f5a  jz      short loc_180029F81
0x180029f5c  test    byte ptr [r10+1Ch], 1
0x180029f61  jz      short loc_180029F81
0x180029f63  mov     rcx, [r10+10h]
0x180029f67  lea     edx, [r14+13h]
0x180029f6b  mov     r9d, eax
0x180029f6e  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029f75  call    WPP_SF_d
0x180029f7a  mov     r10, cs:WPP_GLOBAL_Control
0x180029f81  mov     rcx, [rbp+57h+pProxyInfo.lpszProxy]; hMem
0x180029f85  test    rcx, rcx
0x180029f88  jz      short loc_180029F9B
0x180029f8a  call    cs:__imp_GlobalFree
0x180029f90  mov     r10, cs:WPP_GLOBAL_Control
0x180029f97  mov     [rbp+57h+pProxyInfo.lpszProxy], rbx
0x180029f9b  mov     rcx, [rbp+57h+pProxyInfo.lpszProxyBypass]; hMem
0x180029f9f  test    rcx, rcx
0x180029fa2  jz      short loc_180029FB5
0x180029fa4  call    cs:__imp_GlobalFree
0x180029faa  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rbx
0x180029fae  mov     r10, cs:WPP_GLOBAL_Control
0x180029fb5  lea     rax, WPP_GLOBAL_Control
0x180029fbc  cmp     r10, rax
0x180029fbf  jz      short loc_180029FE4
0x180029fc1  test    byte ptr [r10+1Ch], 2
0x180029fc6  jz      short loc_180029FE4
0x180029fc8  mov     rcx, [r10+10h]
0x180029fcc  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029fd3  mov     edx, 14h
0x180029fd8  call    WPP_SF_
0x180029fdd  mov     r10, cs:WPP_GLOBAL_Control
0x180029fe4  mov     rax, [rbp+57h+pProxyConfig.lpszProxy]
0x180029fe8  test    rax, rax
0x180029feb  jz      short loc_18002A009
0x180029fed  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x180029ff1  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x180029ff5  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x180029ff9  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x18002a000  jmp     short loc_18002A009
0x18002a002  mov     r10, cs:WPP_GLOBAL_Control
0x18002a009  cmp     [rbp+57h+pProxyInfo.lpszProxy], rbx
0x18002a00d  jnz     loc_18002A1C2
0x18002a013  xor     r9d, r9d
0x18002a016  mov     rbx, rdi
0x18002a019  mov     edx, r9d
0x18002a01c  test    rdi, rdi
0x18002a01f  jz      short loc_18002A046
0x18002a021  mov     eax, edx
0x18002a023  cmp     [rdi+rax*2], r9w
0x18002a028  jz      short loc_18002A046
0x18002a02a  cmp     word ptr [rdi+rax*2], 2Fh ; '/'
0x18002a02f  lea     ecx, [rdx+1]
0x18002a032  jnz     short loc_18002A03B
0x18002a034  cmp     word ptr [rdi+rcx*2], 2Fh ; '/'
0x18002a039  jz      short loc_18002A03F
0x18002a03b  mov     edx, ecx
0x18002a03d  jmp     short loc_18002A021
0x18002a03f  lea     eax, [rdx+2]
0x18002a042  lea     rbx, [rdi+rax*2]
0x18002a046  mov     ecx, r9d
0x18002a049  test    rbx, rbx
0x18002a04c  jz      short loc_18002A075
0x18002a04e  mov     edx, ecx
0x18002a050  movzx   eax, word ptr [rbx+rdx*2]
0x18002a054  test    ax, ax
0x18002a057  jz      short loc_18002A075
0x18002a059  cmp     ax, 3Ah ; ':'
0x18002a05d  jz      short loc_18002A069
0x18002a05f  cmp     ax, 2Fh ; '/'
0x18002a063  jz      short loc_18002A069
0x18002a065  inc     ecx
0x18002a067  jmp     short loc_18002A04E
0x18002a069  mov     [rbx+rdx*2], r9w
0x18002a06e  mov     r10, cs:WPP_GLOBAL_Control
0x18002a075  test    r14d, r14d
0x18002a078  jz      loc_18002A109
0x18002a07e  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x18002a085  lea     rax, aNone; "none"
0x18002a08c  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x18002a090  test    rdi, rdi
0x18002a093  jz      short loc_18002A0CB
0x18002a095  test    rbx, rbx
0x18002a098  jz      short loc_18002A0CB
0x18002a09a  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rbx
0x18002a09e  lea     rax, WPP_GLOBAL_Control
0x18002a0a5  cmp     r10, rax
0x18002a0a8  jz      short loc_18002A0FE
0x18002a0aa  test    byte ptr [r10+1Ch], 2
0x18002a0af  jz      short loc_18002A0FE
0x18002a0b1  mov     rcx, [r10+10h]
0x18002a0b5  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18002a0bc  mov     edx, 16h
0x18002a0c1  mov     r9, rbx
0x18002a0c4  call    WPP_SF_S
0x18002a0c9  jmp     short loc_18002A0FE
0x18002a0cb  lea     rax, aLocal; "<local>"
0x18002a0d2  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x18002a0d6  lea     rax, WPP_GLOBAL_Control
0x18002a0dd  cmp     r10, rax
0x18002a0e0  jz      short loc_18002A0FE
0x18002a0e2  test    byte ptr [r10+1Ch], 2
0x18002a0e7  jz      short loc_18002A0FE
0x18002a0e9  mov     rcx, [r10+10h]
0x18002a0ed  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18002a0f4  mov     edx, 15h
0x18002a0f9  call    WPP_SF_
0x18002a0fe  mov     r15d, 1
0x18002a104  jmp     loc_18002A205
0x18002a109  mov     rcx, rdi
0x18002a10c  mov     [rbp+57h+pProxyInfo.dwAccessType], 1
0x18002a113  call    DavIsUrlPathLocal
0x18002a118  test    eax, eax
0x18002a11a  jz      short loc_18002A166
0x18002a11c  lea     rax, WPP_GLOBAL_Control
0x18002a123  cmp     r10, rax
0x18002a126  jz      short loc_18002A144
0x18002a128  test    byte ptr [r10+1Ch], 2
0x18002a12d  jz      short loc_18002A144
0x18002a12f  mov     rcx, [r10+10h]
0x18002a133  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18002a13a  mov     edx, 17h
0x18002a13f  call    WPP_SF_
0x18002a144  lea     rax, aNone; "none"
0x18002a14b  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x18002a152  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x18002a156  lea     rax, aLocal; "<local>"
0x18002a15d  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x18002a161  jmp     loc_18002A205
0x18002a166  mov     rdx, rdi
0x18002a169  mov     rcx, rsi
0x18002a16c  call    DavIsHostInAdminBypassList
0x18002a171  test    eax, eax
0x18002a173  jz      loc_18002A205
0x18002a179  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a180  lea     rax, WPP_GLOBAL_Control
0x18002a187  cmp     rcx, rax
0x18002a18a  jz      short loc_18002A1AA
0x18002a18c  test    byte ptr [rcx+1Ch], 2
0x18002a190  jz      short loc_18002A1AA
0x18002a192  mov     rcx, [rcx+10h]
0x18002a196  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18002a19d  mov     edx, 18h
0x18002a1a2  mov     r9, rbx
0x18002a1a5  call    WPP_SF_S
0x18002a1aa  lea     rax, aNone; "none"
0x18002a1b1  mov     [rbp+57h+pProxyInfo.dwAccessType], 3
0x18002a1b8  mov     [rbp+57h+pProxyInfo.lpszProxy], rax
0x18002a1bc  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rbx
0x18002a1c0  jmp     short loc_18002A205
0x18002a1c2  lea     rax, WPP_GLOBAL_Control
0x18002a1c9  cmp     r10, rax
0x18002a1cc  jz      short loc_18002A205
0x18002a1ce  test    byte ptr [r10+1Ch], 2
0x18002a1d3  jz      short loc_18002A205
0x18002a1d5  mov     rcx, [rbp+57h+pProxyInfo.lpszProxyBypass]
0x18002a1d9  lea     rax, aNull_0; "NULL"
0x18002a1e0  mov     r9, [rbp+57h+pProxyInfo.lpszProxy]
0x18002a1e4  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18002a1eb  test    rcx, rcx
0x18002a1ee  mov     edx, 19h
0x18002a1f3  cmovnz  rax, rcx
0x18002a1f7  mov     rcx, [r10+10h]
0x18002a1fb  mov     [rsp+0D0h+var_B0], rax
0x18002a200  call    WPP_SF_SS
0x18002a205  mov     r9d, 18h; dwBufferLength
0x18002a20b  lea     r8, [rbp+57h+pProxyInfo]; lpBuffer
0x18002a20f  mov     rcx, r12; hInternet
0x18002a212  lea     esi, [r9+0Eh]
0x18002a216  mov     edx, esi; dwOption
0x18002a218  call    cs:__imp_WinHttpSetOption
0x18002a21e  test    eax, eax
0x18002a220  jnz     short loc_18002A259
0x18002a222  call    cs:__imp_GetLastError
0x18002a228  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a22f  lea     r12, WPP_GLOBAL_Control
0x18002a236  cmp     rcx, r12
0x18002a239  jz      short loc_18002A260
0x18002a23b  test    byte ptr [rcx+1Ch], 1
0x18002a23f  jz      short loc_18002A260
0x18002a241  mov     rcx, [rcx+10h]
0x18002a245  lea     edx, [rsi-0Ch]
0x18002a248  mov     r9d, eax
0x18002a24b  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x18002a252  call    WPP_SF_d
0x18002a257  jmp     short loc_18002A260
0x18002a259  lea     r12, WPP_GLOBAL_Control
0x18002a260  mov     r9d, 18h; dwBufferLength
0x18002a266  lea     r8, [rbp+57h+pProxyInfo]; lpBuffer
0x18002a26a  mov     edx, esi; dwOption
0x18002a26c  mov     rcx, r13; hInternet
0x18002a26f  call    cs:__imp_WinHttpSetOption
0x18002a275  test    eax, eax
0x18002a277  jnz     short loc_18002A2A9
0x18002a279  call    cs:__imp_GetLastError
0x18002a27f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a286  cmp     rcx, r12
0x18002a289  jz      short loc_18002A2A9
0x18002a28b  test    byte ptr [rcx+1Ch], 1
0x18002a28f  jz      short loc_18002A2A9
0x18002a291  mov     rcx, [rcx+10h]
0x18002a295  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
  ... truncated ...
```
