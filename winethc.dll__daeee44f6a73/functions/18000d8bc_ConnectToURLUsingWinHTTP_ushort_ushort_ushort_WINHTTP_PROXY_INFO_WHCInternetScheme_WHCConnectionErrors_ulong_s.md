# ConnectToURLUsingWinHTTP(ushort *,ushort *,ushort,_WINHTTP_PROXY_INFO *,WHCInternetScheme,WHCConnectionErrors *,ulong *,sockaddr *)

- ea: `0x18000d8bc`
- end: `0x18000dd4e`
- name: `?ConnectToURLUsingWinHTTP@@YAJPEAG0GPEAU_WINHTTP_PROXY_INFO@@W4WHCInternetScheme@@PEAW4WHCConnectionErrors@@PEAKPEAUsockaddr@@@Z`
- size: `1170`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f710`

## callees

- `0x18000d8bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d943`
- `KERNEL32!GetLastError` at `0x18000d991`
- `KERNEL32!GetLastError` at `0x18000d9e2`
- `KERNEL32!GetLastError` at `0x18000da83`
- `KERNEL32!GetLastError` at `0x18000daee`
- `KERNEL32!GetLastError` at `0x18000db38`
- `KERNEL32!GetLastError` at `0x18000db83`
- `KERNEL32!GetLastError` at `0x18000dbda`
- `KERNEL32!GetLastError` at `0x18000dc12`
- `KERNEL32!GetLastError` at `0x18000dc63`
- `KERNEL32!GetLastError` at `0x18000d943`
- `KERNEL32!GetLastError` at `0x18000d991`
- `KERNEL32!GetLastError` at `0x18000d9e2`
- `KERNEL32!GetLastError` at `0x18000da83`
- `KERNEL32!GetLastError` at `0x18000daee`
- `KERNEL32!GetLastError` at `0x18000db38`
- `KERNEL32!GetLastError` at `0x18000db83`
- `KERNEL32!GetLastError` at `0x18000dbda`
- `KERNEL32!GetLastError` at `0x18000dc12`
- `KERNEL32!GetLastError` at `0x18000dc63`
- `WINHTTP!WinHttpReceiveResponse` at `0x18000dc02`
- `WINHTTP!WinHttpReceiveResponse` at `0x18000dc02`
- `WINHTTP!WinHttpConnect` at `0x18000da6f`
- `WINHTTP!WinHttpConnect` at `0x18000da6f`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18000da56`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18000da56`
- `WINHTTP!WinHttpCloseHandle` at `0x18000dcff`
- `WINHTTP!WinHttpCloseHandle` at `0x18000dd13`
- `WINHTTP!WinHttpCloseHandle` at `0x18000dd27`
- `WINHTTP!WinHttpCloseHandle` at `0x18000dcff`
- `WINHTTP!WinHttpCloseHandle` at `0x18000dd13`
- `WINHTTP!WinHttpCloseHandle` at `0x18000dd27`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000dc53`
- `WINHTTP!WinHttpQueryHeaders` at `0x18000dc53`
- `WINHTTP!WinHttpSendRequest` at `0x18000dbca`
- `WINHTTP!WinHttpSendRequest` at `0x18000dbca`
- `WINHTTP!WinHttpOpen` at `0x18000d92b`
- `WINHTTP!WinHttpOpen` at `0x18000d92b`
- `WINHTTP!WinHttpSetOption` at `0x18000d981`
- `WINHTTP!WinHttpSetOption` at `0x18000d9d2`
- `WINHTTP!WinHttpSetOption` at `0x18000da35`
- `WINHTTP!WinHttpSetOption` at `0x18000db28`
- `WINHTTP!WinHttpSetOption` at `0x18000db73`
- `WINHTTP!WinHttpSetOption` at `0x18000d981`
- `WINHTTP!WinHttpSetOption` at `0x18000d9d2`
- `WINHTTP!WinHttpSetOption` at `0x18000da35`
- `WINHTTP!WinHttpSetOption` at `0x18000db28`
- `WINHTTP!WinHttpSetOption` at `0x18000db73`
- `WINHTTP!WinHttpOpenRequest` at `0x18000dada`
- `WINHTTP!WinHttpOpenRequest` at `0x18000dada`

## pseudocode

