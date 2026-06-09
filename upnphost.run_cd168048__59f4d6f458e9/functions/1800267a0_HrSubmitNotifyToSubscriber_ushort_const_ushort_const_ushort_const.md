# HrSubmitNotifyToSubscriber(ushort const *,ushort const *,ushort const *)

- ea: `0x1800267a0`
- end: `0x180026f0c`
- name: `?HrSubmitNotifyToSubscriber@@YAJPEBG00@Z`
- size: `1900`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180027700`

## callees

- `0x1800074dc`
- `0x1800200f4`
- `0x1800209c8`
- `0x1800267a0`
- `0x180026f14`
- `0x18003b904`
- `0x18003c018`
- `0x18003cb60`
- `0x180049258`
- `0x1800492d8`
- `0x180057c40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026b3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026b3a`
- `WINHTTP!WinHttpReceiveResponse` at `0x180026a10`
- `WINHTTP!WinHttpReceiveResponse` at `0x180026a10`
- `WINHTTP!WinHttpCrackUrl` at `0x180026832`
- `WINHTTP!WinHttpCrackUrl` at `0x180026832`
- `WINHTTP!WinHttpSendRequest` at `0x180026993`
- `WINHTTP!WinHttpSendRequest` at `0x180026993`
- `WINHTTP!WinHttpOpenRequest` at `0x1800268e9`
- `WINHTTP!WinHttpOpenRequest` at `0x1800268e9`
- `WINHTTP!WinHttpSetOption` at `0x180026929`
- `WINHTTP!WinHttpSetOption` at `0x180026929`
- `WINHTTP!WinHttpCloseHandle` at `0x180026b49`
- `WINHTTP!WinHttpCloseHandle` at `0x180026b58`
- `WINHTTP!WinHttpCloseHandle` at `0x180026b49`
- `WINHTTP!WinHttpCloseHandle` at `0x180026b58`
- `WINHTTP!WinHttpConnect` at `0x180026870`
- `WINHTTP!WinHttpConnect` at `0x180026870`

## string_xrefs

- `0x180026dd7`: `HrSubmitNotifyToSubscriber: HttpOpenRequest`

## pseudocode

```c
__int64 __fastcall HrSubmitNotifyToSubscriber(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void *v5; // r15
  void *v6; // rax
  void *v7; // r14
  STRSAFE_PCNZWCH v8; // rcx
  char *v9; // rax
  char *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rcx
  STRSAFE_PCNZWCH v13; // rcx
  unsigned int v14; // edi
  unsigned int v15; // eax
  STRSAFE_PCNZWCH v16; // rcx
  __int64 result; // rax
  char v18; // al
  unsigned int v19; // eax
  unsigned int Win32Error; // eax
  int Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pswzServerName[256]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pwszObjectName[2088]; // [rsp+2C0h] [rbp+1C0h] BYREF

  UrlComponents.lpszHostName = (LPSTR)pswzServerName;
  UrlComponents.lpszUrlPath = (LPSTR)pwszObjectName;
  memset(&UrlComponents, 0, 24);
  UrlComponents.dwStructSize = 104;
  memset(&UrlComponents.dwHostNameLength, 0, 40);
  UrlComponents.dwHostNameLength = 256;
  memset(&UrlComponents.dwUrlPathLength, 0, 24);
  UrlComponents.dwUrlPathLength = 2084;
  if ( !WinHttpCrackUrl(a3, 0, 0, &UrlComponents) )
  {
    result = HrFromLastWin32Error();
    v14 = result;
    if ( !(_DWORD)result )
      return result;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return v14;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_89;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      125,
      (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
      (unsigned int)"HrSubmitNotifyToSubscriber: WinHttpCrackUrl",
      result);
LABEL_88:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_89;
  }
  if ( !g_hInetSess || g_fEventApiShutDown )
  {
    v14 = -2147418113;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return v14;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
    {
LABEL_89:
      if ( v16 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v16[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)v16 + 2),
          126,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (unsigned int)"HrSubmitNotifyToSubscriber",
          v14);
      return v14;
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      124,
      (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
      (unsigned int)"HrSubmitNotifyToSubscriber: No internet session!",
      255);
    goto LABEL_88;
  }
  v5 = WinHttpConnect(g_hInetSess, pswzServerName, UrlComponents.nPort, 0);
  if ( v5 && !g_fEventApiShutDown )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)pswzServerName,
        UrlComponents.nPort);
    }
    v6 = WinHttpOpenRequest(v5, L"NOTIFY", pwszObjectName, L"HTTP/1.1", 0, 0, 0x100u);
    v7 = v6;
    if ( !v6 || g_fEventApiShutDown )
    {
      Win32Error = HrFromLastWin32Error();
      v14 = Win32Error;
      if ( Win32Error && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          122,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (unsigned int)"HrSubmitNotifyToSubscriber: HttpOpenRequest",
          Win32Error);
      goto LABEL_49;
    }
    Buffer[0] = 8;
    if ( !WinHttpSetOption(v6, 0x3Fu, Buffer, 4u) && (unsigned int)HrFromLastWin32Error() )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        goto LABEL_12;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_11:
        if ( v8 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v8 + 7) & 0x800) != 0 )
          {
            WPP_SF_S(*((_QWORD *)v8 + 2), 110, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, pwszObjectName);
            v8 = WPP_GLOBAL_Control;
          }
          if ( v8 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v8 + 7) & 0x800) != 0 )
            {
              WPP_SF_(*((_QWORD *)v8 + 2), 111, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
              v8 = WPP_GLOBAL_Control;
            }
            if ( v8 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)v8 + 7) & 0x800) != 0 )
              {
                WPP_SF_SS(
                  *((_QWORD *)v8 + 2),
                  112,
                  (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
                  (_DWORD)a1,
                  (__int64)a2);
                v8 = WPP_GLOBAL_Control;
              }
              if ( v8 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 )
                WPP_SF_(*((_QWORD *)v8 + 2), 113, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
            }
          }
        }
