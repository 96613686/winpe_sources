# CHttpRequest::DiscoverProxyInfoForUrl(wchar_t const *,wchar_t const *,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ulong *)

- ea: `0x18009ef74`
- end: `0x18009f5a5`
- name: `?DiscoverProxyInfoForUrl@CHttpRequest@@IEAAJPEB_W0HPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1PEAK@Z`
- size: `1585`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009f5ac`

## callees

- `0x180004c64`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x18001c368`
- `0x180020680`
- `0x18003de9c`
- `0x180068e08`
- `0x18009ef74`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009f300`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009f32e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009f300`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009f32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f02d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f02d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f578`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009f552`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009f552`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009f019`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009f019`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f091`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0a6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0bb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f091`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0a6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0bb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009f0eb`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18009f1f8`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18009f1f8`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009f320`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009f320`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18009f130`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18009f130`

## pseudocode

```c
__int64 __fastcall CHttpRequest::DiscoverProxyInfoForUrl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _QWORD *a5,
        __int64 *a6,
        _DWORD *a7)
{
  __int64 v9; // rcx
  _DWORD *v10; // r15
  void *v11; // rcx
  DWORD v12; // eax
  unsigned int v13; // eax
  int v14; // ebx
  wchar_t *v15; // rcx
  _WORD *v17; // rcx
  _WORD *v18; // rcx
  LPWSTR lpszProxyBypass; // rdx
  wchar_t *v20; // rcx
  __int64 v21; // rdx
  int v22; // edx
  DWORD dwFlags; // eax
  const wchar_t *v24; // r8
  int v25; // eax
  wchar_t *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  BOOL ProxyForUrl; // ebx
  DWORD LastError; // eax
  unsigned int v31; // eax
  LPWSTR lpszProxy; // rdx
  DWORD v33; // eax
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+30h] [rbp-89h] BYREF
  HGLOBAL v35; // [rsp+48h] [rbp-71h]
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG v36; // [rsp+50h] [rbp-69h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+70h] [rbp-49h] BYREF
  LPCWSTR lpcwszUrl[13]; // [rsp+90h] [rbp-29h] BYREF
  int v41; // [rsp+118h] [rbp+5Fh]

  v41 = 0;
  v9 = 0;
  v35 = 0;
  *(_OWORD *)&pProxyInfo.lpszProxy = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&v36, 0, sizeof(v36));
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, 0, a3);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  v10 = a7;
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  v11 = *(void **)(a1 + 224);
  if ( !v11 )
    goto LABEL_29;
  if ( ImpersonateLoggedOnUser(v11) )
  {
    v41 = 1;
LABEL_29:
    v17 = (_WORD *)*a5;
    a5[1] = *a5;
    *v17 = 0;
    v18 = (_WORD *)*a6;
    a6[1] = *a6;
    *v18 = 0;
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
                                v35) )
        {
          v14 = 0;
          *a7 = pProxyInfo.lpszProxy;
          v15 = WPP_GLOBAL_Control;
LABEL_100:
          if ( a5 && a6 && v10 && v15 != (wchar_t *)&WPP_GLOBAL_Control && (v15[14] & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)v15 + 2),
              32,
              (unsigned int)WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
              *a5,
              *a6,
              *v10);
          goto LABEL_106;
        }
        v14 = -2147024882;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v21 = 23;
LABEL_40:
          WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, 2147942414LL);
          goto LABEL_106;
        }
        goto LABEL_106;
      }
    }
    if ( !WinHttpGetIEProxyConfigForCurrentUser(&v36) )
      goto LABEL_50;
    v22 = 0;
    if ( v36.fAutoDetect )
    {
      dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
      v22 = 1;
    }
    else
    {
      dwFlags = pAutoProxyOptions.dwFlags;
    }
    if ( v36.lpszAutoConfigUrl )
    {
      pAutoProxyOptions.lpszAutoConfigUrl = v36.lpszAutoConfigUrl;
      pAutoProxyOptions.dwFlags = dwFlags | 2;
      v22 = 1;
    }
    if ( !v36.fAutoDetect && !v36.lpszAutoConfigUrl && !v36.lpszProxy )
    {
LABEL_50:
      v22 = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
    }
    pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    if ( !v22 )
      goto LABEL_77;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpcwszUrl);
    v24 = L"s";
    if ( !a4 )
      v24 = (const wchar_t *)&Src;
    v25 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            lpcwszUrl,
            L"http%ls://%ls/%ls",
            v24,
            a2,
            a3);
    v14 = v25;
    if ( v25 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_72;
      v27 = 24;
      v28 = (unsigned int)v25;
LABEL_71:
      WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v28);
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
                               v35) )
      {
        v14 = -2147024882;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_72;
        v27 = 27;
        v28 = 2147942414LL;
        goto LABEL_71;
      }
      *a7 = pProxyInfo.lpszProxy;
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      v31 = ERROR_HR_FROM_WIN32(LastError);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v31);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpcwszUrl);
    if ( ProxyForUrl )
    {
      v14 = 0;
    }
    else
    {
LABEL_77:
      v14 = 0;
      if ( v36.lpszProxy )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
          v15 = WPP_GLOBAL_Control;
        }
        if ( *v36.lpszProxy && (*v36.lpszProxy != 58 || v36.lpszProxy[1]) )
        {
          lpszProxy = v36.lpszProxy;
          *a7 = 3;
          if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                   a5,
                                   lpszProxy) )
          {
            v14 = -2147024882;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v21 = 30;
              goto LABEL_40;
            }
LABEL_106:
            if ( v41 && !RevertToSelf() )
            {
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v33 = GetLastError();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v33);
              }
              __fastfail(7u);
            }
            goto LABEL_17;
          }
          v15 = WPP_GLOBAL_Control;
        }
        if ( !v36.lpszProxyBypass || !*v36.lpszProxyBypass || *v36.lpszProxyBypass == 58 && !v36.lpszProxyBypass[1] )
        {
LABEL_99:
          v10 = a7;
          goto LABEL_100;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a6,
                                 v36.lpszProxyBypass) )
        {
          v14 = -2147024882;
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v21 = 31;
            goto LABEL_40;
          }
          goto LABEL_106;
        }
      }
    }
    v15 = WPP_GLOBAL_Control;
    goto LABEL_99;
  }
  v12 = GetLastError();
  v13 = ERROR_HR_FROM_WIN32(v12);
  v14 = v13;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v13);
    v15 = WPP_GLOBAL_Control;
  }
  v41 = 0;
  if ( v14 >= 0 )
    goto LABEL_100;
LABEL_17:
  if ( pProxyInfo.lpszProxyBypass )
    GlobalFree(pProxyInfo.lpszProxyBypass);
  if ( v35 )
    GlobalFree(v35);
  if ( v36.lpszAutoConfigUrl )
    GlobalFree(v36.lpszAutoConfigUrl);
  if ( v36.lpszProxy )
    GlobalFree(v36.lpszProxy);
  if ( v36.lpszProxyBypass )
    GlobalFree(v36.lpszProxyBypass);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18009ef74  mov     rax, rsp
0x18009ef77  mov     [rax+20h], r9d
0x18009ef7b  mov     [rax+10h], rdx
0x18009ef7f  mov     [rax+8], rcx
0x18009ef83  push    rbp
0x18009ef84  push    rbx
0x18009ef85  push    rsi
0x18009ef86  push    rdi
0x18009ef87  push    r12
0x18009ef89  push    r13
0x18009ef8b  push    r14
0x18009ef8d  push    r15
0x18009ef8f  lea     rbp, [rax-47h]
0x18009ef93  sub     rsp, 0B8h
0x18009ef9a  xorps   xmm0, xmm0
0x18009ef9d  xor     esi, esi
0x18009ef9f  xorps   xmm1, xmm1
0x18009efa2  mov     [rbp+3Fh+arg_10], esi
0x18009efa5  mov     rdi, rcx
0x18009efa8  mov     rbx, r8
0x18009efab  xor     ecx, ecx
0x18009efad  mov     [rbp+3Fh+var_B0], rcx
0x18009efb1  movups  xmmword ptr [rsp+0F0h+pProxyInfo.lpszProxy], xmm0
0x18009efb6  movups  xmmword ptr [rbp+3Fh+pAutoProxyOptions.dwFlags], xmm1
0x18009efba  movups  xmmword ptr [rbp+3Fh+pAutoProxyOptions.lpvReserved], xmm1
0x18009efbe  movups  xmmword ptr [rbp+3Fh+var_A8], xmm0
0x18009efc2  movups  xmmword ptr [rbp+3Fh+var_98], xmm0
0x18009efc6  test    rdx, rdx
0x18009efc9  jnz     short loc_18009EFD0
0x18009efcb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009efd0  test    rbx, rbx
0x18009efd3  jnz     short loc_18009EFDA
0x18009efd5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009efda  mov     r13, [rbp+3Fh+arg_20]
0x18009efde  test    r13, r13
0x18009efe1  jnz     short loc_18009EFE8
0x18009efe3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009efe8  mov     r12, [rbp+3Fh+arg_28]
0x18009efec  test    r12, r12
0x18009efef  jnz     short loc_18009EFF6
0x18009eff1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009eff6  mov     r15, [rbp+3Fh+arg_30]
0x18009effa  test    r15, r15
0x18009effd  jnz     short loc_18009F004
0x18009efff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009f004  mov     rcx, [rdi+0E0h]; hToken
0x18009f00b  mov     edi, 1
0x18009f010  test    rcx, rcx
0x18009f013  jz      loc_18009F111
0x18009f019  call    cs:__imp_ImpersonateLoggedOnUser
0x18009f020  nop     dword ptr [rax+rax+00h]
0x18009f025  test    eax, eax
0x18009f027  jnz     loc_18009F10E
0x18009f02d  call    cs:__imp_GetLastError
0x18009f034  nop     dword ptr [rax+rax+00h]
0x18009f039  mov     ecx, eax; unsigned int
0x18009f03b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009f040  mov     ebx, eax
0x18009f042  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f049  lea     rsi, WPP_GLOBAL_Control
0x18009f050  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009f057  cmp     rcx, rsi
0x18009f05a  jz      short loc_18009F07B
0x18009f05c  test    [rcx+1Ch], dil
0x18009f060  jz      short loc_18009F07B
0x18009f062  mov     rcx, [rcx+10h]
0x18009f066  lea     edx, [rdi+14h]
0x18009f069  mov     r9d, eax
0x18009f06c  mov     r8, r14
0x18009f06f  call    WPP_SF_d
0x18009f074  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f07b  xor     edx, edx
0x18009f07d  mov     [rbp+3Fh+arg_10], edx
0x18009f080  test    ebx, ebx
0x18009f082  jns     loc_18009F506
0x18009f088  mov     rcx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]; hMem
0x18009f08c  test    rcx, rcx
0x18009f08f  jz      short loc_18009F09D
0x18009f091  call    cs:__imp_GlobalFree
0x18009f098  nop     dword ptr [rax+rax+00h]
0x18009f09d  mov     rcx, [rbp+3Fh+var_B0]; hMem
0x18009f0a1  test    rcx, rcx
0x18009f0a4  jz      short loc_18009F0B2
0x18009f0a6  call    cs:__imp_GlobalFree
0x18009f0ad  nop     dword ptr [rax+rax+00h]
0x18009f0b2  mov     rcx, [rbp+3Fh+var_A8+8]; hMem
0x18009f0b6  test    rcx, rcx
0x18009f0b9  jz      short loc_18009F0C7
0x18009f0bb  call    cs:__imp_GlobalFree
0x18009f0c2  nop     dword ptr [rax+rax+00h]
0x18009f0c7  mov     rax, [rbp+3Fh+var_98]
0x18009f0cb  test    rax, rax
0x18009f0ce  jz      short loc_18009F0DF
0x18009f0d0  mov     rcx, rax; hMem
0x18009f0d3  call    cs:__imp_GlobalFree
0x18009f0da  nop     dword ptr [rax+rax+00h]
0x18009f0df  mov     rax, [rbp+3Fh+var_98+8]
0x18009f0e3  test    rax, rax
0x18009f0e6  jz      short loc_18009F0F7
0x18009f0e8  mov     rcx, rax; hMem
0x18009f0eb  call    cs:__imp_GlobalFree
0x18009f0f2  nop     dword ptr [rax+rax+00h]
0x18009f0f7  mov     eax, ebx
0x18009f0f9  add     rsp, 0B8h
0x18009f100  pop     r15
0x18009f102  pop     r14
0x18009f104  pop     r13
0x18009f106  pop     r12
0x18009f108  pop     rdi
0x18009f109  pop     rsi
0x18009f10a  pop     rbx
0x18009f10b  pop     rbp
0x18009f10c  retn
0x18009f10e  mov     [rbp+3Fh+arg_10], edi
0x18009f111  mov     rcx, [r13+0]
0x18009f115  mov     [r13+8], rcx
0x18009f119  mov     [rcx], si
0x18009f11c  mov     rcx, [r12]
0x18009f120  mov     [r12+8], rcx
0x18009f125  mov     [rcx], si
0x18009f128  lea     rcx, [rsp+0F0h+pProxyInfo.lpszProxy]; pProxyInfo
0x18009f12d  mov     [r15], esi
0x18009f130  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18009f137  nop     dword ptr [rax+rax+00h]
0x18009f13c  test    eax, eax
0x18009f13e  jz      loc_18009F1F4
0x18009f144  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009f148  test    rdx, rdx
0x18009f14b  jz      loc_18009F1F4
0x18009f151  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f158  lea     rsi, WPP_GLOBAL_Control
0x18009f15f  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009f166  cmp     rcx, rsi
0x18009f169  jz      short loc_18009F186
0x18009f16b  test    byte ptr [rcx+1Ch], 4
0x18009f16f  jz      short loc_18009F186
0x18009f171  mov     rcx, [rcx+10h]
0x18009f175  mov     edx, 16h
0x18009f17a  mov     r8, r14
0x18009f17d  call    WPP_SF_
0x18009f182  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009f186  mov     rcx, r13
0x18009f189  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009f18e  test    al, al
0x18009f190  jz      short loc_18009F1B9
0x18009f192  mov     rdx, [rbp+3Fh+var_B0]
0x18009f196  mov     rcx, r12
0x18009f199  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009f19e  xor     edx, edx
0x18009f1a0  test    al, al
0x18009f1a2  jz      short loc_18009F1B9
0x18009f1a4  mov     eax, dword ptr [rsp+0F0h+pProxyInfo.lpszProxy]
0x18009f1a8  mov     ebx, edx
0x18009f1aa  mov     [r15], eax
0x18009f1ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f1b4  jmp     loc_18009F506
0x18009f1b9  mov     ebx, 8007000Eh
0x18009f1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f1c5  cmp     rcx, rsi
0x18009f1c8  jz      loc_18009F545
0x18009f1ce  test    [rcx+1Ch], dil
0x18009f1d2  jz      loc_18009F545
0x18009f1d8  mov     edx, 17h
0x18009f1dd  mov     rcx, [rcx+10h]
0x18009f1e1  mov     r9d, 8007000Eh
0x18009f1e7  mov     r8, r14
0x18009f1ea  call    WPP_SF_d
0x18009f1ef  jmp     loc_18009F545
0x18009f1f4  lea     rcx, [rbp+3Fh+var_A8]; pProxyConfig
0x18009f1f8  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18009f1ff  nop     dword ptr [rax+rax+00h]
0x18009f204  mov     r15d, 3
0x18009f20a  test    eax, eax
0x18009f20c  jz      short loc_18009F24F
0x18009f20e  mov     r8d, dword ptr [rbp+3Fh+var_A8]
0x18009f212  mov     edx, esi
0x18009f214  test    r8d, r8d
0x18009f217  jz      short loc_18009F226
0x18009f219  mov     eax, edi
0x18009f21b  mov     [rbp+3Fh+pAutoProxyOptions.dwAutoDetectFlags], r15d
0x18009f21f  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], eax
0x18009f222  mov     edx, edi
0x18009f224  jmp     short loc_18009F229
0x18009f226  mov     eax, [rbp+3Fh+pAutoProxyOptions.dwFlags]
0x18009f229  mov     rcx, [rbp+3Fh+var_A8+8]
0x18009f22d  test    rcx, rcx
0x18009f230  jz      short loc_18009F23E
0x18009f232  or      eax, 2
0x18009f235  mov     [rbp+3Fh+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x18009f239  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], eax
0x18009f23c  mov     edx, edi
0x18009f23e  test    r8d, r8d
0x18009f241  jnz     short loc_18009F258
0x18009f243  cmp     [rbp+3Fh+var_A8+8], rsi
0x18009f247  jnz     short loc_18009F258
0x18009f249  cmp     [rbp+3Fh+var_98], rsi
0x18009f24d  jnz     short loc_18009F258
0x18009f24f  mov     edx, edi
0x18009f251  mov     [rbp+3Fh+pAutoProxyOptions.dwAutoDetectFlags], r15d
0x18009f255  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], edi
0x18009f258  mov     [rbp+3Fh+pAutoProxyOptions.fAutoLogonIfChallenged], edi
0x18009f25b  lea     rsi, WPP_GLOBAL_Control
0x18009f262  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009f269  test    edx, edx
0x18009f26b  jz      loc_18009F41E
0x18009f271  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009f275  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009f27a  cmp     [rbp+3Fh+arg_18], 0
0x18009f27e  lea     rax, Src
0x18009f285  mov     r9, [rbp+3Fh+arg_8]
0x18009f289  lea     r8, aS_1; "s"
0x18009f290  cmovz   r8, rax
0x18009f294  mov     qword ptr [rsp+0F0h+var_D0], rbx
0x18009f299  lea     rdx, aHttpLsLsLs; "http%ls://%ls/%ls"
0x18009f2a0  lea     rcx, [rbp+3Fh+lpcwszUrl]
0x18009f2a4  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18009f2a9  mov     ebx, eax
0x18009f2ab  test    eax, eax
0x18009f2ad  jns     short loc_18009F2DD
0x18009f2af  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f2b6  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009f2bd  cmp     rcx, rsi
0x18009f2c0  jz      loc_18009F3BF
0x18009f2c6  test    [rcx+1Ch], dil
0x18009f2ca  jz      loc_18009F3BF
0x18009f2d0  mov     edx, 18h
0x18009f2d5  mov     r9d, eax
0x18009f2d8  jmp     loc_18009F3B3
0x18009f2dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f2e4  cmp     rcx, rsi
0x18009f2e7  jz      short loc_18009F300
0x18009f2e9  test    byte ptr [rcx+1Ch], 4
0x18009f2ed  jz      short loc_18009F300
0x18009f2ef  mov     rcx, [rcx+10h]
0x18009f2f3  mov     edx, 19h
0x18009f2f8  mov     r8, r14
0x18009f2fb  call    WPP_SF_
0x18009f300  call    cs:__imp_GetTickCount
0x18009f307  nop     dword ptr [rax+rax+00h]
0x18009f30c  mov     rcx, [rbp+3Fh+arg_0]
0x18009f310  lea     r9, [rsp+0F0h+pProxyInfo.lpszProxy]; pProxyInfo
0x18009f315  mov     rdx, [rbp+3Fh+lpcwszUrl]; lpcwszUrl
0x18009f319  lea     r8, [rbp+3Fh+pAutoProxyOptions]; pAutoProxyOptions
0x18009f31d  mov     rcx, [rcx]; hSession
0x18009f320  call    cs:__imp_WinHttpGetProxyForUrl
0x18009f327  nop     dword ptr [rax+rax+00h]
0x18009f32c  mov     ebx, eax
0x18009f32e  call    cs:__imp_GetTickCount
0x18009f335  nop     dword ptr [rax+rax+00h]
0x18009f33a  test    ebx, ebx
0x18009f33c  jz      loc_18009F3CD
0x18009f342  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f349  cmp     rcx, rsi
0x18009f34c  jz      short loc_18009F365
0x18009f34e  test    byte ptr [rcx+1Ch], 4
0x18009f352  jz      short loc_18009F365
0x18009f354  mov     rcx, [rcx+10h]
0x18009f358  mov     edx, 1Ah
0x18009f35d  mov     r8, r14
0x18009f360  call    WPP_SF_
0x18009f365  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009f369  mov     rcx, r13
0x18009f36c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009f371  test    al, al
0x18009f373  jz      short loc_18009F391
0x18009f375  mov     rdx, [rbp+3Fh+var_B0]
0x18009f379  mov     rcx, r12
0x18009f37c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009f381  test    al, al
0x18009f383  jz      short loc_18009F391
0x18009f385  mov     rcx, [rbp+3Fh+arg_30]
0x18009f389  mov     eax, dword ptr [rsp+0F0h+pProxyInfo.lpszProxy]
0x18009f38d  mov     [rcx], eax
0x18009f38f  jmp     short loc_18009F40D
0x18009f391  mov     ebx, 8007000Eh
0x18009f396  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f39d  cmp     rcx, rsi
0x18009f3a0  jz      short loc_18009F3BF
0x18009f3a2  test    [rcx+1Ch], dil
0x18009f3a6  jz      short loc_18009F3BF
0x18009f3a8  mov     edx, 1Bh
0x18009f3ad  mov     r9d, 8007000Eh
0x18009f3b3  mov     rcx, [rcx+10h]
0x18009f3b7  mov     r8, r14
0x18009f3ba  call    WPP_SF_d
0x18009f3bf  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009f3c3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009f3c8  jmp     loc_18009F545
0x18009f3cd  mov     rax, cs:WPP_GLOBAL_Control
0x18009f3d4  cmp     rax, rsi
0x18009f3d7  jz      short loc_18009F40D
0x18009f3d9  test    [rax+1Ch], dil
0x18009f3dd  jz      short loc_18009F40D
0x18009f3df  call    cs:__imp_GetLastError
0x18009f3e6  nop     dword ptr [rax+rax+00h]
0x18009f3eb  mov     ecx, eax; unsigned int
0x18009f3ed  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009f3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f3f9  mov     edx, 1Ch
0x18009f3fe  mov     r9d, eax
  ... truncated ...
```
