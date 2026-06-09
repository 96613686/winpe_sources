# CHttpRequest::DiscoverProxyInfoForUrl(wchar_t const *,wchar_t const *,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ulong *)

- ea: `0x18009a7bc`
- end: `0x18009ad92`
- name: `?DiscoverProxyInfoForUrl@CHttpRequest@@IEAAJPEB_W0HPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1PEAK@Z`
- size: `1494`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009ad98`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x18001fe24`
- `0x18003bf14`
- `0x180065d54`
- `0x18009a7bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009ab11`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009ab33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009ab11`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009ab33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009abde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009abde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad6b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009ad4b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009ad4b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009a861`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009a861`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8cd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8dc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8fd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a90f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8cd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8dc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8fd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a90f`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18009aa0f`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18009aa0f`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009ab2b`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009ab2b`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18009a94d`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18009a94d`

## pseudocode

```c
__int64 __fastcall CHttpRequest::DiscoverProxyInfoForUrl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 *a6,
        _DWORD *a7)
{
  _DWORD *v9; // r15
  void *v10; // rcx
  DWORD v11; // eax
  unsigned int v12; // eax
  int v13; // ebx
  wchar_t *v14; // rcx
  _WORD *v16; // rcx
  _WORD *v17; // rcx
  LPWSTR lpszProxyBypass; // rdx
  wchar_t *v19; // rcx
  __int64 v20; // rdx
  int v21; // edx
  DWORD dwFlags; // eax
  const wchar_t *v23; // r8
  int v24; // eax
  wchar_t *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  BOOL ProxyForUrl; // ebx
  DWORD LastError; // eax
  unsigned int v30; // eax
  LPWSTR lpszProxy; // rdx
  DWORD v32; // eax
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+30h] [rbp-89h] BYREF
  HGLOBAL v34; // [rsp+48h] [rbp-71h]
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG v35; // [rsp+50h] [rbp-69h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+70h] [rbp-49h] BYREF
  LPCWSTR lpcwszUrl[13]; // [rsp+90h] [rbp-29h] BYREF
  int v40; // [rsp+118h] [rbp+5Fh]

  v40 = 0;
  v34 = 0;
  *(_OWORD *)&pProxyInfo.lpszProxy = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&v35, 0, sizeof(v35));
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v9 = a7;
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v10 = *(void **)(a1 + 224);
  if ( !v10 )
    goto LABEL_29;
  if ( ImpersonateLoggedOnUser(v10) )
  {
    v40 = 1;
LABEL_29:
    v16 = *(_WORD **)a5;
    *(_QWORD *)(a5 + 8) = *(_QWORD *)a5;
    *v16 = 0;
    v17 = (_WORD *)*a6;
    a6[1] = *a6;
    *v17 = 0;
    *a7 = 0;
    if ( WinHttpGetDefaultProxyConfiguration((WINHTTP_PROXY_INFO *)&pProxyInfo.lpszProxy) )
    {
      lpszProxyBypass = pProxyInfo.lpszProxyBypass;
      if ( pProxyInfo.lpszProxyBypass )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
          lpszProxyBypass = pProxyInfo.lpszProxyBypass;
        }
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                a5,
                                lpszProxyBypass)
          && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                a6,
                                v34) )
        {
          v13 = 0;
          *a7 = pProxyInfo.lpszProxy;
          v14 = WPP_GLOBAL_Control;
LABEL_100:
          if ( a5 && a6 && v9 && v14 != (wchar_t *)&WPP_GLOBAL_Control && (v14[14] & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)v14 + 2),
              32,
              (unsigned int)WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
              *(_QWORD *)a5,
              *a6,
              *v9);
          goto LABEL_106;
        }
        v13 = -2147024882;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v20 = 23;
LABEL_40:
          WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, 2147942414LL);
          goto LABEL_106;
        }
        goto LABEL_106;
      }
    }
    if ( !WinHttpGetIEProxyConfigForCurrentUser(&v35) )
      goto LABEL_50;
    v21 = 0;
    if ( v35.fAutoDetect )
    {
      dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
      v21 = 1;
    }
    else
    {
      dwFlags = pAutoProxyOptions.dwFlags;
    }
    if ( v35.lpszAutoConfigUrl )
    {
      pAutoProxyOptions.lpszAutoConfigUrl = v35.lpszAutoConfigUrl;
      pAutoProxyOptions.dwFlags = dwFlags | 2;
      v21 = 1;
    }
    if ( !v35.fAutoDetect && !v35.lpszAutoConfigUrl && !v35.lpszProxy )
    {
LABEL_50:
      v21 = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
    }
    pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    if ( !v21 )
      goto LABEL_77;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpcwszUrl);
    v23 = L"s";
    if ( !a4 )
      v23 = (const wchar_t *)&Src;
    v24 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            lpcwszUrl,
            L"http%ls://%ls/%ls",
            v23,
            a2,
            a3);
    v13 = v24;
    if ( v24 < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_72;
      v26 = 24;
      v27 = (unsigned int)v24;
LABEL_71:
      WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v27);
LABEL_72:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpcwszUrl);
      goto LABEL_106;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
    GetTickCount();
    ProxyForUrl = WinHttpGetProxyForUrl(
                    *(HINTERNET *)a1,
                    lpcwszUrl[0],
                    &pAutoProxyOptions,
                    (WINHTTP_PROXY_INFO *)&pProxyInfo.lpszProxy);
    GetTickCount();
    if ( ProxyForUrl )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a5,
                               pProxyInfo.lpszProxyBypass)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a6,
                               v34) )
      {
        v13 = -2147024882;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_72;
        v26 = 27;
        v27 = 2147942414LL;
        goto LABEL_71;
      }
      *a7 = pProxyInfo.lpszProxy;
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      v30 = ERROR_HR_FROM_WIN32(LastError);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v30);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpcwszUrl);
    if ( ProxyForUrl )
    {
      v13 = 0;
    }
    else
    {
LABEL_77:
      v13 = 0;
      if ( v35.lpszProxy )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
          v14 = WPP_GLOBAL_Control;
        }
        if ( *v35.lpszProxy && (*v35.lpszProxy != 58 || v35.lpszProxy[1]) )
        {
          lpszProxy = v35.lpszProxy;
          *a7 = 3;
          if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                   a5,
                                   lpszProxy) )
          {
            v13 = -2147024882;
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v20 = 30;
              goto LABEL_40;
            }
LABEL_106:
            if ( v40 && !RevertToSelf() )
            {
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v32 = GetLastError();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v32);
              }
              __fastfail(7u);
            }
            goto LABEL_17;
          }
          v14 = WPP_GLOBAL_Control;
        }
        if ( !v35.lpszProxyBypass || !*v35.lpszProxyBypass || *v35.lpszProxyBypass == 58 && !v35.lpszProxyBypass[1] )
        {
LABEL_99:
          v9 = a7;
          goto LABEL_100;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a6,
                                 v35.lpszProxyBypass) )
        {
          v13 = -2147024882;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v20 = 31;
            goto LABEL_40;
          }
          goto LABEL_106;
        }
      }
    }
    v14 = WPP_GLOBAL_Control;
    goto LABEL_99;
  }
  v11 = GetLastError();
  v12 = ERROR_HR_FROM_WIN32(v11);
  v13 = v12;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v12);
    v14 = WPP_GLOBAL_Control;
  }
  v40 = 0;
  if ( v13 >= 0 )
    goto LABEL_100;
LABEL_17:
  if ( pProxyInfo.lpszProxyBypass )
    GlobalFree(pProxyInfo.lpszProxyBypass);
  if ( v34 )
    GlobalFree(v34);
  if ( v35.lpszAutoConfigUrl )
    GlobalFree(v35.lpszAutoConfigUrl);
  if ( v35.lpszProxy )
    GlobalFree(v35.lpszProxy);
  if ( v35.lpszProxyBypass )
    GlobalFree(v35.lpszProxyBypass);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18009a7bc  mov     rax, rsp
0x18009a7bf  mov     [rax+20h], r9d
0x18009a7c3  mov     [rax+10h], rdx
0x18009a7c7  mov     [rax+8], rcx
0x18009a7cb  push    rbp
0x18009a7cc  push    rbx
0x18009a7cd  push    rsi
0x18009a7ce  push    rdi
0x18009a7cf  push    r12
0x18009a7d1  push    r13
0x18009a7d3  push    r14
0x18009a7d5  push    r15
0x18009a7d7  lea     rbp, [rax-47h]
0x18009a7db  sub     rsp, 0B8h
0x18009a7e2  xorps   xmm0, xmm0
0x18009a7e5  xor     esi, esi
0x18009a7e7  xorps   xmm1, xmm1
0x18009a7ea  mov     [rbp+3Fh+arg_10], esi
0x18009a7ed  mov     rdi, rcx
0x18009a7f0  mov     rbx, r8
0x18009a7f3  xor     ecx, ecx
0x18009a7f5  mov     [rbp+3Fh+var_B0], rcx
0x18009a7f9  movups  xmmword ptr [rsp+0F0h+pProxyInfo.lpszProxy], xmm0
0x18009a7fe  movups  xmmword ptr [rbp+3Fh+pAutoProxyOptions.dwFlags], xmm1
0x18009a802  movups  xmmword ptr [rbp+3Fh+pAutoProxyOptions.lpvReserved], xmm1
0x18009a806  movups  xmmword ptr [rbp+3Fh+var_A8], xmm0
0x18009a80a  movups  xmmword ptr [rbp+3Fh+var_98], xmm0
0x18009a80e  test    rdx, rdx
0x18009a811  jnz     short loc_18009A818
0x18009a813  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a818  test    rbx, rbx
0x18009a81b  jnz     short loc_18009A822
0x18009a81d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a822  mov     r13, [rbp+3Fh+arg_20]
0x18009a826  test    r13, r13
0x18009a829  jnz     short loc_18009A830
0x18009a82b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a830  mov     r12, [rbp+3Fh+arg_28]
0x18009a834  test    r12, r12
0x18009a837  jnz     short loc_18009A83E
0x18009a839  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a83e  mov     r15, [rbp+3Fh+arg_30]
0x18009a842  test    r15, r15
0x18009a845  jnz     short loc_18009A84C
0x18009a847  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a84c  mov     rcx, [rdi+0E0h]; hToken
0x18009a853  mov     edi, 1
0x18009a858  test    rcx, rcx
0x18009a85b  jz      loc_18009A92E
0x18009a861  call    cs:__imp_ImpersonateLoggedOnUser
0x18009a867  test    eax, eax
0x18009a869  jnz     loc_18009A92B
0x18009a86f  call    cs:__imp_GetLastError
0x18009a875  mov     ecx, eax; unsigned int
0x18009a877  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009a87c  mov     ebx, eax
0x18009a87e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a885  lea     rsi, WPP_GLOBAL_Control
0x18009a88c  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009a893  cmp     rcx, rsi
0x18009a896  jz      short loc_18009A8B7
0x18009a898  test    [rcx+1Ch], dil
0x18009a89c  jz      short loc_18009A8B7
0x18009a89e  mov     rcx, [rcx+10h]
0x18009a8a2  lea     edx, [rdi+14h]
0x18009a8a5  mov     r9d, eax
0x18009a8a8  mov     r8, r14
0x18009a8ab  call    WPP_SF_d
0x18009a8b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a8b7  xor     edx, edx
0x18009a8b9  mov     [rbp+3Fh+arg_10], edx
0x18009a8bc  test    ebx, ebx
0x18009a8be  jns     loc_18009ACFF
0x18009a8c4  mov     rcx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]; hMem
0x18009a8c8  test    rcx, rcx
0x18009a8cb  jz      short loc_18009A8D3
0x18009a8cd  call    cs:__imp_GlobalFree
0x18009a8d3  mov     rcx, [rbp+3Fh+var_B0]; hMem
0x18009a8d7  test    rcx, rcx
0x18009a8da  jz      short loc_18009A8E2
0x18009a8dc  call    cs:__imp_GlobalFree
0x18009a8e2  mov     rcx, [rbp+3Fh+var_A8+8]; hMem
0x18009a8e6  test    rcx, rcx
0x18009a8e9  jz      short loc_18009A8F1
0x18009a8eb  call    cs:__imp_GlobalFree
0x18009a8f1  mov     rax, [rbp+3Fh+var_98]
0x18009a8f5  test    rax, rax
0x18009a8f8  jz      short loc_18009A903
0x18009a8fa  mov     rcx, rax; hMem
0x18009a8fd  call    cs:__imp_GlobalFree
0x18009a903  mov     rax, [rbp+3Fh+var_98+8]
0x18009a907  test    rax, rax
0x18009a90a  jz      short loc_18009A915
0x18009a90c  mov     rcx, rax; hMem
0x18009a90f  call    cs:__imp_GlobalFree
0x18009a915  mov     eax, ebx
0x18009a917  add     rsp, 0B8h
0x18009a91e  pop     r15
0x18009a920  pop     r14
0x18009a922  pop     r13
0x18009a924  pop     r12
0x18009a926  pop     rdi
0x18009a927  pop     rsi
0x18009a928  pop     rbx
0x18009a929  pop     rbp
0x18009a92a  retn
0x18009a92b  mov     [rbp+3Fh+arg_10], edi
0x18009a92e  mov     rcx, [r13+0]
0x18009a932  mov     [r13+8], rcx
0x18009a936  mov     [rcx], si
0x18009a939  mov     rcx, [r12]
0x18009a93d  mov     [r12+8], rcx
0x18009a942  mov     [rcx], si
0x18009a945  lea     rcx, [rsp+0F0h+pProxyInfo.lpszProxy]; pProxyInfo
0x18009a94a  mov     [r15], esi
0x18009a94d  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18009a953  test    eax, eax
0x18009a955  jz      loc_18009AA0B
0x18009a95b  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009a95f  test    rdx, rdx
0x18009a962  jz      loc_18009AA0B
0x18009a968  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a96f  lea     rsi, WPP_GLOBAL_Control
0x18009a976  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009a97d  cmp     rcx, rsi
0x18009a980  jz      short loc_18009A99D
0x18009a982  test    byte ptr [rcx+1Ch], 4
0x18009a986  jz      short loc_18009A99D
0x18009a988  mov     rcx, [rcx+10h]
0x18009a98c  mov     edx, 16h
0x18009a991  mov     r8, r14
0x18009a994  call    WPP_SF_
0x18009a999  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009a99d  mov     rcx, r13
0x18009a9a0  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009a9a5  test    al, al
0x18009a9a7  jz      short loc_18009A9D0
0x18009a9a9  mov     rdx, [rbp+3Fh+var_B0]
0x18009a9ad  mov     rcx, r12
0x18009a9b0  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009a9b5  xor     edx, edx
0x18009a9b7  test    al, al
0x18009a9b9  jz      short loc_18009A9D0
0x18009a9bb  mov     eax, dword ptr [rsp+0F0h+pProxyInfo.lpszProxy]
0x18009a9bf  mov     ebx, edx
0x18009a9c1  mov     [r15], eax
0x18009a9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a9cb  jmp     loc_18009ACFF
0x18009a9d0  mov     ebx, 8007000Eh
0x18009a9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a9dc  cmp     rcx, rsi
0x18009a9df  jz      loc_18009AD3E
0x18009a9e5  test    [rcx+1Ch], dil
0x18009a9e9  jz      loc_18009AD3E
0x18009a9ef  mov     edx, 17h
0x18009a9f4  mov     rcx, [rcx+10h]
0x18009a9f8  mov     r9d, 8007000Eh
0x18009a9fe  mov     r8, r14
0x18009aa01  call    WPP_SF_d
0x18009aa06  jmp     loc_18009AD3E
0x18009aa0b  lea     rcx, [rbp+3Fh+var_A8]; pProxyConfig
0x18009aa0f  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18009aa15  mov     r15d, 3
0x18009aa1b  test    eax, eax
0x18009aa1d  jz      short loc_18009AA60
0x18009aa1f  mov     r8d, dword ptr [rbp+3Fh+var_A8]
0x18009aa23  mov     edx, esi
0x18009aa25  test    r8d, r8d
0x18009aa28  jz      short loc_18009AA37
0x18009aa2a  mov     eax, edi
0x18009aa2c  mov     [rbp+3Fh+pAutoProxyOptions.dwAutoDetectFlags], r15d
0x18009aa30  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], eax
0x18009aa33  mov     edx, edi
0x18009aa35  jmp     short loc_18009AA3A
0x18009aa37  mov     eax, [rbp+3Fh+pAutoProxyOptions.dwFlags]
0x18009aa3a  mov     rcx, [rbp+3Fh+var_A8+8]
0x18009aa3e  test    rcx, rcx
0x18009aa41  jz      short loc_18009AA4F
0x18009aa43  or      eax, 2
0x18009aa46  mov     [rbp+3Fh+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x18009aa4a  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], eax
0x18009aa4d  mov     edx, edi
0x18009aa4f  test    r8d, r8d
0x18009aa52  jnz     short loc_18009AA69
0x18009aa54  cmp     [rbp+3Fh+var_A8+8], rsi
0x18009aa58  jnz     short loc_18009AA69
0x18009aa5a  cmp     [rbp+3Fh+var_98], rsi
0x18009aa5e  jnz     short loc_18009AA69
0x18009aa60  mov     edx, edi
0x18009aa62  mov     [rbp+3Fh+pAutoProxyOptions.dwAutoDetectFlags], r15d
0x18009aa66  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], edi
0x18009aa69  mov     [rbp+3Fh+pAutoProxyOptions.fAutoLogonIfChallenged], edi
0x18009aa6c  lea     rsi, WPP_GLOBAL_Control
0x18009aa73  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009aa7a  test    edx, edx
0x18009aa7c  jz      loc_18009AC17
0x18009aa82  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009aa86  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009aa8b  cmp     [rbp+3Fh+arg_18], 0
0x18009aa8f  lea     rax, Src
0x18009aa96  mov     r9, [rbp+3Fh+arg_8]
0x18009aa9a  lea     r8, aS_1; "s"
0x18009aaa1  cmovz   r8, rax
0x18009aaa5  mov     qword ptr [rsp+0F0h+var_D0], rbx
0x18009aaaa  lea     rdx, aHttpLsLsLs; "http%ls://%ls/%ls"
0x18009aab1  lea     rcx, [rbp+3Fh+lpcwszUrl]
0x18009aab5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18009aaba  mov     ebx, eax
0x18009aabc  test    eax, eax
0x18009aabe  jns     short loc_18009AAEE
0x18009aac0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009aac7  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009aace  cmp     rcx, rsi
0x18009aad1  jz      loc_18009ABBE
0x18009aad7  test    [rcx+1Ch], dil
0x18009aadb  jz      loc_18009ABBE
0x18009aae1  mov     edx, 18h
0x18009aae6  mov     r9d, eax
0x18009aae9  jmp     loc_18009ABB2
0x18009aaee  mov     rcx, cs:WPP_GLOBAL_Control
0x18009aaf5  cmp     rcx, rsi
0x18009aaf8  jz      short loc_18009AB11
0x18009aafa  test    byte ptr [rcx+1Ch], 4
0x18009aafe  jz      short loc_18009AB11
0x18009ab00  mov     rcx, [rcx+10h]
0x18009ab04  mov     edx, 19h
0x18009ab09  mov     r8, r14
0x18009ab0c  call    WPP_SF_
0x18009ab11  call    cs:__imp_GetTickCount
0x18009ab17  mov     rcx, [rbp+3Fh+arg_0]
0x18009ab1b  lea     r9, [rsp+0F0h+pProxyInfo.lpszProxy]; pProxyInfo
0x18009ab20  mov     rdx, [rbp+3Fh+lpcwszUrl]; lpcwszUrl
0x18009ab24  lea     r8, [rbp+3Fh+pAutoProxyOptions]; pAutoProxyOptions
0x18009ab28  mov     rcx, [rcx]; hSession
0x18009ab2b  call    cs:__imp_WinHttpGetProxyForUrl
0x18009ab31  mov     ebx, eax
0x18009ab33  call    cs:__imp_GetTickCount
0x18009ab39  test    ebx, ebx
0x18009ab3b  jz      loc_18009ABCC
0x18009ab41  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ab48  cmp     rcx, rsi
0x18009ab4b  jz      short loc_18009AB64
0x18009ab4d  test    byte ptr [rcx+1Ch], 4
0x18009ab51  jz      short loc_18009AB64
0x18009ab53  mov     rcx, [rcx+10h]
0x18009ab57  mov     edx, 1Ah
0x18009ab5c  mov     r8, r14
0x18009ab5f  call    WPP_SF_
0x18009ab64  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009ab68  mov     rcx, r13
0x18009ab6b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009ab70  test    al, al
0x18009ab72  jz      short loc_18009AB90
0x18009ab74  mov     rdx, [rbp+3Fh+var_B0]
0x18009ab78  mov     rcx, r12
0x18009ab7b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009ab80  test    al, al
0x18009ab82  jz      short loc_18009AB90
0x18009ab84  mov     rcx, [rbp+3Fh+arg_30]
0x18009ab88  mov     eax, dword ptr [rsp+0F0h+pProxyInfo.lpszProxy]
0x18009ab8c  mov     [rcx], eax
0x18009ab8e  jmp     short loc_18009AC06
0x18009ab90  mov     ebx, 8007000Eh
0x18009ab95  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ab9c  cmp     rcx, rsi
0x18009ab9f  jz      short loc_18009ABBE
0x18009aba1  test    [rcx+1Ch], dil
0x18009aba5  jz      short loc_18009ABBE
0x18009aba7  mov     edx, 1Bh
0x18009abac  mov     r9d, 8007000Eh
0x18009abb2  mov     rcx, [rcx+10h]
0x18009abb6  mov     r8, r14
0x18009abb9  call    WPP_SF_d
0x18009abbe  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009abc2  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009abc7  jmp     loc_18009AD3E
0x18009abcc  mov     rax, cs:WPP_GLOBAL_Control
0x18009abd3  cmp     rax, rsi
0x18009abd6  jz      short loc_18009AC06
0x18009abd8  test    [rax+1Ch], dil
0x18009abdc  jz      short loc_18009AC06
0x18009abde  call    cs:__imp_GetLastError
0x18009abe4  mov     ecx, eax; unsigned int
0x18009abe6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009abeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009abf2  mov     edx, 1Ch
0x18009abf7  mov     r9d, eax
0x18009abfa  mov     r8, r14
0x18009abfd  mov     rcx, [rcx+10h]
0x18009ac01  call    WPP_SF_d
0x18009ac06  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009ac0a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009ac0f  test    ebx, ebx
0x18009ac11  jnz     loc_18009ACF2
0x18009ac17  xor     ebx, ebx
0x18009ac19  cmp     [rbp+3Fh+var_98], rbx
0x18009ac1d  jz      loc_18009ACF4
0x18009ac23  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ac2a  cmp     rcx, rsi
0x18009ac2d  jz      short loc_18009AC4B
  ... truncated ...
```
