# CToken::GetLogonIDSid(void *,void * *)

- ea: `0x18007b088`
- end: `0x18007b309`
- name: `?GetLogonIDSid@CToken@@SAJPEAXPEAPEAX@Z`
- size: `641`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c4b0`
- `0x18004e578`

## callees

- `0x180034260`
- `0x18007b088`
- `0x1800a7388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b18a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b18a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b28a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007b27a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007b27a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007b0b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007b17a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007b0b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007b17a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007b23f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007b23f`
- `KERNELBASE!LocalAlloc` at `0x18007b145`
- `KERNELBASE!LocalAlloc` at `0x18007b253`
- `KERNELBASE!LocalAlloc` at `0x18007b145`
- `KERNELBASE!LocalAlloc` at `0x18007b253`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007b221`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007b2f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007b221`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007b2f8`

## string_xrefs

- `0x18007b12e`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18007b1e9`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18007b2e9`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18007b127`: `CToken::GetLogonIDSid`
- `0x18007b1e2`: `CToken::GetLogonIDSid`
- `0x18007b2e2`: `CToken::GetLogonIDSid`

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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (unsigned int)"CToken::GetLogonIDSid",
          1592,
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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          ComTraceMessageT<int>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            (unsigned int)"CToken::GetLogonIDSid",
            1614,
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
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<int>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (unsigned int)"CToken::GetLogonIDSid",
      1572,
      0,
      (__int64)L"%!WINERROR!",
      v5);
  return v6;
}

```

## disassembly

