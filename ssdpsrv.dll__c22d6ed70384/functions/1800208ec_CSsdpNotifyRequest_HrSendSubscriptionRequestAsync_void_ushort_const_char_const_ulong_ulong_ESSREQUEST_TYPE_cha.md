# CSsdpNotifyRequest::HrSendSubscriptionRequestAsync(void *,ushort const *,char const *,ulong,ulong,_ESSREQUEST_TYPE,char *)

- ea: `0x1800208ec`
- end: `0x180020f84`
- name: `?HrSendSubscriptionRequestAsync@CSsdpNotifyRequest@@QEAAJPEAXPEBGPEBDKKW4_ESSREQUEST_TYPE@@PEAD@Z`
- size: `1688`
- prototype: `__int64 __fastcall(DWORD_PTR, void *, const WCHAR *, const char *, unsigned int, int, int, const char *)`
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180014ec4`
- `0x1800207d0`

## callees

- `0x18000554c`
- `0x18000a418`
- `0x180017400`
- `0x18001e95c`
- `0x18001f87c`
- `0x1800208ec`
- `0x1800255a8`
- `0x180025e20`
- `0x180026a30`
- `0x18002735c`
- `0x180028000`
- `0x18002dcf4`
- `0x18002edf0`
- `0x18002ee3c`
- `0x18002ee9c`
- `0x18002ef14`
- `0x180035220`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002098b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020ed9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002098b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020ed9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800209a9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800209a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020ee9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020ee9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ad4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800209f5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180020a02`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800209f5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180020a02`
- `WS2_32!WSAAddressToStringA` at `0x180020c5e`
- `WS2_32!WSAAddressToStringA` at `0x180020c5e`
- `WS2_32!__imp_htons` at `0x180020c18`
- `WS2_32!__imp_htons` at `0x180020c18`
- `WS2_32!__imp_WSAGetLastError` at `0x180020cd3`
- `WS2_32!__imp_WSAGetLastError` at `0x180020d03`
- `WS2_32!__imp_WSAGetLastError` at `0x180020cd3`
- `WS2_32!__imp_WSAGetLastError` at `0x180020d03`
- `WINHTTP!WinHttpOpenRequest` at `0x180020b04`
- `WINHTTP!WinHttpOpenRequest` at `0x180020b04`
- `WINHTTP!WinHttpCrackUrl` at `0x180020a15`
- `WINHTTP!WinHttpCrackUrl` at `0x180020a15`
- `WINHTTP!WinHttpConnect` at `0x180020a65`
- `WINHTTP!WinHttpConnect` at `0x180020a65`
- `WINHTTP!WinHttpSetOption` at `0x180020b61`
- `WINHTTP!WinHttpSetOption` at `0x180020b61`
- `WINHTTP!WinHttpSendRequest` at `0x180020e9b`
- `WINHTTP!WinHttpSendRequest` at `0x180020e9b`

## string_xrefs

- `0x180020d29`: `SID: %s\n`
- `0x180020bb6`: `SID: %s\nTimeout: Second-%d\n`

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
  signed int v36; // eax
  LPCWSTR pwszReferrer; // [rsp+20h] [rbp-E0h]
  int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwAddressStringLength; // [rsp+44h] [rbp-BCh] BYREF
  const char *v40; // [rsp+48h] [rbp-B8h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-B0h] BYREF
  struct sockaddr saAddress; // [rsp+C0h] [rbp-40h] BYREF
  int v43; // [rsp+D8h] [rbp-28h]
  WCHAR pswzServerName[264]; // [rsp+140h] [rbp+40h] BYREF
  CHAR szAddressString[256]; // [rsp+350h] [rbp+250h] BYREF
  CHAR MultiByteStr[1024]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR pwszObjectName[2088]; // [rsp+850h] [rbp+750h] BYREF

  v40 = a8;
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
            v26 = v43;
            dwAddressStringLength = 256;
            if ( saAddress.sa_family == 23 )
              v26 = 0;
            v43 = v26;
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
                      v40,
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
  {
    LODWORD(pwszReferrer) = LocalIpAddress;
    WPP_SF_Dd(
      *((_QWORD *)v18 + 2),
      131,
      WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
      (unsigned int)LocalIpAddress,
      pwszReferrer);
  }
  return (unsigned int)LocalIpAddress;
}

```