```c
__int64 __fastcall ConnectToURLUsingWinHTTP(
        const WCHAR *a1,
        __int64 a2,
        INTERNET_PORT a3,
        _QWORD *a4,
        int a5,
        int *a6,
        _DWORD *a7,
        _BYTE *a8)
{
  int *v11; // rdi
  signed int v12; // ebx
  void *v13; // r14
  void *v14; // r12
  signed int LastError; // eax
  signed int v16; // eax
  signed int v17; // eax
  _BYTE *v18; // rax
  __int64 v19; // rcx
  void *v20; // rsi
  signed int v21; // eax
  DWORD v22; // ecx
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  bool v27; // sf
  signed int v28; // eax
  int v29; // eax
  int v30; // eax
  int v32; // [rsp+40h] [rbp-28h] BYREF
  int Buffer; // [rsp+44h] [rbp-24h] BYREF
  int v34; // [rsp+48h] [rbp-20h] BYREF
  DWORD dwBufferLength[6]; // [rsp+50h] [rbp-18h] BYREF
  int v36; // [rsp+B0h] [rbp+48h] BYREF

  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  v11 = a6;
  if ( !a6 || !a7 || !a4 )
    return 2147942487LL;
  *a6 = 0;
  v36 = 0;
  v12 = 0;
  v13 = 0;
  v14 = WinHttpOpen(L"Microsoft Windows Network Diagnostics", 0, 0, 0, 0);
  if ( !v14 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_59;
  }
  Buffer = 10000;
  if ( !WinHttpSetOption(v14, 3u, &Buffer, 4u) )
  {
    v16 = GetLastError();
    v12 = v16;
    if ( v16 > 0 )
      v12 = (unsigned __int16)v16 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_59;
  }
  BYTE2(v36) = 0;
  LOWORD(v36) = 1000;
  if ( !WinHttpSetOption(v14, 0x71u, &v36, 4u) )
  {
    v17 = GetLastError();
    v12 = v17;
    if ( v17 > 0 )
      v12 = (unsigned __int16)v17 | 0x80070000;
    if ( v12 < 0 )
    {
LABEL_59:
      v20 = 0;
LABEL_60:
      switch ( v12 )
      {
        case -2147012894:
          *v11 = 4;
          break;
        case -2147012891:
          *v11 = 7;
          break;
        case -2147012889:
          *v11 = 5;
          break;
        default:
          v30 = 3;
          if ( v12 != -2147012867 )
            v30 = 1;
          *v11 = v30;
          break;
      }
      goto LABEL_69;
    }
  }
  v18 = a8;
  if ( a8 )
  {
    v19 = 16;
    do
    {
      *v18++ = 0;
      --v19;
    }
    while ( v19 );
    if ( WinHttpSetOption(v14, 0x2Du, &a8, 8u) )
      WinHttpSetStatusCallback(v14, WinHttpCallback, 2u, 0);
  }
  v20 = WinHttpConnect(v14, a1, a3, 0);
  if ( !v20 )
  {
    v21 = GetLastError();
    v12 = v21;
    if ( v21 > 0 )
      v12 = (unsigned __int16)v21 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_60;
  }
  v22 = 0x800000;
  if ( a5 != 1 )
    v22 = 0;
  v13 = WinHttpOpenRequest(v20, L"GET", L"/", 0, 0, 0, v22);
  if ( !v13 )
  {
    v23 = GetLastError();
    v12 = v23;
    if ( v23 > 0 )
      v12 = (unsigned __int16)v23 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_60;
  }
  if ( a4[1] && !WinHttpSetOption(v13, 0x26u, a4, 0x18u) )
  {
    v24 = GetLastError();
    v12 = v24;
    if ( v24 > 0 )
      v12 = (unsigned __int16)v24 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_60;
  }
  v34 = 13056;
  if ( !WinHttpSetOption(v13, 0x1Fu, &v34, 4u) )
  {
    v25 = GetLastError();
    v12 = v25;
    if ( v25 > 0 )
      v12 = (unsigned __int16)v25 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_60;
  }
  if ( !WinHttpSendRequest(v13, 0, 0, 0, 0, 0, 0) )
  {
    v26 = GetLastError();
    v12 = v26;
    if ( v26 > 0 )
      v12 = (unsigned __int16)v26 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_60;
  }
  if ( WinHttpReceiveResponse(v13, 0) )
  {
    v32 = 0;
    dwBufferLength[0] = 4;
    if ( WinHttpQueryHeaders(v13, 0x20000013u, 0, &v32, dwBufferLength, 0) )
    {
      v29 = v32;
      *a7 = v32;
      if ( v29 == 403 )
        *v11 = 6;
      if ( v29 == 502 )
        *v11 = 8;
      goto LABEL_69;
    }
    v28 = GetLastError();
    v12 = v28;
    if ( v28 > 0 )
      v12 = (unsigned __int16)v28 | 0x80070000;
    v27 = v12 < 0;
  }
  else
  {
    v12 = GetLastError();
    v27 = v12 < 0;
  }
  if ( v27 )
    goto LABEL_60;
LABEL_69:
  if ( v13 )
    WinHttpCloseHandle(v13);
  if ( v20 )
    WinHttpCloseHandle(v20);
  if ( v14 )
    WinHttpCloseHandle(v14);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d8bc  push    rbp
0x18000d8be  push    rbx
0x18000d8bf  push    rsi
0x18000d8c0  push    rdi
0x18000d8c1  push    r12
0x18000d8c3  push    r13
0x18000d8c5  push    r14
0x18000d8c7  push    r15
0x18000d8c9  mov     rbp, rsp
0x18000d8cc  sub     rsp, 68h
0x18000d8d0  xor     eax, eax
0x18000d8d2  mov     r15, r9
0x18000d8d5  movzx   r13d, r8w
0x18000d8d9  mov     rsi, rcx
0x18000d8dc  test    rcx, rcx
0x18000d8df  jz      loc_18000DD37
0x18000d8e5  test    rdx, rdx
0x18000d8e8  jz      loc_18000DD37
0x18000d8ee  mov     rdi, [rbp+arg_28]
0x18000d8f2  test    rdi, rdi
0x18000d8f5  jz      loc_18000DD37
0x18000d8fb  cmp     [rbp+arg_30], rax
0x18000d8ff  jz      loc_18000DD37
0x18000d905  test    r9, r9
0x18000d908  jz      loc_18000DD37
0x18000d90e  xor     r9d, r9d; pszProxyBypassW
0x18000d911  mov     [rdi], eax
0x18000d913  xor     r8d, r8d; pszProxyW
0x18000d916  mov     [rbp+arg_0], eax
0x18000d919  xor     edx, edx; dwAccessType
0x18000d91b  mov     [rsp+68h+dwFlags], eax; dwFlags
0x18000d91f  lea     rcx, pszAgentW; "Microsoft Windows Network Diagnostics"
0x18000d926  mov     ebx, eax
0x18000d928  mov     r14d, eax
0x18000d92b  call    cs:__imp_WinHttpOpen
0x18000d932  nop     dword ptr [rax+rax+00h]
0x18000d937  mov     r12, rax
0x18000d93a  lea     eax, [r14+3]
0x18000d93e  test    r12, r12
0x18000d941  jnz     short loc_18000D96B
0x18000d943  call    cs:__imp_GetLastError
0x18000d94a  nop     dword ptr [rax+rax+00h]
0x18000d94f  mov     ebx, eax
0x18000d951  test    eax, eax
0x18000d953  jle     short loc_18000D95E
0x18000d955  movzx   ebx, ax
0x18000d958  or      ebx, 80070000h
0x18000d95e  test    ebx, ebx
0x18000d960  js      loc_18000DCAD
0x18000d966  mov     eax, 3
0x18000d96b  mov     r9d, 4; dwBufferLength
0x18000d971  mov     [rbp+Buffer], 2710h
0x18000d978  lea     r8, [rbp+Buffer]; lpBuffer
0x18000d97c  mov     edx, eax; dwOption
0x18000d97e  mov     rcx, r12; hInternet
0x18000d981  call    cs:__imp_WinHttpSetOption
0x18000d988  nop     dword ptr [rax+rax+00h]
0x18000d98d  test    eax, eax
0x18000d98f  jnz     short loc_18000D9B4
0x18000d991  call    cs:__imp_GetLastError
0x18000d998  nop     dword ptr [rax+rax+00h]
0x18000d99d  mov     ebx, eax
0x18000d99f  test    eax, eax
0x18000d9a1  jle     short loc_18000D9AC
0x18000d9a3  movzx   ebx, ax
0x18000d9a6  or      ebx, 80070000h
0x18000d9ac  test    ebx, ebx
0x18000d9ae  js      loc_18000DCAD
0x18000d9b4  mov     r9d, 4; dwBufferLength
0x18000d9ba  mov     byte ptr [rbp+arg_0+2], r14b
0x18000d9be  mov     eax, 3E8h
0x18000d9c3  lea     r8, [rbp+arg_0]; lpBuffer
0x18000d9c7  mov     rcx, r12; hInternet
0x18000d9ca  mov     word ptr [rbp+arg_0], ax
0x18000d9ce  lea     edx, [r9+6Dh]; dwOption
0x18000d9d2  call    cs:__imp_WinHttpSetOption
0x18000d9d9  nop     dword ptr [rax+rax+00h]
0x18000d9de  test    eax, eax
0x18000d9e0  jnz     short loc_18000DA05
0x18000d9e2  call    cs:__imp_GetLastError
0x18000d9e9  nop     dword ptr [rax+rax+00h]
0x18000d9ee  mov     ebx, eax
0x18000d9f0  test    eax, eax
0x18000d9f2  jle     short loc_18000D9FD
0x18000d9f4  movzx   ebx, ax
0x18000d9f7  or      ebx, 80070000h
0x18000d9fd  test    ebx, ebx
0x18000d9ff  js      loc_18000DCAD
0x18000da05  mov     rax, [rbp+arg_38]
0x18000da0c  test    rax, rax
0x18000da0f  jz      short loc_18000DA62
0x18000da11  mov     ecx, 10h
0x18000da16  lea     edx, [rcx-0Fh]
0x18000da19  mov     [rax], r14b
0x18000da1c  add     rax, rdx
0x18000da1f  sub     rcx, rdx
0x18000da22  jnz     short loc_18000DA19
0x18000da24  lea     r9d, [rcx+8]; dwBufferLength
0x18000da28  lea     edx, [rcx+2Dh]; dwOption
0x18000da2b  mov     rcx, r12; hInternet
0x18000da2e  lea     r8, [rbp+arg_38]; lpBuffer
0x18000da35  call    cs:__imp_WinHttpSetOption
0x18000da3c  nop     dword ptr [rax+rax+00h]
0x18000da41  test    eax, eax
0x18000da43  jz      short loc_18000DA62
0x18000da45  xor     r9d, r9d; dwReserved
0x18000da48  lea     rdx, ?WinHttpCallback@@YAXPEAX_KK0K@Z; lpfnInternetCallback
0x18000da4f  mov     rcx, r12; hInternet
0x18000da52  lea     r8d, [r9+2]; dwNotificationFlags
0x18000da56  call    cs:__imp_WinHttpSetStatusCallback
0x18000da5d  nop     dword ptr [rax+rax+00h]
0x18000da62  xor     r9d, r9d; dwReserved
0x18000da65  movzx   r8d, r13w; nServerPort
0x18000da69  mov     rdx, rsi; pswzServerName
0x18000da6c  mov     rcx, r12; hSession
0x18000da6f  call    cs:__imp_WinHttpConnect
0x18000da76  nop     dword ptr [rax+rax+00h]
0x18000da7b  mov     rsi, rax
0x18000da7e  test    rax, rax
0x18000da81  jnz     short loc_18000DAA6
0x18000da83  call    cs:__imp_GetLastError
0x18000da8a  nop     dword ptr [rax+rax+00h]
0x18000da8f  mov     ebx, eax
0x18000da91  test    eax, eax
0x18000da93  jle     short loc_18000DA9E
0x18000da95  movzx   ebx, ax
0x18000da98  or      ebx, 80070000h
0x18000da9e  test    ebx, ebx
0x18000daa0  js      loc_18000DCB0
0x18000daa6  xor     eax, eax
0x18000daa8  lea     r8, pwszObjectName; "/"
0x18000daaf  mov     ecx, 800000h
0x18000dab4  lea     rdx, pwszVerb; "GET"
0x18000dabb  lea     r13d, [rax+1]
0x18000dabf  cmp     [rbp+arg_20], r13d
0x18000dac3  cmovnz  ecx, eax
0x18000dac6  xor     r9d, r9d; pwszVersion
0x18000dac9  mov     [rsp+68h+var_38], ecx; dwFlags
0x18000dacd  mov     rcx, rsi; hConnect
0x18000dad0  mov     [rsp+68h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x18000dad5  mov     qword ptr [rsp+68h+dwFlags], rax; pwszReferrer
0x18000dada  call    cs:__imp_WinHttpOpenRequest
0x18000dae1  nop     dword ptr [rax+rax+00h]
0x18000dae6  mov     r14, rax
0x18000dae9  test    rax, rax
0x18000daec  jnz     short loc_18000DB11
0x18000daee  call    cs:__imp_GetLastError
0x18000daf5  nop     dword ptr [rax+rax+00h]
0x18000dafa  mov     ebx, eax
0x18000dafc  test    eax, eax
0x18000dafe  jle     short loc_18000DB09
0x18000db00  movzx   ebx, ax
0x18000db03  or      ebx, 80070000h
0x18000db09  test    ebx, ebx
0x18000db0b  js      loc_18000DCB6
0x18000db11  cmp     qword ptr [r15+8], 0
0x18000db16  jz      short loc_18000DB5B
0x18000db18  mov     r9d, 18h; dwBufferLength
0x18000db1e  mov     r8, r15; lpBuffer
0x18000db21  mov     rcx, r14; hInternet
0x18000db24  lea     edx, [r9+0Eh]; dwOption
0x18000db28  call    cs:__imp_WinHttpSetOption
0x18000db2f  nop     dword ptr [rax+rax+00h]
0x18000db34  test    eax, eax
0x18000db36  jnz     short loc_18000DB5B
0x18000db38  call    cs:__imp_GetLastError
0x18000db3f  nop     dword ptr [rax+rax+00h]
0x18000db44  mov     ebx, eax
0x18000db46  test    eax, eax
0x18000db48  jle     short loc_18000DB53
0x18000db4a  movzx   ebx, ax
0x18000db4d  or      ebx, 80070000h
0x18000db53  test    ebx, ebx
0x18000db55  js      loc_18000DCB6
0x18000db5b  mov     r9d, 4; dwBufferLength
0x18000db61  mov     [rbp+var_20], 3300h
0x18000db68  lea     r8, [rbp+var_20]; lpBuffer
0x18000db6c  mov     rcx, r14; hInternet
0x18000db6f  lea     edx, [r9+1Bh]; dwOption
0x18000db73  call    cs:__imp_WinHttpSetOption
0x18000db7a  nop     dword ptr [rax+rax+00h]
0x18000db7f  test    eax, eax
0x18000db81  jnz     short loc_18000DBA6
0x18000db83  call    cs:__imp_GetLastError
0x18000db8a  nop     dword ptr [rax+rax+00h]
0x18000db8f  mov     ebx, eax
0x18000db91  test    eax, eax
0x18000db93  jle     short loc_18000DB9E
0x18000db95  movzx   ebx, ax
0x18000db98  or      ebx, 80070000h
0x18000db9e  test    ebx, ebx
0x18000dba0  js      loc_18000DCB6
0x18000dba6  mov     qword ptr [rsp+68h+var_38], 0; dwContext
0x18000dbaf  xor     r9d, r9d; lpOptional
0x18000dbb2  mov     dword ptr [rsp+68h+ppwszAcceptTypes], 0; dwTotalLength
0x18000dbba  xor     r8d, r8d; dwHeadersLength
0x18000dbbd  xor     edx, edx; lpszHeaders
0x18000dbbf  mov     [rsp+68h+dwFlags], 0; dwOptionalLength
0x18000dbc7  mov     rcx, r14; hRequest
0x18000dbca  call    cs:__imp_WinHttpSendRequest
0x18000dbd1  nop     dword ptr [rax+rax+00h]
0x18000dbd6  test    eax, eax
0x18000dbd8  jnz     short loc_18000DBFD
0x18000dbda  call    cs:__imp_GetLastError
0x18000dbe1  nop     dword ptr [rax+rax+00h]
0x18000dbe6  mov     ebx, eax
0x18000dbe8  test    eax, eax
0x18000dbea  jle     short loc_18000DBF5
0x18000dbec  movzx   ebx, ax
0x18000dbef  or      ebx, 80070000h
0x18000dbf5  test    ebx, ebx
0x18000dbf7  js      loc_18000DCB6
0x18000dbfd  xor     edx, edx; lpReserved
0x18000dbff  mov     rcx, r14; hRequest
0x18000dc02  call    cs:__imp_WinHttpReceiveResponse
0x18000dc09  nop     dword ptr [rax+rax+00h]
0x18000dc0e  test    eax, eax
0x18000dc10  jnz     short loc_18000DC24
0x18000dc12  call    cs:__imp_GetLastError
0x18000dc19  nop     dword ptr [rax+rax+00h]
0x18000dc1e  mov     ebx, eax
0x18000dc20  test    eax, eax
0x18000dc22  jmp     short loc_18000DC80
0x18000dc24  lea     rax, [rbp+dwBufferLength]
0x18000dc28  mov     [rsp+68h+ppwszAcceptTypes], 0; lpdwIndex
0x18000dc31  lea     r9, [rbp+var_28]; lpBuffer
0x18000dc35  mov     qword ptr [rsp+68h+dwFlags], rax; lpdwBufferLength
0x18000dc3a  xor     r8d, r8d; pwszName
0x18000dc3d  mov     [rbp+var_28], 0
0x18000dc44  mov     edx, 20000013h; dwInfoLevel
0x18000dc49  mov     [rbp+dwBufferLength], 4
0x18000dc50  mov     rcx, r14; hRequest
0x18000dc53  call    cs:__imp_WinHttpQueryHeaders
0x18000dc5a  nop     dword ptr [rax+rax+00h]
0x18000dc5f  test    eax, eax
0x18000dc61  jnz     short loc_18000DC84
0x18000dc63  call    cs:__imp_GetLastError
0x18000dc6a  nop     dword ptr [rax+rax+00h]
0x18000dc6f  mov     ebx, eax
0x18000dc71  test    eax, eax
0x18000dc73  jle     short loc_18000DC7E
0x18000dc75  movzx   ebx, ax
0x18000dc78  or      ebx, 80070000h
0x18000dc7e  test    ebx, ebx
0x18000dc80  js      short loc_18000DCB6
0x18000dc82  jmp     short loc_18000DCF7
0x18000dc84  mov     eax, [rbp+var_28]
0x18000dc87  mov     rcx, [rbp+arg_30]
0x18000dc8b  mov     [rcx], eax
0x18000dc8d  cmp     eax, 193h
0x18000dc92  jnz     short loc_18000DC9A
0x18000dc94  mov     dword ptr [rdi], 6
0x18000dc9a  cmp     eax, 1F6h
0x18000dc9f  jnz     short loc_18000DCA7
0x18000dca1  mov     dword ptr [rdi], 8
0x18000dca7  test    ebx, ebx
0x18000dca9  jns     short loc_18000DCF7
0x18000dcab  jmp     short loc_18000DCB6
0x18000dcad  mov     rsi, r14
0x18000dcb0  mov     r13d, 1
0x18000dcb6  cmp     ebx, 80072EE2h
0x18000dcbc  jz      short loc_18000DCF1
0x18000dcbe  cmp     ebx, 80072EE5h
0x18000dcc4  jz      short loc_18000DCE9
0x18000dcc6  cmp     ebx, 80072EE7h
0x18000dccc  jz      short loc_18000DCE1
0x18000dcce  cmp     ebx, 80072EFDh
0x18000dcd4  mov     eax, 3
0x18000dcd9  cmovnz  eax, r13d
0x18000dcdd  mov     [rdi], eax
0x18000dcdf  jmp     short loc_18000DCF7
0x18000dce1  mov     dword ptr [rdi], 5
0x18000dce7  jmp     short loc_18000DCF7
0x18000dce9  mov     dword ptr [rdi], 7
0x18000dcef  jmp     short loc_18000DCF7
0x18000dcf1  mov     dword ptr [rdi], 4
0x18000dcf7  test    r14, r14
0x18000dcfa  jz      short loc_18000DD0B
0x18000dcfc  mov     rcx, r14; hInternet
0x18000dcff  call    cs:__imp_WinHttpCloseHandle
0x18000dd06  nop     dword ptr [rax+rax+00h]
0x18000dd0b  test    rsi, rsi
0x18000dd0e  jz      short loc_18000DD1F
0x18000dd10  mov     rcx, rsi; hInternet
0x18000dd13  call    cs:__imp_WinHttpCloseHandle
0x18000dd1a  nop     dword ptr [rax+rax+00h]
0x18000dd1f  test    r12, r12
0x18000dd22  jz      short loc_18000DD33
0x18000dd24  mov     rcx, r12; hInternet
0x18000dd27  call    cs:__imp_WinHttpCloseHandle
0x18000dd2e  nop     dword ptr [rax+rax+00h]
0x18000dd33  mov     eax, ebx
0x18000dd35  jmp     short loc_18000DD3C
0x18000dd37  mov     eax, 80070057h
0x18000dd3c  add     rsp, 68h
0x18000dd40  pop     r15
0x18000dd42  pop     r14
0x18000dd44  pop     r13
0x18000dd46  pop     r12
0x18000dd48  pop     rdi
  ... truncated ...
```
