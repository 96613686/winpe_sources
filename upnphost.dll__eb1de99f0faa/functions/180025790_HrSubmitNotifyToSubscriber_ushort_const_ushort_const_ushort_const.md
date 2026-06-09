# HrSubmitNotifyToSubscriber(ushort const *,ushort const *,ushort const *)

- ea: `0x180025790`
- end: `0x180025ec9`
- name: `?HrSubmitNotifyToSubscriber@@YAJPEBG00@Z`
- size: `1849`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180026630`

## callees

- `0x18000db4c`
- `0x18000e3ec`
- `0x18001347c`
- `0x180025790`
- `0x180025ed0`
- `0x180039388`
- `0x180039a84`
- `0x18003a560`
- `0x180046540`
- `0x1800465b8`
- `0x1800542a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025b0a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025b0a`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800259e6`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800259e6`
- `WINHTTP!WinHttpCrackUrl` at `0x180025822`
- `WINHTTP!WinHttpCrackUrl` at `0x180025822`
- `WINHTTP!WinHttpSendRequest` at `0x18002596f`
- `WINHTTP!WinHttpSendRequest` at `0x18002596f`
- `WINHTTP!WinHttpOpenRequest` at `0x1800258cd`
- `WINHTTP!WinHttpOpenRequest` at `0x1800258cd`
- `WINHTTP!WinHttpSetOption` at `0x180025907`
- `WINHTTP!WinHttpSetOption` at `0x180025907`
- `WINHTTP!WinHttpCloseHandle` at `0x180025b13`
- `WINHTTP!WinHttpCloseHandle` at `0x180025b1c`
- `WINHTTP!WinHttpCloseHandle` at `0x180025b13`
- `WINHTTP!WinHttpCloseHandle` at `0x180025b1c`
- `WINHTTP!WinHttpConnect` at `0x18002585a`
- `WINHTTP!WinHttpConnect` at `0x18002585a`

## string_xrefs

- `0x180025d94`: `HrSubmitNotifyToSubscriber: HttpOpenRequest`

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
0x180025790  push    rbp
0x180025792  push    rbx
0x180025793  push    rsi
0x180025794  push    rdi
0x180025795  push    r15
0x180025797  lea     rbp, [rsp-1230h]
0x18002579f  mov     eax, 1330h
0x1800257a4  call    _alloca_probe
0x1800257a9  sub     rsp, rax
0x1800257ac  mov     rax, cs:__security_cookie
0x1800257b3  xor     rax, rsp
0x1800257b6  mov     [rbp+1250h+var_40], rax
0x1800257bd  xorps   xmm0, xmm0
0x1800257c0  lea     r9, [rsp+1350h+UrlComponents]; lpUrlComponents
0x1800257c5  mov     rdi, rcx
0x1800257c8  mov     rax, r8
0x1800257cb  xor     ecx, ecx
0x1800257cd  mov     rbx, rdx
0x1800257d0  mov     qword ptr [rbp+1250h+UrlComponents.dwExtraInfoLength], rcx
0x1800257d4  xor     r8d, r8d; dwFlags
0x1800257d7  lea     rcx, [rbp+1250h+pswzServerName]
0x1800257db  xor     edx, edx; dwUrlLength
0x1800257dd  movups  xmmword ptr [rsp+1350h+UrlComponents.dwSchemeLength], xmm0
0x1800257e2  mov     [rsp+1350h+UrlComponents.lpszHostName], rcx
0x1800257e7  lea     rcx, [rbp+1250h+pwszObjectName]
0x1800257ee  movups  xmmword ptr [rbp+1250h+UrlComponents.dwPasswordLength], xmm0
0x1800257f2  mov     [rbp+1250h+UrlComponents.lpszUrlPath], rcx
0x1800257f6  mov     rcx, rax; pwszUrl
0x1800257f9  movups  xmmword ptr [rsp+1350h+UrlComponents.dwStructSize], xmm0
0x1800257fe  mov     [rsp+1350h+UrlComponents.dwStructSize], 68h ; 'h'
0x180025806  movups  xmmword ptr [rsp+1350h+UrlComponents.dwHostNameLength], xmm0
0x18002580b  mov     [rsp+1350h+UrlComponents.dwHostNameLength], 100h
0x180025813  movups  xmmword ptr [rbp+1250h+UrlComponents.dwUrlPathLength], xmm0
0x180025817  mov     [rbp+1250h+UrlComponents.dwUrlPathLength], 824h
0x18002581e  movups  xmmword ptr [rbp+1250h+UrlComponents.dwUserNameLength], xmm0
0x180025822  call    cs:__imp_WinHttpCrackUrl
0x180025828  test    eax, eax
0x18002582a  jz      loc_180025E3E
0x180025830  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hSession
0x180025837  test    rcx, rcx
0x18002583a  jz      loc_180025E0A
0x180025840  cmp     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x180025847  jnz     loc_180025E0A
0x18002584d  movzx   r8d, [rsp+1350h+UrlComponents.nPort]; nServerPort
0x180025853  lea     rdx, [rbp+1250h+pswzServerName]; pswzServerName
0x180025857  xor     r9d, r9d; dwReserved
0x18002585a  call    cs:__imp_WinHttpConnect
0x180025860  mov     r15, rax
0x180025863  test    rax, rax
0x180025866  jz      loc_180025DB5
0x18002586c  cmp     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x180025873  jnz     loc_180025DB5
0x180025879  mov     [rsp+1350h+var_28], r12
0x180025881  mov     [rsp+1350h+var_30], r14
0x180025889  mov     rcx, cs:WPP_GLOBAL_Control
0x180025890  lea     rsi, WPP_GLOBAL_Control
0x180025897  cmp     rcx, rsi
0x18002589a  jnz     loc_180025B60
0x1800258a0  xor     r12d, r12d
0x1800258a3  mov     [rsp+1350h+dwFlags], 100h; dwFlags
0x1800258ab  mov     [rsp+1350h+ppwszAcceptTypes], r12; ppwszAcceptTypes
0x1800258b0  lea     r9, pwszVersion; "HTTP/1.1"
0x1800258b7  lea     r8, [rbp+1250h+pwszObjectName]; pwszObjectName
0x1800258be  mov     [rsp+1350h+pwszReferrer], r12; pwszReferrer
0x1800258c3  lea     rdx, pwszVerb; "NOTIFY"
0x1800258ca  mov     rcx, r15; hConnect
0x1800258cd  call    cs:__imp_WinHttpOpenRequest
0x1800258d3  mov     r14, rax
0x1800258d6  test    rax, rax
0x1800258d9  jz      loc_180025D67
0x1800258df  cmp     cs:?g_fEventApiShutDown@@3HA, r12d; int g_fEventApiShutDown
0x1800258e6  jnz     loc_180025D67
0x1800258ec  mov     r9d, 4; dwBufferLength
0x1800258f2  mov     [rsp+1350h+Buffer], 8
0x1800258fa  lea     r8, [rsp+1350h+Buffer]; lpBuffer
0x1800258ff  mov     edx, 3Fh ; '?'; dwOption
0x180025904  mov     rcx, rax; hInternet
0x180025907  call    cs:__imp_WinHttpSetOption
0x18002590d  test    eax, eax
0x18002590f  jz      loc_180025B94
0x180025915  mov     rcx, cs:WPP_GLOBAL_Control
0x18002591c  cmp     rcx, rsi
0x18002591f  jnz     loc_180025A7B
0x180025925  mov     rcx, rbx; lpWideCharStr
0x180025928  call    ?Utf8FromWsz@@YAPEADPEBG@Z; Utf8FromWsz(ushort const *)
0x18002592d  mov     rbx, rax
0x180025930  test    rax, rax
0x180025933  jz      loc_180025D23
0x180025939  mov     r8d, r12d; dwHeadersLength
0x18002593c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025943  test    rdi, rdi
0x180025946  jnz     loc_180025AE4
0x18002594c  nop     dword ptr [rax+00h]
0x180025950  inc     rcx
0x180025953  cmp     [rax+rcx], r12b
0x180025957  jnz     short loc_180025950
0x180025959  mov     qword ptr [rsp+1350h+dwFlags], r12; dwContext
0x18002595e  mov     r9, rbx; lpOptional
0x180025961  mov     dword ptr [rsp+1350h+ppwszAcceptTypes], ecx; dwTotalLength
0x180025965  mov     rdx, rdi; lpszHeaders
0x180025968  mov     dword ptr [rsp+1350h+pwszReferrer], ecx; dwOptionalLength
0x18002596c  mov     rcx, r14; hRequest
0x18002596f  call    cs:__imp_WinHttpSendRequest
0x180025975  test    eax, eax
0x180025977  jz      loc_180025C5E
0x18002597d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025984  mov     edi, r12d
0x180025987  cmp     rcx, rsi
0x18002598a  jz      short loc_1800259B1
0x18002598c  test    dword ptr [rcx+1Ch], 800h
0x180025993  jz      short loc_1800259B1
0x180025995  mov     rcx, [rcx+10h]
0x180025999  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x1800259a0  mov     edx, 74h ; 't'
0x1800259a5  call    WPP_SF_
0x1800259aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259b1  cmp     cs:?g_fEventApiShutDown@@3HA, r12d; int g_fEventApiShutDown
0x1800259b8  jnz     loc_180025B07
0x1800259be  cmp     rcx, rsi
0x1800259c1  jz      short loc_1800259E1
0x1800259c3  test    dword ptr [rcx+1Ch], 800h
0x1800259ca  jz      short loc_1800259E1
0x1800259cc  mov     rcx, [rcx+10h]
0x1800259d0  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x1800259d7  mov     edx, 75h ; 'u'
0x1800259dc  call    WPP_SF_
0x1800259e1  xor     edx, edx; lpReserved
0x1800259e3  mov     rcx, r14; hRequest
0x1800259e6  call    cs:__imp_WinHttpReceiveResponse
0x1800259ec  test    eax, eax
0x1800259ee  jnz     loc_180025CEC
0x1800259f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259fb  cmp     rcx, rsi
0x1800259fe  jz      short loc_180025A2D
0x180025a00  test    byte ptr [rcx+1Ch], 1
0x180025a04  jz      short loc_180025A2D
0x180025a06  movzx   eax, [rsp+1350h+UrlComponents.nPort]
0x180025a0b  lea     r8, [rbp+1250h+pwszObjectName]
0x180025a12  mov     rcx, [rcx+10h]
0x180025a16  lea     r9, [rbp+1250h+pswzServerName]
0x180025a1a  mov     [rsp+1350h+ppwszAcceptTypes], r8
0x180025a1f  mov     edx, 76h ; 'v'
0x180025a24  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180025a28  call    WPP_SF_SdS
0x180025a2d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180025a32  mov     edi, eax
0x180025a34  test    eax, eax
0x180025a36  jz      loc_180025B07
0x180025a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a43  cmp     rcx, rsi
0x180025a46  jz      loc_180025B07
0x180025a4c  test    byte ptr [rcx+1Ch], 1
0x180025a50  jz      loc_180025B07
0x180025a56  mov     rcx, [rcx+10h]
0x180025a5a  lea     r9, aHrsubmitnotify_4; "HrSubmitNotifyToSubscriber: HttpReceive"...
0x180025a61  mov     edx, 77h ; 'w'
0x180025a66  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180025a6a  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025a71  call    WPP_SF_sd
0x180025a76  jmp     loc_180025B07
0x180025a7b  test    dword ptr [rcx+1Ch], 800h
0x180025a82  jnz     loc_180025BEC
0x180025a88  cmp     rcx, rsi
0x180025a8b  jz      loc_180025925
0x180025a91  test    dword ptr [rcx+1Ch], 800h
0x180025a98  jnz     loc_180025C14
0x180025a9e  cmp     rcx, rsi
0x180025aa1  jz      loc_180025925
0x180025aa7  test    dword ptr [rcx+1Ch], 800h
0x180025aae  jnz     loc_180025C35
0x180025ab4  cmp     rcx, rsi
0x180025ab7  jz      loc_180025925
0x180025abd  test    dword ptr [rcx+1Ch], 800h
0x180025ac4  jz      loc_180025925
0x180025aca  mov     rcx, [rcx+10h]
0x180025ace  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025ad5  mov     edx, 71h ; 'q'
0x180025ada  call    WPP_SF_
0x180025adf  jmp     loc_180025925
0x180025ae4  mov     r8, rcx
0x180025ae7  nop     word ptr [rax+rax+00000000h]
0x180025af0  inc     r8
0x180025af3  cmp     [rdi+r8*2], r12w
0x180025af8  jnz     short loc_180025AF0
0x180025afa  jmp     loc_180025950
0x180025aff  test    edi, edi
0x180025b01  jns     loc_1800259B1
0x180025b07  mov     rcx, rbx; Block
0x180025b0a  call    cs:__imp_free
0x180025b10  mov     rcx, r14; hInternet
0x180025b13  call    cs:__imp_WinHttpCloseHandle
0x180025b19  mov     rcx, r15; hInternet
0x180025b1c  call    cs:__imp_WinHttpCloseHandle
0x180025b22  mov     r14, [rsp+1350h+var_30]
0x180025b2a  mov     r12, [rsp+1350h+var_28]
0x180025b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b39  test    edi, edi
0x180025b3b  jnz     loc_180025E91
0x180025b41  mov     eax, edi
0x180025b43  mov     rcx, [rbp+1250h+var_40]
0x180025b4a  xor     rcx, rsp; StackCookie
0x180025b4d  call    __security_check_cookie
0x180025b52  add     rsp, 1330h
0x180025b59  pop     r15
0x180025b5b  pop     rdi
0x180025b5c  pop     rsi
0x180025b5d  pop     rbx
0x180025b5e  pop     rbp
0x180025b5f  retn
0x180025b60  test    dword ptr [rcx+1Ch], 800h
0x180025b67  jz      loc_1800258A0
0x180025b6d  movzx   eax, [rsp+1350h+UrlComponents.nPort]
0x180025b72  lea     r9, [rbp+1250h+pswzServerName]
0x180025b76  mov     rcx, [rcx+10h]
0x180025b7a  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025b81  mov     edx, 6Ch ; 'l'
0x180025b86  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180025b8a  call    WPP_SF_Sd
0x180025b8f  jmp     loc_1800258A0
0x180025b94  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180025b99  test    eax, eax
0x180025b9b  jz      loc_180025915
0x180025ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ba8  cmp     rcx, rsi
0x180025bab  jz      loc_180025925
0x180025bb1  test    byte ptr [rcx+1Ch], 1
0x180025bb5  jz      loc_18002591C
0x180025bbb  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180025bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bc7  lea     r9, aHrsubmitnotify_0; "HrSubmitNotifyToSubscriber: HttpSetOpti"...
0x180025bce  mov     edx, 6Dh ; 'm'
0x180025bd3  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180025bd7  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025bde  mov     rcx, [rcx+10h]
0x180025be2  call    WPP_SF_sd
0x180025be7  jmp     loc_180025915
0x180025bec  mov     rcx, [rcx+10h]
0x180025bf0  lea     r9, [rbp+1250h+pwszObjectName]
0x180025bf7  mov     edx, 6Eh ; 'n'
0x180025bfc  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025c03  call    WPP_SF_S
0x180025c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c0f  jmp     loc_180025A88
0x180025c14  mov     rcx, [rcx+10h]
0x180025c18  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025c1f  mov     edx, 6Fh ; 'o'
0x180025c24  call    WPP_SF_
0x180025c29  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c30  jmp     loc_180025A9E
0x180025c35  mov     rcx, [rcx+10h]
0x180025c39  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025c40  mov     edx, 70h ; 'p'
0x180025c45  mov     [rsp+1350h+pwszReferrer], rbx
0x180025c4a  mov     r9, rdi
0x180025c4d  call    WPP_SF_SS
0x180025c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c59  jmp     loc_180025AB4
0x180025c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c65  cmp     rcx, rsi
0x180025c68  jz      short loc_180025C97
0x180025c6a  test    byte ptr [rcx+1Ch], 1
0x180025c6e  jz      short loc_180025C97
0x180025c70  movzx   eax, [rsp+1350h+UrlComponents.nPort]
0x180025c75  lea     r8, [rbp+1250h+pwszObjectName]
0x180025c7c  mov     rcx, [rcx+10h]
0x180025c80  lea     r9, [rbp+1250h+pswzServerName]
0x180025c84  mov     [rsp+1350h+ppwszAcceptTypes], r8
0x180025c89  mov     edx, 72h ; 'r'
0x180025c8e  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180025c92  call    WPP_SF_SdS
0x180025c97  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180025c9c  mov     edi, eax
0x180025c9e  test    eax, eax
0x180025ca0  jz      loc_1800259AA
0x180025ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cad  cmp     rcx, rsi
0x180025cb0  jz      loc_180025AFF
0x180025cb6  test    byte ptr [rcx+1Ch], 1
0x180025cba  jz      loc_180025AFF
0x180025cc0  mov     rcx, [rcx+10h]
0x180025cc4  lea     r9, aHrsubmitnotify_1; "HrSubmitNotifyToSubscriber: HttpSendReq"...
0x180025ccb  mov     edx, 73h ; 's'
0x180025cd0  mov     dword ptr [rsp+1350h+pwszReferrer], eax
0x180025cd4  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025cdb  call    WPP_SF_sd
0x180025ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ce7  jmp     loc_180025AFF
0x180025cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cf3  cmp     rcx, rsi
0x180025cf6  jz      loc_180025B07
0x180025cfc  test    dword ptr [rcx+1Ch], 800h
0x180025d03  jz      loc_180025B07
0x180025d09  mov     rcx, [rcx+10h]
0x180025d0d  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180025d14  mov     edx, 78h ; 'x'
0x180025d19  call    WPP_SF_
0x180025d1e  jmp     loc_180025B07
0x180025d23  mov     edi, 8007000Eh
0x180025d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d2f  cmp     rcx, rsi
  ... truncated ...
```
