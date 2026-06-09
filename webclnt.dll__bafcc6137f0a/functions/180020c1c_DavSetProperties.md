# DavSetProperties

- ea: `0x180020c1c`
- end: `0x180021000`
- name: `DavSetProperties`
- size: `996`
- prototype: `__int64 __fastcall(__int64, void *, void *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18002097c`

## callees

- `0x18000b7dc`
- `0x180012468`
- `0x1800134d8`
- `0x180013c08`
- `0x1800206bc`
- `0x180020c1c`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020f34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020f74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020f34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020f74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fac`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020d6b`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020dcc`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020e2c`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020e7a`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020d6b`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020dcc`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020e2c`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020e7a`
- `WINHTTP!WinHttpSetOption` at `0x180020d05`
- `WINHTTP!WinHttpSetOption` at `0x180020d05`
- `WINHTTP!WinHttpCloseHandle` at `0x180020feb`
- `WINHTTP!WinHttpCloseHandle` at `0x180020feb`

## string_xrefs

- `0x180020f06`: `Content-Type: text/xml; charset="utf-8"`

## pseudocode

```c
__int64 __fastcall DavSetProperties(__int64 a1, void *a2, void *a3, __int64 a4, _BYTE *a5)
{
  int v6; // eax
  void *v7; // rsi
  unsigned int LastError; // ebx
  __int64 v9; // r9
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  const WCHAR *v12; // rdx
  const WCHAR *v13; // rdx
  const WCHAR *v14; // rdx
  __int64 v15; // rax
  int v16; // r9d
  __int64 v17; // r8
  __int64 v18; // rax
  DWORD v19; // eax
  DWORD v20; // eax
  __int64 v21; // r8
  DWORD v22; // eax
  DWORD v24; // [rsp+20h] [rbp-88h]
  DWORD v25; // [rsp+28h] [rbp-80h]
  int v26; // [rsp+30h] [rbp-78h]
  int v27; // [rsp+30h] [rbp-78h]
  __int64 v28; // [rsp+40h] [rbp-68h]
  __int64 v29; // [rsp+58h] [rbp-50h]
  HINTERNET hInternet[7]; // [rsp+70h] [rbp-38h] BYREF
  int Buffer; // [rsp+B0h] [rbp+8h] BYREF

  hInternet[0] = 0;
  Buffer = 0;
  v6 = DavHttpOpenRequestW(
         a2,
         a3,
         L"PROPPATCH",
         a4,
         v24,
         v25,
         v26,
         0x100u,
         v28,
         (int *)L"DavSetProperties",
         *(_DWORD *)(*(_QWORD *)(a1 + 504) + 32LL),
         v29,
         hInternet);
  v7 = hInternet[0];
  if ( !v6 )
  {
    LastError = GetLastError();
    goto LABEL_55;
  }
  if ( hInternet[0] )
  {
    Buffer = 1;
    if ( g_DisableCookies && !WinHttpSetOption(hInternet[0], 0x3Fu, &Buffer, 4u) )
    {
      LastError = 0;
      v9 = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 69;
LABEL_54:
        WPP_SF_d(v10[2], v11, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v9);
      }
LABEL_55:
      if ( v7 )
        WinHttpCloseHandle(v7);
      return LastError;
    }
    switch ( *(_DWORD *)(a1 + 48) )
    {
      case 3:
        v12 = *(const WCHAR **)(a1 + 680);
        if ( v12 && !WinHttpAddRequestHeaders(v7, v12, 0xFFFFFFFF, 0xA0000000) )
        {
          LastError = GetLastError();
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_55;
          v11 = 70;
          goto LABEL_53;
        }
        break;
      case 0xA:
        v13 = *(const WCHAR **)(a1 + 664);
        if ( v13 && !WinHttpAddRequestHeaders(v7, v13, 0xFFFFFFFF, 0xA0000000) )
        {
          LastError = GetLastError();
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_55;
          v11 = 71;
          goto LABEL_53;
        }
        break;
      case 0xD:
        v14 = **(const WCHAR ***)(a1 + 672);
        if ( v14 )
        {
          if ( !WinHttpAddRequestHeaders(v7, v14, 0xFFFFFFFF, 0xA0000000) )
          {
            LastError = GetLastError();
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_55;
            v11 = 72;
LABEL_53:
            v9 = LastError;
            goto LABEL_54;
          }
        }
        break;
    }
    if ( WinHttpAddRequestHeaders(v7, L"translate: f\n", 0xFFFFFFFF, 0xA0000000) )
    {
      v15 = *(_QWORD *)(a1 + 496);
      if ( !v15 || (v16 = 0, *(_DWORD *)(v15 + 104) != 2) )
        v16 = 1;
      LastError = DavInternetSetOption(a1, 0, v7, v16, 0);
      if ( LastError )
        goto LABEL_55;
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( a5[v18] );
      do
        ++v17;
      while ( rgXmlHeader[v17] );
      v19 = DavSendRequest(v7, rgXmlHeader, v17, a5, v18, v18, v27, a1);
      LastError = v19;
      if ( v19 )
      {
        SetLastError(v19);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_55;
        v11 = 74;
      }
      else
      {
        v20 = DavQueryAndParseResponseEx(v7, 0);
        LastError = v20;
        if ( v20 )
        {
          SetLastError(v20);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_55;
          v11 = 75;
        }
        else
        {
          v22 = DavParseXmlResponse(v7, 0, v21);
          LastError = v22;
          if ( !v22 )
            goto LABEL_55;
          SetLastError(v22);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_55;
          v11 = 76;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v11 = 73;
    }
    goto LABEL_53;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180020c1c  mov     rax, rsp
0x180020c1f  push    rbx
0x180020c20  push    rbp
0x180020c21  push    rsi
0x180020c22  push    r14
0x180020c24  sub     rsp, 88h
0x180020c2b  mov     rbp, rcx
0x180020c2e  mov     r10, r8
0x180020c31  mov     r11, rdx
0x180020c34  lea     r8, aProppatch; "PROPPATCH"
0x180020c3b  xor     r14d, r14d
0x180020c3e  mov     rdx, r10
0x180020c41  mov     [rax-38h], r14
0x180020c45  mov     [rax+8], r14d
0x180020c49  mov     rax, [rcx+1F8h]
0x180020c50  lea     rcx, [rsp+0A8h+hInternet]
0x180020c55  mov     [rsp+0A8h+var_48], rcx
0x180020c5a  mov     rcx, r11
0x180020c5d  mov     eax, [rax+20h]
0x180020c60  mov     [rsp+0A8h+var_58], eax
0x180020c64  lea     rax, aDavsetproperti; "DavSetProperties"
0x180020c6b  mov     [rsp+0A8h+var_60], rax
0x180020c70  mov     dword ptr [rsp+0A8h+var_70], 100h
0x180020c78  call    DavHttpOpenRequestW
0x180020c7d  mov     rsi, [rsp+0A8h+hInternet]
0x180020c82  test    eax, eax
0x180020c84  jnz     short loc_180020C93
0x180020c86  call    cs:__imp_GetLastError
0x180020c8c  mov     ebx, eax
0x180020c8e  jmp     loc_180020FE3
0x180020c93  test    rsi, rsi
0x180020c96  jnz     short loc_180020CDC
0x180020c98  call    cs:__imp_GetLastError
0x180020c9e  mov     ebx, eax
0x180020ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ca7  lea     rax, WPP_GLOBAL_Control
0x180020cae  cmp     rcx, rax
0x180020cb1  jz      loc_180020FF1
0x180020cb7  test    byte ptr [rcx+1Ch], 1
0x180020cbb  jz      loc_180020FF1
0x180020cc1  mov     rcx, [rcx+10h]
0x180020cc5  lea     edx, [rsi+44h]
0x180020cc8  mov     r9d, ebx
0x180020ccb  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x180020cd2  call    WPP_SF_d
0x180020cd7  jmp     loc_180020FF1
0x180020cdc  cmp     cs:g_DisableCookies, r14d
0x180020ce3  mov     [rsp+0A8h+Buffer], 1
0x180020cee  jz      short loc_180020D46
0x180020cf0  mov     r9d, 4; dwBufferLength
0x180020cf6  lea     r8, [rsp+0A8h+Buffer]; lpBuffer
0x180020cfe  mov     rcx, rsi; hInternet
0x180020d01  lea     edx, [r9+3Bh]; dwOption
0x180020d05  call    cs:__imp_WinHttpSetOption
0x180020d0b  test    eax, eax
0x180020d0d  jnz     short loc_180020D46
0x180020d0f  mov     ebx, r14d
0x180020d12  call    cs:__imp_GetLastError
0x180020d18  mov     r9d, eax
0x180020d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d22  lea     rax, WPP_GLOBAL_Control
0x180020d29  cmp     rcx, rax
0x180020d2c  jz      loc_180020FE3
0x180020d32  test    byte ptr [rcx+1Ch], 1
0x180020d36  jz      loc_180020FE3
0x180020d3c  mov     edx, 45h ; 'E'
0x180020d41  jmp     loc_180020FD3
0x180020d46  cmp     dword ptr [rbp+30h], 3
0x180020d4a  mov     ebx, 0A0000000h
0x180020d4f  jnz     short loc_180020DAC
0x180020d51  mov     rdx, [rbp+2A8h]; lpszHeaders
0x180020d58  test    rdx, rdx
0x180020d5b  jz      loc_180020E69
0x180020d61  mov     r9d, ebx; dwModifiers
0x180020d64  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180020d68  mov     rcx, rsi; hRequest
0x180020d6b  call    cs:__imp_WinHttpAddRequestHeaders
0x180020d71  test    eax, eax
0x180020d73  jnz     loc_180020E69
0x180020d79  call    cs:__imp_GetLastError
0x180020d7f  mov     ebx, eax
0x180020d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d88  lea     rax, WPP_GLOBAL_Control
0x180020d8f  cmp     rcx, rax
0x180020d92  jz      loc_180020FE3
0x180020d98  test    byte ptr [rcx+1Ch], 1
0x180020d9c  jz      loc_180020FE3
0x180020da2  mov     edx, 46h ; 'F'
0x180020da7  jmp     loc_180020FD0
0x180020dac  cmp     dword ptr [rbp+30h], 0Ah
0x180020db0  jnz     short loc_180020E0D
0x180020db2  mov     rdx, [rbp+298h]; lpszHeaders
0x180020db9  test    rdx, rdx
0x180020dbc  jz      loc_180020E69
0x180020dc2  mov     r9d, ebx; dwModifiers
0x180020dc5  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180020dc9  mov     rcx, rsi; hRequest
0x180020dcc  call    cs:__imp_WinHttpAddRequestHeaders
0x180020dd2  test    eax, eax
0x180020dd4  jnz     loc_180020E69
0x180020dda  call    cs:__imp_GetLastError
0x180020de0  mov     ebx, eax
0x180020de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020de9  lea     rax, WPP_GLOBAL_Control
0x180020df0  cmp     rcx, rax
0x180020df3  jz      loc_180020FE3
0x180020df9  test    byte ptr [rcx+1Ch], 1
0x180020dfd  jz      loc_180020FE3
0x180020e03  mov     edx, 47h ; 'G'
0x180020e08  jmp     loc_180020FD0
0x180020e0d  cmp     dword ptr [rbp+30h], 0Dh
0x180020e11  jnz     short loc_180020E69
0x180020e13  mov     rax, [rbp+2A0h]
0x180020e1a  mov     rdx, [rax]; lpszHeaders
0x180020e1d  test    rdx, rdx
0x180020e20  jz      short loc_180020E69
0x180020e22  mov     r9d, ebx; dwModifiers
0x180020e25  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180020e29  mov     rcx, rsi; hRequest
0x180020e2c  call    cs:__imp_WinHttpAddRequestHeaders
0x180020e32  test    eax, eax
0x180020e34  jnz     short loc_180020E69
0x180020e36  call    cs:__imp_GetLastError
0x180020e3c  mov     ebx, eax
0x180020e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e45  lea     rax, WPP_GLOBAL_Control
0x180020e4c  cmp     rcx, rax
0x180020e4f  jz      loc_180020FE3
0x180020e55  test    byte ptr [rcx+1Ch], 1
0x180020e59  jz      loc_180020FE3
0x180020e5f  mov     edx, 48h ; 'H'
0x180020e64  jmp     loc_180020FD0
0x180020e69  mov     r9d, ebx; dwModifiers
0x180020e6c  lea     rdx, szHeaders; "translate: f\n"
0x180020e73  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180020e77  mov     rcx, rsi; hRequest
0x180020e7a  call    cs:__imp_WinHttpAddRequestHeaders
0x180020e80  test    eax, eax
0x180020e82  jnz     short loc_180020EB7
0x180020e84  call    cs:__imp_GetLastError
0x180020e8a  mov     ebx, eax
0x180020e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e93  lea     rax, WPP_GLOBAL_Control
0x180020e9a  cmp     rcx, rax
0x180020e9d  jz      loc_180020FE3
0x180020ea3  test    byte ptr [rcx+1Ch], 1
0x180020ea7  jz      loc_180020FE3
0x180020ead  mov     edx, 49h ; 'I'
0x180020eb2  jmp     loc_180020FD0
0x180020eb7  mov     rax, [rbp+1F0h]
0x180020ebe  test    rax, rax
0x180020ec1  jz      short loc_180020ECC
0x180020ec3  cmp     dword ptr [rax+68h], 2
0x180020ec7  mov     r9d, r14d
0x180020eca  jz      short loc_180020ED2
0x180020ecc  mov     r9d, 1
0x180020ed2  mov     r8, rsi
0x180020ed5  mov     [rsp+0A8h+var_88], r14d
0x180020eda  xor     edx, edx
0x180020edc  mov     rcx, rbp
0x180020edf  call    DavInternetSetOption
0x180020ee4  mov     ebx, eax
0x180020ee6  test    eax, eax
0x180020ee8  jnz     loc_180020FE3
0x180020eee  mov     r9, [rsp+0A8h+arg_20]
0x180020ef6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020efa  mov     rax, r8
0x180020efd  inc     rax
0x180020f00  cmp     [r9+rax], r14b
0x180020f04  jnz     short loc_180020EFD
0x180020f06  lea     rdx, rgXmlHeader; "Content-Type: text/xml; charset=\"utf-8"...
0x180020f0d  inc     r8
0x180020f10  cmp     [rdx+r8*2], r14w
0x180020f15  jnz     short loc_180020F0D
0x180020f17  mov     [rsp+0A8h+var_70], rbp; __int64
0x180020f1c  mov     rcx, rsi; hRequest
0x180020f1f  mov     [rsp+0A8h+var_80], eax; DWORD
0x180020f23  mov     [rsp+0A8h+var_88], eax; DWORD
0x180020f27  call    DavSendRequest
0x180020f2c  mov     ebx, eax
0x180020f2e  test    eax, eax
0x180020f30  jz      short loc_180020F62
0x180020f32  mov     ecx, eax; dwErrCode
0x180020f34  call    cs:__imp_SetLastError
0x180020f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f41  lea     rax, WPP_GLOBAL_Control
0x180020f48  cmp     rcx, rax
0x180020f4b  jz      loc_180020FE3
0x180020f51  test    byte ptr [rcx+1Ch], 1
0x180020f55  jz      loc_180020FE3
0x180020f5b  mov     edx, 4Ah ; 'J'
0x180020f60  jmp     short loc_180020FD0
0x180020f62  xor     edx, edx
0x180020f64  mov     rcx, rsi
0x180020f67  call    DavQueryAndParseResponseEx
0x180020f6c  mov     ebx, eax
0x180020f6e  test    eax, eax
0x180020f70  jz      short loc_180020F9A
0x180020f72  mov     ecx, eax; dwErrCode
0x180020f74  call    cs:__imp_SetLastError
0x180020f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f81  lea     rax, WPP_GLOBAL_Control
0x180020f88  cmp     rcx, rax
0x180020f8b  jz      short loc_180020FE3
0x180020f8d  test    byte ptr [rcx+1Ch], 1
0x180020f91  jz      short loc_180020FE3
0x180020f93  mov     edx, 4Bh ; 'K'
0x180020f98  jmp     short loc_180020FD0
0x180020f9a  xor     edx, edx; hMem
0x180020f9c  mov     rcx, rsi; hRequest
0x180020f9f  call    DavParseXmlResponse
0x180020fa4  mov     ebx, eax
0x180020fa6  test    eax, eax
0x180020fa8  jz      short loc_180020FE3
0x180020faa  mov     ecx, eax; dwErrCode
0x180020fac  call    cs:__imp_SetLastError
0x180020fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fb9  lea     rax, WPP_GLOBAL_Control
0x180020fc0  cmp     rcx, rax
0x180020fc3  jz      short loc_180020FE3
0x180020fc5  test    byte ptr [rcx+1Ch], 1
0x180020fc9  jz      short loc_180020FE3
0x180020fcb  mov     edx, 4Ch ; 'L'
0x180020fd0  mov     r9d, ebx
0x180020fd3  mov     rcx, [rcx+10h]
0x180020fd7  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x180020fde  call    WPP_SF_d
0x180020fe3  test    rsi, rsi
0x180020fe6  jz      short loc_180020FF1
0x180020fe8  mov     rcx, rsi; hInternet
0x180020feb  call    cs:__imp_WinHttpCloseHandle
0x180020ff1  mov     eax, ebx
0x180020ff3  add     rsp, 88h
0x180020ffa  pop     r14
0x180020ffc  pop     rsi
0x180020ffd  pop     rbp
0x180020ffe  pop     rbx
0x180020fff  retn
```