```asm
0x18007b088  push    rbx
0x18007b08a  push    rsi
0x18007b08b  push    rdi
0x18007b08c  push    r14
0x18007b08e  sub     rsp, 38h
0x18007b092  xor     r9d, r9d; TokenInformationLength
0x18007b095  mov     [rsp+58h+TokenInformationLength], 0
0x18007b09d  mov     r14, rdx
0x18007b0a0  lea     rax, [rsp+58h+TokenInformationLength]
0x18007b0a5  xor     r8d, r8d; TokenInformation
0x18007b0a8  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007b0ad  mov     rbx, rcx
0x18007b0b0  lea     esi, [r9+2]
0x18007b0b4  mov     edx, esi; TokenInformationClass
0x18007b0b6  call    cs:__imp_GetTokenInformation
0x18007b0bd  nop     dword ptr [rax+rax+00h]
0x18007b0c2  call    cs:__imp_GetLastError
0x18007b0c9  nop     dword ptr [rax+rax+00h]
0x18007b0ce  mov     r8d, eax
0x18007b0d1  cmp     eax, 7Ah ; 'z'
0x18007b0d4  jz      short loc_18007B13F
0x18007b0d6  test    eax, eax
0x18007b0d8  jg      short loc_18007B0DE
0x18007b0da  mov     ebx, eax
0x18007b0dc  jmp     short loc_18007B0E8
0x18007b0de  movzx   ebx, r8w
0x18007b0e2  or      ebx, 80070000h
0x18007b0e8  mov     eax, cs:dword_1801574B8
0x18007b0ee  test    eax, eax
0x18007b0f0  jnz     short loc_18007B10D
0x18007b0f2  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18007b0f8  jz      loc_18007B22D
0x18007b0fe  xor     ecx, ecx
0x18007b100  call    IsWppLevelEnabled
0x18007b105  test    al, al
0x18007b107  jz      loc_18007B22D
0x18007b10d  mov     [rsp+58h+var_30], r8d
0x18007b112  lea     rax, aWinerror; "%!WINERROR!"
0x18007b119  mov     r8d, 624h
0x18007b11f  mov     [rsp+58h+ReturnLength], rax
0x18007b124  xor     r9d, r9d
0x18007b127  lea     rdx, aCtokenGetlogon; "CToken::GetLogonIDSid"
0x18007b12e  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18007b135  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18007b13a  jmp     loc_18007B22D
0x18007b13f  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18007b143  xor     ecx, ecx; uFlags
0x18007b145  call    cs:__imp_LocalAlloc
0x18007b14c  nop     dword ptr [rax+rax+00h]
0x18007b151  mov     rdi, rax
0x18007b154  test    rax, rax
0x18007b157  jnz     short loc_18007B163
0x18007b159  mov     ebx, 8007000Eh
0x18007b15e  jmp     loc_18007B22D
0x18007b163  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18007b168  lea     rax, [rsp+58h+TokenInformationLength]
0x18007b16d  mov     r8, rdi; TokenInformation
0x18007b170  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007b175  mov     edx, esi; TokenInformationClass
0x18007b177  mov     rcx, rbx; TokenHandle
0x18007b17a  call    cs:__imp_GetTokenInformation
0x18007b181  nop     dword ptr [rax+rax+00h]
0x18007b186  test    eax, eax
0x18007b188  jnz     short loc_18007B1F7
0x18007b18a  call    cs:__imp_GetLastError
0x18007b191  nop     dword ptr [rax+rax+00h]
0x18007b196  mov     r8d, eax
0x18007b199  test    eax, eax
0x18007b19b  jg      short loc_18007B1A1
0x18007b19d  mov     ebx, eax
0x18007b19f  jmp     short loc_18007B1AB
0x18007b1a1  movzx   ebx, r8w
0x18007b1a5  or      ebx, 80070000h
0x18007b1ab  mov     eax, cs:dword_1801574B8
0x18007b1b1  test    eax, eax
0x18007b1b3  jnz     short loc_18007B1C8
0x18007b1b5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18007b1bb  jz      short loc_18007B21E
0x18007b1bd  xor     ecx, ecx
0x18007b1bf  call    IsWppLevelEnabled
0x18007b1c4  test    al, al
0x18007b1c6  jz      short loc_18007B21E
0x18007b1c8  mov     [rsp+58h+var_30], r8d
0x18007b1cd  lea     rax, aWinerror; "%!WINERROR!"
0x18007b1d4  mov     r8d, 638h
0x18007b1da  mov     [rsp+58h+ReturnLength], rax
0x18007b1df  xor     r9d, r9d
0x18007b1e2  lea     rdx, aCtokenGetlogon; "CToken::GetLogonIDSid"
0x18007b1e9  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18007b1f0  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18007b1f5  jmp     short loc_18007B21E
0x18007b1f7  xor     esi, esi
0x18007b1f9  xor     ecx, ecx
0x18007b1fb  cmp     [rdi], ecx
0x18007b1fd  jbe     short loc_18007B219
0x18007b1ff  mov     edx, 0C0000008h
0x18007b204  mov     ebx, ecx
0x18007b206  add     rbx, rbx
0x18007b209  mov     eax, [rdi+rbx*8+10h]
0x18007b20d  and     eax, edx
0x18007b20f  cmp     eax, edx
0x18007b211  jz      short loc_18007B23A
0x18007b213  inc     ecx
0x18007b215  cmp     ecx, [rdi]
0x18007b217  jb      short loc_18007B204
0x18007b219  xor     ebx, ebx
0x18007b21b  mov     [r14], rsi
0x18007b21e  mov     rcx, rdi; hMem
0x18007b221  call    cs:__imp_LocalFree
0x18007b228  nop     dword ptr [rax+rax+00h]
0x18007b22d  mov     eax, ebx
0x18007b22f  add     rsp, 38h
0x18007b233  pop     r14
0x18007b235  pop     rdi
0x18007b236  pop     rsi
0x18007b237  pop     rbx
0x18007b238  retn
0x18007b23a  mov     rcx, [rdi+rbx*8+8]; pSid
0x18007b23f  call    cs:__imp_GetLengthSid
0x18007b246  nop     dword ptr [rax+rax+00h]
0x18007b24b  mov     edx, eax; uBytes
0x18007b24d  xor     ecx, ecx; uFlags
0x18007b24f  mov     [rsp+58h+TokenInformationLength], edx
0x18007b253  call    cs:__imp_LocalAlloc
0x18007b25a  nop     dword ptr [rax+rax+00h]
0x18007b25f  mov     rsi, rax
0x18007b262  test    rax, rax
0x18007b265  jnz     short loc_18007B26E
0x18007b267  mov     ebx, 8007000Eh
0x18007b26c  jmp     short loc_18007B21E
0x18007b26e  mov     r8, [rdi+rbx*8+8]; pSourceSid
0x18007b273  mov     rdx, rsi; pDestinationSid
0x18007b276  mov     ecx, [rsp+58h+TokenInformationLength]; nDestinationSidLength
0x18007b27a  call    cs:__imp_CopySid
0x18007b281  nop     dword ptr [rax+rax+00h]
0x18007b286  test    eax, eax
0x18007b288  jnz     short loc_18007B219
0x18007b28a  call    cs:__imp_GetLastError
0x18007b291  nop     dword ptr [rax+rax+00h]
0x18007b296  mov     r8d, eax
0x18007b299  test    eax, eax
0x18007b29b  jg      short loc_18007B2A1
0x18007b29d  mov     ebx, eax
0x18007b29f  jmp     short loc_18007B2AB
0x18007b2a1  movzx   ebx, r8w
0x18007b2a5  or      ebx, 80070000h
0x18007b2ab  mov     eax, cs:dword_1801574B8
0x18007b2b1  test    eax, eax
0x18007b2b3  jnz     short loc_18007B2C8
0x18007b2b5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18007b2bb  jz      short loc_18007B2F5
0x18007b2bd  xor     ecx, ecx
0x18007b2bf  call    IsWppLevelEnabled
0x18007b2c4  test    al, al
0x18007b2c6  jz      short loc_18007B2F5
0x18007b2c8  mov     [rsp+58h+var_30], r8d
0x18007b2cd  lea     rax, aWinerror; "%!WINERROR!"
0x18007b2d4  mov     r8d, 64Eh
0x18007b2da  mov     [rsp+58h+ReturnLength], rax
0x18007b2df  xor     r9d, r9d
0x18007b2e2  lea     rdx, aCtokenGetlogon; "CToken::GetLogonIDSid"
0x18007b2e9  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18007b2f0  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18007b2f5  mov     rcx, rsi; hMem
0x18007b2f8  call    cs:__imp_LocalFree
0x18007b2ff  nop     dword ptr [rax+rax+00h]
0x18007b304  jmp     loc_18007B21E
```
