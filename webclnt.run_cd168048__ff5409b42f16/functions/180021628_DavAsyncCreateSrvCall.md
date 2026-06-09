# DavAsyncCreateSrvCall

- ea: `0x180021628`
- end: `0x180021c4e`
- name: `DavAsyncCreateSrvCall`
- size: `1574`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d9e4`

## callees

- `0x18000b4f0`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x180013414`
- `0x1800134d8`
- `0x180021628`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bda`
- `KERNEL32!LocalFree` at `0x180021bcf`
- `KERNEL32!LocalFree` at `0x180021c13`
- `KERNEL32!LocalFree` at `0x180021c26`
- `KERNEL32!LocalFree` at `0x180021bcf`
- `KERNEL32!LocalFree` at `0x180021c13`
- `KERNEL32!LocalFree` at `0x180021c26`
- `KERNEL32!LocalAlloc` at `0x180021743`
- `KERNEL32!LocalAlloc` at `0x180021863`
- `KERNEL32!LocalAlloc` at `0x180021a1b`
- `KERNEL32!LocalAlloc` at `0x180021743`
- `KERNEL32!LocalAlloc` at `0x180021863`
- `KERNEL32!LocalAlloc` at `0x180021a1b`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800217ab`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800218bc`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800219a3`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021a71`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021af2`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800217ab`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800218bc`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800219a3`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021a71`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021af2`

## pseudocode

```c
__int64 __fastcall DavAsyncCreateSrvCall(__int64 a1)
{
  __int64 v1; // r9
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  void *v6; // r13
  unsigned int v7; // eax
  WCHAR *v8; // r12
  DWORD LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HLOCAL v12; // rax
  const WCHAR *v13; // rbx
  LPDWORD lpdwIndex; // r11
  BOOL v15; // eax
  _DWORD *v16; // rax
  DWORD v17; // eax
  _WORD *v18; // r12
  DWORD v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  DWORD v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  DWORD dwBufferLength; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpdwBufferLength; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *v28; // [rsp+38h] [rbp-C8h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h]
  _BYTE Buffer[208]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = *(unsigned int *)(a1 + 52);
  lpdwBufferLength = 0;
  if ( (_DWORD)v1 != 3 )
  {
    v3 = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 54;
LABEL_12:
      WPP_SF_d(v4[2], v5, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v1);
      return v3;
    }
    return v3;
  }
  dwBufferLength = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
  v6 = *(void **)(a1 + 528);
  v7 = DavQueryAndParseResponseEx(v6, 0);
  v3 = v7;
  if ( !v7 )
  {
    v3 = 0;
    v8 = 0;
    v28 = 0;
    hMem = 0;
    if ( !*(_DWORD *)&AcceptOfficeAndTahoeServers )
    {
      v28 = (wchar_t *)LocalAlloc(0x40u, 0x32u);
      v8 = v28;
      if ( !v28 )
        return 8;
      memset_0(Buffer, 0, 0xC8u);
      StringCbCopyW(v28, 0x32u, L"MicrosoftOfficeWebServer");
      dwBufferLength = 200;
      if ( WinHttpQueryHeaders(v6, 0xFFFFu, v28, Buffer, &dwBufferLength, 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
        *(_DWORD *)(*(_QWORD *)(a1 + 504) + 48LL) = 1;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError != 12150 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_92;
          v11 = 40;
          goto LABEL_36;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
        *(_DWORD *)(*(_QWORD *)(a1 + 504) + 48LL) = 0;
      }
      memset_0(Buffer, 0, 0xC8u);
      v12 = LocalAlloc(0x40u, 0x2Au);
      hMem = v12;
      v13 = (const WCHAR *)v12;
      if ( !v12 )
      {
        v3 = 8;
LABEL_92:
        LocalFree(v8);
LABEL_93:
        if ( hMem )
          LocalFree(hMem);
        return v3;
      }
      StringCbCopyW((STRSAFE_LPWSTR)v12, 0x2Au, L"MicrosoftTahoeServer");
      dwBufferLength = 200;
      v15 = WinHttpQueryHeaders(v6, 0xFFFFu, v13, Buffer, &dwBufferLength, lpdwIndex);
      v3 = 0;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
        *(_DWORD *)(*(_QWORD *)(a1 + 504) + 52LL) = 1;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError != 12150 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_92;
          v11 = 43;
LABEL_36:
          WPP_SF_d(v10[2], v11, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, LastError);
          goto LABEL_92;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
        v3 = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 504) + 52LL) = 0;
      }
      v16 = *(_DWORD **)(a1 + 504);
      if ( v16[12] || v16[13] )
      {
        v16[9] = 0;
        v3 = 53;
        goto LABEL_92;
      }
    }
    if ( !WinHttpQueryHeaders(v6, 0x16u, 0, 0, &lpdwBufferLength, 0) )
    {
      v17 = GetLastError();
      v3 = v17;
      if ( v17 != 122 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v17);
LABEL_91:
        if ( !v8 )
          goto LABEL_93;
        goto LABEL_92;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
      v3 = 0;
    }
    v18 = LocalAlloc(0x40u, lpdwBufferLength);
    if ( !v18 )
    {
      v19 = GetLastError();
      v3 = v19;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_90;
      v21 = 48;
LABEL_89:
      WPP_SF_d(v20[2], v21, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v19);
LABEL_90:
      v8 = v28;
      goto LABEL_91;
    }
    if ( !WinHttpQueryHeaders(v6, 0x16u, 0, v18, &lpdwBufferLength, 0) )
    {
      v22 = GetLastError();
      v3 = v22;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_85;
      v24 = 49;
      goto LABEL_65;
    }
    DavObtainServerProperties(
      v18,
      *(_QWORD *)(a1 + 504) + 28LL,
      *(_QWORD *)(a1 + 504) + 44LL,
      *(_QWORD *)(a1 + 504) + 36LL);
    if ( WinHttpQueryHeaders(v6, 0xFFFFu, L"X-MSDAVEXT", v18, &lpdwBufferLength, 0) )
    {
      if ( *v18 == 49 && !v18[1] )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
        *(_DWORD *)(*(_QWORD *)(a1 + 504) + 40LL) = 1;
        goto LABEL_85;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v18);
    }
    else
    {
      v22 = GetLastError();
      v3 = v22;
      if ( v22 != 12150 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_85;
        v24 = 50;
LABEL_65:
        WPP_SF_d(v23[2], v24, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v22);
        goto LABEL_85;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids);
    }
    v3 = 0;