LABEL_12:
        v9 = Utf8FromWsz(a2);
        v10 = v9;
        if ( !v9 )
        {
          v14 = -2147024882;
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              121,
              (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
              (unsigned int)"HrSubmitNotifyToSubscriber: SzFromWsz",
              14);
          goto LABEL_48;
        }
        LODWORD(v11) = 0;
        v12 = -1;
        if ( a1 )
        {
          v11 = -1;
          do
            ++v11;
          while ( a1[v11] );
        }
        do
          ++v12;
        while ( v9[v12] );
        if ( WinHttpSendRequest(v7, a1, v11, v9, v12, v12, 0) )
        {
          v13 = WPP_GLOBAL_Control;
          v14 = 0;
          if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
          {
LABEL_20:
            if ( !g_fEventApiShutDown )
            {
              if ( v13 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x800) != 0 )
                WPP_SF_(*((_QWORD *)v13 + 2), 117, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
              if ( WinHttpReceiveResponse(v7, 0) )
              {
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  WPP_SF_SdS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    118,
                    (unsigned int)pwszObjectName,
                    (unsigned int)pswzServerName,
                    UrlComponents.nPort,
                    (__int64)pwszObjectName);
                v15 = HrFromLastWin32Error();
                v14 = v15;
                if ( v15
                  && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    119,
                    (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
                    (unsigned int)"HrSubmitNotifyToSubscriber: HttpReceiveResponse",
                    v15);
                }
              }
            }
LABEL_47:
            free(v10);
LABEL_48:
            WinHttpCloseHandle(v7);
LABEL_49:
            WinHttpCloseHandle(v5);
            goto LABEL_50;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_SdS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              114,
              (unsigned int)pwszObjectName,
              (unsigned int)pswzServerName,
              UrlComponents.nPort,
              (__int64)pwszObjectName);
          v19 = HrFromLastWin32Error();
          v14 = v19;
          if ( v19 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                115,
                (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
                (unsigned int)"HrSubmitNotifyToSubscriber: HttpSendRequest",
                v19);
              v13 = WPP_GLOBAL_Control;
            }
            if ( (v14 & 0x80000000) != 0 )
              goto LABEL_47;
            goto LABEL_20;
          }
        }
        v13 = WPP_GLOBAL_Control;
        goto LABEL_20;
      }
      v18 = HrFromLastWin32Error();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrSubmitNotifyToSubscriber: HttpSetOption",
        v18);
    }
    v8 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  result = HrFromLastWin32Error();
  v14 = result;
  if ( (_DWORD)result )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    {
LABEL_51:
      if ( !v14 )
        return v14;
      goto LABEL_89;
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      123,
      (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
      (unsigned int)"HrSubmitNotifyToSubscriber: InternetConnect",
      result);
LABEL_50:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_51;
  }
  return result;
}

