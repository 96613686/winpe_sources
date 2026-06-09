# CToken::GetLogonIDSid(void *,void * *)

- ea: `0x180078e8c`
- end: `0x1800790ca`
- name: `?GetLogonIDSid@CToken@@SAJPEAXPEAPEAX@Z`
- size: `574`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004cd64`
- `0x1800507c0`

## callees

- `0x180034540`
- `0x180078e8c`
- `0x1800a1e98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079057`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007904d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007904d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078eba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078f6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078eba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078f6c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007901e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007901e`
- `KERNELBASE!LocalAlloc` at `0x180078f3d`
- `KERNELBASE!LocalAlloc` at `0x18007902c`
- `KERNELBASE!LocalAlloc` at `0x180078f3d`
- `KERNELBASE!LocalAlloc` at `0x18007902c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180079007`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800790bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180079007`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800790bf`

## string_xrefs

- `0x180078f26`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180078fcf`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800790b0`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180078f1f`: `CToken::GetLogonIDSid`
- `0x180078fc8`: `CToken::GetLogonIDSid`
- `0x1800790a9`: `CToken::GetLogonIDSid`

## pseudocode

```c
__int64 __fastcall CToken::GetLogonIDSid(HANDLE TokenHandle, void **a2)
{
  signed int LastError; // eax
  signed int v5; // r8d
  unsigned int v6; // ebx
  _DWORD *v7; // rdi
  signed int v8; // eax
  signed int v9; // r8d
  void *v10; // rsi
  unsigned int v11; // ecx
  __int64 v12; // rbx
  HLOCAL v14; // rax
  signed int v15; // eax
  signed int v16; // r8d
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError == 122 )
  {
    v7 = LocalAlloc(0, TokenInformationLength);
    if ( !v7 )
      return (unsigned int)-2147024882;
    if ( !GetTokenInformation(TokenHandle, TokenGroups, v7, TokenInformationLength, &TokenInformationLength) )
    {
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      else
        v6 = v8;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<int>(
          (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (__int64)"CToken::GetLogonIDSid",
          0x638u,
          0,
          (__int64)L"%!WINERROR!",
          v9);
      goto LABEL_23;
    }
    v10 = 0;
    v11 = 0;
    if ( *v7 )
    {
      while ( 1 )
      {
        v12 = 2LL * v11;
        if ( (v7[4 * v11 + 4] & 0xC0000008) == 0xC0000008 )
          break;
        if ( ++v11 >= *v7 )
          goto LABEL_22;
      }
      TokenInformationLength = GetLengthSid(*(PSID *)&v7[4 * v11 + 2]);
      v14 = LocalAlloc(0, TokenInformationLength);
      v10 = v14;
      if ( !v14 )
      {
        v6 = -2147024882;
        goto LABEL_23;
      }
      if ( !CopySid(TokenInformationLength, v14, *(PSID *)&v7[2 * v12 + 2]) )
      {
        v15 = GetLastError();
        v16 = v15;
        if ( v15 > 0 )
          v6 = (unsigned __int16)v15 | 0x80070000;
        else
          v6 = v15;
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          ComTraceMessageT<int>(
            (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            (__int64)"CToken::GetLogonIDSid",
            0x64Eu,
            0,
            (__int64)L"%!WINERROR!",
            v16);
        LocalFree(v10);
        goto LABEL_23;
      }
    }
LABEL_22:
    v6 = 0;
    *a2 = v10;
LABEL_23:
    LocalFree(v7);
    return v6;
  }
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  else
    v6 = LastError;
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<int>(
      (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (__int64)"CToken::GetLogonIDSid",
      0x624u,
      0,
      (__int64)L"%!WINERROR!",
      v5);
  return v6;
}

```

## disassembly

```asm
0x180078e8c  push    rbx
0x180078e8e  push    rsi
0x180078e8f  push    rdi
0x180078e90  push    r14
0x180078e92  sub     rsp, 38h
0x180078e96  xor     r9d, r9d; TokenInformationLength
0x180078e99  mov     [rsp+58h+TokenInformationLength], 0
0x180078ea1  mov     r14, rdx
0x180078ea4  lea     rax, [rsp+58h+TokenInformationLength]
0x180078ea9  xor     r8d, r8d; TokenInformation
0x180078eac  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180078eb1  mov     rbx, rcx
0x180078eb4  lea     esi, [r9+2]
0x180078eb8  mov     edx, esi; TokenInformationClass
0x180078eba  call    cs:__imp_GetTokenInformation
0x180078ec0  call    cs:__imp_GetLastError
0x180078ec6  mov     r8d, eax
0x180078ec9  cmp     eax, 7Ah ; 'z'
0x180078ecc  jz      short loc_180078F37
0x180078ece  test    eax, eax
0x180078ed0  jg      short loc_180078ED6
0x180078ed2  mov     ebx, eax
0x180078ed4  jmp     short loc_180078EE0
0x180078ed6  movzx   ebx, r8w
0x180078eda  or      ebx, 80070000h
0x180078ee0  mov     eax, cs:dword_18014E4B8
0x180078ee6  test    eax, eax
0x180078ee8  jnz     short loc_180078F05
0x180078eea  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180078ef0  jz      loc_18007900D
0x180078ef6  xor     ecx, ecx
0x180078ef8  call    IsWppLevelEnabled
0x180078efd  test    al, al
0x180078eff  jz      loc_18007900D
0x180078f05  mov     [rsp+58h+var_30], r8d
0x180078f0a  lea     rax, aWinerror; "%!WINERROR!"
0x180078f11  mov     r8d, 624h
0x180078f17  mov     [rsp+58h+ReturnLength], rax
0x180078f1c  xor     r9d, r9d
0x180078f1f  lea     rdx, aCtokenGetlogon; "CToken::GetLogonIDSid"
0x180078f26  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180078f2d  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180078f32  jmp     loc_18007900D
0x180078f37  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x180078f3b  xor     ecx, ecx; uFlags
0x180078f3d  call    cs:__imp_LocalAlloc
0x180078f43  mov     rdi, rax
0x180078f46  test    rax, rax
0x180078f49  jnz     short loc_180078F55
0x180078f4b  mov     ebx, 8007000Eh
0x180078f50  jmp     loc_18007900D
0x180078f55  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180078f5a  lea     rax, [rsp+58h+TokenInformationLength]
0x180078f5f  mov     r8, rdi; TokenInformation
0x180078f62  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180078f67  mov     edx, esi; TokenInformationClass
0x180078f69  mov     rcx, rbx; TokenHandle
0x180078f6c  call    cs:__imp_GetTokenInformation
0x180078f72  test    eax, eax
0x180078f74  jnz     short loc_180078FDD
0x180078f76  call    cs:__imp_GetLastError
0x180078f7c  mov     r8d, eax
0x180078f7f  test    eax, eax
0x180078f81  jg      short loc_180078F87
0x180078f83  mov     ebx, eax
0x180078f85  jmp     short loc_180078F91
0x180078f87  movzx   ebx, r8w
0x180078f8b  or      ebx, 80070000h
0x180078f91  mov     eax, cs:dword_18014E4B8
0x180078f97  test    eax, eax
0x180078f99  jnz     short loc_180078FAE
0x180078f9b  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180078fa1  jz      short loc_180079004
0x180078fa3  xor     ecx, ecx
0x180078fa5  call    IsWppLevelEnabled
0x180078faa  test    al, al
0x180078fac  jz      short loc_180079004
0x180078fae  mov     [rsp+58h+var_30], r8d
0x180078fb3  lea     rax, aWinerror; "%!WINERROR!"
0x180078fba  mov     r8d, 638h
0x180078fc0  mov     [rsp+58h+ReturnLength], rax
0x180078fc5  xor     r9d, r9d
0x180078fc8  lea     rdx, aCtokenGetlogon; "CToken::GetLogonIDSid"
0x180078fcf  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180078fd6  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180078fdb  jmp     short loc_180079004
0x180078fdd  xor     esi, esi
0x180078fdf  xor     ecx, ecx
0x180078fe1  cmp     [rdi], ecx
0x180078fe3  jbe     short loc_180078FFF
0x180078fe5  mov     edx, 0C0000008h
0x180078fea  mov     ebx, ecx
0x180078fec  add     rbx, rbx
0x180078fef  mov     eax, [rdi+rbx*8+10h]
0x180078ff3  and     eax, edx
0x180078ff5  cmp     eax, edx
0x180078ff7  jz      short loc_180079019
0x180078ff9  inc     ecx
0x180078ffb  cmp     ecx, [rdi]
0x180078ffd  jb      short loc_180078FEA
0x180078fff  xor     ebx, ebx
0x180079001  mov     [r14], rsi
0x180079004  mov     rcx, rdi; hMem
0x180079007  call    cs:__imp_LocalFree
0x18007900d  mov     eax, ebx
0x18007900f  add     rsp, 38h
0x180079013  pop     r14
0x180079015  pop     rdi
0x180079016  pop     rsi
0x180079017  pop     rbx
0x180079018  retn
0x180079019  mov     rcx, [rdi+rbx*8+8]; pSid
0x18007901e  call    cs:__imp_GetLengthSid
0x180079024  mov     edx, eax; uBytes
0x180079026  xor     ecx, ecx; uFlags
0x180079028  mov     [rsp+58h+TokenInformationLength], edx
0x18007902c  call    cs:__imp_LocalAlloc
0x180079032  mov     rsi, rax
0x180079035  test    rax, rax
0x180079038  jnz     short loc_180079041
0x18007903a  mov     ebx, 8007000Eh
0x18007903f  jmp     short loc_180079004
0x180079041  mov     r8, [rdi+rbx*8+8]; pSourceSid
0x180079046  mov     rdx, rsi; pDestinationSid
0x180079049  mov     ecx, [rsp+58h+TokenInformationLength]; nDestinationSidLength
0x18007904d  call    cs:__imp_CopySid
0x180079053  test    eax, eax
0x180079055  jnz     short loc_180078FFF
0x180079057  call    cs:__imp_GetLastError
0x18007905d  mov     r8d, eax
0x180079060  test    eax, eax
0x180079062  jg      short loc_180079068
0x180079064  mov     ebx, eax
0x180079066  jmp     short loc_180079072
0x180079068  movzx   ebx, r8w
0x18007906c  or      ebx, 80070000h
0x180079072  mov     eax, cs:dword_18014E4B8
0x180079078  test    eax, eax
0x18007907a  jnz     short loc_18007908F
0x18007907c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180079082  jz      short loc_1800790BC
0x180079084  xor     ecx, ecx
0x180079086  call    IsWppLevelEnabled
0x18007908b  test    al, al
0x18007908d  jz      short loc_1800790BC
0x18007908f  mov     [rsp+58h+var_30], r8d
0x180079094  lea     rax, aWinerror; "%!WINERROR!"
0x18007909b  mov     r8d, 64Eh
0x1800790a1  mov     [rsp+58h+ReturnLength], rax
0x1800790a6  xor     r9d, r9d
0x1800790a9  lea     rdx, aCtokenGetlogon; "CToken::GetLogonIDSid"
0x1800790b0  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x1800790b7  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800790bc  mov     rcx, rsi; hMem
0x1800790bf  call    cs:__imp_LocalFree
0x1800790c5  jmp     loc_180079004
```