## disassembly

```asm
0x1800208ec  push    rbp
0x1800208ee  push    rbx
0x1800208ef  push    rsi
0x1800208f0  push    rdi
0x1800208f1  push    r12
0x1800208f3  push    r13
0x1800208f5  push    r14
0x1800208f7  push    r15
0x1800208f9  lea     rbp, [rsp-17B8h]
0x180020901  mov     eax, 18B8h
0x180020906  call    _alloca_probe
0x18002090b  sub     rsp, rax
0x18002090e  mov     rax, cs:__security_cookie
0x180020915  xor     rax, rsp
0x180020918  mov     [rbp+17F0h+var_50], rax
0x18002091f  mov     rbx, [rbp+17F0h+arg_38]
0x180020926  mov     r12, r8
0x180020929  mov     r13, rdx
0x18002092c  mov     [rsp+18F0h+var_18A8], rbx
0x180020931  mov     r14, rcx
0x180020934  mov     esi, 68h ; 'h'
0x180020939  mov     r8d, esi; Size
0x18002093c  lea     rcx, [rsp+18F0h+UrlComponents]; void *
0x180020941  xor     edx, edx; Val
0x180020943  mov     r15, r9
0x180020946  call    memset_0
0x18002094b  xor     eax, eax
0x18002094d  mov     [rbp+17F0h+pswzServerName], ax
0x180020951  mov     [rbp+17F0h+pwszObjectName], ax
0x180020958  mov     eax, [rbp+17F0h+arg_30]
0x18002095e  test    eax, eax
0x180020960  jnz     short loc_180020971
0x180020962  test    rbx, rbx
0x180020965  jnz     short loc_180020971
0x180020967  mov     eax, 80004005h
0x18002096c  jmp     loc_180020F61
0x180020971  xor     edi, edi
0x180020973  mov     [r14+178h], eax
0x18002097a  test    r15, r15
0x18002097d  jz      short loc_1800209C7
0x18002097f  mov     rcx, [r14+150h]; Block
0x180020986  test    rcx, rcx
0x180020989  jz      short loc_180020998
0x18002098b  call    cs:__imp_free
0x180020991  mov     [r14+150h], rdi
0x180020998  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002099c  inc     rbx
0x18002099f  cmp     [r15+rbx], dil
0x1800209a3  jnz     short loc_18002099C
0x1800209a5  lea     rcx, [rbx+1]; Size
0x1800209a9  call    cs:__imp_malloc
0x1800209af  mov     r8, r15; char *
0x1800209b2  lea     rdx, [rbx+1]; unsigned __int64
0x1800209b6  mov     rcx, rax; char *
0x1800209b9  mov     [r14+150h], rax
0x1800209c0  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800209c5  mov     edi, eax
0x1800209c7  mov     rcx, [r14+138h]; hEvent
0x1800209ce  lea     rax, [rbp+17F0h+pswzServerName]
0x1800209d2  mov     [rsp+18F0h+UrlComponents.lpszHostName], rax
0x1800209d7  lea     rax, [rbp+17F0h+pwszObjectName]
0x1800209de  mov     [rbp+17F0h+UrlComponents.lpszUrlPath], rax
0x1800209e2  mov     [rsp+18F0h+UrlComponents.dwStructSize], esi
0x1800209e6  mov     [rsp+18F0h+UrlComponents.dwHostNameLength], 100h
0x1800209ee  mov     [rbp+17F0h+UrlComponents.dwUrlPathLength], 824h
0x1800209f5  call    cs:__imp_ResetEvent
0x1800209fb  mov     rcx, [r14+140h]; hEvent
0x180020a02  call    cs:__imp_ResetEvent
0x180020a08  lea     r9, [rsp+18F0h+UrlComponents]; lpUrlComponents
0x180020a0d  xor     r8d, r8d; dwFlags
0x180020a10  xor     edx, edx; dwUrlLength
0x180020a12  mov     rcx, r12; pwszUrl
0x180020a15  call    cs:__imp_WinHttpCrackUrl
0x180020a1b  test    eax, eax
0x180020a1d  jz      loc_180020EF1
0x180020a23  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a2a  lea     rsi, WPP_GLOBAL_Control
0x180020a31  cmp     rcx, rsi
0x180020a34  jz      short loc_180020A55
0x180020a36  test    byte ptr [rcx+1Ch], 8
0x180020a3a  jz      short loc_180020A55
0x180020a3c  mov     rcx, [rcx+10h]
0x180020a40  lea     r9, [rbp+17F0h+pswzServerName]
0x180020a44  mov     edx, 76h ; 'v'
0x180020a49  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180020a50  call    WPP_SF_S
0x180020a55  movzx   r8d, [rsp+18F0h+UrlComponents.nPort]; nServerPort
0x180020a5b  lea     rdx, [rbp+17F0h+pswzServerName]; pswzServerName
0x180020a5f  xor     r9d, r9d; dwReserved
0x180020a62  mov     rcx, r13; hSession
0x180020a65  call    cs:__imp_WinHttpConnect
0x180020a6b  mov     [r14+100h], rax
0x180020a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a79  cmp     rcx, rsi
0x180020a7c  jz      short loc_180020AA0
0x180020a7e  test    byte ptr [rcx+1Ch], 8
0x180020a82  jz      short loc_180020AA0
0x180020a84  mov     rcx, [rcx+10h]
0x180020a88  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180020a8f  mov     edx, 77h ; 'w'
0x180020a94  call    WPP_SF_
0x180020a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180020aa0  xor     r13d, r13d
0x180020aa3  cmp     [r14+100h], r13
0x180020aaa  jz      loc_180020F34
0x180020ab0  cmp     dword ptr [r14+178h], 2
0x180020ab8  lea     rax, pwszVerb; "SUBSCRIBE"
0x180020abf  lea     r12, [r14+110h]
0x180020ac6  lea     rbx, aUnsubscribe_1; "UNSUBSCRIBE"
0x180020acd  mov     rcx, r12; lpCriticalSection
0x180020ad0  cmovnz  rbx, rax
0x180020ad4  call    cs:__imp_EnterCriticalSection
0x180020ada  mov     rcx, [r14+100h]; hConnect
0x180020ae1  lea     r9, pwszVersion; "HTTP/1.1"
0x180020ae8  mov     [rsp+18F0h+dwFlags], 100h; dwFlags
0x180020af0  lea     r8, [rbp+17F0h+pwszObjectName]; pwszObjectName
0x180020af7  mov     [rsp+18F0h+ppwszAcceptTypes], r13; ppwszAcceptTypes
0x180020afc  mov     rdx, rbx; pwszVerb
0x180020aff  mov     [rsp+18F0h+pwszReferrer], r13; pwszReferrer
0x180020b04  call    cs:__imp_WinHttpOpenRequest
0x180020b0a  mov     [r14+108h], rax
0x180020b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b18  lea     rbx, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180020b1f  cmp     rcx, rsi
0x180020b22  jz      short loc_180020B3A
0x180020b24  test    byte ptr [rcx+1Ch], 8
0x180020b28  jz      short loc_180020B3A
0x180020b2a  mov     rcx, [rcx+10h]
0x180020b2e  lea     edx, [r13+78h]
0x180020b32  mov     r8, rbx
0x180020b35  call    WPP_SF_
0x180020b3a  mov     rcx, [r14+108h]; hInternet
0x180020b41  test    rcx, rcx
0x180020b44  jz      loc_180020EE6
0x180020b4a  mov     r9d, 4; dwBufferLength
0x180020b50  mov     [rsp+18F0h+Buffer], 8
0x180020b58  lea     r8, [rsp+18F0h+Buffer]; lpBuffer
0x180020b5d  lea     edx, [r9+3Bh]; dwOption
0x180020b61  call    cs:__imp_WinHttpSetOption
0x180020b67  test    eax, eax
0x180020b69  jnz     short loc_180020B9D
0x180020b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b72  cmp     rcx, rsi
0x180020b75  jz      short loc_180020BA4
0x180020b77  test    byte ptr [rcx+1Ch], 1
0x180020b7b  jz      short loc_180020BA4
0x180020b7d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180020b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b89  mov     edx, 79h ; 'y'
0x180020b8e  mov     r9d, eax
0x180020b91  mov     r8, rbx
0x180020b94  mov     rcx, [rcx+10h]
0x180020b98  call    WPP_SF_d
0x180020b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ba4  mov     eax, [r14+178h]
0x180020bab  cmp     eax, 1
0x180020bae  jnz     short loc_180020BDA
0x180020bb0  mov     eax, [rbp+17F0h+arg_28]
0x180020bb6  lea     r8, aSidSTimeoutSec; "SID: %s\r\nTimeout: Second-%d\r\n"
0x180020bbd  mov     r9, r15
0x180020bc0  mov     dword ptr [rsp+18F0h+pwszReferrer], eax
0x180020bc4  mov     edx, 400h; unsigned __int64
0x180020bc9  lea     rcx, [rbp+17F0h+MultiByteStr]; char *
0x180020bd0  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180020bd5  jmp     loc_180020D41
0x180020bda  test    eax, eax
0x180020bdc  jnz     loc_180020D21
0x180020be2  xor     edx, edx; Val
0x180020be4  mov     [rbp+17F0h+var_15B0], r13w
0x180020bec  mov     r8d, 80h; Size
0x180020bf2  lea     rcx, [rbp+17F0h+saAddress]; void *
0x180020bf6  call    memset_0
0x180020bfb  mov     edx, [rbp+17F0h+arg_20]; unsigned int
0x180020c01  lea     r8, [rbp+17F0h+saAddress]; struct sockaddr *
0x180020c05  lea     rcx, [rbp+17F0h+pswzServerName]; unsigned __int16 *
0x180020c09  call    ?GetLocalIpAddress@@YAJPEAGKPEAUsockaddr@@@Z; GetLocalIpAddress(ushort *,ulong,sockaddr *)
0x180020c0e  mov     edi, eax
0x180020c10  call    ?GetEventingPort@@YAGXZ; GetEventingPort(void)
0x180020c15  movzx   ecx, ax; hostshort
0x180020c18  call    cs:__imp_htons
0x180020c1e  mov     word ptr [rbp+17F0h+saAddress.sa_data], ax
0x180020c22  test    edi, edi
0x180020c24  js      loc_180020D41
0x180020c2a  mov     ecx, [rbp+17F0h+var_1818]
0x180020c2d  lea     rax, [rsp+18F0h+dwAddressStringLength]
0x180020c32  cmp     [rbp+17F0h+saAddress.sa_family], 17h
0x180020c37  lea     r9, [rbp+17F0h+szAddressString]; lpszAddressString
0x180020c3e  mov     edx, 80h; dwAddressLength
0x180020c43  mov     [rsp+18F0h+dwAddressStringLength], 100h
0x180020c4b  cmovz   ecx, r13d
0x180020c4f  mov     [rsp+18F0h+pwszReferrer], rax; lpdwAddressStringLength
0x180020c54  mov     [rbp+17F0h+var_1818], ecx
0x180020c57  xor     r8d, r8d; lpProtocolInfo
0x180020c5a  lea     rcx, [rbp+17F0h+saAddress]; lpsaAddress
0x180020c5e  call    cs:__imp_WSAAddressToStringA
0x180020c64  test    eax, eax
0x180020c66  jnz     short loc_180020CD3
0x180020c68  mov     rax, [rsp+18F0h+var_18A8]
0x180020c6d  lea     r9, [rbp+17F0h+szAddressString]
0x180020c74  mov     dword ptr [rsp+18F0h+ppwszAcceptTypes], 708h
0x180020c7c  lea     r8, aNtUpnpEventCal; "NT: upnp:event\r\nCallback: <http://%s/"...
0x180020c83  mov     edx, 400h; unsigned __int64
0x180020c88  mov     [rsp+18F0h+pwszReferrer], rax
0x180020c8d  lea     rcx, [rbp+17F0h+MultiByteStr]; char *
0x180020c94  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180020c99  mov     edi, eax
0x180020c9b  test    eax, eax
0x180020c9d  jns     loc_180020D41
0x180020ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180020caa  cmp     rcx, rsi
0x180020cad  jz      loc_180020EE6
0x180020cb3  test    byte ptr [rcx+1Ch], 1
0x180020cb7  jz      loc_180020D48
0x180020cbd  mov     edx, 7Ah ; 'z'
0x180020cc2  mov     rcx, [rcx+10h]
0x180020cc6  mov     r8, rbx
0x180020cc9  mov     r9d, eax
0x180020ccc  call    WPP_SF_d
0x180020cd1  jmp     short loc_180020D41
0x180020cd3  call    cs:__imp_WSAGetLastError
0x180020cd9  mov     r15d, 80070000h
0x180020cdf  test    eax, eax
0x180020ce1  jle     short loc_180020CEB
0x180020ce3  movzx   eax, ax
0x180020ce6  or      eax, r15d
0x180020ce9  test    eax, eax
0x180020ceb  jz      short loc_180020D41
0x180020ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cf4  cmp     rcx, rsi
0x180020cf7  jz      loc_180020E4F
0x180020cfd  test    byte ptr [rcx+1Ch], 1
0x180020d01  jz      short loc_180020D48
0x180020d03  call    cs:__imp_WSAGetLastError
0x180020d09  test    eax, eax
0x180020d0b  jle     short loc_180020D13
0x180020d0d  movzx   eax, ax
0x180020d10  or      eax, r15d
0x180020d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d1a  mov     edx, 7Bh ; '{'
0x180020d1f  jmp     short loc_180020CC2
0x180020d21  cmp     eax, 2
0x180020d24  jnz     short loc_180020D48
0x180020d26  mov     r9, r15
0x180020d29  lea     r8, aSidS; "SID: %s\r\n"
0x180020d30  mov     edx, 400h; unsigned __int64
0x180020d35  lea     rcx, [rbp+17F0h+MultiByteStr]; char *
0x180020d3c  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180020d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d48  cmp     rcx, rsi
0x180020d4b  jz      loc_180020E47
0x180020d51  test    byte ptr [rcx+1Ch], 8
0x180020d55  jz      short loc_180020D80
0x180020d57  movzx   eax, [rsp+18F0h+UrlComponents.nPort]
0x180020d5c  lea     rdx, [rbp+17F0h+pwszObjectName]
0x180020d63  mov     rcx, [rcx+10h]
0x180020d67  lea     r9, [rbp+17F0h+pswzServerName]
0x180020d6b  mov     [rsp+18F0h+ppwszAcceptTypes], rdx
0x180020d70  mov     dword ptr [rsp+18F0h+pwszReferrer], eax
0x180020d74  call    WPP_SF_SdS
0x180020d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d80  cmp     rcx, rsi
0x180020d83  jz      loc_180020E47
0x180020d89  test    byte ptr [rcx+1Ch], 8
0x180020d8d  jz      short loc_180020DDE
0x180020d8f  mov     eax, [r14+178h]
0x180020d96  test    eax, eax
0x180020d98  jnz     short loc_180020DA3
0x180020d9a  lea     r9, aSubscription; "subscription"
0x180020da1  jmp     short loc_180020DC6
0x180020da3  cmp     eax, 1
0x180020da6  jnz     short loc_180020DB1
0x180020da8  lea     r9, aReSubscription; "re-subscription"
0x180020daf  jmp     short loc_180020DC6
0x180020db1  cmp     eax, 2
0x180020db4  lea     r9, aUnsubscribe; "unsubscribe"
0x180020dbb  lea     rdx, aUnknown_0; "Unknown!"
0x180020dc2  cmovnz  r9, rdx
0x180020dc6  mov     rcx, [rcx+10h]
0x180020dca  mov     edx, 7Dh ; '}'
0x180020dcf  mov     r8, rbx
0x180020dd2  call    WPP_SF_s
0x180020dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dde  cmp     rcx, rsi
0x180020de1  jz      short loc_180020E47
0x180020de3  test    byte ptr [rcx+1Ch], 8
0x180020de7  jz      short loc_180020E01
0x180020de9  mov     rcx, [rcx+10h]
0x180020ded  mov     edx, 7Eh ; '~'
0x180020df2  mov     r8, rbx
0x180020df5  call    WPP_SF_
0x180020dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e01  cmp     rcx, rsi
0x180020e04  jz      short loc_180020E47
0x180020e06  test    byte ptr [rcx+1Ch], 8
0x180020e0a  jz      short loc_180020E2B
0x180020e0c  mov     rcx, [rcx+10h]
0x180020e10  lea     r9, [rbp+17F0h+MultiByteStr]
0x180020e17  mov     edx, 7Fh
0x180020e1c  mov     r8, rbx
0x180020e1f  call    WPP_SF_s
  ... truncated ...
```
