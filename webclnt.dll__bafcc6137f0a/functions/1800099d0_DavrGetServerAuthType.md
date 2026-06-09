# DavrGetServerAuthType

- ea: `0x1800099d0`
- end: `0x18000a00a`
- name: `DavrGetServerAuthType`
- size: `1594`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, HLOCAL *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800045e8`
- `0x18000591c`
- `0x180006618`
- `0x1800099d0`
- `0x18000b7dc`
- `0x18000b89c`
- `0x18000ba14`
- `0x18000bb44`
- `0x180026a68`
- `0x180029c44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dbc`
- `DAVHLPR!DavParseUncServerName` at `0x180009b35`
- `DAVHLPR!DavParseUncServerName` at `0x180009b35`
- `KERNEL32!LocalFree` at `0x180009e7b`
- `KERNEL32!LocalFree` at `0x180009f73`
- `KERNEL32!LocalFree` at `0x180009e7b`
- `KERNEL32!LocalFree` at `0x180009f73`
- `KERNEL32!LocalAlloc` at `0x180009acf`
- `KERNEL32!LocalAlloc` at `0x180009acf`
- `WINHTTP!WinHttpOpen` at `0x180009bbe`
- `WINHTTP!WinHttpOpen` at `0x180009bbe`
- `WINHTTP!WinHttpSetOption` at `0x180009c06`
- `WINHTTP!WinHttpSetOption` at `0x180009c5d`
- `WINHTTP!WinHttpSetOption` at `0x180009ca5`
- `WINHTTP!WinHttpSetOption` at `0x180009cf0`
- `WINHTTP!WinHttpSetOption` at `0x180009d55`
- `WINHTTP!WinHttpSetOption` at `0x180009c06`
- `WINHTTP!WinHttpSetOption` at `0x180009c5d`
- `WINHTTP!WinHttpSetOption` at `0x180009ca5`
- `WINHTTP!WinHttpSetOption` at `0x180009cf0`
- `WINHTTP!WinHttpSetOption` at `0x180009d55`
- `WINHTTP!WinHttpCloseHandle` at `0x180009e64`
- `WINHTTP!WinHttpCloseHandle` at `0x180009f09`
- `WINHTTP!WinHttpCloseHandle` at `0x180009f12`
- `WINHTTP!WinHttpCloseHandle` at `0x180009f25`
- `WINHTTP!WinHttpCloseHandle` at `0x180009e64`
- `WINHTTP!WinHttpCloseHandle` at `0x180009f09`
- `WINHTTP!WinHttpCloseHandle` at `0x180009f12`
- `WINHTTP!WinHttpCloseHandle` at `0x180009f25`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180009e42`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180009e42`

## pseudocode

```c
__int64 __fastcall DavrGetServerAuthType(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, HLOCAL *a5)
{
  HLOCAL *v5; // r12
  unsigned int v6; // ebx
  DWORD v9; // esi
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  DWORD LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // r8d
  const char *v17; // rax
  void *v18; // rax
  void *v19; // r14
  DWORD v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  int IsUrlPathLocal; // eax
  int v24; // ecx
  INTERNET_PORT v25; // r8
  HINTERNET v26; // rax
  void *v27; // r15
  DWORD v28; // eax
  int AuthInfo; // eax
  void *v30; // rdi
  unsigned int v31; // eax
  unsigned int v33; // [rsp+40h] [rbp-30h]
  int v34; // [rsp+44h] [rbp-2Ch] BYREF
  int Buffer; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-20h] BYREF
  HINTERNET hRequest; // [rsp+58h] [rbp-18h] BYREF
  int v38; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwSupportedSchemes; // [rsp+64h] [rbp-Ch] BYREF
  DWORD pdwAuthTarget; // [rsp+68h] [rbp-8h] BYREF
  DWORD dwFirstScheme; // [rsp+6Ch] [rbp-4h] BYREF
  unsigned __int8 v43; // [rsp+C8h] [rbp+58h] BYREF

  v5 = a5;
  v6 = 0;
  *a4 = 0;
  Buffer = 0;
  v34 = 0;
  *v5 = 0;
  v9 = -1;
  v38 = 0;
  hRequest = 0;
  v43 = 0;
  hMem = 0;
  dwSupportedSchemes = 0;
  dwFirstScheme = 0;
  pdwAuthTarget = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      324,
      (unsigned int)WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
      a2,
      a3);
  v10 = DavImpersonateClient();
  if ( !v10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a2 + 2 * v12) );
    hMem = LocalAlloc(0x40u, 2 * v12 + 2);
    if ( !hMem )
    {
      LastError = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 326;
LABEL_15:
        WPP_SF_d(v14[2], v15, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
        goto LABEL_75;
      }
      goto LABEL_75;
    }
    LastError = DavParseUncServerName(a2, &v43, &hMem, &v38);
    if ( LastError )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 327;
        goto LABEL_15;
      }
