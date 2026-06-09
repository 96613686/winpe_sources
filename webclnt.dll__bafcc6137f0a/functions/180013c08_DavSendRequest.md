# DavSendRequest

- ea: `0x180013c08`
- end: `0x180013fe3`
- name: `DavSendRequest`
- size: `987`
- prototype: `__int64 __fastcall(HINTERNET hRequest, const WCHAR *, DWORD, void *, DWORD dwOptionalLength, DWORD dwTotalLength, int Buffer, __int64)`
- caller_count: `7`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1800049bc`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x18001f190`
- `0x180020c1c`
- `0x180021008`
- `0x180024190`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000c128`
- `0x1800114fc`
- `0x18001171c`
- `0x180011da8`
- `0x180012468`
- `0x180013c08`
- `0x180013fec`
- `0x18001456c`
- `0x180014820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f55`
- `KERNEL32!LocalFree` at `0x180013e38`
- `KERNEL32!LocalFree` at `0x180013e38`
- `WINHTTP!WinHttpReceiveResponse` at `0x180013d05`
- `WINHTTP!WinHttpReceiveResponse` at `0x180013d05`
- `WINHTTP!WinHttpSendRequest` at `0x180013caa`
- `WINHTTP!WinHttpSendRequest` at `0x180013caa`
- `WINHTTP!WinHttpQueryHeaders` at `0x180013db3`
- `WINHTTP!WinHttpQueryHeaders` at `0x180013db3`

## pseudocode

```c
__int64 __fastcall DavSendRequest(
        HINTERNET hRequest,
        const WCHAR *a2,
        DWORD a3,
        void *a4,
        DWORD dwOptionalLength,
        DWORD dwTotalLength,
        int Buffer,
        __int64 a8)
{
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  int v10; // r14d
  int v11; // r12d
  __int64 v13; // rsi
  DWORD v14; // eax
  BOOL v15; // eax
  DWORD v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  int ExtErrorInfo; // eax
  HLOCAL v21; // rbx
  __int64 v22; // rax
  unsigned int updated; // eax
  DWORD LastError; // eax
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v28; // [rsp+40h] [rbp-20h] BYREF
  DWORD dwBufferLength; // [rsp+44h] [rbp-1Ch] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  __int64 v31; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpszHeaders; // [rsp+A8h] [rbp+48h]
  DWORD dwHeadersLength; // [rsp+B0h] [rbp+50h]
  LPVOID lpOptional; // [rsp+B8h] [rbp+58h]

  lpOptional = a4;
  dwHeadersLength = a3;
  lpszHeaders = a2;
  v8 = 0;
  dwBufferLength = 4;
  v9 = 0;
  Buffer = 0;
  v10 = 0;
  hMem = 0;
  v11 = 0;
  v31 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
    a4 = lpOptional;
    a3 = dwHeadersLength;
    a2 = lpszHeaders;
  }
  v13 = a8;
  while ( WinHttpSendRequest(hRequest, a2, a3, a4, dwOptionalLength, dwTotalLength, 0) )
  {
    v15 = WinHttpReceiveResponse(hRequest, 0);
    if ( !v13 )
      return v8;
    if ( v15 )
    {
      if ( !WinHttpQueryHeaders(hRequest, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
      {
        LastError = GetLastError();
        v8 = LastError;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_56;
        v18 = 218;
        v19 = LastError;
LABEL_21:
        WPP_SF_d(v17[2], v18, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v19);
        goto LABEL_56;
      }
      if ( Buffer == 200 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
LABEL_40:
        updated = DavUpdateExtErrorInformation(hRequest);
        v8 = updated;
        if ( updated )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, updated);
          v8 = 0;
        }
LABEL_56:
        v25 = *(unsigned int *)(v13 + 7116);
        if ( (_DWORD)v25 )
        {
          v26 = DavMapExtErrorToWin32Error(v25);
          if ( v26 )
          {
            v8 = v26;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v26);
          }
        }
        return v8;
      }
      if ( Buffer != 401 )
        goto LABEL_40;
      if ( (unsigned int)DavGetFBAAuthRequiredExtErrorInfo(hRequest) )
      {
        ExtErrorInfo = DavGetExtErrorInfo(hRequest, &hMem);
        v21 = hMem;
        if ( ExtErrorInfo )
          goto LABEL_32;
        if ( hMem )
        {
          if ( !(unsigned int)DavVerifyAndGetExtErrorInfo(hMem, &v28, &v31)
            && (unsigned int)DavMapExtErrorToWin32Error(v28) == 224 )
          {
            v11 = 1;
          }
LABEL_32:
          if ( v21 )
            LocalFree(v21);
        }
      }
      else
      {
        v11 = 1;
      }
      if ( !v9 )
      {
        v22 = *(_QWORD *)(v13 + 496);
        if ( v22 )
        {
          if ( *(_DWORD *)(v22 + 104) != 2 )
            *(_DWORD *)(v22 + 104) = 2;
        }
      }
      v8 = DavInternetSetOption(v13, v11, hRequest, 0, ++v9);
      if ( v8 )
        goto LABEL_56;
      DavSetAutoLogonLowForTrustedSites(hRequest);
      if ( v9 >= 3 )
        goto LABEL_40;
LABEL_11:
      a4 = lpOptional;
      a3 = dwHeadersLength;
      a2 = lpszHeaders;
    }
    else
    {
      v16 = GetLastError();
      a4 = lpOptional;
      v8 = v16;
      a3 = dwHeadersLength;
      a2 = lpszHeaders;
      if ( v16 != 12032 )
      {
        if ( v16 != 12044 || (v8 = DavInternetSetCert(v13, hRequest)) != 0 || v10 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_56;
          v18 = 216;
          v19 = v8;
          goto LABEL_21;
        }
LABEL_10:
        v10 = 1;
        goto LABEL_11;
      }
    }
  }
  v14 = GetLastError();
  v8 = v14;
  if ( (v14 == 12044 || v14 == 12175) && !v10 )
  {
    v8 = DavInternetSetCert(v13, hRequest);
    if ( !v8 )
      goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v8);
  if ( v13 )
    goto LABEL_56;
  return v8;
}