```

## disassembly

```asm
0x1800267a0  push    rbp
0x1800267a2  push    rbx
0x1800267a3  push    rsi
0x1800267a4  push    rdi
0x1800267a5  push    r15
0x1800267a7  lea     rbp, [rsp-1230h]
0x1800267af  mov     eax, 1330h
0x1800267b4  call    _alloca_probe
0x1800267b9  sub     rsp, rax
0x1800267bc  mov     rax, cs:__security_cookie
0x1800267c3  xor     rax, rsp
0x1800267c6  mov     [rbp+1250h+var_40], rax
0x1800267cd  xorps   xmm0, xmm0
0x1800267d0  lea     r9, [rsp+1350h+UrlComponents]; lpUrlComponents
0x1800267d5  mov     rdi, rcx
0x1800267d8  mov     rax, r8
0x1800267db  xor     ecx, ecx
0x1800267dd  mov     rbx, rdx
0x1800267e0  mov     qword ptr [rbp+1250h+UrlComponents.dwExtraInfoLength], rcx
0x1800267e4  xor     r8d, r8d; dwFlags
0x1800267e7  lea     rcx, [rbp+1250h+pswzServerName]
0x1800267eb  xor     edx, edx; dwUrlLength
0x1800267ed  movups  xmmword ptr [rsp+1350h+UrlComponents.dwSchemeLength], xmm0
0x1800267f2  mov     [rsp+1350h+UrlComponents.lpszHostName], rcx
0x1800267f7  lea     rcx, [rbp+1250h+pwszObjectName]
0x1800267fe  movups  xmmword ptr [rbp+1250h+UrlComponents.dwPasswordLength], xmm0
0x180026802  mov     [rbp+1250h+UrlComponents.lpszUrlPath], rcx
0x180026806  mov     rcx, rax; pwszUrl
0x180026809  movups  xmmword ptr [rsp+1350h+UrlComponents.dwStructSize], xmm0
0x18002680e  mov     [rsp+1350h+UrlComponents.dwStructSize], 68h ; 'h'
0x180026816  movups  xmmword ptr [rsp+1350h+UrlComponents.dwHostNameLength], xmm0
0x18002681b  mov     [rsp+1350h+UrlComponents.dwHostNameLength], 100h
0x180026823  movups  xmmword ptr [rbp+1250h+UrlComponents.dwUrlPathLength], xmm0
0x180026827  mov     [rbp+1250h+UrlComponents.dwUrlPathLength], 824h
0x18002682e  movups  xmmword ptr [rbp+1250h+UrlComponents.dwUserNameLength], xmm0
0x180026832  call    cs:__imp_WinHttpCrackUrl
0x180026839  nop     dword ptr [rax+rax+00h]
0x18002683e  test    eax, eax
0x180026840  jz      loc_180026E81
0x180026846  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hSession
0x18002684d  test    rcx, rcx
0x180026850  jz      loc_180026E4D
0x180026856  cmp     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x18002685d  jnz     loc_180026E4D
0x180026863  movzx   r8d, [rsp+1350h+UrlComponents.nPort]; nServerPort
0x180026869  lea     rdx, [rbp+1250h+pswzServerName]; pswzServerName
0x18002686d  xor     r9d, r9d; dwReserved
0x180026870  call    cs:__imp_WinHttpConnect
0x180026877  nop     dword ptr [rax+rax+00h]
0x18002687c  mov     r15, rax
0x18002687f  test    rax, rax
0x180026882  jz      loc_180026DF8
0x180026888  cmp     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x18002688f  jnz     loc_180026DF8
0x180026895  mov     [rsp+1350h+var_28], r12
0x18002689d  mov     [rsp+1350h+var_30], r14
0x1800268a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268ac  lea     rsi, WPP_GLOBAL_Control
0x1800268b3  cmp     rcx, rsi
0x1800268b6  jnz     loc_180026BA3
0x1800268bc  xor     r12d, r12d
0x1800268bf  mov     [rsp+1350h+dwFlags], 100h; dwFlags
0x1800268c7  mov     [rsp+1350h+ppwszAcceptTypes], r12; ppwszAcceptTypes
0x1800268cc  lea     r9, pwszVersion; "HTTP/1.1"
0x1800268d3  lea     r8, [rbp+1250h+pwszObjectName]; pwszObjectName
0x1800268da  mov     [rsp+1350h+pwszReferrer], r12; pwszReferrer
0x1800268df  lea     rdx, pwszVerb; "NOTIFY"
0x1800268e6  mov     rcx, r15; hConnect
0x1800268e9  call    cs:__imp_WinHttpOpenRequest
0x1800268f0  nop     dword ptr [rax+rax+00h]
0x1800268f5  mov     r14, rax
0x1800268f8  test    rax, rax
0x1800268fb  jz      loc_180026DAA
0x180026901  cmp     cs:?g_fEventApiShutDown@@3HA, r12d; int g_fEventApiShutDown
0x180026908  jnz     loc_180026DAA
0x18002690e  mov     r9d, 4; dwBufferLength
0x180026914  mov     [rsp+1350h+Buffer], 8
0x18002691c  lea     r8, [rsp+1350h+Buffer]; lpBuffer
0x180026921  mov     edx, 3Fh ; '?'; dwOption
0x180026926  mov     rcx, rax; hInternet
0x180026929  call    cs:__imp_WinHttpSetOption
0x180026930  nop     dword ptr [rax+rax+00h]
0x180026935  test    eax, eax
0x180026937  jz      loc_180026BD7
0x18002693d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026944  cmp     rcx, rsi
0x180026947  jnz     loc_180026AAB
0x18002694d  mov     rcx, rbx; lpWideCharStr
0x180026950  call    ?Utf8FromWsz@@YAPEADPEBG@Z; Utf8FromWsz(ushort const *)
0x180026955  mov     rbx, rax
0x180026958  test    rax, rax
0x18002695b  jz      loc_180026D66
0x180026961  mov     r8d, r12d; dwHeadersLength
0x180026964  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002696b  test    rdi, rdi
0x18002696e  jnz     loc_180026B14
0x180026974  inc     rcx
0x180026977  cmp     [rax+rcx], r12b
0x18002697b  jnz     short loc_180026974
0x18002697d  mov     qword ptr [rsp+1350h+dwFlags], r12; dwContext
0x180026982  mov     r9, rbx; lpOptional
0x180026985  mov     dword ptr [rsp+1350h+ppwszAcceptTypes], ecx; dwTotalLength
0x180026989  mov     rdx, rdi; lpszHeaders
0x18002698c  mov     dword ptr [rsp+1350h+pwszReferrer], ecx; dwOptionalLength
0x180026990  mov     rcx, r14; hRequest
0x180026993  call    cs:__imp_WinHttpSendRequest
0x18002699a  nop     dword ptr [rax+rax+00h]
0x18002699f  test    eax, eax
0x1800269a1  jz      loc_180026CA1
0x1800269a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269ae  mov     edi, r12d
0x1800269b1  cmp     rcx, rsi
0x1800269b4  jz      short loc_1800269DB
0x1800269b6  test    dword ptr [rcx+1Ch], 800h
0x1800269bd  jz      short loc_1800269DB
0x1800269bf  mov     rcx, [rcx+10h]
0x1800269c3  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x1800269ca  mov     edx, 74h ; 't'
0x1800269cf  call    WPP_SF_
0x1800269d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269db  cmp     cs:?g_fEventApiShutDown@@3HA, r12d; int g_fEventApiShutDown
0x1800269e2  jnz     loc_180026B37
0x1800269e8  cmp     rcx, rsi
0x1800269eb  jz      short loc_180026A0B
0x1800269ed  test    dword ptr [rcx+1Ch], 800h
0x1800269f4  jz      short loc_180026A0B
0x1800269f6  mov     rcx, [rcx+10h]
0x1800269fa  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026a01  mov     edx, 75h ; 'u'
0x180026a06  call    WPP_SF_
0x180026a0b  xor     edx, edx; lpReserved
0x180026a0d  mov     rcx, r14; hRequest
0x180026a10  call    cs:__imp_WinHttpReceiveResponse
0x180026a17  nop     dword ptr [rax+rax+00h]
0x180026a1c  test    eax, eax
0x180026a1e  jnz     loc_180026D2F
0x180026a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a2b  cmp     rcx, rsi
0x180026a2e  jz      short loc_180026A5D
0x180026a30  test    byte ptr [rcx+1Ch], 1
0x180026a34  jz      short loc_180026A5D
0x180026a36  movzx   eax, [rsp+1350h+UrlComponents.nPort]
0x180026a3b  lea     r8, [rbp+1250h+pwszObjectName]
0x180026a42  mov     rcx, [rcx+10h]
0x180026a46  lea     r9, [rbp+1250h+pswzServerName]
0x180026a4a  mov     [rsp+1350h+ppwszAcceptTypes], r8
0x180026a4f  mov     edx, 76h ; 'v'
0x180026a54  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180026a58  call    WPP_SF_SdS
0x180026a5d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180026a62  mov     edi, eax
0x180026a64  test    eax, eax
0x180026a66  jz      loc_180026B37
0x180026a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a73  cmp     rcx, rsi
0x180026a76  jz      loc_180026B37
0x180026a7c  test    byte ptr [rcx+1Ch], 1
0x180026a80  jz      loc_180026B37
0x180026a86  mov     rcx, [rcx+10h]
0x180026a8a  lea     r9, aHrsubmitnotify_4; "HrSubmitNotifyToSubscriber: HttpReceive"...
0x180026a91  mov     edx, 77h ; 'w'
0x180026a96  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180026a9a  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026aa1  call    WPP_SF_sd
0x180026aa6  jmp     loc_180026B37
0x180026aab  test    dword ptr [rcx+1Ch], 800h
0x180026ab2  jnz     loc_180026C2F
0x180026ab8  cmp     rcx, rsi
0x180026abb  jz      loc_18002694D
0x180026ac1  test    dword ptr [rcx+1Ch], 800h
0x180026ac8  jnz     loc_180026C57
0x180026ace  cmp     rcx, rsi
0x180026ad1  jz      loc_18002694D
0x180026ad7  test    dword ptr [rcx+1Ch], 800h
0x180026ade  jnz     loc_180026C78
0x180026ae4  cmp     rcx, rsi
0x180026ae7  jz      loc_18002694D
0x180026aed  test    dword ptr [rcx+1Ch], 800h
0x180026af4  jz      loc_18002694D
0x180026afa  mov     rcx, [rcx+10h]
0x180026afe  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026b05  mov     edx, 71h ; 'q'
0x180026b0a  call    WPP_SF_
0x180026b0f  jmp     loc_18002694D
0x180026b14  mov     r8, rcx
0x180026b17  nop     word ptr [rax+rax+00000000h]
0x180026b20  inc     r8
0x180026b23  cmp     [rdi+r8*2], r12w
0x180026b28  jnz     short loc_180026B20
0x180026b2a  jmp     loc_180026974
0x180026b2f  test    edi, edi
0x180026b31  jns     loc_1800269DB
0x180026b37  mov     rcx, rbx; Block
0x180026b3a  call    cs:__imp_free
0x180026b41  nop     dword ptr [rax+rax+00h]
0x180026b46  mov     rcx, r14; hInternet
0x180026b49  call    cs:__imp_WinHttpCloseHandle
0x180026b50  nop     dword ptr [rax+rax+00h]
0x180026b55  mov     rcx, r15; hInternet
0x180026b58  call    cs:__imp_WinHttpCloseHandle
0x180026b5f  nop     dword ptr [rax+rax+00h]
0x180026b64  mov     r14, [rsp+1350h+var_30]
0x180026b6c  mov     r12, [rsp+1350h+var_28]
0x180026b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b7b  test    edi, edi
0x180026b7d  jnz     loc_180026ED4
0x180026b83  mov     eax, edi
0x180026b85  mov     rcx, [rbp+1250h+var_40]
0x180026b8c  xor     rcx, rsp; StackCookie
0x180026b8f  call    __security_check_cookie
0x180026b94  add     rsp, 1330h
0x180026b9b  pop     r15
0x180026b9d  pop     rdi
0x180026b9e  pop     rsi
0x180026b9f  pop     rbx
0x180026ba0  pop     rbp
0x180026ba1  retn
0x180026ba3  test    dword ptr [rcx+1Ch], 800h
0x180026baa  jz      loc_1800268BC
0x180026bb0  movzx   eax, [rsp+1350h+UrlComponents.nPort]
0x180026bb5  lea     r9, [rbp+1250h+pswzServerName]
0x180026bb9  mov     rcx, [rcx+10h]
0x180026bbd  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026bc4  mov     edx, 6Ch ; 'l'
0x180026bc9  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180026bcd  call    WPP_SF_Sd
0x180026bd2  jmp     loc_1800268BC
0x180026bd7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180026bdc  test    eax, eax
0x180026bde  jz      loc_18002693D
0x180026be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180026beb  cmp     rcx, rsi
0x180026bee  jz      loc_18002694D
0x180026bf4  test    byte ptr [rcx+1Ch], 1
0x180026bf8  jz      loc_180026944
0x180026bfe  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180026c03  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c0a  lea     r9, aHrsubmitnotify_0; "HrSubmitNotifyToSubscriber: HttpSetOpti"...
0x180026c11  mov     edx, 6Dh ; 'm'
0x180026c16  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180026c1a  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026c21  mov     rcx, [rcx+10h]
0x180026c25  call    WPP_SF_sd
0x180026c2a  jmp     loc_18002693D
0x180026c2f  mov     rcx, [rcx+10h]
0x180026c33  lea     r9, [rbp+1250h+pwszObjectName]
0x180026c3a  mov     edx, 6Eh ; 'n'
0x180026c3f  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026c46  call    WPP_SF_S
0x180026c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c52  jmp     loc_180026AB8
0x180026c57  mov     rcx, [rcx+10h]
0x180026c5b  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026c62  mov     edx, 6Fh ; 'o'
0x180026c67  call    WPP_SF_
0x180026c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c73  jmp     loc_180026ACE
0x180026c78  mov     rcx, [rcx+10h]
0x180026c7c  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026c83  mov     edx, 70h ; 'p'
0x180026c88  mov     [rsp+1350h+pwszReferrer], rbx
0x180026c8d  mov     r9, rdi
0x180026c90  call    WPP_SF_SS
0x180026c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c9c  jmp     loc_180026AE4
0x180026ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ca8  cmp     rcx, rsi
0x180026cab  jz      short loc_180026CDA
0x180026cad  test    byte ptr [rcx+1Ch], 1
0x180026cb1  jz      short loc_180026CDA
0x180026cb3  movzx   eax, [rsp+1350h+UrlComponents.nPort]
0x180026cb8  lea     r8, [rbp+1250h+pwszObjectName]
0x180026cbf  mov     rcx, [rcx+10h]
0x180026cc3  lea     r9, [rbp+1250h+pswzServerName]
0x180026cc7  mov     [rsp+1350h+ppwszAcceptTypes], r8
0x180026ccc  mov     edx, 72h ; 'r'
0x180026cd1  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180026cd5  call    WPP_SF_SdS
0x180026cda  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180026cdf  mov     edi, eax
0x180026ce1  test    eax, eax
0x180026ce3  jz      loc_1800269D4
0x180026ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cf0  cmp     rcx, rsi
0x180026cf3  jz      loc_180026B2F
0x180026cf9  test    byte ptr [rcx+1Ch], 1
0x180026cfd  jz      loc_180026B2F
0x180026d03  mov     rcx, [rcx+10h]
0x180026d07  lea     r9, aHrsubmitnotify_1; "HrSubmitNotifyToSubscriber: HttpSendReq"...
0x180026d0e  mov     edx, 73h ; 's'
0x180026d13  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180026d17  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026d1e  call    WPP_SF_sd
0x180026d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d2a  jmp     loc_180026B2F
0x180026d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d36  cmp     rcx, rsi
0x180026d39  jz      loc_180026B37
0x180026d3f  test    dword ptr [rcx+1Ch], 800h
0x180026d46  jz      loc_180026B37
  ... truncated ...
```