LABEL_84:
    *(_DWORD *)(*(_QWORD *)(a1 + 504) + 40LL) = 0;
LABEL_85:
    if ( !LocalFree(v18) )
      goto LABEL_90;
    v19 = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_90;
    v21 = 56;
    goto LABEL_89;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 39;
    v1 = v7;
    goto LABEL_12;
  }
  return v3;
}

```

## disassembly

```asm
0x180021628  push    rbp
0x18002162a  push    rbx
0x18002162b  push    rsi
0x18002162c  push    rdi
0x18002162d  push    r12
0x18002162f  push    r13
0x180021631  push    r14
0x180021633  push    r15
0x180021635  lea     rbp, [rsp-38h]
0x18002163a  sub     rsp, 138h
0x180021641  mov     rax, cs:__security_cookie
0x180021648  xor     rax, rsp
0x18002164b  mov     [rbp+70h+var_50], rax
0x18002164f  mov     r9d, [rcx+34h]
0x180021653  xor     r14d, r14d
0x180021656  mov     [rsp+170h+var_13C], r14d
0x18002165b  mov     r15, rcx
0x18002165e  cmp     r9d, 3
0x180021662  jz      short loc_180021699
0x180021664  lea     ebx, [r14+57h]
0x180021668  mov     rcx, cs:WPP_GLOBAL_Control
0x18002166f  lea     rdi, WPP_GLOBAL_Control
0x180021676  cmp     rcx, rdi
0x180021679  jz      loc_180021C2C
0x18002167f  lea     r14d, [rbx-56h]
0x180021683  test    [rcx+1Ch], r14b
0x180021687  jz      loc_180021C2C
0x18002168d  lea     edx, [rbx-21h]
0x180021690  lea     r8, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids
0x180021697  jmp     short loc_180021710
0x180021699  mov     [rsp+170h+dwBufferLength], r14d
0x18002169e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216a5  lea     rdi, WPP_GLOBAL_Control
0x1800216ac  lea     rsi, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids
0x1800216b3  cmp     rcx, rdi
0x1800216b6  jz      short loc_1800216CF
0x1800216b8  test    byte ptr [rcx+1Ch], 2
0x1800216bc  jz      short loc_1800216CF
0x1800216be  mov     rcx, [rcx+10h]
0x1800216c2  mov     edx, 26h ; '&'
0x1800216c7  mov     r8, rsi
0x1800216ca  call    WPP_SF_
0x1800216cf  mov     r13, [r15+210h]
0x1800216d6  xor     edx, edx
0x1800216d8  mov     rcx, r13
0x1800216db  call    DavQueryAndParseResponseEx
0x1800216e0  mov     ebx, eax
0x1800216e2  test    eax, eax
0x1800216e4  jz      short loc_18002171E
0x1800216e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216ed  cmp     rcx, rdi
0x1800216f0  jz      loc_180021C2C
0x1800216f6  mov     r14d, 1
0x1800216fc  test    [rcx+1Ch], r14b
0x180021700  jz      loc_180021C2C
0x180021706  lea     edx, [r14+26h]
0x18002170a  mov     r9d, eax
0x18002170d  mov     r8, rsi
0x180021710  mov     rcx, [rcx+10h]
0x180021714  call    WPP_SF_d
0x180021719  jmp     loc_180021C2C
0x18002171e  xor     ebx, ebx
0x180021720  cmp     cs:AcceptOfficeAndTahoeServers, ebx
0x180021726  mov     r12d, ebx
0x180021729  mov     [rsp+170h+var_138], rbx
0x18002172e  mov     [rsp+170h+hMem], rbx
0x180021733  lea     r14d, [rbx+1]
0x180021737  jnz     loc_180021987
0x18002173d  lea     edx, [rbx+32h]; uBytes
0x180021740  lea     ecx, [rbx+40h]; uFlags
0x180021743  call    cs:__imp_LocalAlloc
0x180021749  mov     [rsp+170h+var_138], rax
0x18002174e  mov     r12, rax
0x180021751  test    rax, rax
0x180021754  jnz     short loc_18002175E
0x180021756  lea     ebx, [rax+8]
0x180021759  jmp     loc_180021C2C
0x18002175e  xor     edx, edx; Val
0x180021760  lea     rcx, [rsp+170h+Buffer]; void *
0x180021765  mov     r8d, 0C8h; Size
0x18002176b  call    memset_0
0x180021770  lea     r8, aMicrosoftoffic; "MicrosoftOfficeWebServer"
0x180021777  mov     edx, 32h ; '2'; cbDest
0x18002177c  mov     rcx, r12; pszDest
0x18002177f  call    StringCbCopyW
0x180021784  lea     rax, [rsp+170h+dwBufferLength]
0x180021789  mov     [rsp+170h+lpdwIndex], rbx; lpdwIndex
0x18002178e  lea     r9, [rsp+170h+Buffer]; lpBuffer
0x180021793  mov     [rsp+170h+lpdwBufferLength], rax; lpdwBufferLength
0x180021798  mov     r8, r12; pwszName
0x18002179b  mov     [rsp+170h+dwBufferLength], 0C8h
0x1800217a3  mov     edx, 0FFFFh; dwInfoLevel
0x1800217a8  mov     rcx, r13; hRequest
0x1800217ab  call    cs:__imp_WinHttpQueryHeaders
0x1800217b1  test    eax, eax
0x1800217b3  jnz     short loc_18002181B
0x1800217b5  call    cs:__imp_GetLastError
0x1800217bb  mov     ebx, eax
0x1800217bd  cmp     eax, 2F76h
0x1800217c2  jz      short loc_1800217E8
0x1800217c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217cb  cmp     rcx, rdi
0x1800217ce  jz      loc_180021C10
0x1800217d4  test    [rcx+1Ch], r14b
0x1800217d8  jz      loc_180021C10
0x1800217de  mov     edx, 28h ; '('
0x1800217e3  jmp     loc_1800218F6
0x1800217e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217ef  cmp     rcx, rdi
0x1800217f2  jz      short loc_18002180B
0x1800217f4  test    byte ptr [rcx+1Ch], 2
0x1800217f8  jz      short loc_18002180B
0x1800217fa  mov     rcx, [rcx+10h]
0x1800217fe  mov     edx, 29h ; ')'
0x180021803  mov     r8, rsi
0x180021806  call    WPP_SF_
0x18002180b  mov     rax, [r15+1F8h]
0x180021812  mov     dword ptr [rax+30h], 0
0x180021819  jmp     short loc_180021849
0x18002181b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021822  cmp     rcx, rdi
0x180021825  jz      short loc_18002183E
0x180021827  test    byte ptr [rcx+1Ch], 2
0x18002182b  jz      short loc_18002183E
0x18002182d  mov     rcx, [rcx+10h]
0x180021831  mov     edx, 2Ah ; '*'
0x180021836  mov     r8, rsi
0x180021839  call    WPP_SF_
0x18002183e  mov     rax, [r15+1F8h]
0x180021845  mov     [rax+30h], r14d
0x180021849  xor     edx, edx; Val
0x18002184b  lea     rcx, [rsp+170h+Buffer]; void *
0x180021850  mov     r8d, 0C8h; Size
0x180021856  call    memset_0
0x18002185b  mov     edx, 2Ah ; '*'; uBytes
0x180021860  lea     ecx, [rdx+16h]; uFlags
0x180021863  call    cs:__imp_LocalAlloc
0x180021869  xor     r11d, r11d
0x18002186c  mov     [rsp+170h+hMem], rax
0x180021871  mov     rbx, rax
0x180021874  test    rax, rax
0x180021877  jnz     short loc_180021881
0x180021879  lea     ebx, [rax+8]
0x18002187c  jmp     loc_180021C10
0x180021881  lea     r8, aMicrosofttahoe; "MicrosoftTahoeServer"
0x180021888  mov     edx, 2Ah ; '*'; cbDest
0x18002188d  mov     rcx, rbx; pszDest
0x180021890  call    StringCbCopyW
0x180021895  lea     rax, [rsp+170h+dwBufferLength]
0x18002189a  mov     [rsp+170h+lpdwIndex], r11; lpdwIndex
0x18002189f  lea     r9, [rsp+170h+Buffer]; lpBuffer
0x1800218a4  mov     [rsp+170h+lpdwBufferLength], rax; lpdwBufferLength
0x1800218a9  mov     r8, rbx; pwszName
0x1800218ac  mov     [rsp+170h+dwBufferLength], 0C8h
0x1800218b4  mov     edx, 0FFFFh; dwInfoLevel
0x1800218b9  mov     rcx, r13; hRequest
0x1800218bc  call    cs:__imp_WinHttpQueryHeaders
0x1800218c2  xor     ebx, ebx
0x1800218c4  test    eax, eax
0x1800218c6  jnz     short loc_18002193B
0x1800218c8  call    cs:__imp_GetLastError
0x1800218ce  mov     ebx, eax
0x1800218d0  cmp     eax, 2F76h
0x1800218d5  jz      short loc_18002190A
0x1800218d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218de  cmp     rcx, rdi
0x1800218e1  jz      loc_180021C10
0x1800218e7  test    [rcx+1Ch], r14b
0x1800218eb  jz      loc_180021C10
0x1800218f1  mov     edx, 2Bh ; '+'
0x1800218f6  mov     rcx, [rcx+10h]
0x1800218fa  mov     r9d, eax
0x1800218fd  mov     r8, rsi
0x180021900  call    WPP_SF_d
0x180021905  jmp     loc_180021C10
0x18002190a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021911  cmp     rcx, rdi
0x180021914  jz      short loc_18002192D
0x180021916  test    byte ptr [rcx+1Ch], 2
0x18002191a  jz      short loc_18002192D
0x18002191c  mov     rcx, [rcx+10h]
0x180021920  mov     edx, 2Ch ; ','
0x180021925  mov     r8, rsi
0x180021928  call    WPP_SF_
0x18002192d  mov     rax, [r15+1F8h]
0x180021934  xor     ebx, ebx
0x180021936  mov     [rax+34h], ebx
0x180021939  jmp     short loc_180021969
0x18002193b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021942  cmp     rcx, rdi
0x180021945  jz      short loc_18002195E
0x180021947  test    byte ptr [rcx+1Ch], 2
0x18002194b  jz      short loc_18002195E
0x18002194d  mov     rcx, [rcx+10h]
0x180021951  mov     edx, 2Dh ; '-'
0x180021956  mov     r8, rsi
0x180021959  call    WPP_SF_
0x18002195e  mov     rax, [r15+1F8h]
0x180021965  mov     [rax+34h], r14d
0x180021969  mov     rax, [r15+1F8h]
0x180021970  cmp     [rax+30h], ebx
0x180021973  jnz     short loc_18002197A
0x180021975  cmp     [rax+34h], ebx
0x180021978  jz      short loc_180021987
0x18002197a  mov     [rax+24h], ebx
0x18002197d  mov     ebx, 35h ; '5'
0x180021982  jmp     loc_180021C10
0x180021987  xor     r9d, r9d; lpBuffer
0x18002198a  mov     [rsp+170h+lpdwIndex], rbx; lpdwIndex
0x18002198f  lea     rax, [rsp+170h+var_13C]
0x180021994  xor     r8d, r8d; pwszName
0x180021997  mov     rcx, r13; hRequest
0x18002199a  mov     [rsp+170h+lpdwBufferLength], rax; lpdwBufferLength
0x18002199f  lea     edx, [r9+16h]; dwInfoLevel
0x1800219a3  call    cs:__imp_WinHttpQueryHeaders
0x1800219a9  test    eax, eax
0x1800219ab  jnz     short loc_180021A12
0x1800219ad  call    cs:__imp_GetLastError
0x1800219b3  mov     ebx, eax
0x1800219b5  cmp     eax, 7Ah ; 'z'
0x1800219b8  jz      short loc_1800219ED
0x1800219ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219c1  cmp     rcx, rdi
0x1800219c4  jz      loc_180021C0B
0x1800219ca  test    [rcx+1Ch], r14b
0x1800219ce  jz      loc_180021C0B
0x1800219d4  mov     rcx, [rcx+10h]
0x1800219d8  mov     edx, 2Eh ; '.'
0x1800219dd  mov     r9d, eax
0x1800219e0  mov     r8, rsi
0x1800219e3  call    WPP_SF_d
0x1800219e8  jmp     loc_180021C0B
0x1800219ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219f4  cmp     rcx, rdi
0x1800219f7  jz      short loc_180021A10
0x1800219f9  test    byte ptr [rcx+1Ch], 2
0x1800219fd  jz      short loc_180021A10
0x1800219ff  mov     rcx, [rcx+10h]
0x180021a03  mov     edx, 2Fh ; '/'
0x180021a08  mov     r8, rsi
0x180021a0b  call    WPP_SF_
0x180021a10  xor     ebx, ebx
0x180021a12  mov     edx, [rsp+170h+var_13C]; uBytes
0x180021a16  mov     ecx, 40h ; '@'; uFlags
0x180021a1b  call    cs:__imp_LocalAlloc
0x180021a21  mov     r12, rax
0x180021a24  test    rax, rax
0x180021a27  jnz     short loc_180021A55
0x180021a29  call    cs:__imp_GetLastError
0x180021a2f  mov     ebx, eax
0x180021a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a38  cmp     rcx, rdi
0x180021a3b  jz      loc_180021C06
0x180021a41  test    [rcx+1Ch], r14b
0x180021a45  jz      loc_180021C06
0x180021a4b  lea     edx, [r12+30h]
0x180021a50  jmp     loc_180021BF7
0x180021a55  xor     r8d, r8d; pwszName
0x180021a58  mov     [rsp+170h+lpdwIndex], rbx; lpdwIndex
0x180021a5d  lea     rax, [rsp+170h+var_13C]
0x180021a62  mov     r9, r12; lpBuffer
0x180021a65  mov     rcx, r13; hRequest
0x180021a68  mov     [rsp+170h+lpdwBufferLength], rax; lpdwBufferLength
0x180021a6d  lea     edx, [r8+16h]; dwInfoLevel
0x180021a71  call    cs:__imp_WinHttpQueryHeaders
0x180021a77  test    eax, eax
0x180021a79  jnz     short loc_180021AB6
0x180021a7b  call    cs:__imp_GetLastError
0x180021a81  mov     ebx, eax
0x180021a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a8a  cmp     rcx, rdi
0x180021a8d  jz      loc_180021BCC
0x180021a93  test    [rcx+1Ch], r14b
0x180021a97  jz      loc_180021BCC
0x180021a9d  mov     edx, 31h ; '1'
0x180021aa2  mov     rcx, [rcx+10h]
0x180021aa6  mov     r9d, eax
0x180021aa9  mov     r8, rsi
0x180021aac  call    WPP_SF_d
0x180021ab1  jmp     loc_180021BCC
0x180021ab6  mov     rdx, [r15+1F8h]
0x180021abd  mov     rcx, r12
0x180021ac0  lea     r9, [rdx+24h]
0x180021ac4  lea     r8, [rdx+2Ch]
0x180021ac8  add     rdx, 1Ch
0x180021acc  call    DavObtainServerProperties
0x180021ad1  lea     rax, [rsp+170h+var_13C]
0x180021ad6  mov     [rsp+170h+lpdwIndex], rbx; lpdwIndex
0x180021adb  mov     r9, r12; lpBuffer
0x180021ade  mov     [rsp+170h+lpdwBufferLength], rax; lpdwBufferLength
0x180021ae3  lea     r8, aXMsdavext; "X-MSDAVEXT"
0x180021aea  mov     edx, 0FFFFh; dwInfoLevel
0x180021aef  mov     rcx, r13; hRequest
0x180021af2  call    cs:__imp_WinHttpQueryHeaders
0x180021af8  test    eax, eax
0x180021afa  jnz     short loc_180021B58
0x180021afc  call    cs:__imp_GetLastError
0x180021b02  mov     ebx, eax
0x180021b04  cmp     eax, 2F76h
0x180021b09  jz      short loc_180021B2F
  ... truncated ...
```