```

## disassembly

```asm
0x180013c08  mov     rax, rsp
0x180013c0b  mov     [rax+8], rbx
0x180013c0f  mov     [rax+20h], r9
0x180013c13  mov     [rax+18h], r8d
0x180013c17  mov     [rax+10h], rdx
0x180013c1b  push    rbp
0x180013c1c  push    rsi
0x180013c1d  push    rdi
0x180013c1e  push    r12
0x180013c20  push    r13
0x180013c22  push    r14
0x180013c24  push    r15
0x180013c26  mov     rbp, rsp
0x180013c29  sub     rsp, 60h
0x180013c2d  xor     ebx, ebx
0x180013c2f  mov     [rbp+dwBufferLength], 4
0x180013c36  xor     r15d, r15d
0x180013c39  mov     [rbp+Buffer], ebx
0x180013c3c  xor     r14d, r14d
0x180013c3f  mov     [rbp+hMem], rbx
0x180013c43  xor     r12d, r12d
0x180013c46  mov     [rbp+var_10], rbx
0x180013c4a  mov     [rbp+var_20], ebx
0x180013c4d  mov     rdi, rcx
0x180013c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c57  lea     rax, WPP_GLOBAL_Control
0x180013c5e  cmp     rcx, rax
0x180013c61  jz      short loc_180013C8A
0x180013c63  test    byte ptr [rcx+1Ch], 2
0x180013c67  jz      short loc_180013C8A
0x180013c69  mov     rcx, [rcx+10h]
0x180013c6d  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013c74  mov     edx, 0D6h
0x180013c79  call    WPP_SF_
0x180013c7e  mov     r9, [rbp+lpOptional]; lpOptional
0x180013c82  mov     r8d, [rbp+dwHeadersLength]; dwHeadersLength
0x180013c86  mov     rdx, [rbp+lpszHeaders]; lpszHeaders
0x180013c8a  mov     rsi, [rbp+arg_38]
0x180013c8e  mov     r13d, [rbp+arg_28]
0x180013c92  mov     eax, [rbp+arg_20]
0x180013c95  mov     rcx, rdi; hRequest
0x180013c98  mov     [rsp+60h+dwContext], 0; dwContext
0x180013ca1  mov     [rsp+60h+dwTotalLength], r13d; dwTotalLength
0x180013ca6  mov     [rsp+60h+dwOptionalLength], eax; dwOptionalLength
0x180013caa  call    cs:__imp_WinHttpSendRequest
0x180013cb0  test    eax, eax
0x180013cb2  jnz     short loc_180013D00
0x180013cb4  call    cs:__imp_GetLastError
0x180013cba  mov     ebx, eax
0x180013cbc  cmp     eax, 2F0Ch
0x180013cc1  jz      short loc_180013CCE
0x180013cc3  cmp     eax, 2F8Fh
0x180013cc8  jnz     loc_180013EDE
0x180013cce  test    r14d, r14d
0x180013cd1  jnz     loc_180013EDE
0x180013cd7  mov     rdx, rdi
0x180013cda  mov     rcx, rsi
0x180013cdd  call    DavInternetSetCert
0x180013ce2  mov     ebx, eax
0x180013ce4  test    eax, eax
0x180013ce6  jnz     loc_180013EDE
0x180013cec  mov     r14d, 1
0x180013cf2  mov     r9, [rbp+lpOptional]
0x180013cf6  mov     r8d, [rbp+dwHeadersLength]
0x180013cfa  mov     rdx, [rbp+lpszHeaders]
0x180013cfe  jmp     short loc_180013C92
0x180013d00  xor     edx, edx; lpReserved
0x180013d02  mov     rcx, rdi; hRequest
0x180013d05  call    cs:__imp_WinHttpReceiveResponse
0x180013d0b  test    rsi, rsi
0x180013d0e  jz      loc_180013FC9
0x180013d14  test    eax, eax
0x180013d16  jnz     short loc_180013D92
0x180013d18  call    cs:__imp_GetLastError
0x180013d1e  mov     r9, [rbp+lpOptional]
0x180013d22  mov     ebx, eax
0x180013d24  mov     r8d, [rbp+dwHeadersLength]
0x180013d28  mov     rdx, [rbp+lpszHeaders]
0x180013d2c  cmp     eax, 2F00h
0x180013d31  jz      loc_180013C92
0x180013d37  cmp     eax, 2F0Ch
0x180013d3c  jnz     short loc_180013D54
0x180013d3e  mov     rdx, rdi
0x180013d41  mov     rcx, rsi
0x180013d44  call    DavInternetSetCert
0x180013d49  mov     ebx, eax
0x180013d4b  test    eax, eax
0x180013d4d  jnz     short loc_180013D54
0x180013d4f  test    r14d, r14d
0x180013d52  jz      short loc_180013CEC
0x180013d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d5b  lea     r14, WPP_GLOBAL_Control
0x180013d62  cmp     rcx, r14
0x180013d65  jz      loc_180013F8A
0x180013d6b  test    byte ptr [rcx+1Ch], 1
0x180013d6f  jz      loc_180013F8A
0x180013d75  mov     edx, 0D8h
0x180013d7a  mov     r9d, ebx
0x180013d7d  mov     rcx, [rcx+10h]
0x180013d81  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013d88  call    WPP_SF_d
0x180013d8d  jmp     loc_180013F8A
0x180013d92  lea     rax, [rbp+dwBufferLength]
0x180013d96  mov     qword ptr [rsp+60h+dwTotalLength], 0; lpdwIndex
0x180013d9f  lea     r9, [rbp+Buffer]; lpBuffer
0x180013da3  mov     qword ptr [rsp+60h+dwOptionalLength], rax; lpdwBufferLength
0x180013da8  xor     r8d, r8d; pwszName
0x180013dab  mov     edx, 20000013h; dwInfoLevel
0x180013db0  mov     rcx, rdi; hRequest
0x180013db3  call    cs:__imp_WinHttpQueryHeaders
0x180013db9  test    eax, eax
0x180013dbb  jz      loc_180013F55
0x180013dc1  cmp     [rbp+Buffer], 0C8h
0x180013dc8  jz      loc_180013F1A
0x180013dce  cmp     [rbp+Buffer], 191h
0x180013dd5  jnz     loc_180013E91
0x180013ddb  mov     rcx, rdi
0x180013dde  call    DavGetFBAAuthRequiredExtErrorInfo
0x180013de3  test    eax, eax
0x180013de5  jnz     short loc_180013DED
0x180013de7  lea     r12d, [rax+1]
0x180013deb  jmp     short loc_180013E3E
0x180013ded  lea     rdx, [rbp+hMem]
0x180013df1  mov     rcx, rdi; hRequest
0x180013df4  call    DavGetExtErrorInfo
0x180013df9  mov     rbx, [rbp+hMem]
0x180013dfd  test    eax, eax
0x180013dff  jnz     short loc_180013E30
0x180013e01  test    rbx, rbx
0x180013e04  jz      short loc_180013E3E
0x180013e06  lea     r8, [rbp+var_10]
0x180013e0a  mov     rcx, rbx
0x180013e0d  lea     rdx, [rbp+var_20]
0x180013e11  call    DavVerifyAndGetExtErrorInfo
0x180013e16  test    eax, eax
0x180013e18  jnz     short loc_180013E30
0x180013e1a  mov     ecx, [rbp+var_20]
0x180013e1d  call    DavMapExtErrorToWin32Error
0x180013e22  cmp     eax, 0E0h
0x180013e27  mov     eax, 1
0x180013e2c  cmovz   r12d, eax
0x180013e30  test    rbx, rbx
0x180013e33  jz      short loc_180013E3E
0x180013e35  mov     rcx, rbx; hMem
0x180013e38  call    cs:__imp_LocalFree
0x180013e3e  test    r15d, r15d
0x180013e41  jnz     short loc_180013E5C
0x180013e43  mov     rax, [rsi+1F0h]
0x180013e4a  test    rax, rax
0x180013e4d  jz      short loc_180013E5C
0x180013e4f  cmp     dword ptr [rax+68h], 2
0x180013e53  jz      short loc_180013E5C
0x180013e55  mov     dword ptr [rax+68h], 2
0x180013e5c  inc     r15d
0x180013e5f  xor     r9d, r9d
0x180013e62  mov     r8, rdi
0x180013e65  mov     [rsp+60h+dwOptionalLength], r15d
0x180013e6a  mov     edx, r12d
0x180013e6d  mov     rcx, rsi
0x180013e70  call    DavInternetSetOption
0x180013e75  mov     ebx, eax
0x180013e77  test    eax, eax
0x180013e79  jnz     loc_180013F83
0x180013e7f  mov     rcx, rdi; hInternet
0x180013e82  call    DavSetAutoLogonLowForTrustedSites
0x180013e87  cmp     r15d, 3
0x180013e8b  jb      loc_180013CF2
0x180013e91  lea     r14, WPP_GLOBAL_Control
0x180013e98  mov     rdx, rsi
0x180013e9b  mov     rcx, rdi; hRequest
0x180013e9e  call    DavUpdateExtErrorInformation
0x180013ea3  mov     ebx, eax
0x180013ea5  test    eax, eax
0x180013ea7  jz      loc_180013F8A
0x180013ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eb4  cmp     rcx, r14
0x180013eb7  jz      short loc_180013ED7
0x180013eb9  test    byte ptr [rcx+1Ch], 2
0x180013ebd  jz      short loc_180013ED7
0x180013ebf  mov     rcx, [rcx+10h]
0x180013ec3  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013eca  mov     edx, 0DBh
0x180013ecf  mov     r9d, eax
0x180013ed2  call    WPP_SF_d
0x180013ed7  xor     ebx, ebx
0x180013ed9  jmp     loc_180013F8A
0x180013ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ee5  lea     r14, WPP_GLOBAL_Control
0x180013eec  cmp     rcx, r14
0x180013eef  jz      short loc_180013F0F
0x180013ef1  test    byte ptr [rcx+1Ch], 1
0x180013ef5  jz      short loc_180013F0F
0x180013ef7  mov     rcx, [rcx+10h]
0x180013efb  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013f02  mov     edx, 0D7h
0x180013f07  mov     r9d, ebx
0x180013f0a  call    WPP_SF_d
0x180013f0f  test    rsi, rsi
0x180013f12  jz      loc_180013FC9
0x180013f18  jmp     short loc_180013F8A
0x180013f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f21  lea     r14, WPP_GLOBAL_Control
0x180013f28  cmp     rcx, r14
0x180013f2b  jz      loc_180013E98
0x180013f31  test    byte ptr [rcx+1Ch], 2
0x180013f35  jz      loc_180013E98
0x180013f3b  mov     rcx, [rcx+10h]
0x180013f3f  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013f46  mov     edx, 0D9h
0x180013f4b  call    WPP_SF_
0x180013f50  jmp     loc_180013E98
0x180013f55  call    cs:__imp_GetLastError
0x180013f5b  mov     ebx, eax
0x180013f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f64  lea     r14, WPP_GLOBAL_Control
0x180013f6b  cmp     rcx, r14
0x180013f6e  jz      short loc_180013F8A
0x180013f70  test    byte ptr [rcx+1Ch], 1
0x180013f74  jz      short loc_180013F8A
0x180013f76  mov     edx, 0DAh
0x180013f7b  mov     r9d, eax
0x180013f7e  jmp     loc_180013D7D
0x180013f83  lea     r14, WPP_GLOBAL_Control
0x180013f8a  mov     ecx, [rsi+1BCCh]
0x180013f90  test    ecx, ecx
0x180013f92  jz      short loc_180013FC9
0x180013f94  call    DavMapExtErrorToWin32Error
0x180013f99  test    eax, eax
0x180013f9b  jz      short loc_180013FC9
0x180013f9d  mov     ebx, eax
0x180013f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fa6  cmp     rcx, r14
0x180013fa9  jz      short loc_180013FC9
0x180013fab  test    byte ptr [rcx+1Ch], 1
0x180013faf  jz      short loc_180013FC9
0x180013fb1  mov     rcx, [rcx+10h]
0x180013fb5  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013fbc  mov     edx, 0DCh
0x180013fc1  mov     r9d, eax
0x180013fc4  call    WPP_SF_d
0x180013fc9  mov     eax, ebx
0x180013fcb  mov     rbx, [rsp+60h+arg_0]
0x180013fd3  add     rsp, 60h
0x180013fd7  pop     r15
0x180013fd9  pop     r14
0x180013fdb  pop     r13
0x180013fdd  pop     r12
0x180013fdf  pop     rdi
0x180013fe0  pop     rsi
0x180013fe1  pop     rbp
0x180013fe2  retn
```