LABEL_75:
      v31 = DavRevertToSelf();
      if ( v31 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_80;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v31);
      }
      v11 = WPP_GLOBAL_Control;
LABEL_80:
      v6 = v33;
      goto LABEL_81;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = "HTTPS";
      if ( !v43 )
        v17 = "HTTP";
      WPP_SF_Ss(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)"HTTP", v16, (_DWORD)hMem, (__int64)v17);
    }
    Buffer = -1;
    v18 = WinHttpOpen(DAVUserAgent, 0, 0, 0, 0);
    v19 = v18;
    if ( !v18 )
    {
      LastError = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 329;
        goto LABEL_15;
      }
      goto LABEL_75;
    }
    if ( WinHttpSetOption(v18, 0x49u, &Buffer, 4u) )
    {
      if ( WinHttpSetOption(v19, 0x4Au, &Buffer, 4u) )
      {
        v34 = 0x10000000;
        if ( WinHttpSetOption(v19, 0x53u, &v34, 4u) )
        {
          v34 = 0x40000000;
          if ( WinHttpSetOption(v19, 0x53u, &v34, 4u) )
          {
            IsUrlPathLocal = DavIsUrlPathLocal(hMem);
            v24 = *(_DWORD *)&DavInternetServerTimeoutInSec;
            if ( IsUrlPathLocal )
              v24 = *(_DWORD *)&DavLocalServerTimeoutInSec;
            v34 = 1000 * v24;
            if ( WinHttpSetOption(v19, 3u, &v34, 4u) )
            {
              if ( v38 )
                v25 = v38;
              else
                v25 = v43 != 0 ? 443 : 80;
              v26 = DavIdnWinHttpConnect(v19, (WCHAR *)hMem, v25);
              v27 = v26;
              if ( v26 )
              {
                AuthInfo = DavGetAuthInfo(
                             (_DWORD)v19,
                             (_DWORD)v26,
                             0,
                             v43,
                             a3,
                             (__int64)&hRequest,
                             (__int64)a4,
                             (__int64)v5);
                if ( AuthInfo )
                {
LABEL_67:
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      336,
                      WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
                      v33,
                      AuthInfo);
                  }
                  v30 = hRequest;
                }
                else
                {
                  while ( 1 )
                  {
                    v30 = hRequest;
                    if ( WinHttpQueryAuthSchemes(hRequest, &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget) )
                      break;
                    if ( v33 )
                      goto LABEL_71;
                    v33 = 1;
                    if ( v30 )
                    {
                      WinHttpCloseHandle(v30);
                      hRequest = 0;
                    }
                    if ( *v5 )
                    {
                      LocalFree(*v5);
                      *v5 = 0;
                      *a4 = 0;
                    }
                    AuthInfo = DavGetAuthInfo(
                                 (_DWORD)v19,
                                 (_DWORD)v27,
                                 1,
                                 v43,
                                 a3,
                                 (__int64)&hRequest,
                                 (__int64)a4,
                                 (__int64)v5);
                    if ( AuthInfo )
                      goto LABEL_67;
                  }
                  v9 = 16;
                  if ( (dwSupportedSchemes & 0x10) == 0 )
                  {
                    if ( (dwSupportedSchemes & 2) != 0 )
                    {
                      v9 = 2;
                    }
                    else if ( (dwSupportedSchemes & 4) != 0 )
                    {
                      v9 = 4;
                    }
                    else
                    {
                      v9 = 8;
                      if ( (dwSupportedSchemes & 8) == 0 )
                        v9 = dwSupportedSchemes & 1;
                    }
                  }
                }
LABEL_71:
                if ( v30 )
                  WinHttpCloseHandle(v30);
                WinHttpCloseHandle(v27);
              }
              else
              {
                v28 = GetLastError();
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    335,
                    WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
                    v28);
                }
              }
              goto LABEL_74;
            }
            v20 = GetLastError();
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
LABEL_74:
              WinHttpCloseHandle(v19);
              goto LABEL_75;
            }
            v22 = 334;
          }
          else
          {
            v20 = GetLastError();
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_74;
            v22 = 333;
          }
        }
        else
        {
          v20 = GetLastError();
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_74;
          v22 = 332;
        }
      }
      else
      {
        v20 = GetLastError();
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_74;
        v22 = 331;
      }
    }
    else
    {
      v20 = GetLastError();
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_74;
      v22 = 330;
    }
    WPP_SF_d(v21[2], v22, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v20);
    goto LABEL_74;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 325, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v10);
      v11 = WPP_GLOBAL_Control;
    }
    v6 = 0;
  }
