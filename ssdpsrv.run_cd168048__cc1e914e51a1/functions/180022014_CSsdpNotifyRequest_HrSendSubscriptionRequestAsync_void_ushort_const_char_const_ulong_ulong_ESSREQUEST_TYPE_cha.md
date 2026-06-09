# CSsdpNotifyRequest::HrSendSubscriptionRequestAsync(void *,ushort const *,char const *,ulong,ulong,_ESSREQUEST_TYPE,char *)

- ea: `0x180022014`
- end: `0x180022711`
- name: `?HrSendSubscriptionRequestAsync@CSsdpNotifyRequest@@QEAAJPEAXPEBGPEBDKKW4_ESSREQUEST_TYPE@@PEAD@Z`
- size: `1789`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180014580`
- `0x180021ef8`

## callees

- `0x18000683c`
- `0x180019850`
- `0x18001a10c`
- `0x18001feac`
- `0x180020a30`
- `0x180022014`
- `0x1800271fc`
- `0x180027b48`
- `0x1800287d0`
- `0x18002911c`
- `0x180029df0`
- `0x18002fe28`
- `0x180031018`
- `0x18003106c`
- `0x1800310d4`
- `0x180031154`
- `0x180037d60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800220b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180022659`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800220b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180022659`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800220d7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800220d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002266f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002266f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022220`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022220`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180022129`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002213c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180022129`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002213c`
- `WS2_32!WSAAddressToStringA` at `0x1800223c2`
- `WS2_32!WSAAddressToStringA` at `0x1800223c2`
- `WS2_32!__imp_htons` at `0x180022376`
- `WS2_32!__imp_htons` at `0x180022376`
- `WS2_32!__imp_WSAGetLastError` at `0x18002243d`
- `WS2_32!__imp_WSAGetLastError` at `0x180022473`
- `WS2_32!__imp_WSAGetLastError` at `0x18002243d`
- `WS2_32!__imp_WSAGetLastError` at `0x180022473`
- `WINHTTP!WinHttpOpenRequest` at `0x180022256`
- `WINHTTP!WinHttpOpenRequest` at `0x180022256`
- `WINHTTP!WinHttpCrackUrl` at `0x180022155`
- `WINHTTP!WinHttpCrackUrl` at `0x180022155`
- `WINHTTP!WinHttpConnect` at `0x1800221ab`
- `WINHTTP!WinHttpConnect` at `0x1800221ab`
- `WINHTTP!WinHttpSetOption` at `0x1800222b9`
- `WINHTTP!WinHttpSetOption` at `0x1800222b9`
- `WINHTTP!WinHttpSendRequest` at `0x180022615`
- `WINHTTP!WinHttpSendRequest` at `0x180022615`

## string_xrefs

- `0x18002249f`: `SID: %s\n`
- `0x180022314`: `SID: %s\nTimeout: Second-%d\n`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequest::HrSendSubscriptionRequestAsync(
        DWORD_PTR a1,
        void *a2,
        const WCHAR *a3,
        const char *a4,
        unsigned int a5,
        int a6,
        int a7,
        const char *a8)
{
  int LocalIpAddress; // edi
  void *v14; // rcx
  __int64 v15; // rbx
  char *v16; // rax
  void *v17; // rcx
  LPCSTR v18; // rcx
  const WCHAR *v19; // rbx
  void *v20; // rcx
  int v21; // r8d
  LPCSTR v22; // rcx
  unsigned int v23; // eax
  int v24; // eax
  u_short EventingPort; // ax
  int v26; // ecx
  int v27; // eax
  __int64 v28; // rdx
  int Error; // eax
  bool v30; // zf
  int v31; // eax
  const char *v32; // r9
  WCHAR *v33; // rbx
  __int64 v34; // rax
  unsigned int Win32Error; // eax
  int v36; // eax
  int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwAddressStringLength; // [rsp+44h] [rbp-BCh] BYREF
  const char *v39; // [rsp+48h] [rbp-B8h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-B0h] BYREF
  struct sockaddr saAddress; // [rsp+C0h] [rbp-40h] BYREF
  int v42; // [rsp+D8h] [rbp-28h]
  WCHAR pswzServerName[264]; // [rsp+140h] [rbp+40h] BYREF
  CHAR szAddressString[256]; // [rsp+350h] [rbp+250h] BYREF
  CHAR MultiByteStr[1024]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR pwszObjectName[2088]; // [rsp+850h] [rbp+750h] BYREF

  v39 = a8;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  pswzServerName[0] = 0;
  pwszObjectName[0] = 0;
  if ( !a7 && !a8 )
    return 2147500037LL;
  LocalIpAddress = 0;
  *(_DWORD *)(a1 + 376) = a7;
  if ( a4 )
  {
    v14 = *(void **)(a1 + 336);
    if ( v14 )
    {
      free(v14);
      *(_QWORD *)(a1 + 336) = 0;
    }
    v15 = -1;
    do
      ++v15;
    while ( a4[v15] );
    v16 = (char *)malloc(v15 + 1);
    *(_QWORD *)(a1 + 336) = v16;
    LocalIpAddress = StringCbCopyA(v16, v15 + 1, a4);
  }
  v17 = *(void **)(a1 + 312);
  UrlComponents.lpszHostName = (LPSTR)pswzServerName;
  UrlComponents.lpszUrlPath = (LPSTR)pwszObjectName;
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = 256;
  UrlComponents.dwUrlPathLength = 2084;
  ResetEvent(v17);
  ResetEvent(*(HANDLE *)(a1 + 320));
  if ( WinHttpCrackUrl(a3, 0, 0, &UrlComponents) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
        pswzServerName);
    *(_QWORD *)(a1 + 256) = WinHttpConnect(a2, pswzServerName, UrlComponents.nPort, 0);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
      v18 = WPP_GLOBAL_Control;
    }
    if ( !*(_QWORD *)(a1 + 256) )
      goto LABEL_88;
    v19 = aUnsubscribe_1;
    if ( *(_DWORD *)(a1 + 376) != 2 )
      v19 = pwszVerb;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 272));
    *(_QWORD *)(a1 + 264) = WinHttpOpenRequest(*(HINTERNET *)(a1 + 256), v19, pwszObjectName, L"HTTP/1.1", 0, 0, 0x100u);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
    v20 = *(void **)(a1 + 264);
    if ( !v20 )
      goto LABEL_83;
    Buffer = 8;
    if ( !WinHttpSetOption(v20, 0x3Fu, &Buffer, 4u) )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      {
LABEL_29:
        v24 = *(_DWORD *)(a1 + 376);
        if ( v24 == 1 )
        {
          StringCbPrintfA(MultiByteStr, 0x400u, "SID: %s\r\nTimeout: Second-%d\r\n", a4, a6);
        }
        else
        {
          if ( v24 )
          {
            if ( v24 != 2 )
              goto LABEL_52;
            StringCbPrintfA(MultiByteStr, 0x400u, "SID: %s\r\n", a4);
            goto LABEL_51;
          }
          pswzServerName[256] = 0;
          memset_0(&saAddress, 0, 0x80u);
          LocalIpAddress = GetLocalIpAddress(pswzServerName, a5, &saAddress);
          EventingPort = GetEventingPort();
          *(_WORD *)saAddress.sa_data = htons(EventingPort);
          if ( LocalIpAddress >= 0 )
          {
            v26 = v42;
            dwAddressStringLength = 256;
            if ( saAddress.sa_family == 23 )
              v26 = 0;
            v42 = v26;
            if ( WSAAddressToStringA(&saAddress, 0x80u, 0, szAddressString, &dwAddressStringLength) )
            {
              Error = WSAGetLastError();
              v30 = Error == 0;
              if ( Error > 0 )
                v30 = 0;
              if ( v30 )
                goto LABEL_51;
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
              {
LABEL_74:
                v33 = WszFromSz(MultiByteStr);
                if ( v33 )
                {
                  *(_DWORD *)(a1 + 352) = 1;
                  v34 = -1;
                  do
                    ++v34;
                  while ( v33[v34] );
                  if ( !WinHttpSendRequest(*(HINTERNET *)(a1 + 264), v33, v34, 0, 0, 0, a1) )
                  {
                    Win32Error = HrFromLastWin32Error();
                    LocalIpAddress = Win32Error;
                    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        129,
                        WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
                        Win32Error);
                  }
                  free(v33);
                }
                else
                {
                  LocalIpAddress = -2147024882;
                }
                goto LABEL_83;
              }
              if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
              {
LABEL_52:
                if ( v22 != (LPCSTR)&WPP_GLOBAL_Control )
                {
                  if ( (v22[28] & 8) != 0 )
                  {
                    WPP_SF_SdS(
                      *((_QWORD *)v22 + 2),
                      (unsigned int)pwszObjectName,
                      v21,
                      (unsigned int)pswzServerName,
                      UrlComponents.nPort,
                      (__int64)pwszObjectName);
                    v22 = WPP_GLOBAL_Control;
                  }
                  if ( v22 != (LPCSTR)&WPP_GLOBAL_Control )
                  {
                    if ( (v22[28] & 8) != 0 )
                    {
                      v31 = *(_DWORD *)(a1 + 376);
                      if ( v31 )
                      {
                        if ( v31 == 1 )
                        {
                          v32 = "re-subscription";
                        }
                        else
                        {
                          v32 = "unsubscribe";
                          if ( v31 != 2 )
                            v32 = "Unknown!";
                        }
                      }
                      else
                      {
                        v32 = "subscription";
                      }
                      WPP_SF_s(*((_QWORD *)v22 + 2), 125, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, v32);
                      v22 = WPP_GLOBAL_Control;
                    }
                    if ( v22 != (LPCSTR)&WPP_GLOBAL_Control )
                    {
                      if ( (v22[28] & 8) != 0 )
                      {
                        WPP_SF_(*((_QWORD *)v22 + 2), 126, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
                        v22 = WPP_GLOBAL_Control;
                      }
                      if ( v22 != (LPCSTR)&WPP_GLOBAL_Control )
                      {
                        if ( (v22[28] & 8) != 0 )
                        {
                          WPP_SF_s(
                            *((_QWORD *)v22 + 2),
                            127,
                            WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
                            MultiByteStr);
                          v22 = WPP_GLOBAL_Control;
                        }
                        if ( v22 != (LPCSTR)&WPP_GLOBAL_Control && (v22[28] & 8) != 0 )
                          WPP_SF_(*((_QWORD *)v22 + 2), 128, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
                      }
                    }
                  }
                }
                if ( LocalIpAddress < 0 )
                  goto LABEL_83;
                goto LABEL_74;
              }
              v27 = WSAGetLastError();
              if ( v27 > 0 )
                v27 = (unsigned __int16)v27 | 0x80070000;
              v22 = WPP_GLOBAL_Control;
              v28 = 123;
            }
            else
            {
              v27 = StringCbPrintfA(
                      MultiByteStr,
                      0x400u,
                      "NT: upnp:event\r\nCallback: <http://%s/upnp/eventing/%s>\r\nTimeout: Second-%d\r\n\r\n",
                      szAddressString,
                      v39,
                      1800);
              LocalIpAddress = v27;
              if ( v27 >= 0 )
                goto LABEL_51;
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
              {
LABEL_83:
                LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 272));
                goto LABEL_87;
              }
              if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
                goto LABEL_52;
              v28 = 122;
            }
            WPP_SF_d(*((_QWORD *)v22 + 2), v28, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, (unsigned int)v27);
          }
        }
LABEL_51:
        v22 = WPP_GLOBAL_Control;
        goto LABEL_52;
      }
      v23 = HrFromLastWin32Error();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, v23);
    }
    v22 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  v36 = HrFromLastWin32Error();
  LocalIpAddress = v36;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
    goto LABEL_88;
  WPP_SF_Sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    130,
    (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
    (_DWORD)a3,
    v36);
LABEL_87:
  v18 = WPP_GLOBAL_Control;
LABEL_88:
  if ( LocalIpAddress && v18 != (LPCSTR)&WPP_GLOBAL_Control && (v18[28] & 1) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)v18 + 2),
      131,
      WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
      (unsigned int)LocalIpAddress,
      LocalIpAddress);
  return (unsigned int)LocalIpAddress;
}

```