LABEL_81:
  if ( hMem )
  {
    LocalFree(hMem);
    v11 = WPP_GLOBAL_Control;
    hMem = 0;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
    WPP_SF_Dd(v11[2], 338, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v9, v6);
  return v9;
}

```

## disassembly

```asm
0x1800099d0  mov     [rsp-38h+arg_0], rbx
0x1800099d5  mov     [rsp-38h+arg_10], r8
0x1800099da  push    rbp
0x1800099db  push    rsi
0x1800099dc  push    rdi
0x1800099dd  push    r12
0x1800099df  push    r13
0x1800099e1  push    r14
0x1800099e3  push    r15
0x1800099e5  mov     rbp, rsp
0x1800099e8  sub     rsp, 70h
0x1800099ec  mov     r12, [rbp+arg_20]
0x1800099f0  xor     r15d, r15d
0x1800099f3  mov     ebx, r15d
0x1800099f6  mov     [r9], r15d
0x1800099f9  mov     r13, r9
0x1800099fc  mov     [rbp+Buffer], r15d
0x180009a00  mov     rdi, rdx
0x180009a03  mov     [rbp+var_2C], r15d
0x180009a07  mov     [r12], r15
0x180009a0b  or      esi, 0FFFFFFFFh
0x180009a0e  mov     [rbp+var_10], r15d
0x180009a12  mov     [rbp+hRequest], r15
0x180009a16  mov     [rbp+arg_18], r15b
0x180009a1a  mov     [rbp+hMem], r15
0x180009a1e  mov     [rbp+dwSupportedSchemes], r15d
0x180009a22  mov     [rbp+dwFirstScheme], r15d
0x180009a26  mov     [rbp+pdwAuthTarget], r15d
0x180009a2a  mov     [rbp+var_30], ebx
0x180009a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a34  lea     rdx, WPP_GLOBAL_Control
0x180009a3b  cmp     rcx, rdx
0x180009a3e  jz      short loc_180009A63
0x180009a40  test    byte ptr [rcx+1Ch], 2
0x180009a44  jz      short loc_180009A63
0x180009a46  mov     rcx, [rcx+10h]
0x180009a4a  mov     edx, 144h
0x180009a4f  mov     qword ptr [rsp+70h+dwFlags], r8
0x180009a54  mov     r9, rdi
0x180009a57  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180009a5e  call    WPP_SF_SS
0x180009a63  call    DavImpersonateClient
0x180009a68  test    eax, eax
0x180009a6a  jz      short loc_180009AB4
0x180009a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a73  lea     rdi, WPP_GLOBAL_Control
0x180009a7a  cmp     rcx, rdi
0x180009a7d  jz      loc_180009F67
0x180009a83  mov     ebx, 1
0x180009a88  test    [rcx+1Ch], bl
0x180009a8b  jz      short loc_180009AAC
0x180009a8d  mov     rcx, [rcx+10h]
0x180009a91  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180009a98  mov     edx, 145h
0x180009a9d  mov     r9d, eax
0x180009aa0  call    WPP_SF_d
0x180009aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aac  mov     ebx, r15d
0x180009aaf  jmp     loc_180009F67
0x180009ab4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009ab8  inc     rdx
0x180009abb  cmp     [rdi+rdx*2], r15w
0x180009ac0  jnz     short loc_180009AB8
0x180009ac2  lea     rdx, ds:2[rdx*2]; uBytes
0x180009aca  mov     ecx, 40h ; '@'; uFlags
0x180009acf  call    cs:__imp_LocalAlloc
0x180009ad5  mov     [rbp+hMem], rax
0x180009ad9  mov     ebx, 1
0x180009ade  test    rax, rax
0x180009ae1  jnz     short loc_180009B26
0x180009ae3  call    cs:__imp_GetLastError
0x180009ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009af0  lea     rdi, WPP_GLOBAL_Control
0x180009af7  cmp     rcx, rdi
0x180009afa  jz      loc_180009F2B
0x180009b00  test    [rcx+1Ch], bl
0x180009b03  jz      loc_180009F2B
0x180009b09  mov     edx, 146h
0x180009b0e  mov     rcx, [rcx+10h]
0x180009b12  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180009b19  mov     r9d, eax
0x180009b1c  call    WPP_SF_d
0x180009b21  jmp     loc_180009F2B
0x180009b26  lea     r9, [rbp+var_10]
0x180009b2a  mov     rcx, rdi
0x180009b2d  lea     r8, [rbp+hMem]
0x180009b31  lea     rdx, [rbp+arg_18]
0x180009b35  call    cs:__imp_DavParseUncServerName
0x180009b3b  test    eax, eax
0x180009b3d  jz      short loc_180009B66
0x180009b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b46  lea     rdi, WPP_GLOBAL_Control
0x180009b4d  cmp     rcx, rdi
0x180009b50  jz      loc_180009F2B
0x180009b56  test    [rcx+1Ch], bl
0x180009b59  jz      loc_180009F2B
0x180009b5f  mov     edx, 147h
0x180009b64  jmp     short loc_180009B0E
0x180009b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b6d  lea     rdi, WPP_GLOBAL_Control
0x180009b74  cmp     rcx, rdi
0x180009b77  jz      short loc_180009BA7
0x180009b79  test    byte ptr [rcx+1Ch], 2
0x180009b7d  jz      short loc_180009BA7
0x180009b7f  cmp     [rbp+arg_18], r15b
0x180009b83  lea     rdx, aHttp_1; "HTTP"
0x180009b8a  mov     r9, [rbp+hMem]
0x180009b8e  lea     rax, aHttps_1; "HTTPS"
0x180009b95  mov     rcx, [rcx+10h]
0x180009b99  cmovz   rax, rdx
0x180009b9d  mov     qword ptr [rsp+70h+dwFlags], rax
0x180009ba2  call    WPP_SF_Ss
0x180009ba7  mov     rcx, cs:DAVUserAgent; pszAgentW
0x180009bae  xor     r9d, r9d; pszProxyBypassW
0x180009bb1  xor     r8d, r8d; pszProxyW
0x180009bb4  mov     [rbp+Buffer], esi
0x180009bb7  xor     edx, edx; dwAccessType
0x180009bb9  mov     [rsp+70h+dwFlags], r15d; dwFlags
0x180009bbe  call    cs:__imp_WinHttpOpen
0x180009bc4  mov     r14, rax
0x180009bc7  test    rax, rax
0x180009bca  jnz     short loc_180009BF5
0x180009bcc  call    cs:__imp_GetLastError
0x180009bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bd9  cmp     rcx, rdi
0x180009bdc  jz      loc_180009F2B
0x180009be2  test    [rcx+1Ch], bl
0x180009be5  jz      loc_180009F2B
0x180009beb  mov     edx, 149h
0x180009bf0  jmp     loc_180009B0E
0x180009bf5  mov     r9d, 4; dwBufferLength
0x180009bfb  lea     r8, [rbp+Buffer]; lpBuffer
0x180009bff  mov     rcx, r14; hInternet
0x180009c02  lea     edx, [r9+45h]; dwOption
0x180009c06  call    cs:__imp_WinHttpSetOption
0x180009c0c  test    eax, eax
0x180009c0e  jnz     short loc_180009C4C
0x180009c10  call    cs:__imp_GetLastError
0x180009c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c1d  cmp     rcx, rdi
0x180009c20  jz      loc_180009F22
0x180009c26  test    [rcx+1Ch], bl
0x180009c29  jz      loc_180009F22
0x180009c2f  mov     edx, 14Ah
0x180009c34  mov     rcx, [rcx+10h]
0x180009c38  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180009c3f  mov     r9d, eax
0x180009c42  call    WPP_SF_d
0x180009c47  jmp     loc_180009F22
0x180009c4c  mov     r9d, 4; dwBufferLength
0x180009c52  lea     r8, [rbp+Buffer]; lpBuffer
0x180009c56  mov     rcx, r14; hInternet
0x180009c59  lea     edx, [r9+46h]; dwOption
0x180009c5d  call    cs:__imp_WinHttpSetOption
0x180009c63  test    eax, eax
0x180009c65  jnz     short loc_180009C8D
0x180009c67  call    cs:__imp_GetLastError
0x180009c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c74  cmp     rcx, rdi
0x180009c77  jz      loc_180009F22
0x180009c7d  test    [rcx+1Ch], bl
0x180009c80  jz      loc_180009F22
0x180009c86  mov     edx, 14Bh
0x180009c8b  jmp     short loc_180009C34
0x180009c8d  mov     r9d, 4; dwBufferLength
0x180009c93  mov     [rbp+var_2C], 10000000h
0x180009c9a  lea     r8, [rbp+var_2C]; lpBuffer
0x180009c9e  mov     rcx, r14; hInternet
0x180009ca1  lea     edx, [r9+4Fh]; dwOption
0x180009ca5  call    cs:__imp_WinHttpSetOption
0x180009cab  test    eax, eax
0x180009cad  jnz     short loc_180009CD8
0x180009caf  call    cs:__imp_GetLastError
0x180009cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cbc  cmp     rcx, rdi
0x180009cbf  jz      loc_180009F22
0x180009cc5  test    [rcx+1Ch], bl
0x180009cc8  jz      loc_180009F22
0x180009cce  mov     edx, 14Ch
0x180009cd3  jmp     loc_180009C34
0x180009cd8  mov     r9d, 4; dwBufferLength
0x180009cde  mov     [rbp+var_2C], 40000000h
0x180009ce5  lea     r8, [rbp+var_2C]; lpBuffer
0x180009ce9  mov     rcx, r14; hInternet
0x180009cec  lea     edx, [r9+4Fh]; dwOption
0x180009cf0  call    cs:__imp_WinHttpSetOption
0x180009cf6  test    eax, eax
0x180009cf8  jnz     short loc_180009D23
0x180009cfa  call    cs:__imp_GetLastError
0x180009d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d07  cmp     rcx, rdi
0x180009d0a  jz      loc_180009F22
0x180009d10  test    [rcx+1Ch], bl
0x180009d13  jz      loc_180009F22
0x180009d19  mov     edx, 14Dh
0x180009d1e  jmp     loc_180009C34
0x180009d23  mov     rcx, [rbp+hMem]
0x180009d27  call    DavIsUrlPathLocal
0x180009d2c  mov     ecx, cs:DavInternetServerTimeoutInSec
0x180009d32  lea     r8, [rbp+var_2C]; lpBuffer
0x180009d36  test    eax, eax
0x180009d38  mov     r9d, 4; dwBufferLength
0x180009d3e  cmovnz  ecx, cs:DavLocalServerTimeoutInSec
0x180009d45  imul    eax, ecx, 3E8h
0x180009d4b  mov     rcx, r14; hInternet
0x180009d4e  lea     edx, [r9-1]; dwOption
0x180009d52  mov     [rbp+var_2C], eax
0x180009d55  call    cs:__imp_WinHttpSetOption
0x180009d5b  test    eax, eax
0x180009d5d  jnz     short loc_180009D88
0x180009d5f  call    cs:__imp_GetLastError
0x180009d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d6c  cmp     rcx, rdi
0x180009d6f  jz      loc_180009F22
0x180009d75  test    [rcx+1Ch], bl
0x180009d78  jz      loc_180009F22
0x180009d7e  mov     edx, 14Eh
0x180009d83  jmp     loc_180009C34
0x180009d88  mov     eax, [rbp+var_10]
0x180009d8b  test    eax, eax
0x180009d8d  jnz     short loc_180009DA4
0x180009d8f  mov     al, [rbp+arg_18]
0x180009d92  neg     al
0x180009d94  sbb     r8d, r8d
0x180009d97  and     r8d, 16Bh
0x180009d9e  add     r8d, 50h ; 'P'
0x180009da2  jmp     short loc_180009DA8
0x180009da4  movzx   r8d, ax
0x180009da8  mov     rdx, [rbp+hMem]; lpUnicodeCharStr
0x180009dac  mov     rcx, r14; hSession
0x180009daf  call    DavIdnWinHttpConnect
0x180009db4  mov     r15, rax
0x180009db7  test    rax, rax
0x180009dba  jnz     short loc_180009DF8
0x180009dbc  call    cs:__imp_GetLastError
0x180009dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dc9  cmp     rcx, rdi
0x180009dcc  jz      loc_180009F1F
0x180009dd2  test    [rcx+1Ch], bl
0x180009dd5  jz      loc_180009F1F
0x180009ddb  mov     rcx, [rcx+10h]
0x180009ddf  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180009de6  mov     edx, 14Fh
0x180009deb  mov     r9d, eax
0x180009dee  call    WPP_SF_d
0x180009df3  jmp     loc_180009F1F
0x180009df8  movzx   r9d, [rbp+arg_18]
0x180009dfd  lea     rax, [rbp+hRequest]
0x180009e01  mov     [rsp+70h+var_38], r12
0x180009e06  xor     r8d, r8d
0x180009e09  mov     [rsp+70h+var_40], r13
0x180009e0e  mov     rdx, r15
0x180009e11  mov     [rsp+70h+var_48], rax
0x180009e16  mov     rcx, r14
0x180009e19  mov     rax, [rbp+arg_10]
0x180009e1d  mov     qword ptr [rsp+70h+dwFlags], rax
0x180009e22  call    DavGetAuthInfo
0x180009e27  test    eax, eax
0x180009e29  jnz     loc_180009ECF
0x180009e2f  mov     rdi, [rbp+hRequest]
0x180009e33  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x180009e37  mov     rcx, rdi; hRequest
0x180009e3a  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x180009e3e  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x180009e42  call    cs:__imp_WinHttpQueryAuthSchemes
0x180009e48  test    eax, eax
0x180009e4a  jnz     loc_180009FC5
0x180009e50  cmp     [rbp+var_30], eax
0x180009e53  jnz     loc_180009F01
0x180009e59  mov     [rbp+var_30], ebx
0x180009e5c  test    rdi, rdi
0x180009e5f  jz      short loc_180009E72
0x180009e61  mov     rcx, rdi; hInternet
0x180009e64  call    cs:__imp_WinHttpCloseHandle
0x180009e6a  mov     [rbp+hRequest], 0
0x180009e72  mov     rcx, [r12]; hMem
0x180009e76  test    rcx, rcx
0x180009e79  jz      short loc_180009E91
0x180009e7b  call    cs:__imp_LocalFree
0x180009e81  mov     qword ptr [r12], 0
0x180009e89  mov     dword ptr [r13+0], 0
0x180009e91  movzx   r9d, [rbp+arg_18]
0x180009e96  lea     rax, [rbp+hRequest]
0x180009e9a  mov     [rsp+70h+var_38], r12
0x180009e9f  mov     r8d, ebx
0x180009ea2  mov     [rsp+70h+var_40], r13
0x180009ea7  mov     rdx, r15
0x180009eaa  mov     [rsp+70h+var_48], rax
0x180009eaf  mov     rcx, r14
0x180009eb2  mov     rax, [rbp+arg_10]
0x180009eb6  mov     qword ptr [rsp+70h+dwFlags], rax
0x180009ebb  call    DavGetAuthInfo
0x180009ec0  test    eax, eax
0x180009ec2  jz      loc_180009E2F
0x180009ec8  lea     rdi, WPP_GLOBAL_Control
0x180009ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ed6  cmp     rcx, rdi
0x180009ed9  jz      short loc_180009EFD
0x180009edb  test    [rcx+1Ch], bl
0x180009ede  jz      short loc_180009EFD
  ... truncated ...
```