## disassembly

```asm
0x180022014  push    rbp
0x180022016  push    rbx
0x180022017  push    rsi
0x180022018  push    rdi
0x180022019  push    r12
0x18002201b  push    r13
0x18002201d  push    r14
0x18002201f  push    r15
0x180022021  lea     rbp, [rsp-17B8h]
0x180022029  mov     eax, 18B8h
0x18002202e  call    _alloca_probe
0x180022033  sub     rsp, rax
0x180022036  mov     rax, cs:__security_cookie
0x18002203d  xor     rax, rsp
0x180022040  mov     [rbp+17F0h+var_50], rax
0x180022047  mov     rbx, [rbp+17F0h+arg_38]
0x18002204e  mov     r12, r8
0x180022051  mov     r13, rdx
0x180022054  mov     [rsp+18F0h+var_18A8], rbx
0x180022059  mov     r14, rcx
0x18002205c  mov     esi, 68h ; 'h'
0x180022061  mov     r8d, esi; Size
0x180022064  lea     rcx, [rsp+18F0h+UrlComponents]; void *
0x180022069  xor     edx, edx; Val
0x18002206b  mov     r15, r9
0x18002206e  call    memset_0
0x180022073  xor     eax, eax
0x180022075  mov     [rbp+17F0h+pswzServerName], ax
0x180022079  mov     [rbp+17F0h+pwszObjectName], ax
0x180022080  mov     eax, [rbp+17F0h+arg_30]
0x180022086  test    eax, eax
0x180022088  jnz     short loc_180022099
0x18002208a  test    rbx, rbx
0x18002208d  jnz     short loc_180022099
0x18002208f  mov     eax, 80004005h
0x180022094  jmp     loc_1800226ED
0x180022099  xor     edi, edi
0x18002209b  mov     [r14+178h], eax
0x1800220a2  test    r15, r15
0x1800220a5  jz      short loc_1800220FB
0x1800220a7  mov     rcx, [r14+150h]; Block
0x1800220ae  test    rcx, rcx
0x1800220b1  jz      short loc_1800220C6
0x1800220b3  call    cs:__imp_free
0x1800220ba  nop     dword ptr [rax+rax+00h]
0x1800220bf  mov     [r14+150h], rdi
0x1800220c6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800220ca  inc     rbx
0x1800220cd  cmp     [r15+rbx], dil
0x1800220d1  jnz     short loc_1800220CA
0x1800220d3  lea     rcx, [rbx+1]; Size
0x1800220d7  call    cs:__imp_malloc
0x1800220de  nop     dword ptr [rax+rax+00h]
0x1800220e3  mov     r8, r15; char *
0x1800220e6  lea     rdx, [rbx+1]; unsigned __int64
0x1800220ea  mov     rcx, rax; char *
0x1800220ed  mov     [r14+150h], rax
0x1800220f4  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800220f9  mov     edi, eax
0x1800220fb  mov     rcx, [r14+138h]; hEvent
0x180022102  lea     rax, [rbp+17F0h+pswzServerName]
0x180022106  mov     [rsp+18F0h+UrlComponents.lpszHostName], rax
0x18002210b  lea     rax, [rbp+17F0h+pwszObjectName]
0x180022112  mov     [rbp+17F0h+UrlComponents.lpszUrlPath], rax
0x180022116  mov     [rsp+18F0h+UrlComponents.dwStructSize], esi
0x18002211a  mov     [rsp+18F0h+UrlComponents.dwHostNameLength], 100h
0x180022122  mov     [rbp+17F0h+UrlComponents.dwUrlPathLength], 824h
0x180022129  call    cs:__imp_ResetEvent
0x180022130  nop     dword ptr [rax+rax+00h]
0x180022135  mov     rcx, [r14+140h]; hEvent
0x18002213c  call    cs:__imp_ResetEvent
0x180022143  nop     dword ptr [rax+rax+00h]
0x180022148  lea     r9, [rsp+18F0h+UrlComponents]; lpUrlComponents
0x18002214d  xor     r8d, r8d; dwFlags
0x180022150  xor     edx, edx; dwUrlLength
0x180022152  mov     rcx, r12; pwszUrl
0x180022155  call    cs:__imp_WinHttpCrackUrl
0x18002215c  nop     dword ptr [rax+rax+00h]
0x180022161  test    eax, eax
0x180022163  jz      loc_18002267D
0x180022169  mov     rcx, cs:WPP_GLOBAL_Control
0x180022170  lea     rsi, WPP_GLOBAL_Control
0x180022177  cmp     rcx, rsi
0x18002217a  jz      short loc_18002219B
0x18002217c  test    byte ptr [rcx+1Ch], 8
0x180022180  jz      short loc_18002219B
0x180022182  mov     rcx, [rcx+10h]
0x180022186  lea     r9, [rbp+17F0h+pswzServerName]
0x18002218a  mov     edx, 76h ; 'v'
0x18002218f  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180022196  call    WPP_SF_S
0x18002219b  movzx   r8d, [rsp+18F0h+UrlComponents.nPort]; nServerPort
0x1800221a1  lea     rdx, [rbp+17F0h+pswzServerName]; pswzServerName
0x1800221a5  xor     r9d, r9d; dwReserved
0x1800221a8  mov     rcx, r13; hSession
0x1800221ab  call    cs:__imp_WinHttpConnect
0x1800221b2  nop     dword ptr [rax+rax+00h]
0x1800221b7  mov     [r14+100h], rax
0x1800221be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221c5  cmp     rcx, rsi
0x1800221c8  jz      short loc_1800221EC
0x1800221ca  test    byte ptr [rcx+1Ch], 8
0x1800221ce  jz      short loc_1800221EC
0x1800221d0  mov     rcx, [rcx+10h]
0x1800221d4  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x1800221db  mov     edx, 77h ; 'w'
0x1800221e0  call    WPP_SF_
0x1800221e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221ec  xor     r13d, r13d
0x1800221ef  cmp     [r14+100h], r13
0x1800221f6  jz      loc_1800226C0
0x1800221fc  cmp     dword ptr [r14+178h], 2
0x180022204  lea     rax, pwszVerb; "SUBSCRIBE"
0x18002220b  lea     r12, [r14+110h]
0x180022212  lea     rbx, aUnsubscribe_1; "UNSUBSCRIBE"
0x180022219  mov     rcx, r12; lpCriticalSection
0x18002221c  cmovnz  rbx, rax
0x180022220  call    cs:__imp_EnterCriticalSection
0x180022227  nop     dword ptr [rax+rax+00h]
0x18002222c  mov     rcx, [r14+100h]; hConnect
0x180022233  lea     r9, pwszVersion; "HTTP/1.1"
0x18002223a  mov     [rsp+18F0h+dwFlags], 100h; dwFlags
0x180022242  lea     r8, [rbp+17F0h+pwszObjectName]; pwszObjectName
0x180022249  mov     [rsp+18F0h+ppwszAcceptTypes], r13; ppwszAcceptTypes
0x18002224e  mov     rdx, rbx; pwszVerb
0x180022251  mov     [rsp+18F0h+pwszReferrer], r13; pwszReferrer
0x180022256  call    cs:__imp_WinHttpOpenRequest
0x18002225d  nop     dword ptr [rax+rax+00h]
0x180022262  mov     [r14+108h], rax
0x180022269  mov     rcx, cs:WPP_GLOBAL_Control
0x180022270  lea     rbx, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180022277  cmp     rcx, rsi
0x18002227a  jz      short loc_180022292
0x18002227c  test    byte ptr [rcx+1Ch], 8
0x180022280  jz      short loc_180022292
0x180022282  mov     rcx, [rcx+10h]
0x180022286  lea     edx, [r13+78h]
0x18002228a  mov     r8, rbx
0x18002228d  call    WPP_SF_
0x180022292  mov     rcx, [r14+108h]; hInternet
0x180022299  test    rcx, rcx
0x18002229c  jz      loc_18002266C
0x1800222a2  mov     r9d, 4; dwBufferLength
0x1800222a8  mov     [rsp+18F0h+Buffer], 8
0x1800222b0  lea     r8, [rsp+18F0h+Buffer]; lpBuffer
0x1800222b5  lea     edx, [r9+3Bh]; dwOption
0x1800222b9  call    cs:__imp_WinHttpSetOption
0x1800222c0  nop     dword ptr [rax+rax+00h]
0x1800222c5  test    eax, eax
0x1800222c7  jnz     short loc_1800222FB
0x1800222c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222d0  cmp     rcx, rsi
0x1800222d3  jz      short loc_180022302
0x1800222d5  test    byte ptr [rcx+1Ch], 1
0x1800222d9  jz      short loc_180022302
0x1800222db  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800222e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222e7  mov     edx, 79h ; 'y'
0x1800222ec  mov     r9d, eax
0x1800222ef  mov     r8, rbx
0x1800222f2  mov     rcx, [rcx+10h]
0x1800222f6  call    WPP_SF_d
0x1800222fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022302  mov     eax, [r14+178h]
0x180022309  cmp     eax, 1
0x18002230c  jnz     short loc_180022338
0x18002230e  mov     eax, [rbp+17F0h+arg_28]
0x180022314  lea     r8, aSidSTimeoutSec; "SID: %s\r\nTimeout: Second-%d\r\n"
0x18002231b  mov     r9, r15
0x18002231e  mov     dword ptr [rsp+18F0h+pwszReferrer], eax
0x180022322  mov     edx, 400h; unsigned __int64
0x180022327  lea     rcx, [rbp+17F0h+MultiByteStr]; char *
0x18002232e  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180022333  jmp     loc_1800224B7
0x180022338  test    eax, eax
0x18002233a  jnz     loc_180022497
0x180022340  xor     edx, edx; Val
0x180022342  mov     [rbp+17F0h+var_15B0], r13w
0x18002234a  mov     r8d, 80h; Size
0x180022350  lea     rcx, [rbp+17F0h+saAddress]; void *
0x180022354  call    memset_0
0x180022359  mov     edx, [rbp+17F0h+arg_20]; unsigned int
0x18002235f  lea     r8, [rbp+17F0h+saAddress]; struct sockaddr *
0x180022363  lea     rcx, [rbp+17F0h+pswzServerName]; unsigned __int16 *
0x180022367  call    ?GetLocalIpAddress@@YAJPEAGKPEAUsockaddr@@@Z; GetLocalIpAddress(ushort *,ulong,sockaddr *)
0x18002236c  mov     edi, eax
0x18002236e  call    ?GetEventingPort@@YAGXZ; GetEventingPort(void)
0x180022373  movzx   ecx, ax; hostshort
0x180022376  call    cs:__imp_htons
0x18002237d  nop     dword ptr [rax+rax+00h]
0x180022382  mov     word ptr [rbp+17F0h+saAddress.sa_data], ax
0x180022386  test    edi, edi
0x180022388  js      loc_1800224B7
0x18002238e  mov     ecx, [rbp+17F0h+var_1818]
0x180022391  lea     rax, [rsp+18F0h+dwAddressStringLength]
0x180022396  cmp     [rbp+17F0h+saAddress.sa_family], 17h
0x18002239b  lea     r9, [rbp+17F0h+szAddressString]; lpszAddressString
0x1800223a2  mov     edx, 80h; dwAddressLength
0x1800223a7  mov     [rsp+18F0h+dwAddressStringLength], 100h
0x1800223af  cmovz   ecx, r13d
0x1800223b3  mov     [rsp+18F0h+pwszReferrer], rax; lpdwAddressStringLength
0x1800223b8  mov     [rbp+17F0h+var_1818], ecx
0x1800223bb  xor     r8d, r8d; lpProtocolInfo
0x1800223be  lea     rcx, [rbp+17F0h+saAddress]; lpsaAddress
0x1800223c2  call    cs:__imp_WSAAddressToStringA
0x1800223c9  nop     dword ptr [rax+rax+00h]
0x1800223ce  test    eax, eax
0x1800223d0  jnz     short loc_18002243D
0x1800223d2  mov     rax, [rsp+18F0h+var_18A8]
0x1800223d7  lea     r9, [rbp+17F0h+szAddressString]
0x1800223de  mov     dword ptr [rsp+18F0h+ppwszAcceptTypes], 708h
0x1800223e6  lea     r8, aNtUpnpEventCal; "NT: upnp:event\r\nCallback: <http://%s/"...
0x1800223ed  mov     edx, 400h; unsigned __int64
0x1800223f2  mov     [rsp+18F0h+pwszReferrer], rax
0x1800223f7  lea     rcx, [rbp+17F0h+MultiByteStr]; char *
0x1800223fe  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180022403  mov     edi, eax
0x180022405  test    eax, eax
0x180022407  jns     loc_1800224B7
0x18002240d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022414  cmp     rcx, rsi
0x180022417  jz      loc_18002266C
0x18002241d  test    byte ptr [rcx+1Ch], 1
0x180022421  jz      loc_1800224BE
0x180022427  mov     edx, 7Ah ; 'z'
0x18002242c  mov     rcx, [rcx+10h]
0x180022430  mov     r8, rbx
0x180022433  mov     r9d, eax
0x180022436  call    WPP_SF_d
0x18002243b  jmp     short loc_1800224B7
0x18002243d  call    cs:__imp_WSAGetLastError
0x180022444  nop     dword ptr [rax+rax+00h]
0x180022449  mov     r15d, 80070000h
0x18002244f  test    eax, eax
0x180022451  jle     short loc_18002245B
0x180022453  movzx   eax, ax
0x180022456  or      eax, r15d
0x180022459  test    eax, eax
0x18002245b  jz      short loc_1800224B7
0x18002245d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022464  cmp     rcx, rsi
0x180022467  jz      loc_1800225C5
0x18002246d  test    byte ptr [rcx+1Ch], 1
0x180022471  jz      short loc_1800224BE
0x180022473  call    cs:__imp_WSAGetLastError
0x18002247a  nop     dword ptr [rax+rax+00h]
0x18002247f  test    eax, eax
0x180022481  jle     short loc_180022489
0x180022483  movzx   eax, ax
0x180022486  or      eax, r15d
0x180022489  mov     rcx, cs:WPP_GLOBAL_Control
0x180022490  mov     edx, 7Bh ; '{'
0x180022495  jmp     short loc_18002242C
0x180022497  cmp     eax, 2
0x18002249a  jnz     short loc_1800224BE
0x18002249c  mov     r9, r15
0x18002249f  lea     r8, aSidS; "SID: %s\r\n"
0x1800224a6  mov     edx, 400h; unsigned __int64
0x1800224ab  lea     rcx, [rbp+17F0h+MultiByteStr]; char *
0x1800224b2  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x1800224b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224be  cmp     rcx, rsi
0x1800224c1  jz      loc_1800225BD
0x1800224c7  test    byte ptr [rcx+1Ch], 8
0x1800224cb  jz      short loc_1800224F6
0x1800224cd  movzx   eax, [rsp+18F0h+UrlComponents.nPort]
0x1800224d2  lea     rdx, [rbp+17F0h+pwszObjectName]
0x1800224d9  mov     rcx, [rcx+10h]
0x1800224dd  lea     r9, [rbp+17F0h+pswzServerName]
0x1800224e1  mov     [rsp+18F0h+ppwszAcceptTypes], rdx
0x1800224e6  mov     dword ptr [rsp+18F0h+pwszReferrer], eax
0x1800224ea  call    WPP_SF_SdS
0x1800224ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224f6  cmp     rcx, rsi
0x1800224f9  jz      loc_1800225BD
0x1800224ff  test    byte ptr [rcx+1Ch], 8
0x180022503  jz      short loc_180022554
0x180022505  mov     eax, [r14+178h]
0x18002250c  test    eax, eax
0x18002250e  jnz     short loc_180022519
0x180022510  lea     r9, aSubscription; "subscription"
0x180022517  jmp     short loc_18002253C
0x180022519  cmp     eax, 1
0x18002251c  jnz     short loc_180022527
0x18002251e  lea     r9, aReSubscription; "re-subscription"
0x180022525  jmp     short loc_18002253C
0x180022527  cmp     eax, 2
0x18002252a  lea     r9, aUnsubscribe; "unsubscribe"
0x180022531  lea     rdx, aUnknown_0; "Unknown!"
0x180022538  cmovnz  r9, rdx
0x18002253c  mov     rcx, [rcx+10h]
0x180022540  mov     edx, 7Dh ; '}'
0x180022545  mov     r8, rbx
0x180022548  call    WPP_SF_s
0x18002254d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022554  cmp     rcx, rsi
0x180022557  jz      short loc_1800225BD
0x180022559  test    byte ptr [rcx+1Ch], 8
0x18002255d  jz      short loc_180022577
0x18002255f  mov     rcx, [rcx+10h]
  ... truncated ...
```
